# DOC36-MIGRATION-VALIDATION-TSH2607.md
# Migration Validation Report Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC36-MIGRATION-VALIDATION-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This template is used to document the validation results following data migration to UCMS. Complete for each migration phase (Pilot, Full, Incremental).

---

## MIGRATION VALIDATION REPORT

### SECTION A: MIGRATION EXECUTION SUMMARY

| Field | Details |
|-------|---------|
| Validation Report ID | MVR-UCMS-[PHASE]-[YYYY]-[###] |
| Migration Phase | □ Pilot □ Full □ Incremental □ Delta |
| Migration Date | DD/MM/YYYY |
| Migration Start Time | HH:MM |
| Migration End Time | HH:MM |
| Total Duration | _______ hours/minutes |
| Executed By | |
| Validated By | |

#### Migration Scope

| Source System | Entity/Table | Expected Records | Migrated Records | Status |
|---------------|--------------|------------------|------------------|--------|
| | | | | □ Pass □ Fail |
| | | | | □ Pass □ Fail |
| | | | | □ Pass □ Fail |
| | | | | □ Pass □ Fail |
| | | | | □ Pass □ Fail |

---

### SECTION B: ROW COUNT VALIDATION

#### B.1 Entity Count Comparison

| Entity | Source Count | Target Count | Difference | % Match | Status |
|--------|--------------|--------------|------------|---------|--------|
| APPLICANTS | | | | | □ Pass □ Fail |
| SERVICE_PROVIDERS | | | | | □ Pass □ Fail |
| USP_SCHEMES | | | | | □ Pass □ Fail |
| CLAIMS | | | | | □ Pass □ Fail |
| CLAIM_DETAILS | | | | | □ Pass □ Fail |
| PAYMENTS | | | | | □ Pass □ Fail |
| DOCUMENTS | | | | | □ Pass □ Fail |
| WORKFLOW_LOG | | | | | □ Pass □ Fail |
| USERS | | | | | □ Pass □ Fail |

#### B.2 Summary Statistics

| Metric | Source | Target | Variance | Acceptable | Status |
|--------|--------|--------|----------|------------|--------|
| Total Records | | | | ±0% | □ Pass □ Fail |
| Active Records | | | | < 1% | □ Pass □ Fail |
| Rejected Records | - | | | N/A | □ Info |

---

### SECTION C: DATA INTEGRITY VALIDATION

#### C.1 Primary Key Validation

| Entity | PK Column | Unique Count | Null Count | Duplicate Count | Status |
|--------|-----------|--------------|------------|-----------------|--------|
| | | | | | □ Pass □ Fail |
| | | | | | □ Pass □ Fail |
| | | | | | □ Pass □ Fail |
| | | | | | □ Pass □ Fail |

#### C.2 Foreign Key Validation

| Child Table | Parent Table | FK Column | Orphan Count | Status |
|-------------|--------------|-----------|--------------|--------|
| CLAIMS | APPLICANTS | applicant_id | | □ Pass □ Fail |
| CLAIMS | SERVICE_PROVIDERS | provider_id | | □ Pass □ Fail |
| CLAIM_DETAILS | CLAIMS | claim_id | | □ Pass □ Fail |
| PAYMENTS | CLAIMS | claim_id | | □ Pass □ Fail |
| WORKFLOW_LOG | CLAIMS | claim_id | | □ Pass □ Fail |
| DOCUMENTS | (Various) | entity_id | | □ Pass □ Fail |

#### C.3 Referential Integrity Summary

| Check Type | Total Checks | Passed | Failed | Pass Rate |
|------------|--------------|--------|--------|-----------|
| Primary Key Uniqueness | | | | |
| Foreign Key Validity | | | | |
| Check Constraints | | | | |
| Not Null Constraints | | | | |

---

### SECTION D: DATA SAMPLING VALIDATION

#### D.1 Random Sampling Results

| Sample ID | Entity | Sample Size | Records Validated | Issues Found | Status |
|-----------|--------|-------------|-------------------|--------------|--------|
| S001 | APPLICANTS | 1,000 | | | □ Pass □ Fail |
| S002 | CLAIMS | 1,000 | | | □ Pass □ Fail |
| S003 | PAYMENTS | 500 | | | □ Pass □ Fail |
| S004 | DOCUMENTS | 500 | | | □ Pass □ Fail |

#### D.2 Critical Record Validation

| Record Type | Selection Criteria | Records Checked | Issues Found | Status |
|-------------|-------------------|-----------------|--------------|--------|
| High-value claims | > RM 50,000 | | | □ Pass □ Fail |
| Recent claims | Last 30 days | | | □ Pass □ Fail |
| Flagged applicants | B40/Orang Asli | | | □ Pass □ Fail |
| Active providers | Status = Active | | | □ Pass □ Fail |

#### D.3 Sample Validation Details

| Check ID | Entity | Field | Validation Rule | Sample Size | Pass Count | Fail Count | Status |
|----------|--------|-------|-----------------|-------------|------------|------------|--------|
| V001 | APPLICANTS | ic_number | Valid format | 1000 | | | □ Pass □ Fail |
| V002 | APPLICANTS | email | Valid format | 1000 | | | □ Pass □ Fail |
| V003 | CLAIMS | claim_amount | > 0 | 1000 | | | □ Pass □ Fail |
| V004 | CLAIMS | claim_status | Valid values | 1000 | | | □ Pass □ Fail |
| V005 | PAYMENTS | payment_amount | > 0 | 500 | | | □ Pass □ Fail |

---

### SECTION E: AGGREGATION VALIDATION

#### E.1 Financial Totals Comparison

| Metric | Source Value | Target Value | Difference | % Variance | Status |
|--------|--------------|--------------|------------|------------|--------|
| Total Claim Amount | RM | RM | RM | | □ Pass □ Fail |
| Total Approved Amount | RM | RM | RM | | □ Pass □ Fail |
| Total Paid Amount | RM | RM | RM | | □ Pass □ Fail |
| Average Claim Amount | RM | RM | RM | | □ Pass □ Fail |
| Max Claim Amount | RM | RM | RM | | □ Pass □ Fail |
| Min Claim Amount | RM | RM | RM | | □ Pass □ Fail |

#### E.2 Count Aggregates Comparison

| Metric | Source Value | Target Value | Difference | % Variance | Status |
|--------|--------------|--------------|------------|------------|--------|
| Total Applicants | | | | | □ Pass □ Fail |
| Total Claims | | | | | □ Pass □ Fail |
| Total Payments | | | | | □ Pass □ Fail |
| Active Providers | | | | | □ Pass □ Fail |
| Pending Claims | | | | | □ Pass □ Fail |
| Approved Claims | | | | | □ Pass □ Fail |
| Rejected Claims | | | | | □ Pass □ Fail |

#### E.3 Grouped Validation

| Dimension | Group Value | Source Count | Target Count | Match | Status |
|-----------|-------------|--------------|--------------|-------|--------|
| State | Johor | | | □ Yes □ No | □ Pass □ Fail |
| State | Selangor | | | □ Yes □ No | □ Pass □ Fail |
| State | Sabah | | | □ Yes □ No | □ Pass □ Fail |
| State | Sarawak | | | □ Yes □ No | □ Pass □ Fail |
| Scheme | USP-BB | | | □ Yes □ No | □ Pass □ Pass |
| Year | 2024 | | | □ Yes □ No | □ Pass □ Fail |
| Status | Approved | | | □ Yes □ No | □ Pass □ Fail |

---

### SECTION F: CHECKSUM VALIDATION

#### F.1 Hash Comparison

| Entity | Source Checksum | Target Checksum | Match | Status |
|--------|-----------------|-----------------|-------|--------|
| APPLICANTS | | | □ Yes □ No | □ Pass □ Fail |
| CLAIMS | | | □ Yes □ No | □ Pass □ Fail |
| CLAIM_DETAILS | | | □ Yes □ No | □ Pass □ Fail |
| PAYMENTS | | | □ Yes □ No | □ Pass □ Fail |
| DOCUMENTS | | | □ Yes □ No | □ Pass □ Pass |

#### F.2 Row-Level Checksum Sampling

| Sample ID | Entity | Source Hash | Target Hash | Match | Status |
|-----------|--------|-------------|-------------|-------|--------|
| | | | | □ Yes □ No | □ Pass □ Fail |
| | | | | □ Yes □ No | □ Pass □ Fail |
| | | | | □ Yes □ No | □ Pass □ Fail |
| | | | | □ Yes □ No | □ Pass □ Fail |
| | | | | □ Yes □ No | □ Pass □ Fail |

---

### SECTION G: BUSINESS RULE VALIDATION

#### G.1 Rule Compliance Check

| Rule ID | Rule Description | Records Checked | Violations | Status |
|---------|------------------|-----------------|------------|--------|
| BR001 | IC number must be unique | | | □ Pass □ Fail |
| BR002 | Claim amount must be positive | | | □ Pass □ Fail |
| BR003 | Approved amount ≤ claim amount | | | □ Pass □ Fail |
| BR004 | Paid amount ≤ approved amount | | | □ Pass □ Fail |
| BR005 | Payment date ≥ claim date | | | □ Pass □ Fail |
| BR006 | Applicant must have valid status | | | □ Pass □ Fail |
| BR007 | Provider must be active for new claims | | | □ Pass □ Fail |
| BR008 | Document must link to valid entity | | | □ Pass □ Fail |

#### G.2 Cross-Field Validation

| Validation | Records Checked | Passed | Failed | Status |
|------------|-----------------|--------|--------|--------|
| Date consistency (created < modified) | | | | □ Pass □ Fail |
| Amount consistency (paid ≤ approved ≤ claimed) | | | | □ Pass □ Fail |
| Status flow validity | | | | □ Pass □ Fail |
| Geographic consistency (postcode matches state) | | | | □ Pass □ Fail |

---

### SECTION H: PERFORMANCE VALIDATION

#### H.1 Query Performance

| Query Type | Expected Time | Actual Time | Status |
|------------|---------------|-------------|--------|
| Simple lookup (by PK) | < 100ms | | □ Pass □ Fail |
| List query (100 records) | < 500ms | | □ Pass □ Fail |
| Search query | < 2s | | □ Pass □ Fail |
| Report query | < 10s | | □ Pass □ Fail |
| Aggregation query | < 5s | | □ Pass □ Fail |

#### H.2 Index Validation

| Table | Index Name | Status | Usage |
|-------|------------|--------|-------|
| | | □ Valid □ Invalid | |
| | | □ Valid □ Invalid | |
| | | □ Valid □ Invalid | |

---

### SECTION I: ISSUE LOG

#### I.1 Issues Identified

| Issue ID | Severity | Category | Description | Records Affected | Root Cause | Resolution | Status |
|----------|----------|----------|-------------|------------------|------------|------------|--------|
| | □ Critical □ High □ Medium □ Low | | | | | | □ Open □ Resolved |
| | □ Critical □ High □ Medium □ Low | | | | | | □ Open □ Resolved |
| | □ Critical □ High □ Medium □ Low | | | | | | □ Open □ Resolved |
| | □ Critical □ High □ Medium □ Low | | | | | | □ Open □ Resolved |
| | □ Critical □ High □ Medium □ Low | | | | | | □ Open □ Resolved |

#### I.2 Issue Summary by Severity

| Severity | Count | Resolved | Outstanding |
|----------|-------|----------|-------------|
| Critical | | | |
| High | | | |
| Medium | | | |
| Low | | | |
| **TOTAL** | | | |

---

### SECTION J: RECONCILIATION SUMMARY

#### J.1 Reconciliation Report

| Category | Source | Target | Difference | Explained | Unexplained | Status |
|----------|--------|--------|------------|-----------|-------------|--------|
| Record Count | | | | | | □ Pass □ Fail |
| Total Value | | | | | | □ Pass □ Pass |
| Active Records | | | | | | □ Pass □ Fail |
| Archived Records | | | | | | □ Pass □ Fail |

#### J.2 Variance Explanation

| Variance ID | Description | Amount/Count | Reason | Approved By |
|-------------|-------------|--------------|--------|-------------|
| | | | | |
| | | | | |
| | | | | |

---

### SECTION K: SIGN-OFF

#### K.1 Validation Results

| Overall Validation | Result |
|-------------------|--------|
| Row Count Validation | □ Pass □ Fail |
| Data Integrity Validation | □ Pass □ Fail |
| Sampling Validation | □ Pass □ Fail |
| Aggregation Validation | □ Pass □ Fail |
| Business Rule Validation | □ Pass □ Fail |
| **OVERALL STATUS** | □ **PASS** □ **FAIL** |

#### K.2 Go/No-Go Recommendation

| Recommendation | □ Go □ No-Go □ Go with Conditions |
|----------------|-------------------------------------|
| Conditions (if applicable) | |

#### K.3 Approvals

##### Validated By

| Field | Details |
|-------|---------|
| Name | |
| Designation | QA Lead |
| Signature | |
| Date | |

##### Reviewed By

| Field | Details |
|-------|---------|
| Name | |
| Designation | Data Architect |
| Signature | |
| Date | |

##### Approved By

| Field | Details |
|-------|---------|
| Name | |
| Designation | Project Manager |
| Signature | |
| Date | |

##### Business Sign-Off

| Field | Details |
|-------|---------|
| Name | |
| Designation | MCMC Representative |
| Signature | |
| Date | |

---

### SECTION L: APPENDICES

| Appendix | Description | Included |
|----------|-------------|----------|
| A | Detailed validation scripts | □ Yes □ No |
| B | Sampling detail reports | □ Yes □ No |
| C | Error log files | □ Yes □ No |
| D | Reconciliation worksheets | □ Yes □ No |
| E | Performance test results | □ Yes □ No |

---

**Confidentiality Notice:** This validation report contains sensitive migration data. Handle with appropriate care.

**Document Control:** Original - Project Office | Copy - Data Team | Copy - Business Team
