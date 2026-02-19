# ANNEX-T26-AUDIT-TRAIL-TSH2607.md

# ANNEX T26: AUDIT TRAIL DESIGN
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T26  
**Version:** 1.0  
**Date:** February 2026  

---

## AUDIT TRAIL ARCHITECTURE

### Audit Events Captured

| Event Type | Description | Data Captured |
|------------|-------------|---------------|
| CREATE | New record created | User, timestamp, data snapshot |
| READ | Data viewed | User, timestamp, record ID |
| UPDATE | Record modified | User, timestamp, old/new values |
| DELETE | Record deleted | User, timestamp, deleted data |
| LOGIN | User login | User, timestamp, IP address |
| LOGOUT | User logout | User, timestamp |
| EXPORT | Data exported | User, timestamp, export scope |
| APPROVE | Approval action | User, timestamp, decision |

### Audit Trail Table Structure

```sql
CREATE TABLE UCMS_AUDIT_TRAIL (
    AUDIT_ID VARCHAR2(50) PRIMARY KEY,
    TABLE_NAME VARCHAR2(100) NOT NULL,
    RECORD_ID VARCHAR2(50) NOT NULL,
    ACTION VARCHAR2(20) NOT NULL,
    OLD_VALUES CLOB,
    NEW_VALUES CLOB,
    USER_ID VARCHAR2(100) NOT NULL,
    USER_NAME VARCHAR2(200),
    TIMESTAMP TIMESTAMP NOT NULL,
    IP_ADDRESS VARCHAR2(50),
    SESSION_ID VARCHAR2(100),
    MODULE VARCHAR2(50)
);
```

---

**END OF ANNEX T26**
