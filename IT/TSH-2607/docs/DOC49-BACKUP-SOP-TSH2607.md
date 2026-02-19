# DOC49-BACKUP-SOP-TSH2607.md
# Backup and Restore Standard Operating Procedure
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC49-BACKUP-SOP-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 PURPOSE

This Standard Operating Procedure (SOP) defines the backup and restore processes for the UCMS system to ensure data protection and business continuity.

## 2.0 SCOPE

This SOP applies to:
- Database backups
- Application configuration backups
- Document storage backups
- System configuration backups
- Log file backups

## 3.0 BACKUP SCHEDULE

| Data Type | Frequency | Retention | Storage Location |
|-----------|-----------|-----------|------------------|
| Database Full | Daily 02:00 | 30 days | Local + S3 |
| Database Incremental | Every 4 hours | 7 days | Local |
| Database WAL | Continuous | 7 days | Local + S3 |
| Application Config | On change | 90 days | Git + S3 |
| Documents | Continuous (sync) | 1 year | S3 |
| System Config | Weekly | 90 days | S3 |
| Logs | Daily | 90 days | S3 |

## 4.0 BACKUP PROCEDURES

### 4.1 Database Full Backup

```bash
#!/bin/bash
# /opt/ucms/scripts/backup-full.sh

DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_DIR="/backup/postgres/full"
DB_NAME="ucms_prod"
RETENTION_DAYS=30

echo "[$(date)] Starting full backup..."

# Create backup directory
mkdir -p $BACKUP_DIR

# Perform backup
pg_dump -h localhost -U backup_user -Fc $DB_NAME \
  > "$BACKUP_DIR/ucms_full_${DATE}.dump" 2>/var/log/ucms/backup.log

# Compress
if [ -f "$BACKUP_DIR/ucms_full_${DATE}.dump" ]; then
    gzip "$BACKUP_DIR/ucms_full_${DATE}.dump"
    echo "[$(date)] Backup compressed successfully"
else
    echo "[$(date)] ERROR: Backup file not created"
    exit 1
fi

# Calculate checksum
md5sum "$BACKUP_DIR/ucms_full_${DATE}.dump.gz" \
  > "$BACKUP_DIR/ucms_full_${DATE}.md5"

# Sync to S3
aws s3 cp "$BACKUP_DIR/ucms_full_${DATE}.dump.gz" \
  s3://ucms-backups/postgres/full/
aws s3 cp "$BACKUP_DIR/ucms_full_${DATE}.md5" \
  s3://ucms-backups/postgres/full/

# Cleanup old backups
find $BACKUP_DIR -name "ucms_full_*.dump.gz" -mtime +$RETENTION_DAYS -delete
find $BACKUP_DIR -name "ucms_full_*.md5" -mtime +$RETENTION_DAYS -delete

# Cleanup old S3 backups
aws s3 ls s3://ucms-backups/postgres/full/ | \
  awk '{print $4}' | \
  while read file; do
    aws s3 rm s3://ucms-backups/postgres/full/$file
  done

echo "[$(date)] Full backup complete"
```

### 4.2 Verify Backup Integrity

```bash
#!/bin/bash
# Verify backup script

BACKUP_FILE=$1

# Verify file exists
if [ ! -f "$BACKUP_FILE" ]; then
    echo "ERROR: Backup file not found"
    exit 1
fi

# Verify checksum
cd $(dirname $BACKUP_FILE)
md5sum -c $(basename $BACKUP_FILE).md5

if [ $? -ne 0 ]; then
    echo "ERROR: Checksum verification failed"
    exit 1
fi

# Test restore to temp database
gunzip -c $BACKUP_FILE | pg_restore --list > /dev/null

if [ $? -eq 0 ]; then
    echo "Backup verification successful"
else
    echo "ERROR: Backup verification failed"
    exit 1
fi
```

## 5.0 RESTORE PROCEDURES

### 5.1 Point-in-Time Recovery

```bash
#!/bin/bash
# Point-in-time recovery script

TARGET_TIME=$1  # Format: "2025-01-15 14:30:00"
BACKUP_FILE=$2

echo "Starting PITR to: $TARGET_TIME"

# Stop application
pm2 stop ucms-app

# Stop PostgreSQL
sudo systemctl stop postgresql

# Backup current data (if recoverable)
sudo mv /var/lib/postgresql/15/main /var/lib/postgresql/15/main.bak.$(date +%s)

# Create new data directory
sudo mkdir /var/lib/postgresql/15/main
sudo chown postgres:postgres /var/lib/postgresql/15/main

# Initialize from base backup
sudo -u postgres pg_basebackup -D /var/lib/postgresql/15/main

# Configure recovery
sudo -u postgres cat > /var/lib/postgresql/15/main/recovery.conf <<EOF
restore_command = 'cp /archive/wal/%f %p'
recovery_target_time = '$TARGET_TIME'
recovery_target_action = 'promote'
EOF

# Start PostgreSQL
sudo systemctl start postgresql

# Monitor recovery
sudo -u postgres psql -c "SELECT pg_is_in_recovery();"

# Verify and start application
sleep 30
curl http://localhost:3000/health && pm2 start ucms-app

echo "PITR complete"
```

### 5.2 Document Recovery

```bash
#!/bin/bash
# Restore documents from S3

# Sync from S3 to local
aws s3 sync s3://ucms-documents-production /data/documents

# Verify file count
S3_COUNT=$(aws s3 ls s3://ucms-documents-production --recursive | wc -l)
LOCAL_COUNT=$(find /data/documents -type f | wc -l)

if [ $S3_COUNT -eq $LOCAL_COUNT ]; then
    echo "Document recovery successful"
else
    echo "WARNING: File count mismatch"
fi
```

## 6.0 BACKUP MONITORING

### 6.1 Daily Backup Checklist

| Check | Command/Method | Expected Result |
|-------|----------------|-----------------|
| Backup file exists | ls /backup/postgres/full/ | File present |
| File size reasonable | du -h backup_file | > 100MB |
| Checksum verified | md5sum -c | OK |
| S3 sync complete | aws s3 ls | File visible |
| No errors in log | grep ERROR /var/log/ucms/backup.log | No matches |

### 6.2 Backup Failure Escalation

| Time | Action | Contact |
|------|--------|---------|
| 03:00 | Backup should complete | - |
| 03:30 | If no backup alert | On-call engineer |
| 04:00 | Escalate if unresolved | Technical Lead |
| 05:00 | Escalate to management | Project Manager |

## 7.0 TESTING

### 7.1 Monthly Restore Test

1. Schedule maintenance window
2. Restore backup to test environment
3. Verify data integrity
4. Run application smoke tests
5. Document results
6. Cleanup test environment

### 7.2 Annual DR Test

Full disaster recovery simulation as per DRP.

## 8.0 RESPONSIBILITIES

| Role | Responsibilities |
|------|------------------|
| DBA | Database backup/restore, monitoring |
| System Admin | System config backup, infrastructure |
| Security Officer | Backup encryption, access control |
| On-call Engineer | First response to failures |

---

**Approved By:**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| DBA Lead | | | |
| System Admin Lead | | | |

---

*Document Control: Review quarterly. Update when procedures change.*
