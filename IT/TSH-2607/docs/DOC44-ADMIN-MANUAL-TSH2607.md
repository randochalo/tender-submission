# DOC44-ADMIN-MANUAL-TSH2607.md
# System Administrator Manual
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC44-ADMIN-MANUAL-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |
| Target Audience | System Administrators, Technical Support |

---

## TABLE OF CONTENTS

1. [System Architecture Overview](#1-system-architecture-overview)
2. [Installation and Setup](#2-installation-and-setup)
3. [System Configuration](#3-system-configuration)
4. [User Management](#4-user-management)
5. [Security Administration](#5-security-administration)
6. [Database Administration](#6-database-administration)
7. [Backup and Recovery](#7-backup-and-recovery)
8. [Monitoring and Maintenance](#8-monitoring-and-maintenance)
9. [Troubleshooting](#9-troubleshooting)
10. [Disaster Recovery Procedures](#10-disaster-recovery-procedures)

---

## 1. SYSTEM ARCHITECTURE OVERVIEW

### 1.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        UCMS ARCHITECTURE                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐      ┌─────────────┐      ┌─────────────┐     │
│  │   Web Tier  │◄────►│   App Tier  │◄────►│   Data Tier │     │
│  │  (Nginx)    │      │  (Node.js)  │      │(PostgreSQL) │     │
│  └─────────────┘      └─────────────┘      └─────────────┘     │
│        ▲                    ▲                    ▲              │
│        │                    │                    │              │
│  ┌─────┴─────┐        ┌────┴────┐          ┌────┴────┐         │
│  │   CDN     │        │  Cache  │          │  Search │         │
│  │(Static)   │        │ (Redis) │          │(Elastic)│         │
│  └───────────┘        └─────────┘          └─────────┘         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 1.2 Component Specifications

| Component | Technology | Version | Purpose |
|-----------|------------|---------|---------|
| Web Server | Nginx | 1.24+ | Reverse proxy, static content |
| Application | Node.js | 20 LTS | Business logic |
| Database | PostgreSQL | 15.x | Data storage |
| Cache | Redis | 7.x | Session, data caching |
| Search | Elasticsearch | 8.x | Full-text search |
| Message Queue | RabbitMQ | 3.12+ | Async processing |
| Object Storage | MinIO | Latest | Document storage |

### 1.3 Server Inventory

| Hostname | IP Address | Role | Environment |
|----------|------------|------|-------------|
| ucms-web-01 | 10.1.10.10 | Web Server | Production |
| ucms-app-01 | 10.1.20.11 | Application | Production |
| ucms-db-01 | 10.1.30.21 | Database Primary | Production |
| ucms-db-02 | 10.1.30.22 | Database Replica | Production |
| ucms-cache-01 | 10.1.30.31 | Redis | Production |

---

## 2. INSTALLATION AND SETUP

### 2.1 Prerequisites

```bash
# System Requirements
- Ubuntu Server 22.04 LTS
- 8+ CPU cores
- 32+ GB RAM
- 500+ GB SSD storage
- Network access to required ports
```

### 2.2 Installation Steps

#### 2.2.1 Operating System Setup

```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install essential packages
sudo apt install -y curl wget git vim htop net-tools

# Configure timezone
sudo timedatectl set-timezone Asia/Kuala_Lumpur

# Configure hostname
sudo hostnamectl set-hostname ucms-[role]-[number]
```

#### 2.2.2 Database Installation (PostgreSQL)

```bash
# Install PostgreSQL
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt update
sudo apt install -y postgresql-15 postgresql-contrib

# Configure PostgreSQL
sudo systemctl enable postgresql
sudo systemctl start postgresql

# Create database and user
sudo -u postgres psql -c "CREATE DATABASE ucms_prod;"
sudo -u postgres psql -c "CREATE USER ucms_admin WITH ENCRYPTED PASSWORD '[STRONG_PASSWORD]';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE ucms_prod TO ucms_admin;"
```

#### 2.2.3 Application Installation

```bash
# Install Node.js
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs

# Install PM2
sudo npm install -g pm2

# Create application directory
sudo mkdir -p /opt/ucms
sudo chown -R $USER:$USER /opt/ucms

# Clone application code
cd /opt/ucms
git clone [REPOSITORY_URL] .

# Install dependencies
npm install --production

# Configure environment
cp .env.example .env
# Edit .env with production values
vim .env

# Start application
pm2 start app.js --name ucms-app
pm2 save
pm2 startup
```

### 2.3 Initial Configuration

#### 2.3.1 SSL Certificate Setup

```bash
# Install Certbot
sudo apt install -y certbot python3-certbot-nginx

# Obtain certificate
sudo certbot --nginx -d ucms.mcmc.gov.my

# Auto-renewal test
sudo certbot renew --dry-run
```

#### 2.3.2 Firewall Configuration

```bash
# Configure UFW
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable
```

---

## 3. SYSTEM CONFIGURATION

### 3.1 Application Configuration

Edit `/opt/ucms/.env`:

```bash
# Application
NODE_ENV=production
PORT=3000
APP_NAME=UCMS
APP_URL=https://ucms.mcmc.gov.my

# Database
DB_HOST=10.1.30.21
DB_PORT=5432
DB_NAME=ucms_prod
DB_USER=ucms_app
DB_PASSWORD=[ENCRYPTED_PASSWORD]
DB_SSL=true

# Redis
REDIS_HOST=10.1.30.31
REDIS_PORT=6379
REDIS_PASSWORD=[PASSWORD]

# Security
JWT_SECRET=[LONG_RANDOM_STRING]
SESSION_SECRET=[LONG_RANDOM_STRING]
ENCRYPTION_KEY=[32_BYTE_KEY]

# Email
SMTP_HOST=smtp.mcmc.gov.my
SMTP_PORT=587
SMTP_USER=[USERNAME]
SMTP_PASS=[PASSWORD]

# Integrations
MYIDENTITY_ENDPOINT=https://api.myidentity.gov.my
MYIDENTITY_CLIENT_ID=[CLIENT_ID]
MYIDENTITY_CLIENT_SECRET=[SECRET]
```

### 3.2 Nginx Configuration

```nginx
# /etc/nginx/sites-available/ucms
server {
    listen 80;
    server_name ucms.mcmc.gov.my;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    server_name ucms.mcmc.gov.my;

    ssl_certificate /etc/letsencrypt/live/ucms.mcmc.gov.my/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/ucms.mcmc.gov.my/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers HIGH:!aNULL:!MD5;

    access_log /var/log/nginx/ucms-access.log;
    error_log /var/log/nginx/ucms-error.log;

    client_max_body_size 50M;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_cache_bypass $http_upgrade;
    }

    location /static {
        alias /opt/ucms/public;
        expires 30d;
        add_header Cache-Control "public, immutable";
    }
}
```

### 3.3 Log Rotation

```bash
# /etc/logrotate.d/ucms
/var/log/ucms/*.log {
    daily
    rotate 30
    compress
    delaycompress
    missingok
    notifempty
    create 0644 ucms ucms
    postrotate
        pm2 reloadLogs
    endscript
}
```

---

## 4. USER MANAGEMENT

### 4.1 Creating Administrator Accounts

```sql
-- Create system administrator
INSERT INTO t_users (
    user_id, user_type, full_name, email, 
    role_code, password_hash, mfa_enabled, 
    status, created_date
) VALUES (
    'sysadmin01',
    'INTERNAL',
    'System Administrator',
    'admin@ucms.mcmc.gov.my',
    'SYS_ADMIN',
    '[BCRYPT_HASH]',
    true,
    'Active',
    NOW()
);
```

### 4.2 Bulk User Import

```bash
# CSV format: user_id,full_name,email,role,department
# Import command
node scripts/import-users.js --file=/path/to/users.csv
```

### 4.3 Password Reset (Admin)

```bash
# Generate temporary password
node scripts/reset-password.js --user=[USER_ID] --temp

# Output will include temporary password and reset link
```

---

## 5. SECURITY ADMINISTRATION

### 5.1 SSL/TLS Certificate Renewal

```bash
# Manual renewal
sudo certbot renew

# Reload nginx
sudo systemctl reload nginx

# Check certificate expiry
openssl x509 -in /etc/letsencrypt/live/ucms.mcmc.gov.my/cert.pem -noout -dates
```

### 5.2 Security Patching

```bash
# Update system packages
sudo apt update
sudo apt upgrade -y

# Update Node.js application dependencies
cd /opt/ucms
npm audit
npm audit fix

# Restart application
pm2 restart ucms-app
```

### 5.3 Access Log Review

```bash
# Failed login attempts
grep "POST /api/auth/login" /var/log/nginx/ucms-access.log | grep " 401 "

# Suspicious activity
grep -E "(union|select|drop|insert|delete)" /var/log/nginx/ucms-access.log

# Generate security report
node scripts/security-report.js --start-date=2025-01-01 --end-date=2025-01-31
```

---

## 6. DATABASE ADMINISTRATION

### 6.1 Database Backup

```bash
#!/bin/bash
# /opt/ucms/scripts/backup-db.sh

BACKUP_DIR="/backup/postgres"
DATE=$(date +%Y%m%d_%H%M%S)
DB_NAME="ucms_prod"
RETENTION_DAYS=30

# Create backup
pg_dump -h localhost -U ucms_admin -Fc $DB_NAME > "$BACKUP_DIR/ucms_${DATE}.dump"

# Compress
gzip "$BACKUP_DIR/ucms_${DATE}.dump"

# Delete old backups
find $BACKUP_DIR -name "ucms_*.dump.gz" -mtime +$RETENTION_DAYS -delete

# Sync to remote storage
aws s3 sync $BACKUP_DIR s3://ucms-backups/postgres/
```

### 6.2 Database Performance Tuning

```sql
-- Check slow queries
SELECT query, calls, mean_time, total_time
FROM pg_stat_statements
ORDER BY mean_time DESC
LIMIT 10;

-- Analyze table statistics
ANALYZE t_claims;
ANALYZE t_applicants;

-- Reindex if needed
REINDEX INDEX CONCURRENTLY idx_claims_status;
```

### 6.3 Replication Status Check

```bash
# On primary
sudo -u postgres psql -c "SELECT * FROM pg_stat_replication;"

# On replica
sudo -u postgres psql -c "SELECT * FROM pg_stat_wal_receiver;"
```

---

## 7. BACKUP AND RECOVERY

### 7.1 Backup Schedule

| Backup Type | Frequency | Retention | Location |
|-------------|-----------|-----------|----------|
| Database Full | Daily 02:00 | 30 days | Local + S3 |
| Database Incremental | Hourly | 7 days | Local |
| Application Files | Daily 03:00 | 14 days | S3 |
| Configuration | On change | 90 days | Git |
| Document Storage | Continuous | 1 year | S3 |

### 7.2 Database Recovery

```bash
#!/bin/bash
# /opt/ucms/scripts/restore-db.sh

BACKUP_FILE=$1
DB_NAME="ucms_prod"

# Stop application
pm2 stop ucms-app

# Drop and recreate database
sudo -u postgres psql -c "DROP DATABASE IF EXISTS $DB_NAME;"
sudo -u postgres psql -c "CREATE DATABASE $DB_NAME;"

# Restore from backup
gunzip -c $BACKUP_FILE | pg_restore -h localhost -U postgres -d $DB_NAME

# Start application
pm2 start ucms-app
```

### 7.3 Document Storage Recovery

```bash
# Sync from S3 to local
aws s3 sync s3://ucms-documents-production /data/documents
```

---

## 8. MONITORING AND MAINTENANCE

### 8.1 Health Check Commands

```bash
# Application health
curl -f http://localhost:3000/health || echo "Application unhealthy"

# Database health
pg_isready -h localhost -p 5432

# Disk space
df -h

# Memory usage
free -h

# Process status
pm2 status
```

### 8.2 Log Monitoring

```bash
# Real-time application log
pm2 logs ucms-app

# Real-time nginx log
sudo tail -f /var/log/nginx/ucms-error.log

# Database log
sudo tail -f /var/log/postgresql/postgresql-15-main.log
```

### 8.3 Scheduled Maintenance

```bash
# Weekly maintenance script (cron: 0 3 * * 0)
#!/bin/bash
# /opt/ucms/scripts/weekly-maintenance.sh

echo "Starting weekly maintenance..."

# Update statistics
sudo -u postgres psql -d ucms_prod -c "VACUUM ANALYZE;"

# Clear old sessions
sudo -u postgres psql -d ucms_prod -c "DELETE FROM t_sessions WHERE expiry < NOW();"

# Clear temp files
find /tmp -name "ucms_*" -mtime +1 -delete

# Rotate logs
sudo logrotate -f /etc/logrotate.d/ucms

echo "Weekly maintenance complete."
```

---

## 9. TROUBLESHOOTING

### 9.1 Common Issues

#### Application Won't Start

```bash
# Check logs
pm2 logs ucms-app --lines 100

# Check environment variables
cat /opt/ucms/.env

# Verify database connection
psql -h localhost -U ucms_app -d ucms_prod -c "SELECT 1;"

# Check port availability
sudo netstat -tlnp | grep 3000
```

#### Database Connection Issues

```bash
# Check PostgreSQL status
sudo systemctl status postgresql

# Check connection limits
sudo -u postgres psql -c "SHOW max_connections;"
sudo -u postgres psql -c "SELECT count(*) FROM pg_stat_activity;"

# Restart PostgreSQL (if necessary)
sudo systemctl restart postgresql
```

#### High Memory Usage

```bash
# Check memory usage
ps aux --sort=-%mem | head -20

# Check for memory leaks in Node.js
pm2 reload ucms-app

# Clear cache
redis-cli FLUSHDB
```

### 9.2 Emergency Procedures

#### System Unresponsive

1. Check server accessibility: `ping [SERVER_IP]`
2. SSH to server and check resources: `htop`
3. Restart application: `pm2 restart ucms-app`
4. If still unresponsive, restart server: `sudo reboot`

#### Database Corruption

1. Stop application: `pm2 stop ucms-app`
2. Switch to standby: Update DNS/Load Balancer to point to replica
3. Assess corruption on primary
4. Restore from backup if needed

---

## 10. DISASTER RECOVERY PROCEDURES

### 10.1 DR Activation

```bash
# 1. Declare disaster and notify stakeholders
# 2. Activate DR site

# 3. Promote replica to primary
sudo -u postgres psql -c "SELECT pg_promote();"

# 4. Update application configuration
# Edit .env to point to DR database

# 5. Start application on DR site
pm2 start app.js --name ucms-app-dr

# 6. Update DNS to point to DR site
# 7. Verify functionality
```

### 10.2 Failback Procedure

```bash
# 1. Repair primary site
# 2. Sync data from DR to primary
pg_dump -h dr-db-host -Fc ucms_prod | pg_restore -h primary-db -d ucms_prod

# 3. Re-establish replication
# 4. Switch back to primary
# 5. Update DNS
# 6. Verify and monitor
```

---

**Document Control:** This manual is maintained by the UCMS Technical Team. Updates are distributed to all system administrators.

**Emergency Contacts:**
- Primary On-Call: [Number]
- Secondary On-Call: [Number]
- Escalation: [Number]

---

*Version History*

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Jan 2025 | Technical Team | Initial release |
