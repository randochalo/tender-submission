# ANNEX T37: BACKUP & RECOVERY PLAN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the Backup and Recovery Plan for the USP Claims Management System, ensuring business continuity through comprehensive data protection, rapid recovery capabilities, and disaster resilience.

### 1.1 Compliance Requirements
- **KRISA Section 19**: Business continuity and disaster recovery
- **ISO 22301**: Business continuity management
- **ISO 27031**: ICT readiness for business continuity
- **Treasury Guidelines**: Financial system backup requirements

---

## 2. BACKUP STRATEGY

### 2.1 Backup Types and Schedule

| Backup Type | Frequency | Retention | Storage |
|-------------|-----------|-----------|---------|
| Database Full | Daily | 30 days | On-site + Off-site |
| Database Incremental | Every 4 hours | 7 days | On-site |
| Archive Log | Continuous | 30 days | On-site + Off-site |
| Application Code | Weekly | 52 weeks | On-site + Off-site |
| Configuration | Daily | 90 days | On-site + Off-site |
| Document Store | Daily | 30 days | On-site + Off-site |
| System Image | Monthly | 12 months | Off-site |

### 2.2 Backup Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    BACKUP ARCHITECTURE                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PRODUCTION ENVIRONMENT                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                     │   │
│  │  ┌─────────────┐    ┌─────────────┐    ┌─────────────────────────┐ │   │
│  │  │ Application │    │   Oracle    │    │    Document Store       │ │   │
│  │  │   Servers   │    │  Database   │    │    (File System)        │ │   │
│  │  └──────┬──────┘    └──────┬──────┘    └───────────┬─────────────┘ │   │
│  │         │                  │                        │               │   │
│  │         └──────────────────┼────────────────────────┘               │   │
│  │                            │                                        │   │
│  │                            ▼                                        │   │
│  │                   ┌─────────────────┐                               │   │
│  │                   │  RMAN / Backup  │                               │   │
│  │                   │     Software    │                               │   │
│  │                   └────────┬────────┘                               │   │
│  │                            │                                        │   │
│  └────────────────────────────┼────────────────────────────────────────┘   │
│                               │                                             │
│              ┌────────────────┼────────────────┐                           │
│              │                │                │                           │
│              ▼                ▼                ▼                           │
│       ┌──────────┐    ┌──────────┐    ┌──────────┐                        │
│       │  Local   │    │  Off-site│    │   Cloud  │                        │
│       │  Disk    │    │  (DR Site)│   │  (AWS/  │                        │
│       │  (NAS)   │    │          │    │  Azure)  │                        │
│       └──────────┘    └──────────┘    └──────────┘                        │
│                                                                             │
│  BACKUP RETENTION TIERS:                                                    │
│  • Hot: 7 days on local NAS (instant recovery)                              │
│  • Warm: 30 days at DR site (4-hour recovery)                               │
│  • Cold: 7 years in cloud archive (24-hour recovery)                        │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. DATABASE BACKUP PROCEDURES

### 3.1 Oracle RMAN Configuration

```sql
-- RMAN Configuration for UCMS Database
CONFIGURE RETENTION POLICY TO RECOVERY WINDOW OF 30 DAYS;
CONFIGURE BACKUP OPTIMIZATION ON;
CONFIGURE CONTROLFILE AUTOBACKUP ON;
CONFIGURE CONTROLFILE AUTOBACKUP FORMAT FOR DEVICE TYPE DISK TO '/backup/%F';
CONFIGURE DEVICE TYPE DISK PARALLELISM 4 BACKUP TYPE TO COMPRESSED BACKUPSET;
CONFIGURE CHANNEL DEVICE TYPE DISK FORMAT '/backup/%U';
CONFIGURE ARCHIVELOG DELETION POLICY TO BACKED UP 2 TIMES TO DISK;

-- Backup Schedule (implemented via cron/scheduler)
-- Full Backup: Daily at 02:00
BACKUP DATABASE PLUS ARCHIVELOG DELETE INPUT;

-- Incremental Backup: Every 4 hours
BACKUP INCREMENTAL LEVEL 0 DATABASE;

-- Archive Log Backup: Every 15 minutes
BACKUP ARCHIVELOG ALL DELETE INPUT;
```

### 3.2 Backup Verification

| Verification Type | Frequency | Method |
|-------------------|-----------|--------|
| Backup Completion | Every backup | Log review |
| Backup Integrity | Daily | RMAN VALIDATE |
| Restore Test | Weekly | Tablespace restore |
| Full DR Test | Quarterly | Complete restoration |

---

## 4. RECOVERY PROCEDURES

### 4.1 Recovery Time Objectives (RTO)

| Scenario | RTO | RPO | Procedure |
|----------|-----|-----|-----------|
| Single datafile corruption | 1 hour | 0 | Online restore |
| Full database restore | 4 hours | 15 min | Full restore + recovery |
| Complete site failure | 8 hours | 1 hour | DR activation |
| Logical corruption | 4 hours | Variable | Point-in-time recovery |

### 4.2 Recovery Procedures Matrix

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    RECOVERY PROCEDURES                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  SCENARIO 1: USER ERROR (Dropped Table)                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  1. Identify drop time from audit log                               │   │
│  │  2. Restore table from flashback (if within 8 hours)               │   │
│  │  3. OR restore from backup to auxiliary instance                   │   │
│  │  4. Export table from auxiliary, import to production              │   │
│  │  5. Verify data integrity                                           │   │
│  │  TIME: 1-2 hours | DATA LOSS: 0 (if flashback) or to last backup   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  SCENARIO 2: DATABASE CORRUPTION                                           │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  1. Assess corruption extent (V$DATABASE_BLOCK_CORRUPTION)          │   │
│  │  2. If limited: Restore affected datafiles from backup             │   │
│  │  3. Apply archive logs to recover to current time                  │   │
│  │  4. If widespread: Full database restore required                  │   │
│  │  TIME: 2-4 hours | DATA LOSS: 0 (with archive logs)                │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  SCENARIO 3: COMPLETE SITE FAILURE                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  1. Activate DR site (Data Guard failover)                         │   │
│  │  2. Redirect application to DR site                                │   │
│  │  3. Notify stakeholders of DR activation                           │   │
│  │  4. Investigate primary site failure                               │   │
│  │  5. Plan failback when primary restored                            │   │
│  │  TIME: 1 hour | DATA LOSS: < 1 hour (async replication)            │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.3 Point-in-Time Recovery (PITR)

```sql
-- PITR Procedure Example
-- Step 1: Mount database
STARTUP MOUNT;

-- Step 2: Restore to specific time
RUN {
  SET UNTIL TIME "TO_DATE('2025-06-15 10:00:00','YYYY-MM-DD HH24:MI:SS')";
  RESTORE DATABASE;
  RECOVER DATABASE;
}

-- Step 3: Open with resetlogs
ALTER DATABASE OPEN RESETLOGS;

-- Step 4: Verify recovery
SELECT * FROM claim_transactions 
WHERE transaction_date > DATE '2025-06-15';
```

---

## 5. DISASTER RECOVERY

### 5.1 DR Architecture

| Component | Primary | DR Site | Replication |
|-----------|---------|---------|-------------|
| Database | KL Data Center | Cyberjaya | Oracle Data Guard |
| Application | KL Data Center | Cyberjaya | Manual/Scripted |
| Documents | KL NAS | Cyberjaya NAS | Async replication |
| Backups | KL + Cloud | Cyberjaya + Cloud | Geo-redundant |

### 5.2 DR Activation Procedure

| Step | Action | Owner | Time |
|------|--------|-------|------|
| 1 | Declare disaster | Incident Commander | 0 min |
| 2 | Notify DR team | Operations Manager | 5 min |
| 3 | Assess primary site | Infrastructure | 15 min |
| 4 | Activate DR database | DBA | 20 min |
| 5 | Activate DR application | Infrastructure | 30 min |
| 6 | Update DNS/routing | Network | 40 min |
| 7 | Verify DR functionality | QA | 50 min |
| 8 | Notify users | Change Manager | 60 min |

### 5.3 Failback Procedure

```
┌─────────────────────────────────────────────────────────────────┐
│                    FAILBACK PROCEDURE                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  When primary site is restored:                                │
│                                                                 │
│  1. REINSTATE PRIMARY AS STANDBY                               │
│     - Flashback database to before failover (if possible)      │
│     - OR restore from backup                                   │
│     - Configure as physical standby                            │
│                                                                 │
│  2. SYNCHRONIZE DATA                                           │
│     - Allow replication to catch up                            │
│     - Verify data consistency                                  │
│                                                                 │
│  3. PLANNED SWITCHOVER                                         │
│     - Schedule maintenance window                              │
│     - Perform graceful switchover                              │
│     - Verify primary operations                                │
│                                                                 │
│  4. POST-SWITCHOVER                                            │
│     - Monitor primary performance                              │
│     - DR site returns to standby mode                          │
│     - Document lessons learned                                 │
│                                                                 │
│  ESTIMATED TIME: 4-8 hours (depending on data drift)           │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 6. BACKUP MONITORING

### 6.1 Monitoring Dashboard

| Metric | Threshold | Alert |
|--------|-----------|-------|
| Backup completion | < 100% | Critical |
| Backup duration | > 4 hours | Warning |
| Backup size variance | > 20% | Warning |
| Failed backups | > 0 | Critical |
| Storage capacity | > 80% | Warning |
| Last successful backup | > 25 hours | Critical |

### 6.2 Daily Backup Report

```
┌─────────────────────────────────────────────────────────────────┐
│              BACKUP STATUS REPORT - [Date]                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  BACKUP JOBS                                                    │
│  ┌────────────────┬──────────┬──────────┬──────────┬────────┐  │
│  │ Job Name       │ Start    │ Duration │ Status   │ Size   │  │
│  ├────────────────┼──────────┼──────────┼──────────┼────────┤  │
│  │ DB_FULL_0200   │ 02:00:15 │ 1h 23m   │ ✅ SUCCESS│ 45 GB │  │
│  │ DB_INC_0600    │ 06:00:02 │ 15m      │ ✅ SUCCESS│ 2.1 GB│  │
│  │ DB_INC_1000    │ 10:00:05 │ 18m      │ ✅ SUCCESS│ 2.3 GB│  │
│  │ DB_INC_1400    │ 14:00:01 │ 14m      │ ✅ SUCCESS│ 1.9 GB│  │
│  │ DB_INC_1800    │ 18:00:03 │ 16m      │ ✅ SUCCESS│ 2.0 GB│  │
│  │ DB_INC_2200    │ 22:00:04 │ 15m      │ ✅ SUCCESS│ 2.2 GB│  │
│  │ ARCH_LOG       │ Continuous│ -       │ ✅ SUCCESS│ 850 MB│  │
│  │ APP_CODE       │ 02:00:00 │ 5m       │ ✅ SUCCESS│ 500 MB│  │
│  │ DOCUMENTS      │ 03:00:00 │ 45m      │ ✅ SUCCESS│ 120 GB│  │
│  └────────────────┴──────────┴──────────┴──────────┴────────┘  │
│                                                                 │
│  STORAGE STATUS                                                 │
│  Local NAS: 45% used (4.5 TB / 10 TB)                          │
│  DR Site: 42% used (4.2 TB / 10 TB)                            │
│  Cloud Archive: 38% used (38 TB / 100 TB)                      │
│                                                                 │
│  VERIFICATION STATUS                                            │
│  RMAN Validate: ✅ PASSED                                       │
│  Checksum Verify: ✅ PASSED                                     │
│  Test Restore (Weekly): ⏳ SCHEDULED                            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 7. ROLES AND RESPONSIBILITIES

| Role | Responsibility | Contact |
|------|----------------|---------|
| Backup Administrator | Daily backup operations | DBA Team |
| Recovery Lead | Recovery execution | Senior DBA |
| DR Coordinator | DR activation/failback | Operations Manager |
| Incident Commander | Disaster declaration | IT Director |
| Communication Lead | Stakeholder communication | Change Manager |

---

## 8. TESTING SCHEDULE

| Test Type | Frequency | Scope | Documentation |
|-----------|-----------|-------|---------------|
| Backup Restore | Weekly | Single tablespace | Test log |
| Full DR Drill | Quarterly | Complete failover | DR report |
| Tablespace Recovery | Monthly | Random selection | Test log |
| PITR Test | Bi-annual | Specific scenarios | Test report |
| Documentation Review | Annual | Procedure accuracy | Review record |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T31-SECURITY-FRAMEWORK | Data Security |
| CR-002 | ANNEX-T35-DEPLOYMENT-PLAN | DR Environment |
| CR-003 | ANNEX-T40-SUPPORT-PLAN | Support Escalation |
| CR-004 | ANNEX-T41-PROJECT-TIMELINE | DR Implementation |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
