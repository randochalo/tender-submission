# DOC35-CLEANSING-REPORT-TSH2607.md
# Data Cleansing Report Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC35-CLEANSING-REPORT-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This template is used to document data cleansing activities performed during the UCMS data migration. Complete a separate report for each source system or major cleansing activity.

---

## DATA CLEANSING REPORT

### SECTION A: EXECUTIVE SUMMARY

| Field | Details |
|-------|---------|
| Report Reference | DCR-UCMS-[SRC]-[YYYY]-[###] |
| Source System | |
| Cleansing Period | DD/MM/YYYY to DD/MM/YYYY |
| Data Analyst | |
| Reviewed By | |
| Approved By | |

#### Summary Statistics

| Metric | Before Cleansing | After Cleansing | Improvement |
|--------|------------------|-----------------|-------------|
| Total Records | | | |
| Complete Records | | | |
| Completeness % | | | |
| Valid Records | | | |
| Validity % | | | |
| Unique Records | | | |
| Duplicate % | | | |
| Consistent Records | | | |
| Consistency % | | | |

---

### SECTION B: SOURCE DATA PROFILE

#### B.1 Source Information

| Field | Details |
|-------|---------|
| Source System Name | |
| Source Type | □ Database □ File □ API □ Other |
| Platform/Format | |
| Extraction Date | DD/MM/YYYY |
| Record Count | |
| File Size | _______ MB/GB |
| Extraction Method | |

#### B.2 Data Structure

| Column Name | Data Type | Sample Value | Null Count | Null % |
|-------------|-----------|--------------|------------|--------|
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |

---

### SECTION C: DATA QUALITY ISSUES IDENTIFIED

#### C.1 Issue Summary

| Issue ID | Issue Category | Severity | Record Count | % of Total |
|----------|----------------|----------|--------------|------------|
| | □ Completeness □ Validity □ Consistency □ Uniqueness □ Timeliness | □ High □ Medium □ Low | | |
| | □ Completeness □ Validity □ Consistency □ Uniqueness □ Timeliness | □ High □ Medium □ Low | | |
| | □ Completeness □ Validity □ Consistency □ Uniqueness □ Timeliness | □ High □ Medium □ Low | | |
| | □ Completeness □ Validity □ Consistency □ Uniqueness □ Timeliness | □ High □ Medium □ Low | | |
| | □ Completeness □ Validity □ Consistency □ Uniqueness □ Timeliness | □ High □ Medium □ Low | | |

#### C.2 Detailed Issue Descriptions

##### Issue 1: [Description]

| Attribute | Details |
|-----------|---------|
| Issue ID | DQ001 |
| Category | |
| Description | |
| Affected Table | |
| Affected Column(s) | |
| Root Cause | |
| Sample Values | |
| Business Impact | |

##### Issue 2: [Description]

| Attribute | Details |
|-----------|---------|
| Issue ID | DQ002 |
| Category | |
| Description | |
| Affected Table | |
| Affected Column(s) | |
| Root Cause | |
| Sample Values | |
| Business Impact | |

##### Issue 3: [Description]

| Attribute | Details |
|-----------|---------|
| Issue ID | DQ003 |
| Category | |
| Description | |
| Affected Table | |
| Affected Column(s) | |
| Root Cause | |
| Sample Values | |
| Business Impact | |

---

### SECTION D: CLEANSING ACTIVITIES

#### D.1 Completeness Cleansing

| # | Activity | Rule/Logic | Records Affected | Automated/Manual |
|---|----------|------------|------------------|------------------|
| 1 | | | | □ Auto □ Manual |
| 2 | | | | □ Auto □ Manual |
| 3 | | | | □ Auto □ Manual |
| 4 | | | | □ Auto □ Manual |
| 5 | | | | □ Auto □ Manual |

#### D.2 Validity Cleansing

| # | Activity | Rule/Logic | Records Affected | Automated/Manual |
|---|----------|------------|------------------|------------------|
| 1 | | | | □ Auto □ Manual |
| 2 | | | | □ Auto □ Manual |
| 3 | | | | □ Auto □ Manual |
| 4 | | | | □ Auto □ Manual |
| 5 | | | | □ Auto □ Manual |

#### D.3 Consistency Cleansing

| # | Activity | Rule/Logic | Records Affected | Automated/Manual |
|---|----------|------------|------------------|------------------|
| 1 | | | | □ Auto □ Manual |
| 2 | | | | □ Auto □ Manual |
| 3 | | | | □ Auto □ Manual |
| 4 | | | | □ Auto □ Manual |
| 5 | | | | □ Auto □ Manual |

#### D.4 Uniqueness Cleansing (Deduplication)

| # | Activity | Matching Rule | Duplicates Found | Action Taken |
|---|----------|---------------|------------------|--------------|
| 1 | | | | □ Merged □ Deleted □ Flagged |
| 2 | | | | □ Merged □ Deleted □ Flagged |
| 3 | | | | □ Merged □ Deleted □ Flagged |
| 4 | | | | □ Merged □ Deleted □ Flagged |
| 5 | | | | □ Merged □ Deleted □ Flagged |

#### D.5 Standardization Activities

| Column | Original Format | Standardized Format | Example |
|--------|-----------------|---------------------|---------|
| | | | |
| | | | |
| | | | |
| | | | |

---

### SECTION E: CLEANSING TRANSFORMATIONS

#### E.1 Transformation Rules Applied

| Rule ID | Description | Input Pattern | Output Pattern | Records Changed |
|---------|-------------|---------------|----------------|-----------------|
| T001 | | | | |
| T002 | | | | |
| T003 | | | | |
| T004 | | | | |
| T005 | | | | |

#### E.2 Data Enrichment

| # | Enrichment Activity | Source | Records Enriched |
|---|---------------------|--------|------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

### SECTION F: REJECTED RECORDS

#### F.1 Rejection Summary

| Rejection Category | Count | % of Total | Disposition |
|--------------------|-------|------------|-------------|
| Critical data missing | | | □ Deleted □ Quarantined |
| Invalid format | | | □ Deleted □ Quarantined |
| Failed validation | | | □ Deleted □ Quarantined |
| Duplicate records | | | □ Deleted □ Quarantined |
| Business rule violation | | | □ Deleted □ Quarantined |
| **TOTAL REJECTED** | | | |

#### F.2 Rejected Record Details

| Record ID | Rejection Reason | Rejection Category | Action Taken | Reviewed By |
|-----------|------------------|--------------------|--------------|-------------|
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |

---

### SECTION G: DATA QUALITY METRICS

#### G.1 Before vs After Comparison

| Dimension | Metric | Before | After | Target | Status |
|-----------|--------|--------|-------|--------|--------|
| Completeness | % of populated fields | | | 95% | □ Met □ Not Met |
| Validity | % of valid values | | | 98% | □ Met □ Not Met |
| Consistency | % of consistent records | | | 95% | □ Met □ Not Met |
| Uniqueness | % of unique records | | | 99% | □ Met □ Not Met |
| Timeliness | % of current records | | | 95% | □ Met □ Not Met |
| Accuracy | Error rate | | | < 1% | □ Met □ Not Met |

#### G.2 Column-Level Quality Scores

| Column | Completeness | Validity | Consistency | Overall Score |
|--------|--------------|----------|-------------|---------------|
| | | | | |
| | | | | |
| | | | | |
| | | | | |
| | | | | |

---

### SECTION H: CLEANSING SCRIPTS AND TOOLS

#### H.1 Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| | | |
| | | |
| | | |

#### H.2 Scripts/Queries

| Script Name | Purpose | Location | Execution Time |
|-------------|---------|----------|----------------|
| | | | |
| | | | |
| | | | |

---

### SECTION I: EXCEPTIONS AND APPROVALS

#### I.1 Approved Exceptions

| Exception ID | Description | Business Justification | Approved By | Date |
|--------------|-------------|------------------------|-------------|------|
| | | | | |
| | | | | |
| | | | | |

#### I.2 Known Issues (Accepted)

| Issue ID | Description | Impact | Mitigation | Approved By |
|----------|-------------|--------|------------|-------------|
| | | | | |
| | | | | |
| | | | | |

---

### SECTION J: RECOMMENDATIONS

| # | Recommendation | Priority | Owner | Timeline |
|---|----------------|----------|-------|----------|
| 1 | | □ High □ Medium □ Low | | |
| 2 | | □ High □ Medium □ Low | | |
| 3 | | □ High □ Medium □ Low | | |
| 4 | | □ High □ Medium □ Low | | |
| 5 | | □ High □ Medium □ Low | | |

---

### SECTION K: APPROVALS

#### Prepared By

| Field | Details |
|-------|---------|
| Name | |
| Designation | Data Analyst |
| Signature | |
| Date | |

#### Reviewed By

| Field | Details |
|-------|---------|
| Name | |
| Designation | Data Architect |
| Signature | |
| Date | |

#### Approved By

| Field | Details |
|-------|---------|
| Name | |
| Designation | Project Manager |
| Signature | |
| Date | |

---

### SECTION L: APPENDICES

| Appendix | Description | Included |
|----------|-------------|----------|
| A | Detailed data profiling results | □ Yes □ No |
| B | Sample records before/after | □ Yes □ No |
| C | Cleansing scripts/queries | □ Yes □ No |
| D | Rejected records file | □ Yes □ No |
| E | Data quality dashboard screenshots | □ Yes □ No |

---

## MASTER CLEANSING TRACKER

*For tracking all cleansing activities across sources*

| Source | Records | Completeness Before | Completeness After | Status | Approved |
|--------|---------|---------------------|--------------------|--------|----------|
| | | | | | □ Yes □ No |
| | | | | | □ Yes □ No |
| | | | | | □ Yes □ No |
| | | | | | □ Yes □ No |

---

**Confidentiality Notice:** This report contains data quality metrics that may be sensitive. Handle with appropriate care.

**Document Control:** Original - Project Office | Copy - Data Team | Copy - Business Team
