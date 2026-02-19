# DOC48-DRP-TSH2607.md

# DOC 48: DISASTER RECOVERY PLAN (DRP)
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Document ID:** DOC48  
**Version:** 1.0  
**Date:** February 2026  

---

## DISASTER RECOVERY OVERVIEW

### Recovery Objectives

| Metric | Target | Measurement |
|--------|--------|-------------|
| RPO (Recovery Point Objective) | 1 hour | Maximum data loss acceptable |
| RTO (Recovery Time Objective) | 4 hours | Time to restore service |
| WRT (Work Recovery Time) | 2 hours | Time to resume normal operations |

### DR Architecture

- **Primary Site:** Oracle Cloud Infrastructure (Primary Region)
- **DR Site:** Oracle Cloud Infrastructure (Secondary Region)
- **Replication:** Asynchronous data replication
- **Failover:** Automated with manual approval

### DR Testing Schedule

| Test Type | Frequency | Scope |
|-----------|-----------|-------|
| Tabletop Exercise | Quarterly | Process walkthrough |
| Failover Test | Bi-annually | Full system failover |
| Data Recovery Test | Annually | Backup restoration |

---

**END OF DOCUMENT 48**
