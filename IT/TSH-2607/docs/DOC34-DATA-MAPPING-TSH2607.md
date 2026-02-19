# DOC34-DATA-MAPPING-TSH2607.md
# Data Mapping Document
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC34-DATA-MAPPING-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Data Mapping Document provides detailed mapping specifications between source systems and the target UCMS database. It defines field-level transformations, business rules, and data quality requirements.

### 1.2 Source Systems

| System ID | System Name | Platform | Data Access |
|-----------|-------------|----------|-------------|
| SRC001 | Legacy USP System | Oracle 12c | JDBC |
| SRC002 | Claims Spreadsheet | Excel/CSV | File Import |
| SRC003 | Provider Database | MS Access | ODBC |
| SRC004 | Payment System | SQL Server | JDBC |
| SRC005 | Document Repository | File System | File API |

### 1.3 Target System

| Database | Version | Schema |
|----------|---------|--------|
| PostgreSQL | 15.x | ucms_prod |

---

## 2.0 ENTITY MAPPING: APPLICANTS

### 2.1 Source: Legacy USP System (USP_APPLICANTS)
**Target:** T_APPLICANTS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | APPLICANT_ID | NUMBER | applicant_id | VARCHAR(36) | Generate UUID | Primary Key |
| 2 | IC_NUMBER | VARCHAR2(14) | ic_number | VARCHAR(14) | Standardize format | Remove spaces, add dash |
| 3 | FULL_NAME | VARCHAR2(200) | full_name | VARCHAR(200) | Trim, Title Case | |
| 4 | EMAIL | VARCHAR2(255) | email | VARCHAR(255) | Lowercase, trim | Validate format |
| 5 | PHONE_MOBILE | VARCHAR2(15) | phone_mobile | VARCHAR(15) | Clean, standardize | Remove country code if MY |
| 6 | PHONE_FIXED | VARCHAR2(15) | phone_fixed | VARCHAR(15) | Clean, standardize | Optional |
| 7 | DATE_OF_BIRTH | DATE | date_of_birth | DATE | Direct map | Validate < today |
| 8 | GENDER | CHAR(1) | gender | CHAR(1) | Map values | M→M, F→F, U→O |
| 9 | ADDRESS1 | VARCHAR2(255) | address_line1 | VARCHAR(255) | Trim | |
| 10 | ADDRESS2 | VARCHAR2(255) | address_line2 | VARCHAR(255) | Trim | Nullable |
| 11 | POSTCODE | VARCHAR2(10) | postcode | VARCHAR(10) | Clean, validate | 5 digits for MY |
| 12 | CITY | VARCHAR2(100) | city | VARCHAR(100) | Title Case | |
| 13 | STATE | VARCHAR2(50) | state_code | VARCHAR(3) | Lookup mapping | See State Mapping |
| 14 | GPS_LAT | NUMBER(10,8) | gps_latitude | DECIMAL(10,8) | Direct map | Validate range |
| 15 | GPS_LONG | NUMBER(11,8) | gps_longitude | DECIMAL(11,8) | Direct map | Validate range |
| 16 | INCOME_RANGE | VARCHAR2(20) | annual_income | DECIMAL(15,2) | Map to midpoint | See Income Mapping |
| 17 | IS_RURAL | CHAR(1) | rural_status | CHAR(1) | Direct map | Y/N |
| 18 | IS_B40 | CHAR(1) | b40_status | CHAR(1) | Direct map | Y/N |
| 19 | IS_ORANG_ASLI | CHAR(1) | orang_asli | CHAR(1) | Direct map | Y/N |
| 20 | IS_DISABLED | CHAR(1) | disability | CHAR(1) | Direct map | Y/N |
| 21 | CREATED_DATE | DATE | created_date | TIMESTAMP | Direct map | |
| 22 | CREATED_BY | VARCHAR2(50) | created_by | VARCHAR(50) | Direct map | Map user if exists |
| 23 | STATUS | VARCHAR2(20) | status | CHAR(1) | Map values | Active→A, Inactive→I |

### 2.2 Transformation Rules: Applicants

#### IC Number Standardization
```
Input: "900101011234" or "900101 01 1234" or "900101-01-1234"
Output: "900101-01-1234"
Rule: Insert dashes at positions 7 and 9
```

#### State Code Mapping

| Source Value | Target Value |
|--------------|--------------|
| Johor | JHR |
| Kedah | KDH |
| Kelantan | KTN |
| Kuala Lumpur | KUL |
| Labuan | LBN |
| Melaka | MLK |
| Negeri Sembilan | NSN |
| Pahang | PHG |
| Pulau Pinang | PNG |
| Perak | PRK |
| Perlis | PLS |
| Sabah | SBH |
| Sarawak | SWK |
| Selangor | SGR |
| Terengganu | TRG |
| Putrajaya | PJY |

#### Income Range Mapping

| Source Value | Target Value (RM) |
|--------------|-------------------|
| < RM1,000 | 500.00 |
| RM1,000 - RM2,000 | 1500.00 |
| RM2,001 - RM3,000 | 2500.00 |
| RM3,001 - RM4,000 | 3500.00 |
| RM4,001 - RM5,000 | 4500.00 |
| > RM5,000 | 6000.00 |

---

## 3.0 ENTITY MAPPING: CLAIMS

### 3.1 Source: Legacy USP System (USP_CLAIMS)
**Target:** T_CLAIMS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | CLAIM_ID | NUMBER | claim_id | VARCHAR(36) | Generate UUID | Primary Key |
| 2 | CLAIM_REF | VARCHAR2(20) | claim_reference | VARCHAR(30) | Prefix + Sequence | UCMS-YYYY-##### |
| 3 | APPLICANT_ID | NUMBER | applicant_id | VARCHAR(36) | Lookup FK | Map to new UUID |
| 4 | PROVIDER_ID | NUMBER | provider_id | VARCHAR(36) | Lookup FK | Map to new UUID |
| 5 | SCHEME_CODE | VARCHAR2(20) | scheme_id | VARCHAR(20) | Direct map | Validate exists |
| 6 | CLAIM_DATE | DATE | application_date | TIMESTAMP | Add time component | Set to 00:00:00 |
| 7 | CLAIM_AMOUNT | NUMBER(15,2) | claim_amount | DECIMAL(15,2) | Direct map | Validate > 0 |
| 8 | APPROVED_AMOUNT | NUMBER(15,2) | approved_amount | DECIMAL(15,2) | Direct map | Nullable |
| 9 | CLAIM_STATUS | VARCHAR2(20) | claim_status | VARCHAR(30) | Map values | See Status Mapping |
| 10 | INSTALL_ADDR | VARCHAR2(500) | installation_address | VARCHAR(500) | Trim | |
| 11 | SERVICE_DATE | DATE | service_start_date | DATE | Direct map | Nullable |
| 12 | INVOICE_NO | VARCHAR2(50) | invoice_number | VARCHAR(50) | Direct map | Nullable |
| 13 | INVOICE_DATE | DATE | invoice_date | DATE | Direct map | Nullable |
| 14 | PRIORITY | NUMBER | priority_level | INTEGER | Map values | 1-3 |
| 15 | SUBMITTED_BY | VARCHAR2(50) | created_by | VARCHAR(50) | Direct map | |
| 16 | SUBMITTED_DATE | DATE | created_date | TIMESTAMP | Direct map | |

### 3.2 Status Mapping

| Source Status | Target Status | Business Rule |
|---------------|---------------|---------------|
| PENDING | SUBMITTED | New submissions |
| REVIEWING | UNDER_REVIEW | Under evaluation |
| APPROVED | APPROVED | Approved for payment |
| REJECTED | REJECTED | Not approved |
| PAID | PAID | Payment completed |
| CANCELLED | CANCELLED | Withdrawn |
| DRAFT | DRAFT | Incomplete |

---

## 4.0 ENTITY MAPPING: CLAIM DETAILS

### 4.1 Source: Legacy USP System (USP_CLAIM_ITEMS)
**Target:** T_CLAIM_DETAILS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | ITEM_ID | NUMBER | detail_id | VARCHAR(36) | Generate UUID | Primary Key |
| 2 | CLAIM_ID | NUMBER | claim_id | VARCHAR(36) | Lookup FK | Map to new UUID |
| 3 | LINE_NO | NUMBER | line_number | INTEGER | Direct map | |
| 4 | CATEGORY | VARCHAR2(50) | item_category | VARCHAR(50) | Map to new codes | See Category Mapping |
| 5 | DESCRIPTION | VARCHAR2(500) | item_description | VARCHAR(500) | Trim | |
| 6 | QUANTITY | NUMBER(10,2) | quantity | DECIMAL(10,2) | Direct map | |
| 7 | UOM | VARCHAR2(20) | unit_of_measure | VARCHAR(20) | Standardize | See UOM Mapping |
| 8 | UNIT_PRICE | NUMBER(15,2) | unit_price | DECIMAL(15,2) | Direct map | |
| 9 | LINE_TOTAL | NUMBER(15,2) | line_total | DECIMAL(15,2) | Calculate or verify | Qty × Price |
| 10 | ELIGIBLE_AMT | NUMBER(15,2) | usp_eligible_amount | DECIMAL(15,2) | Direct map | |

### 4.2 Category Mapping

| Legacy Code | UCMS Code | Description |
|-------------|-----------|-------------|
| EQUIP | EQUIPMENT | Equipment/Devices |
| INST | INSTALLATION | Installation Services |
| CABL | CABLING | Cabling Infrastructure |
| MAINT | MAINTENANCE | Maintenance Services |
| SUBS | SUBSCRIPTION | Subscription Fees |
| OTHER | OTHER | Other Items |

### 4.3 Unit of Measure Mapping

| Legacy | UCMS | Description |
|--------|------|-------------|
| EA | pc | Each/Piece |
| M | m | Meter |
| KM | km | Kilometer |
| SET | set | Set |
| HR | hr | Hour |
| DAY | day | Day |
| MON | month | Month |
| YR | year | Year |

---

## 5.0 ENTITY MAPPING: PAYMENTS

### 5.1 Source: Payment System (PAY_TRANSACTIONS)
**Target:** T_PAYMENTS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | TRANS_ID | VARCHAR(36) | payment_id | VARCHAR(36) | Direct map | UUID |
| 2 | CLAIM_REF | VARCHAR2(20) | claim_id | VARCHAR(36) | Lookup FK | Map to claim UUID |
| 3 | PAY_REF | VARCHAR2(30) | payment_reference | VARCHAR(30) | Direct map | |
| 4 | PAY_TYPE | VARCHAR2(20) | payment_type | VARCHAR(30) | Map values | DISBURSEMENT/REFUND |
| 5 | PAYEE_TYPE | CHAR(1) | payee_type | CHAR(1) | Direct map | A/P |
| 6 | PAYEE_ID | VARCHAR(50) | payee_id | VARCHAR(36) | Lookup FK | |
| 7 | AMOUNT | DECIMAL(15,2) | payment_amount | DECIMAL(15,2) | Direct map | |
| 8 | PAY_DATE | DATE | payment_date | TIMESTAMP | Direct map | |
| 9 | PAY_METHOD | VARCHAR2(30) | payment_method | VARCHAR(30) | Map values | See Method Mapping |
| 10 | BANK_ACC | VARCHAR2(30) | bank_account | VARCHAR(30) | Mask if logging | Encrypt in DB |
| 11 | BANK_NAME | VARCHAR2(100) | bank_name | VARCHAR(100) | Direct map | |
| 12 | TRANS_REF | VARCHAR2(100) | transaction_reference | VARCHAR(100) | Direct map | Bank ref |
| 13 | STATUS | VARCHAR2(20) | payment_status | VARCHAR(20) | Map values | |
| 14 | AUTH_BY | VARCHAR2(50) | authorized_by | VARCHAR(50) | Direct map | |
| 15 | AUTH_DATE | DATE | authorized_date | TIMESTAMP | Direct map | |

### 5.2 Payment Method Mapping

| Source | Target |
|--------|--------|
| FT | Bank Transfer |
| CHQ | Cheque |
| CASH | Cash |
| ONLINE | Online Banking |
| OTHER | Other |

---

## 6.0 ENTITY MAPPING: SERVICE PROVIDERS

### 6.1 Source: Provider Database (PROVIDERS)
**Target:** T_SERVICE_PROVIDERS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | PROV_ID | NUMBER | provider_id | VARCHAR(36) | Generate UUID | Primary Key |
| 2 | LICENSE_NO | VARCHAR(50) | license_number | VARCHAR(50) | Direct map | |
| 3 | COMPANY_NAME | VARCHAR(200) | company_name | VARCHAR(200) | Title Case | |
| 4 | TRADING_NAME | VARCHAR(200) | trading_name | VARCHAR(200) | Title Case | Nullable |
| 5 | REG_NO | VARCHAR(20) | company_reg_no | VARCHAR(20) | Standardize | SSM format |
| 6 | SERVICE_TYPE | VARCHAR(50) | service_type | VARCHAR(50) | Map values | |
| 7 | CONTACT | VARCHAR(200) | contact_person | VARCHAR(200) | Direct map | |
| 8 | EMAIL | VARCHAR(255) | contact_email | VARCHAR(255) | Lowercase | |
| 9 | PHONE | VARCHAR(15) | contact_phone | VARCHAR(15) | Clean | |
| 10 | ADDRESS | TEXT | address | VARCHAR(500) | Consolidate | |
| 11 | STATE | VARCHAR(50) | state_code | VARCHAR(3) | Map to code | |
| 12 | BANK_ACC | VARCHAR(30) | bank_account | VARCHAR(30) | Encrypt | |
| 13 | BANK | VARCHAR(100) | bank_name | VARCHAR(100) | Direct map | |
| 14 | CONTRACT_START | DATE | contract_start | DATE | Direct map | |
| 15 | CONTRACT_END | DATE | contract_end | DATE | Direct map | Nullable |
| 16 | STATUS | VARCHAR(20) | status | VARCHAR(20) | Map values | |

---

## 7.0 ENTITY MAPPING: DOCUMENTS

### 7.1 Source: Document Repository (Files + Metadata DB)
**Target:** T_DOCUMENTS

| # | Source Field | Source Type | Target Field | Target Type | Transformation Rule | Notes |
|---|--------------|-------------|--------------|-------------|---------------------|-------|
| 1 | DOC_ID | VARCHAR(36) | document_id | VARCHAR(36) | Generate new UUID | |
| 2 | ENTITY_TYPE | VARCHAR(30) | entity_type | VARCHAR(30) | Map values | CLAIM/APPLICANT |
| 3 | ENTITY_ID | VARCHAR(50) | entity_id | VARCHAR(36) | Lookup FK | Map to new UUID |
| 4 | DOC_TYPE | VARCHAR(50) | document_type | VARCHAR(50) | Map values | See Type Mapping |
| 5 | FILE_NAME | VARCHAR(255) | document_name | VARCHAR(255) | Direct map | |
| 6 | FILE_PATH | VARCHAR(500) | file_path | VARCHAR(500) | Transform path | New storage path |
| 7 | FILE_SIZE | NUMBER | file_size | INTEGER | Direct map | Bytes |
| 8 | MIME_TYPE | VARCHAR(100) | mime_type | VARCHAR(100) | Derive from ext | |
| 9 | MD5_HASH | VARCHAR(32) | checksum | VARCHAR(64) | Recompute | SHA-256 |
| 10 | UPLOAD_DATE | DATE | upload_date | TIMESTAMP | Direct map | |
| 11 | UPLOADED_BY | VARCHAR(50) | uploaded_by | VARCHAR(50) | Direct map | |
| 12 | STATUS | VARCHAR(20) | status | CHAR(1) | Map values | A/D |

### 7.2 Document Type Mapping

| Source Folder/Type | Target Type | Description |
|--------------------|-------------|-------------|
| ic_documents | IC_COPY | Identification |
| income_proof | PROOF_OF_INCOME | Salary/EA Form |
| residence_proof | PROOF_OF_RESIDENCE | Utility Bill |
| quotations | QUOTATION | Service Quote |
| invoices | INVOICE | Service Invoice |
| completion | COMPLETION_CERT | Completion Proof |
| bank_statements | BANK_STATEMENT | Bank Details |
| other | SUPPORTING_DOC | Other Documents |

---

## 8.0 DATA QUALITY RULES

### 8.1 Validation Rules

| Entity | Field | Rule | Action on Failure |
|--------|-------|------|-------------------|
| APPLICANTS | ic_number | Must match regex | Reject, flag for review |
| APPLICANTS | email | Valid email format | Reject, flag for review |
| APPLICANTS | phone_mobile | 10-15 digits | Clean or reject |
| CLAIMS | claim_amount | > 0 | Reject |
| CLAIMS | application_date | Not in future | Reject |
| PAYMENTS | payment_amount | > 0 | Reject |
| DOCUMENTS | file_size | < 50MB | Reject |

### 8.2 Business Rules

| Rule ID | Description | Implementation |
|---------|-------------|----------------|
| BR001 | IC must be unique | Check before insert |
| BR002 | Claim amount ≤ scheme max | Validate against T_USP_SCHEMES |
| BR003 | Payment ≤ approved amount | Validate against T_CLAIMS |
| BR004 | Active provider only | Check provider status |
| BR005 | Document must have valid entity | FK validation |

---

## 9.0 LOOKUP TABLES

### 9.1 User ID Mapping

| Legacy User ID | UCMS User ID | Name |
|----------------|--------------|------|
| ADMIN001 | ucms.admin | System Administrator |
| MCMC001 | mcmc.officer.001 | MCMC Officer 1 |
| [Additional mappings...] | | |

### 9.2 Scheme Code Mapping

| Legacy Code | UCMS Scheme ID | Name |
|-------------|----------------|------|
| USP001 | USP-BB-2024 | Broadband Infrastructure |
| USP002 | USP-DEV-2024 | Device Subsidy |
| [Additional mappings...] | | |

---

## 10.0 APPENDICES

### Appendix A: Field-Level Mapping Matrices
[Detailed Excel sheets for each entity]

### Appendix B: Transformation Code Samples
[SQL/Python scripts for complex transformations]

### Appendix C: Data Quality Reports
[Sample DQ reports from profiling]

### Appendix D: Rejected Data Handling
[Procedures for manual review queue]

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Data Architect | | | |
| ETL Lead | | | |
| Business Analyst | | | |
| MCMC Representative | | | |

---

*Document Control: This Data Mapping Document is maintained by the Data Architecture team. Updates require version control and approval.*
