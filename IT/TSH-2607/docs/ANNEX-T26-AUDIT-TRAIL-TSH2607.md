# ANNEX T26: AUDIT TRAIL DESIGN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive Audit Trail design for the USP Claims Management System, ensuring complete traceability of all system activities, data modifications, and user actions for compliance, security, and forensic purposes.

### 1.1 KRISA Compliance
- **KRISA Section 10**: Security audit and logging requirements
- **National Audit Act 1957**: Audit trail requirements
- **PDPA 2010**: Data access logging requirements
- ** Treasury Circular**: Financial system audit requirements

---

## 2. AUDIT TRAIL ARCHITECTURE

### 2.1 Audit Scope

| Category | Scope | Retention |
|----------|-------|-----------|
| Data Changes | All CRUD operations on claim data | 7 years |
| User Actions | Login, logout, navigation, exports | 3 years |
| System Events | Background jobs, errors, alerts | 2 years |
| Security Events | Access attempts, privilege changes | 7 years |
| Financial Events | Payment approvals, amount changes | 10 years |
| Configuration Changes | System setting modifications | 5 years |

### 2.2 Audit Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    AUDIT TRAIL ARCHITECTURE                     │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐        │
│  │  UCMS    │  │  UCMS    │  │  UCMS    │  │ External │        │
│  │ Modules  │  │  Mobile  │  │   API    │  │ Systems  │        │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘        │
│       │             │             │             │               │
│       └─────────────┴─────────────┴─────────────┘               │
│                     │                                           │
│                     ▼                                           │
│       ┌─────────────────────────┐                              │
│       │   AUDIT INTERCEPTOR     │                              │
│       │  ┌─────────────────────┐│                              │
│       │  │ • Action Capture    ││                              │
│       │  │ • Data Snapshots    ││                              │
│       │  │ • Context Enrich    ││                              │
│       │  │ • Hash Generation   ││                              │
│       │  └─────────────────────┘│                              │
│       └───────────┬─────────────┘                              │
│                   │                                             │
│       ┌───────────┼───────────┐                                │
│       ▼           ▼           ▼                                │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                          │
│  │ Audit DB│ │Secure   │ │Real-time│                          │
│  │(Oracle) │ │Archive  │ │ Monitor │                          │
│  └─────────┘ └─────────┘ └─────────┘                          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. AUDIT DATA MODEL

### 3.1 Core Audit Tables

#### AUDIT_LOG_MASTER

| Column | Data Type | Description |
|--------|-----------|-------------|
| AUDIT_ID | VARCHAR2(50) | Primary key (UUID) |
| AUDIT_TIMESTAMP | TIMESTAMP(6) | Event timestamp (GMT+8) |
| AUDIT_DATE | DATE | Partition key |
| EVENT_TYPE | VARCHAR2(50) | Classification |
| EVENT_SEVERITY | VARCHAR2(20) | INFO/WARNING/ERROR/CRITICAL |
| USER_ID | VARCHAR2(50) | Acting user |
| USER_TYPE | VARCHAR2(20) | INTERNAL/EXTERNAL/SYSTEM |
| SESSION_ID | VARCHAR2(100) | Session identifier |
| IP_ADDRESS | VARCHAR2(45) | Source IP (IPv6 compatible) |
| DEVICE_ID | VARCHAR2(100) | Device fingerprint |
| MODULE_CODE | VARCHAR2(20) | UCMS module |
| ENTITY_TYPE | VARCHAR2(50) | Business entity |
| ENTITY_ID | VARCHAR2(50) | Entity identifier |
| TRANSACTION_ID | VARCHAR2(50) | Business transaction |

#### AUDIT_LOG_DETAIL

| Column | Data Type | Description |
|--------|-----------|-------------|
| DETAIL_ID | VARCHAR2(50) | Primary key |
| AUDIT_ID | VARCHAR2(50) | FK to master |
| ACTION_TYPE | VARCHAR2(20) | CREATE/READ/UPDATE/DELETE |
| FIELD_NAME | VARCHAR2(100) | Modified field |
| OLD_VALUE | CLOB | Previous value (encrypted) |
| NEW_VALUE | CLOB | New value (encrypted) |
| CHANGE_REASON | VARCHAR2(500) | Justification |
| APPROVAL_REF | VARCHAR2(50) | Authorization reference |

#### AUDIT_LOG_SECURITY

| Column | Data Type | Description |
|--------|-----------|-------------|
| SECURITY_ID | VARCHAR2(50) | Primary key |
| AUDIT_ID | VARCHAR2(50) | FK to master |
| AUTH_METHOD | VARCHAR2(50) | Authentication method |
| AUTH_RESULT | VARCHAR2(20) | SUCCESS/FAILURE |
| PRIVILEGE_USED | VARCHAR2(100) | Role/permission |
| DATA_CLASSIFICATION | VARCHAR2(20) | Sensitivity level |
| ENCRYPTION_STATUS | VARCHAR2(20) | Encryption applied |

### 3.2 Event Type Classification

| Event Code | Category | Description | Example |
|------------|----------|-------------|---------|
| AUTH | Authentication | Login/logout events | User login attempt |
| AUTHZ | Authorization | Permission checks | Access denied |
| DATA_C | Data Create | New record insertion | New claim submitted |
| DATA_R | Data Read | Record access | Claim viewed |
| DATA_U | Data Update | Record modification | Amount changed |
| DATA_D | Data Delete | Record removal | Draft deleted |
| PROC | Process | Business process | Approval workflow |
| SYS | System | System events | Backup completed |
| SEC | Security | Security events | Password changed |
| CONFIG | Configuration | Settings change | SLA threshold modified |
| EXPORT | Data Export | Bulk data extraction | Report downloaded |

---

## 4. AUDIT CAPTURE MECHANISMS

### 4.1 Database Trigger Audit

```sql
-- Example: Claim modification trigger
CREATE OR REPLACE TRIGGER TRG_AUDIT_CLAIM_UPDATE
AFTER UPDATE ON USP_CLAIMS
FOR EACH ROW
DECLARE
    v_audit_id VARCHAR2(50);
BEGIN
    -- Generate audit record for each changed field
    IF :OLD.CLAIM_AMOUNT != :NEW.CLAIM_AMOUNT THEN
        AUDIT_PKG.LOG_CHANGE(
            p_entity_type => 'USP_CLAIM',
            p_entity_id   => :NEW.CLAIM_ID,
            p_field_name  => 'CLAIM_AMOUNT',
            p_old_value   => :OLD.CLAIM_AMOUNT,
            p_new_value   => :NEW.CLAIM_AMOUNT,
            p_change_reason => :NEW.CHANGE_REASON
        );
    END IF;
    
    -- Log status changes with workflow context
    IF :OLD.CLAIM_STATUS != :NEW.CLAIM_STATUS THEN
        AUDIT_PKG.LOG_STATUS_CHANGE(
            p_claim_id    => :NEW.CLAIM_ID,
            p_old_status  => :OLD.CLAIM_STATUS,
            p_new_status  => :NEW.CLAIM_STATUS,
            p_user_id     => NVL(V('APP_USER'), 'SYSTEM'),
            p_approval_ref => :NEW.APPROVAL_REFERENCE
        );
    END IF;
END;
```

### 4.2 Application-Level Audit

| Layer | Mechanism | Capture Point |
|-------|-----------|---------------|
| UI | JavaScript Logger | User interactions |
| Controller | AOP Interceptor | API calls |
| Service | Method Annotation | Business logic |
| Data Access | Hibernate Interceptor | ORM operations |
| Database | Triggers | Direct SQL |

### 4.3 Critical Field Monitoring

| Entity | Critical Fields | Audit Level |
|--------|-----------------|-------------|
| USP_CLAIM | CLAIM_AMOUNT, CLAIM_STATUS, SP_ID | Full delta |
| PAYMENT | PAYMENT_AMOUNT, PAYEE_ACCOUNT, STATUS | Full delta |
| APPROVAL | APPROVER_ID, APPROVAL_DATE, REMARKS | Full delta |
| SP_MASTER | BANK_DETAILS, CONTACT_INFO | Full delta |
| USER_ACCOUNT | PRIVILEGES, PASSWORD, STATUS | Full delta |

---

## 5. AUDIT SECURITY

### 5.1 Tamper Protection

| Mechanism | Implementation | Verification |
|-----------|----------------|--------------|
| Immutable Storage | WORM storage for archive | Hash verification |
| Chain Hashing | SHA-256 chain linking | Forensic audit |
| Digital Signature | HSM-signed log blocks | Signature validation |
| Separation of Duties | Audit admin ≠ System admin | Access review |

### 5.2 Chain Hashing Algorithm

```
For each audit record:
    RECORD_HASH = SHA256(
        AUDIT_ID + 
        TIMESTAMP + 
        EVENT_TYPE + 
        USER_ID + 
        ENTITY_ID + 
        PREVIOUS_HASH
    )
    
Store: RECORD_HASH in current record
        Link to previous record's hash
```

### 5.3 Access Control

| Role | View Audit | Export Audit | Modify Audit | Delete Audit |
|------|------------|--------------|--------------|--------------|
| Auditor | All | Yes | No | No |
| Security Admin | Security events | Yes | No | No |
| System Admin | System events | Limited | No | No |
| Manager | Own team | Limited | No | No |
| Officer | Own actions | No | No | No |

---

## 6. AUDIT RETENTION AND ARCHIVAL

### 6.1 Retention Schedule

| Data Category | Online Retention | Archive Retention | Destruction |
|---------------|------------------|-------------------|-------------|
| Financial audit | 2 years | 8 years | Secure wipe |
| Security audit | 1 year | 6 years | Secure wipe |
| Operational audit | 6 months | 2 years | Secure wipe |
| System audit | 3 months | 1 year | Standard delete |

### 6.2 Archival Process

```
┌─────────────────────────────────────────────────────────────────┐
│                    AUDIT ARCHIVAL WORKFLOW                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │   Identify  │───▶│   Package   │───▶│   Sign &    │         │
│  │   Records   │    │   Archive   │    │   Hash      │         │
│  │   (> Age)   │    │   (Encrypt) │    │             │         │
│  └─────────────┘    └─────────────┘    └──────┬──────┘         │
│                                               │                 │
│                    ┌──────────────────────────┘                 │
│                    ▼                                            │
│         ┌─────────────────┐     ┌─────────────┐                 │
│         │  Transfer to    │────▶│  Verify     │                 │
│         │  WORM Storage   │     │  Archive    │                 │
│         └─────────────────┘     └──────┬──────┘                 │
│                                        │                        │
│                    ┌───────────────────┘                        │
│                    ▼                                            │
│         ┌─────────────────┐     ┌─────────────┐                 │
│         │  Purge Online   │────▶│  Update     │                 │
│         │  Records        │     │  Metadata   │                 │
│         └─────────────────┘     └─────────────┘                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 7. AUDIT REPORTING

### 7.1 Standard Audit Reports

| Report ID | Name | Description | Frequency |
|-----------|------|-------------|-----------|
| AUD-001 | User Activity Summary | Actions by user | Daily |
| AUD-002 | Data Change Log | All modifications | Real-time |
| AUD-003 | Failed Access Attempts | Security violations | Real-time |
| AUD-004 | Privilege Escalation | Role changes | Weekly |
| AUD-005 | Financial Integrity | Amount changes | Daily |
| AUD-006 | Data Export Log | Bulk exports | Daily |
| AUD-007 | Admin Activity | Privileged actions | Weekly |
| AUD-008 | Compliance Summary | KRISA compliance | Monthly |

### 7.2 Audit Query Interface

```sql
-- Example: Find all changes to a specific claim
SELECT 
    al.AUDIT_TIMESTAMP,
    al.USER_ID,
    al.EVENT_TYPE,
    ad.FIELD_NAME,
    ad.OLD_VALUE,
    ad.NEW_VALUE,
    ad.CHANGE_REASON
FROM AUDIT_LOG_MASTER al
JOIN AUDIT_LOG_DETAIL ad ON al.AUDIT_ID = ad.AUDIT_ID
WHERE al.ENTITY_TYPE = 'USP_CLAIM'
  AND al.ENTITY_ID = 'UCMS-2025-001234'
ORDER BY al.AUDIT_TIMESTAMP DESC;

-- Example: Detect suspicious activity
SELECT 
    USER_ID,
    COUNT(*) as FAILED_ATTEMPTS,
    MIN(AUDIT_TIMESTAMP) as FIRST_ATTEMPT,
    MAX(AUDIT_TIMESTAMP) as LAST_ATTEMPT
FROM AUDIT_LOG_SECURITY
WHERE AUTH_RESULT = 'FAILURE'
  AND AUDIT_TIMESTAMP > SYSDATE - 1
GROUP BY USER_ID
HAVING COUNT(*) > 5;
```

---

## 8. COMPLIANCE MAPPING

| Requirement | Standard | Audit Control |
|-------------|----------|---------------|
| Audit trail completeness | KRISA 10.1 | All events captured |
| Audit trail protection | KRISA 10.2 | Tamper-evident storage |
| Audit review | KRISA 10.3 | Automated reports |
| Audit retention | Treasury | 7+ years retention |
| User access logging | PDPA | Full session tracking |
| Financial integrity | Audit Act | Dual control logging |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T31-SECURITY-FRAMEWORK | Security Controls |
| CR-002 | ANNEX-T33-VAPT-PLAN | Security Testing |
| CR-003 | ANNEX-T24-REPORT-CATALOG | Audit Reports |
| CR-004 | ANNEX-T37-BACKUP-RECOVERY | Audit Backup |

---

## 10. VERSION CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | June 2025 | UCMS Team | Initial release |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
