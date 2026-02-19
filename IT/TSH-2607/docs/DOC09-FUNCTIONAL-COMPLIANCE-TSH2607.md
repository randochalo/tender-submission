# DOC09: Functional Compliance Matrix
## TSH-2607 MCMC UCMS Tender

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Date:** February 2026

---

## 1. FUNCTIONAL REQUIREMENTS COMPLIANCE

### 1.1 Master Data Module Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-MD-01 | Create Project ID (4-tier hierarchy) | ✓ COMPLY | Annex T12, T13 |
| F-MD-02 | NOA/Contract management | ✓ COMPLY | Annex T14 |
| F-MD-03 | Variation Order tracking | ✓ COMPLY | Annex T15 |
| F-MD-04 | Cluster/Site ID generation | ✓ COMPLY | Annex T13 |
| F-MD-05 | Item ID definition | ✓ COMPLY | Annex T12 |
| F-MD-06 | Performance Bond management | ✓ COMPLY | Annex T16 |
| F-MD-07 | Technical Self-Declaration | ✓ COMPLY | Annex T12 |
| F-MD-08 | EOT processing | ✓ COMPLY | Annex T15 |
| F-MD-09 | Litigation tracking | ✓ COMPLY | Annex T12 |

### 1.2 User Management Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-UM-01 | Secure account creation | ✓ COMPLY | Annex T17 |
| F-UM-02 | Delegation with audit | ✓ COMPLY | Annex T17 |
| F-UM-03 | DUSP account maintenance | ✓ COMPLY | Annex T17 |
| F-UM-04 | Subcontractor accounts | ✓ COMPLY | Annex T17 |
| F-UM-05 | User lifecycle management | ✓ COMPLY | Annex T17 |
| F-UM-06 | RBAC matrix | ✓ COMPLY | Annex T18 |

### 1.3 Budget Module Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-BM-01 | Financial control enforcement | ✓ COMPLY | Annex T19 |
| F-BM-02 | Capped cost tracking | ✓ COMPLY | Annex T19 |
| F-BM-03 | Site costing | ✓ COMPLY | Annex T19 |
| F-BM-04 | BOQ management | ✓ COMPLY | Annex T19 |
| F-BM-05 | Cost component allocation | ✓ COMPLY | Annex T19 |

### 1.4 Claims Module Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-CM-01 | Invoice to MCMC (USPFS) | ✓ COMPLY | Annex T20 |
| F-CM-02 | CEO/Financial Declaration | ✓ COMPLY | Annex T20 |
| F-CM-03 | Advance/Quarterly claims | ✓ COMPLY | Annex T20 |
| F-CM-04 | Yearly claim processing | ✓ COMPLY | Annex T21 |
| F-CM-05 | Auditor's Declaration | ✓ COMPLY | Annex T21 |
| F-CM-06 | Auditor's Working Template | ✓ COMPLY | Annex T21 |
| F-CM-07 | Supporting documents | ✓ COMPLY | Annex T20 |

### 1.5 Payment Module Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-PM-01 | Payment memo templates | ✓ COMPLY | Annex T22 |
| F-PM-02 | Multi-layer approval (min 3) | ✓ COMPLY | Annex T22 |
| F-PM-03 | Digital signature integration | ✓ COMPLY | Annex T22 |
| F-PM-04 | Payment voucher generation | ✓ COMPLY | Annex T22 |
| F-PM-05 | DUSP notification letters | ✓ COMPLY | Annex T23 |

### 1.6 Reports Module Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-RM-01 | DUSP reports | ✓ COMPLY | Annex T24 |
| F-RM-02 | Subcontractor reports | ✓ COMPLY | Annex T24 |
| F-RM-03 | Payment reports | ✓ COMPLY | Annex T24 |
| F-RM-04 | Project progress reports | ✓ COMPLY | Annex T24 |
| F-RM-05 | Financial progress reports | ✓ COMPLY | Annex T24 |
| F-RM-06 | Budget reports | ✓ COMPLY | Annex T24 |
| F-RM-07 | Exception reports | ✓ COMPLY | Annex T24 |

### 1.7 Dashboard Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-DB-01 | Fund Position dashboard | ✓ COMPLY | Annex T25 |
| F-DB-02 | Project Delivery dashboard | ✓ COMPLY | Annex T25 |
| F-DB-03 | Payment Disbursement dashboard | ✓ COMPLY | Annex T25 |
| F-DB-04 | Compliance & Exception dashboard | ✓ COMPLY | Annex T25 |
| F-DB-05 | Integration & System dashboard | ✓ COMPLY | Annex T25 |
| F-DB-06 | Project & Site Monitoring dashboard | ✓ COMPLY | Annex T25 |
| F-DB-07 | Claims & Payment Status dashboard | ✓ COMPLY | Annex T25 |
| F-DB-08 | Budget Utilisation dashboard | ✓ COMPLY | Annex T25 |
| F-DB-09 | DUSP/Subcontractor Performance dashboard | ✓ COMPLY | Annex T25 |
| F-DB-10 | Security & Backup dashboard | ✓ COMPLY | Annex T25 |
| F-DB-11 | Exception & Workflow dashboard | ✓ COMPLY | Annex T25 |
| F-DB-12 | Dynamic Excel Export | ✓ COMPLY | Annex T25 |

### 1.8 Self-Service Functions

| Req ID | Functional Requirement | Response | Evidence |
|--------|------------------------|----------|----------|
| F-SS-01 | Claim submission portal | ✓ COMPLY | Annex T27 |
| F-SS-02 | Document upload | ✓ COMPLY | Annex T27 |
| F-SS-03 | Approval tracking | ✓ COMPLY | Annex T27 |
| F-SS-04 | Real-time notifications | ✓ COMPLY | Annex T27 |
| F-SS-05 | Guided workflows | ✓ COMPLY | Annex T27 |

---

## 2. NON-FUNCTIONAL REQUIREMENTS COMPLIANCE

| Category | Requirement | Response | Evidence |
|----------|-------------|----------|----------|
| Performance | < 2s response time | ✓ COMPLY | SRS-UCMS NFR-01 |
| Scalability | 500+ concurrent users | ✓ COMPLY | SRS-UCMS NFR-03 |
| Availability | 99.9% uptime | ✓ COMPLY | SRS-UCMS NFR-02 |
| Security | AES-256, TLS 1.3 | ✓ COMPLY | Annex T31 |
| Audit | 7-year retention | ✓ COMPLY | Annex T26 |

---

## 3. CERTIFICATION

We confirm full functional compliance with all requirements specified in the tender document.

**Authorized Signatory:** _______________________

**Date:** _______________________

---

*This Functional Compliance Matrix is part of TSH-2607 tender submission.*
