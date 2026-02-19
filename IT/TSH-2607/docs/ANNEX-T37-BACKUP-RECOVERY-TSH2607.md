# ANNEX-T37-BACKUP-RECOVERY-TSH2607.md

# ANNEX T37: BACKUP & RECOVERY PLAN
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T37  
**Version:** 1.0  
**Date:** February 2026  

---

## BACKUP STRATEGY

### Backup Schedule

| Type | Frequency | Retention | Storage |
|------|-----------|-----------|---------|
| Full Backup | Weekly | 4 weeks | Primary + DR |
| Incremental | Daily | 7 days | Primary + DR |
| Archive | Monthly | 7 years | Cold Storage |
| Transaction Log | Continuous | 48 hours | Primary |

### Recovery Objectives

| Metric | Target |
|--------|--------|
| RPO (Recovery Point Objective) | 1 hour |
| RTO (Recovery Time Objective) | 4 hours |
| WRT (Work Recovery Time) | 2 hours |

### Backup Components

1. Database (Oracle)
2. Application Files
3. Configuration Files
4. Document Storage
5. Audit Logs

---

**END OF ANNEX T37**
