# DOC27-DATA-DICTIONARY-TSH2607.md
# Data Dictionary
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC27-DATA-DICTIONARY-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Classification | Confidential |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Data Dictionary provides comprehensive definitions, specifications, and metadata for all data elements within the Universal Service Provision (USP) Claims Management System (UCMS).

### 1.2 Scope
This document covers:
- All database tables and their structures
- Data element definitions
- Data types and formats
- Validation rules
- Relationships between entities
- Data ownership and sensitivity classifications

### 1.3 Document Structure
- Section 2: Core Entity Definitions
- Section 3: Data Element Specifications
- Section 4: Reference Data
- Section 5: Data Relationships
- Section 6: Data Quality Rules

---

## 2.0 CORE ENTITY DEFINITIONS

### 2.1 Entity Relationship Overview

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   APPLICANTS    │────►│     CLAIMS      │◄────│  SERVICE_PROVIDERS│
└────────┬────────┘     └────────┬────────┘     └─────────────────┘
         │                       │
         ▼                       ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  CONTACT_INFO   │     │  CLAIM_DETAILS  │────►│   PAYMENTS      │
└─────────────────┘     └────────┬────────┘     └─────────────────┘
                                 │
         ┌───────────────────────┼───────────────────────┐
         ▼                       ▼                       ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  DOCUMENTS      │     │  WORKFLOW_LOG   │     │   AUDIT_LOG     │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

### 2.2 Master Data Entities

| Entity | Description | Record Count Est. | Growth Rate |
|--------|-------------|-------------------|-------------|
| APPLICANTS | Individual and corporate USP applicants | 500,000+ | 10%/year |
| SERVICE_PROVIDERS | Telecommunications service providers | 50 | Stable |
| USP_SCHEMES | Available USP funding schemes | 20 | 2/year |
| GEOGRAPHIC_AREAS | Targeted coverage areas | 15,000 | 500/year |

### 2.3 Transactional Data Entities

| Entity | Description | Record Count Est. | Retention |
|--------|-------------|-------------------|-----------|
| CLAIMS | USP funding claims | 1,000,000+ | 7 years |
| CLAIM_DETAILS | Line items per claim | 5,000,000+ | 7 years |
| PAYMENTS | Disbursement transactions | 2,000,000+ | 10 years |
| WORKFLOW_LOG | Processing history | 10,000,000+ | 7 years |

---

## 3.0 DATA ELEMENT SPECIFICATIONS

### 3.1 APPLICANTS Table

**Table Name:** T_APPLICANTS
**Description:** Stores applicant (beneficiary) information
**Primary Key:** APPLICANT_ID
**Volume:** 500,000+ records

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| APPLICANT_ID | VARCHAR | 36 | No | Unique identifier (UUID) |
| APPLICANT_TYPE | CHAR | 1 | No | I=Individual, C=Corporate |
| IC_NUMBER | VARCHAR | 14 | Yes | Malaysian IC (with dashes) |
| COMPANY_REG_NO | VARCHAR | 20 | Yes | SSM registration number |
| FULL_NAME | VARCHAR | 200 | No | Applicant full name |
| EMAIL | VARCHAR | 255 | No | Primary email address |
| PHONE_MOBILE | VARCHAR | 15 | No | Mobile number |
| PHONE_FIXED | VARCHAR | 15 | Yes | Fixed line number |
| DATE_OF_BIRTH | DATE | - | Yes | For individuals |
| NATIONALITY | VARCHAR | 3 | Yes | ISO country code |
| GENDER | CHAR | 1 | Yes | M/F/O |
| OCCUPATION | VARCHAR | 100 | Yes | Occupation category |
| ANNUAL_INCOME | DECIMAL | 15,2 | Yes | Declared income |
| HOUSEHOLD_SIZE | INTEGER | - | Yes | Number of dependents |
| ADDRESS_LINE1 | VARCHAR | 255 | No | Street address |
| ADDRESS_LINE2 | VARCHAR | 255 | Yes | Additional address |
| ADDRESS_LINE3 | VARCHAR | 255 | Yes | Additional address |
| POSTCODE | VARCHAR | 10 | No | Postal code |
| CITY | VARCHAR | 100 | No | City name |
| STATE_CODE | VARCHAR | 3 | No | State reference |
| COUNTRY_CODE | VARCHAR | 3 | No | Default MYS |
| GPS_LATITUDE | DECIMAL | 10,8 | Yes | Latitude coordinate |
| GPS_LONGITUDE | DECIMAL | 11,8 | Yes | Longitude coordinate |
| RURAL_STATUS | CHAR | 1 | Yes | Y/N - Rural classification |
| B40_STATUS | CHAR | 1 | Yes | Y/N - B40 classification |
| ORANG_ASLI | CHAR | 1 | Yes | Y/N - Indigenous status |
| DISABILITY | CHAR | 1 | Yes | Y/N - Disability status |
| VERIFICATION_STATUS | VARCHAR | 20 | No | Pending/Verified/Rejected |
| VERIFICATION_DATE | DATETIME | - | Yes | Date verified |
| CREATED_DATE | DATETIME | - | No | Record creation timestamp |
| CREATED_BY | VARCHAR | 50 | No | Creator user ID |
| MODIFIED_DATE | DATETIME | - | Yes | Last modification |
| MODIFIED_BY | VARCHAR | 50 | Yes | Modifier user ID |
| STATUS | CHAR | 1 | No | A=Active, I=Inactive |

**Indexes:**
- PK_APPLICANTS (APPLICANT_ID)
- IDX_IC_NUMBER (IC_NUMBER) - Unique
- IDX_COMPANY_REG (COMPANY_REG_NO) - Unique
- IDX_EMAIL (EMAIL)
- IDX_STATE (STATE_CODE)
- IDX_STATUS (STATUS)

### 3.2 SERVICE_PROVIDERS Table

**Table Name:** T_SERVICE_PROVIDERS
**Description:** Telecommunications service providers
**Primary Key:** PROVIDER_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| PROVIDER_ID | VARCHAR | 36 | No | Unique identifier |
| LICENSE_NUMBER | VARCHAR | 50 | No | MCMC license number |
| COMPANY_NAME | VARCHAR | 200 | No | Legal company name |
| TRADING_NAME | VARCHAR | 200 | Yes | Operating name |
| COMPANY_REG_NO | VARCHAR | 20 | No | SSM number |
| SERVICE_TYPE | VARCHAR | 50 | No | Type of service |
| CONTACT_PERSON | VARCHAR | 200 | No | Primary contact |
| CONTACT_EMAIL | VARCHAR | 255 | No | Contact email |
| CONTACT_PHONE | VARCHAR | 15 | No | Contact phone |
| ADDRESS | VARCHAR | 500 | No | Company address |
| STATE_CODE | VARCHAR | 3 | No | State location |
| APPROVED_SCHEMES | VARCHAR | 500 | Yes | Comma-separated scheme IDs |
| BANK_ACCOUNT | VARCHAR | 30 | Yes | Payment account |
| BANK_NAME | VARCHAR | 100 | Yes | Bank name |
| CONTRACT_START | DATE | - | No | Agreement start date |
| CONTRACT_END | DATE | - | Yes | Agreement end date |
| PERFORMANCE_RATING | DECIMAL | 3,2 | Yes | Current rating |
| STATUS | VARCHAR | 20 | No | Active/Suspended/Terminated |
| CREATED_DATE | DATETIME | - | No | Record creation |
| MODIFIED_DATE | DATETIME | - | Yes | Last modification |

### 3.3 USP_SCHEMES Table

**Table Name:** T_USP_SCHEMES
**Description:** Available USP funding programs
**Primary Key:** SCHEME_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| SCHEME_ID | VARCHAR | 20 | No | Scheme code |
| SCHEME_NAME | VARCHAR | 200 | No | Full scheme name |
| SCHEME_DESCRIPTION | TEXT | - | Yes | Detailed description |
| SCHEME_TYPE | VARCHAR | 50 | No | Infrastructure/Subsidy/Device |
| TARGET_GROUP | VARCHAR | 100 | No | Eligible beneficiaries |
| MIN_INCOME | DECIMAL | 15,2 | Yes | Minimum income threshold |
| MAX_INCOME | DECIMAL | 15,2 | Yes | Maximum income threshold |
| MAX_CLAIM_AMOUNT | DECIMAL | 15,2 | No | Per-claim limit |
| FUNDING_PERCENTAGE | DECIMAL | 5,2 | No | USP subsidy % |
| GEOGRAPHIC_SCOPE | VARCHAR | 500 | Yes | Coverage areas |
| START_DATE | DATE | - | No | Scheme commencement |
| END_DATE | DATE | - | Yes | Scheme closure |
| TOTAL_BUDGET | DECIMAL | 15,2 | No | Allocated funds |
| DISBURSED_AMOUNT | DECIMAL | 15,2 | No | Amount paid out |
| REMAINING_BUDGET | DECIMAL | 15,2 | No | Available funds |
| STATUS | VARCHAR | 20 | No | Open/Closed/Suspended |
| CREATED_DATE | DATETIME | - | No | Creation timestamp |

### 3.4 CLAIMS Table

**Table Name:** T_CLAIMS
**Description:** USP funding claims
**Primary Key:** CLAIM_ID
**Volume:** 1,000,000+ records

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| CLAIM_ID | VARCHAR | 36 | No | Unique claim number (UUID) |
| CLAIM_REFERENCE | VARCHAR | 30 | No | Human-readable reference |
| APPLICANT_ID | VARCHAR | 36 | No | FK to APPLICANTS |
| PROVIDER_ID | VARCHAR | 36 | No | FK to SERVICE_PROVIDERS |
| SCHEME_ID | VARCHAR | 20 | No | FK to USP_SCHEMES |
| CLAIM_TYPE | VARCHAR | 50 | No | Type of claim |
| APPLICATION_DATE | DATETIME | - | No | Submission timestamp |
| CLAIM_STATUS | VARCHAR | 30 | No | Current status |
| CLAIM_AMOUNT | DECIMAL | 15,2 | No | Total claim value |
| APPROVED_AMOUNT | DECIMAL | 15,2 | Yes | Approved value |
| PAID_AMOUNT | DECIMAL | 15,2 | Yes | Amount disbursed |
| INSTALLATION_ADDRESS | VARCHAR | 500 | No | Service location |
| GPS_LATITUDE | DECIMAL | 10,8 | Yes | Location latitude |
| GPS_LONGITUDE | DECIMAL | 11,8 | Yes | Location longitude |
| SERVICE_START_DATE | DATE | - | Yes | Service commencement |
| INVOICE_NUMBER | VARCHAR | 50 | Yes | Provider invoice ref |
| INVOICE_DATE | DATE | - | Yes | Invoice date |
| INVOICE_AMOUNT | DECIMAL | 15,2 | Yes | Invoice total |
| SUPPORTING_DOCS | VARCHAR | 500 | Yes | Document references |
| ELIGIBILITY_CHECK | CHAR | 1 | Yes | Y/N/NA |
| ELIGIBILITY_NOTES | TEXT | - | Yes | Eligibility remarks |
| PRIORITY_LEVEL | INTEGER | - | No | 1=High, 2=Normal, 3=Low |
| ASSIGNED_REVIEWER | VARCHAR | 50 | Yes | Reviewer user ID |
| SUBMISSION_CHANNEL | VARCHAR | 30 | No | Portal/Mobile/Branch |
| SOURCE_IP | VARCHAR | 45 | Yes | Submitting IP address |
| CREATED_DATE | DATETIME | - | No | Record creation |
| CREATED_BY | VARCHAR | 50 | No | Creator ID |
| MODIFIED_DATE | DATETIME | - | Yes | Last update |
| MODIFIED_BY | VARCHAR | 50 | Yes | Modifier ID |

**Claim Status Values:**
- DRAFT - Application in progress
- SUBMITTED - Awaiting review
- PENDING_DOCUMENTS - Additional docs required
- UNDER_REVIEW - Being evaluated
- ELIGIBLE - Eligibility confirmed
- APPROVED - Claim approved
- REJECTED - Claim rejected
- PAYMENT_PROCESSING - Disbursement in progress
- PAID - Fully paid
- CANCELLED - Withdrawn/cancelled

### 3.5 CLAIM_DETAILS Table

**Table Name:** T_CLAIM_DETAILS
**Description:** Line items for each claim
**Primary Key:** DETAIL_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| DETAIL_ID | VARCHAR | 36 | No | Unique identifier |
| CLAIM_ID | VARCHAR | 36 | No | FK to CLAIMS |
| LINE_NUMBER | INTEGER | - | No | Sequence number |
| ITEM_CATEGORY | VARCHAR | 50 | No | Category code |
| ITEM_DESCRIPTION | VARCHAR | 500 | No | Item description |
| QUANTITY | DECIMAL | 10,2 | No | Number of units |
| UNIT_OF_MEASURE | VARCHAR | 20 | No | Unit (pc, m, km, etc.) |
| UNIT_PRICE | DECIMAL | 15,2 | No | Price per unit |
| LINE_TOTAL | DECIMAL | 15,2 | No | Quantity × Price |
| USP_ELIGIBLE_AMOUNT | DECIMAL | 15,2 | No | Eligible for subsidy |
| JUSTIFICATION | TEXT | - | Yes | Cost justification |

### 3.6 PAYMENTS Table

**Table Name:** T_PAYMENTS
**Description:** Payment transactions
**Primary Key:** PAYMENT_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| PAYMENT_ID | VARCHAR | 36 | No | Unique identifier |
| CLAIM_ID | VARCHAR | 36 | No | FK to CLAIMS |
| PAYMENT_REFERENCE | VARCHAR | 30 | No | Payment reference no |
| PAYMENT_TYPE | VARCHAR | 30 | No | Disbursement/Refund |
| PAYEE_TYPE | CHAR | 1 | No | A=Applicant, P=Provider |
| PAYEE_ID | VARCHAR | 36 | No | Beneficiary ID |
| PAYMENT_AMOUNT | DECIMAL | 15,2 | No | Amount paid |
| PAYMENT_DATE | DATETIME | - | Yes | Actual payment date |
| PAYMENT_METHOD | VARCHAR | 30 | No | Bank transfer/Check/etc |
| BANK_ACCOUNT | VARCHAR | 30 | Yes | Destination account |
| BANK_NAME | VARCHAR | 100 | Yes | Bank name |
| TRANSACTION_REFERENCE | VARCHAR | 100 | Yes | Bank reference |
| PAYMENT_STATUS | VARCHAR | 20 | No | Pending/Completed/Failed |
| AUTHORIZED_BY | VARCHAR | 50 | No | Approver user ID |
| AUTHORIZED_DATE | DATETIME | - | Yes | Approval timestamp |
| REMARKS | TEXT | - | Yes | Payment notes |
| CREATED_DATE | DATETIME | - | No | Record creation |

### 3.7 WORKFLOW_LOG Table

**Table Name:** T_WORKFLOW_LOG
**Description:** Audit trail of claim processing
**Primary Key:** LOG_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| LOG_ID | VARCHAR | 36 | No | Unique identifier |
| CLAIM_ID | VARCHAR | 36 | No | FK to CLAIMS |
| ACTION_DATE | DATETIME | - | No | Timestamp |
| ACTION_TYPE | VARCHAR | 50 | No | Type of action |
| FROM_STATUS | VARCHAR | 30 | Yes | Previous status |
| TO_STATUS | VARCHAR | 30 | No | New status |
| ACTION_BY | VARCHAR | 50 | No | User/system ID |
| ACTION_BY_TYPE | VARCHAR | 20 | No | User/System/External |
| COMMENTS | TEXT | - | Yes | Action comments |
| ATTACHMENTS | VARCHAR | 500 | Yes | Document references |
| IP_ADDRESS | VARCHAR | 45 | Yes | Action origin IP |
| SESSION_ID | VARCHAR | 100 | Yes | Session identifier |

### 3.8 DOCUMENTS Table

**Table Name:** T_DOCUMENTS
**Description:** Document metadata
**Primary Key:** DOCUMENT_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| DOCUMENT_ID | VARCHAR | 36 | No | Unique identifier |
| ENTITY_TYPE | VARCHAR | 30 | No | Claim/Applicant/etc |
| ENTITY_ID | VARCHAR | 36 | No | Related record ID |
| DOCUMENT_TYPE | VARCHAR | 50 | No | Type of document |
| DOCUMENT_NAME | VARCHAR | 255 | No | Original filename |
| FILE_PATH | VARCHAR | 500 | No | Storage location |
| FILE_SIZE | INTEGER | - | No | Size in bytes |
| MIME_TYPE | VARCHAR | 100 | No | File MIME type |
| CHECKSUM | VARCHAR | 64 | No | SHA-256 hash |
| UPLOAD_DATE | DATETIME | - | No | Upload timestamp |
| UPLOADED_BY | VARCHAR | 50 | No | Uploader ID |
| VERIFICATION_STATUS | VARCHAR | 20 | No | Pending/Verified/Invalid |
| RETENTION_DATE | DATE | - | Yes | Deletion scheduled |
| STATUS | CHAR | 1 | No | A=Active, D=Deleted |

**Document Types:**
- IC_COPY - Identification document
- PROOF_OF_INCOME - Salary slip/EA form
- PROOF_OF_RESIDENCE - Utility bill/etc
- QUOTATION - Service quotation
- INVOICE - Service invoice
- COMPLETION_CERT - Work completion proof
- BANK_STATEMENT - Banking details
- SUPPORTING_DOC - Other documents

### 3.9 USERS Table

**Table Name:** T_USERS
**Description:** System user accounts
**Primary Key:** USER_ID

| Field | Data Type | Length | Nullable | Description |
|-------|-----------|--------|----------|-------------|
| USER_ID | VARCHAR | 50 | No | Username/ID |
| USER_TYPE | VARCHAR | 30 | No | Internal/External/Provider |
| FULL_NAME | VARCHAR | 200 | No | User's full name |
| EMAIL | VARCHAR | 255 | No | Email address |
| PHONE | VARCHAR | 15 | Yes | Contact number |
| DEPARTMENT | VARCHAR | 100 | Yes | Department/division |
| ROLE_CODE | VARCHAR | 20 | No | System role |
| PROVIDER_ID | VARCHAR | 36 | Yes | If service provider user |
| PASSWORD_HASH | VARCHAR | 255 | No | Encrypted password |
| PASSWORD_EXPIRY | DATETIME | - | No | Password expiration |
| MFA_ENABLED | CHAR | 1 | No | Y/N - MFA status |
| MFA_SECRET | VARCHAR | 255 | Yes | Encrypted MFA key |
| LAST_LOGIN | DATETIME | - | Yes | Last successful login |
| LOGIN_ATTEMPTS | INTEGER | - | No | Failed attempt count |
| LOCKED_UNTIL | DATETIME | - | Yes | Account lock expiry |
| CREATED_DATE | DATETIME | - | No | Account creation |
| EXPIRY_DATE | DATE | - | Yes | Account expiration |
| STATUS | VARCHAR | 20 | No | Active/Inactive/Locked |

---

## 4.0 REFERENCE DATA

### 4.1 States (R_STATES)

| STATE_CODE | STATE_NAME | REGION |
|------------|------------|--------|
| JHR | Johor | South |
| KDH | Kedah | North |
| KTN | Kelantan | East Coast |
| KUL | Kuala Lumpur | Central |
| LBN | Labuan | Borneo |
| MLK | Melaka | South |
| NSN | Negeri Sembilan | Central |
| PHG | Pahang | East Coast |
| PNG | Pulau Pinang | North |
| PRK | Perak | Central |
| PLS | Perlis | North |
| SBH | Sabah | Borneo |
| SWK | Sarawak | Borneo |
| SGR | Selangor | Central |
| TRG | Terengganu | East Coast |
| PJY | Putrajaya | Central |

### 4.2 Claim Status Flow (R_CLAIM_STATUS)

| STATUS_CODE | DESCRIPTION | NEXT_VALID_STATUS |
|-------------|-------------|-------------------|
| DRAFT | Application in progress | SUBMITTED,CANCELLED |
| SUBMITTED | Awaiting review | PENDING_DOCUMENTS,UNDER_REVIEW,CANCELLED |
| PENDING_DOCUMENTS | Additional docs required | UNDER_REVIEW,CANCELLED |
| UNDER_REVIEW | Being evaluated | ELIGIBLE,REJECTED |
| ELIGIBLE | Eligibility confirmed | APPROVED,REJECTED |
| APPROVED | Claim approved | PAYMENT_PROCESSING |
| REJECTED | Claim rejected | - |
| PAYMENT_PROCESSING | Disbursement in progress | PAID,PAYMENT_FAILED |
| PAID | Fully paid | - |
| CANCELLED | Withdrawn/cancelled | - |

### 4.3 User Roles (R_ROLES)

| ROLE_CODE | ROLE_NAME | PERMISSIONS |
|-----------|-----------|-------------|
| SYS_ADMIN | System Administrator | Full system access |
| MCMC_ADMIN | MCMC Administrator | Configuration, reports |
| MCMC_OFFICER | MCMC Officer | Review, approve claims |
| MCMC_VIEWER | MCMC Viewer | Read-only access |
| PROVIDER_ADMIN | Provider Administrator | Provider configuration |
| PROVIDER_USER | Provider User | Submit claims |
| PUBLIC_USER | Public User | Self-service portal |

---

## 5.0 DATA RELATIONSHIPS

### 5.1 Foreign Key Relationships

| Table | Column | References | On Delete |
|-------|--------|------------|-----------|
| T_CLAIMS | APPLICANT_ID | T_APPLICANTS(APPLICANT_ID) | RESTRICT |
| T_CLAIMS | PROVIDER_ID | T_SERVICE_PROVIDERS(PROVIDER_ID) | RESTRICT |
| T_CLAIMS | SCHEME_ID | T_USP_SCHEMES(SCHEME_ID) | RESTRICT |
| T_CLAIM_DETAILS | CLAIM_ID | T_CLAIMS(CLAIM_ID) | CASCADE |
| T_PAYMENTS | CLAIM_ID | T_CLAIMS(CLAIM_ID) | RESTRICT |
| T_WORKFLOW_LOG | CLAIM_ID | T_CLAIMS(CLAIM_ID) | CASCADE |
| T_DOCUMENTS | ENTITY_ID | Various (polymorphic) | CASCADE |
| T_USERS | PROVIDER_ID | T_SERVICE_PROVIDERS(PROVIDER_ID) | SET NULL |

### 5.2 Data Cardinality

| Relationship | Cardinality | Description |
|--------------|-------------|-------------|
| APPLICANT → CLAIMS | 1:N | One applicant, many claims |
| PROVIDER → CLAIMS | 1:N | One provider, many claims |
| SCHEME → CLAIMS | 1:N | One scheme, many claims |
| CLAIM → DETAILS | 1:N | One claim, many line items |
| CLAIM → PAYMENTS | 1:N | One claim, multiple payments |
| CLAIM → WORKFLOW_LOG | 1:N | One claim, many status changes |

---

## 6.0 DATA QUALITY RULES

### 6.1 Validation Rules

| Entity | Field | Rule | Error Message |
|--------|-------|------|---------------|
| APPLICANTS | IC_NUMBER | Must match format XXXXXX-XX-XXXX | Invalid IC number format |
| APPLICANTS | EMAIL | Valid email format required | Invalid email address |
| APPLICANTS | PHONE_MOBILE | Must be 10-15 digits | Invalid phone number |
| CLAIMS | CLAIM_AMOUNT | Must be > 0 | Claim amount must be positive |
| CLAIMS | APPLICATION_DATE | Cannot be future date | Future dates not allowed |
| PAYMENTS | PAYMENT_AMOUNT | Must equal approved amount | Payment amount mismatch |

### 6.2 Business Rules

| Rule ID | Description | Implementation |
|---------|-------------|----------------|
| BR001 | IC number uniqueness | Unique constraint on IC_NUMBER |
| BR002 | Active scheme required | FK constraint with status check |
| BR003 | Claim amount limits | Check constraint against scheme max |
| BR004 | Payment approval workflow | Trigger-based status validation |
| BR005 | Document retention | Automated archival after 7 years |
| BR006 | Audit logging | Trigger-based log creation |

### 6.3 Data Sensitivity Classification

| Classification | Fields | Protection Level |
|----------------|--------|------------------|
| CONFIDENTIAL | IC_NUMBER, BANK_ACCOUNT, INCOME | Encryption + Access Control |
| INTERNAL | CONTACT_INFO, ADDRESS | Access Control |
| PUBLIC | SCHEME_INFO, STATUS | Standard Protection |
| RESTRICTED | PASSWORD_HASH, MFA_SECRET | Encryption + Strict Access |

---

## 7.0 DATA RETENTION

| Data Category | Retention Period | Archival Action |
|---------------|------------------|-----------------|
| Active Claims | 7 years from closure | Move to archive |
| Cancelled Claims | 3 years | Purge after retention |
| Applicant Data | Duration of relationship + 7 years | Anonymize |
| Audit Logs | 10 years | Compress and archive |
| Session Logs | 1 year | Purge |
| System Logs | 3 years | Rotate and compress |

---

## 8.0 APPENDICES

### Appendix A: Complete Entity List

| Entity Name | Type | Records (Est.) |
|-------------|------|----------------|
| T_APPLICANTS | Master | 500,000 |
| T_SERVICE_PROVIDERS | Master | 50 |
| T_USP_SCHEMES | Master | 20 |
| T_CLAIMS | Transaction | 1,000,000 |
| T_CLAIM_DETAILS | Transaction | 5,000,000 |
| T_PAYMENTS | Transaction | 2,000,000 |
| T_WORKFLOW_LOG | Transaction | 10,000,000 |
| T_DOCUMENTS | Document | 5,000,000 |
| T_USERS | Security | 500 |
| T_AUDIT_LOG | Audit | 50,000,000 |

### Appendix B: Data Dictionary Change Log

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | Jan 2025 | Initial version |

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Database Administrator | | | |
| Data Architect | | | |
| Project Manager | | | |
| MCMC Representative | | | |

---

*Document Control: This Data Dictionary is maintained by the Data Architecture team. Updates require approval from the Data Architect and MCMC Representative.*
