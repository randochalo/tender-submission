# APPENDIX G: DETAILED COMPLIANCE MATRIX
## TSH-2607 MCMC UCMS Tender

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Date:** February 2026  

---

## G.1 COMPLIANCE OVERVIEW

This appendix provides a detailed cross-reference matrix of all tender requirements against our proposed solution deliverables.

| Section | Total Requirements | Fully Compliant | Partially Compliant | Noted | Compliance % |
|---------|-------------------|-----------------|---------------------|-------|--------------|
| 40 (Background) | 4 | 4 | 0 | 0 | 100% |
| 41.1.1 (System Analysis) | 5 | 5 | 0 | 0 | 100% |
| 41.1.2 (Agile Development) | 5 | 5 | 0 | 0 | 100% |
| 41.1.3 (System Modules) | 68 | 68 | 0 | 0 | 100% |
| 41.1.4-41.1.15 (Technical) | 15 | 15 | 0 | 0 | 100% |
| 42-50 (Other Requirements) | 11 | 10 | 0 | 1 | 99% |
| **TOTAL** | **108** | **107** | **0** | **1** | **99.1%** |

---

## G.2 REQUIREMENT-TO-DELIVERABLE MAPPING

### Section 40: Background

| Para | Requirement Summary | Our Solution | Deliverable Reference |
|------|---------------------|--------------|----------------------|
| 40.1 | Multi-stakeholder management | RBAC for MCMC internal + DUSP/contractor | Annex T17, T18 |
| 40.2 | Oracle + Digital Signature + RPA + OCR | Oracle 19c/21c + MSC TrustSign + UiPath + Tesseract/AWS Textract | Annex T1, T2 |
| 40.3 | UCMS overview diagram | Web frontend + Oracle middleware + USPFS API | Annex T2 |
| 40.4 | Single customer-facing portal | Responsive web app with SSO + full lifecycle | Annex T3 |

### Section 41.1.1: System Analysis & Design

| Para | Requirement Summary | Our Solution | Deliverable Reference |
|------|---------------------|--------------|----------------------|
| 41.1.1.a | Requirements workshops | JAD sessions with dedicated BA (5+ years) | Annex T4 |
| 41.1.1.b | Process flowcharts | BPMN 2.0 diagrams for all 10 modules | Annex T5 |
| 41.1.1.c | SRS and SDD | KRISA-compliant SRS/SDD with traceability | Annex T6 |
| 41.1.1.d | System architecture | Microservices on OCI with Docker/K8s | Annex T2 |
| 41.1.1.e | Approval workflows | Configurable 3-layer workflows + React/Angular UI | Annex T7 |

### Section 41.1.2: System Development (Agile)

| Para | Requirement Summary | Our Solution | Deliverable Reference |
|------|---------------------|--------------|----------------------|
| 41.1.2.a | Agile methodology | SCRUM with 2-week sprints | Annex T8 |
| 41.1.2.b | Sprint reviews with MCMC | Bi-weekly demos + retrospectives | Annex T8 |
| 41.1.2.c | Requirements traceability | JIRA linking stories to acceptance criteria | Annex T9 |
| 41.1.2.d | Efficiency targets | 70% manual reduction, 99.5% accuracy | Annex T10 |
| 41.1.2.e | Bilingual support | i18n EN/BM with Malaysian formats | Annex T11 |

### Section 41.1.3: System Modules

#### Master Data Module (41.1.3.1)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.1.a-d | Centralized framework | Master data hub with USPFS sync | T12 |
| 41.1.3.1.d.i | Project ID creation | 4-tier hierarchy (Project→Sub-Project→Cluster→Site) | T13 |
| 41.1.3.1.d.ii | NOA/Contract management | NOA recording + OCR extraction | T14 |
| 41.1.3.1.d.iii | VO tracking | Scope/cost/timeline tracking | T15 |
| 41.1.3.1.d.iv-vi | ID Management | Cluster, Site, Item ID generation | T13 |
| 41.1.3.1.d.vii | Performance Bonds | Automated monitoring + USPFS validation | T16 |
| 41.1.3.1.d.viii-x | Declarations & Tracking | Technical Self-Declaration, EOT, Litigation | - |

#### User Management Module (41.1.3.2)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.2.xi | Account Creation & Delegation | RBAC + MFA + audit logs | T17 |
| 41.1.3.2.xii | DUSP Account Maintenance | Profile + bank + personnel management | - |
| 41.1.3.2.xiii | Subcontractor Accounts | Unique ID + invoice capture | - |
| 41.1.3.2.xiv | User Lifecycle Management | Create/update/suspend/terminate | - |
| 41.1.3.2.xv | RBAC Matrix | Comprehensive permissions matrix | T18 |

#### Budget Module (41.1.3.3)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.3.a-d | Budget framework | Oracle EBS integration + variance monitoring | T19 |
| 41.1.3.3.d.i | Financial Control | Capped cost vs expenditure validation | - |
| 41.1.3.3.d.ii | Capped Cost | USPFS validation + alerts | - |
| 41.1.3.3.d.iii | Site Costing | Detailed site-level capture | - |
| 41.1.3.3.d.iv | BOQ | Itemized maintenance + validation | - |
| 41.1.3.3.d.v | Cost Components | Preliminaries, CME, Software, Shared | - |

#### Claims Module (41.1.3.4)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.4.a-d | Claims processing | Rule-based validation + milestone verification | T20 |
| 41.1.3.4.d.i | Invoice to MCMC | Submission ID + USPFS integration | - |
| 41.1.3.4.d.ii | CEO Declaration | Capture + approval workflows | - |
| 41.1.3.4.d.iii | Multi-type claims | Advance/Quarterly/Major Contributor | - |
| 41.1.3.4.d.iv | Yearly Claim | Subsidiary ledger + auditor template | T21 |
| 41.1.3.4.d.v-vi | Auditor Documents | Declaration + Working Template | - |
| 41.1.3.4.d.vii | Supporting Documents | POs, invoices, receipts management | - |

#### Payment Module (41.1.3.5)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.5.a-d | Payment processing | Digital signatures + Oracle voucher | T22 |
| 41.1.3.5.d.i | Payment Requisition | Configurable templates | - |
| 41.1.3.5.d.ii | Multi-layer approval | Minimum 3 layers + digital signature | - |
| 41.1.3.5.d.iii | Payment Voucher | USPFS integration | - |
| 41.1.3.5.d.iv | DUSP Letter | Acknowledgement template + API | T23 |

#### Reports & Dashboards (41.1.3.6-7)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.6.a-d | Reporting module | Real-time dashboards + RPA detection | T24 |
| 41.1.3.6.d.i-vii | Report Types | DUSP, Subcontractor, Payment, Progress, Financial, Budget, Exception | T24 |
| 41.1.3.7.a-b | Dashboard function | RPA-powered multi-source dashboards | T25 |
| 41.1.3.7.b.i-xii | 12 Dashboard Types | Fund, Project, Payment, Compliance, Integration, Monitoring, Claims, Budget, Performance, Security, Exception, Excel Export | T25 |

#### Other Modules (41.1.3.8-10)

| Sub-Para | Requirement | Solution Component | Reference |
|----------|-------------|-------------------|-----------|
| 41.1.3.8.a-f | Audit Trail | Immutable timestamped logging | T26 |
| 41.1.3.9.a-f | Self-Service Portal | Role-based portal with guided workflows | T27 |
| 41.1.3.10.a-g | Value-Added Functions | AI/ML analytics + RPA automation | T28 |

### Section 41.1.4-41.1.15: Technical Requirements

| Para | Requirement Summary | Our Solution | Reference |
|------|---------------------|--------------|-----------|
| 41.1.4.a-c | System Integration | REST APIs + Azure AD SSO + Digital Signature + Encryption | T29-T31 |
| 41.1.5.a-j | AI/ML Document Validation | OCR + fraud/tampering detection | T30 |
| 41.1.6.a | Security & Compliance | AES-256 + TLS 1.3 + RBAC | T31 |
| 41.1.7.a-c | Testing (UAT/FAT/SIT) | 3-phase testing with MCMC | T32 |
| 41.1.8.a-d | Penetration Testing | CREST/OWASP certified | T33 |
| 41.1.9.a-c | Change Management | CAB process + documentation | T34 |
| 41.1.10.a-b | Deployment | Phased zero-downtime deployment | T35 |
| 41.1.11.a-c | Documentation | Technical docs + manuals + training | T36 |
| 41.1.12.a-c | Backup & Recovery | Daily/weekly/monthly/yearly backup | T37 |
| 41.1.13.a-e | Training | Manuals + materials + hands-on sessions | T38 |
| 41.1.14.a-f | License Management | Oracle + middleware + 250 users | T39 |
| 41.1.15.a-c | Post-Implementation Support | 48-month support + Resident Engineer | T40 |

### Section 42-50: Other Requirements

| Para | Requirement Summary | Our Solution | Reference |
|------|---------------------|--------------|-----------|
| 42.1 | Progress meetings | Weekly sprint + monthly steering | - |
| 42.2 | Dedicated PM | PMP/PRINCE2 certified | Annex H |
| 43.1-43.3 | Key personnel | All 7 roles with qualifications | Annex H |
| 44.1 | Equipment supply | At our cost | - |
| 45.1 | Past experience | 5-year references | Annex H |
| 46.1-46.3 | Reports & documentation | Per timelines | - |
| 47.1-47.2 | 67-month duration | 16 dev + 3 test + 12 warranty + 36 support | T41 |
| 48.1-48.3 | Price indication | RM3.5M noted (reference only) | Appendix D |
| 49.1-49.2 | IP assignment | Full transfer upon CFA | - |
| 50.1-50.2 | Standby availability | Ad-hoc support + comprehensive quote | Appendix D |

---

## G.3 ANNEX CROSS-REFERENCE

| Annex | Description | Sections Covered |
|-------|-------------|------------------|
| T1 | Architecture Diagram | 40.2 |
| T2 | System Architecture | 40.2-40.3, 41.1.1.d |
| T3 | Portal Interface Mockups | 40.4 |
| T4 | Requirements Methodology | 41.1.1.a |
| T5 | Sample Process Flowcharts | 41.1.1.b |
| T6 | SRS/SDD Templates | 41.1.1.c |
| T7 | Workflow Configurations | 41.1.1.e, 41.1.3.5 |
| T8 | Agile Project Plan | 41.1.2.a-b |
| T9 | Traceability Matrix | 41.1.2.c |
| T10 | Efficiency Metrics | 41.1.2.d |
| T11 | Bilingual Interface Samples | 41.1.2.e |
| T12 | Master Data Architecture | 41.1.3.1 |
| T13 | ID Structure Diagram | 41.1.3.1.d.i, iv-vi |
| T14 | NOA Workflow | 41.1.3.1.d.ii |
| T15 | VO Process Flow | 41.1.3.1.d.iii |
| T16 | Bond Management Screen | 41.1.3.1.d.vii |
| T17 | User Management Module | 41.1.3.2.xi |
| T18 | RBAC Matrix | 41.1.3.2.xv |
| T19 | Budget Module Design | 41.1.3.3 |
| T20 | Claims Workflow | 41.1.3.4.a-d |
| T21 | Yearly Claim Template | 41.1.3.4.d.iv |
| T22 | Payment Workflow | 41.1.3.5.a-d |
| T23 | Letter Templates | 41.1.3.5.d.iv |
| T24 | Report Catalog | 41.1.3.6 |
| T25 | Dashboard Designs | 41.1.3.7 |
| T26 | Audit Trail Design | 41.1.3.8 |
| T27 | Self-Service Portal | 41.1.3.9 |
| T28 | Value-Added Features | 41.1.3.10 |
| T29 | Integration Architecture | 41.1.4 |
| T30 | AI/ML Architecture | 41.1.5 |
| T31 | Security Framework | 41.1.6 |
| T32 | Testing Strategy | 41.1.7 |
| T33 | VAPT Plan | 41.1.8 |
| T34 | Change Management Plan | 41.1.9 |
| T35 | Deployment Plan | 41.1.10 |
| T36 | Documentation Plan | 41.1.11 |
| T37 | Backup & Recovery Plan | 41.1.12 |
| T38 | Training Plan | 41.1.13 |
| T39 | License Schedule | 41.1.14 |
| T40 | Support Plan | 41.1.15 |
| T41 | Project Timeline | 47.1-47.2 |
| H | Personnel CVs & Experience | 42.2, 43.1-43.3, 45.1 |
| D | Financial Proposal | 48.1-48.3, 50.2 |

---

## G.4 COMPLIANCE CERTIFICATION

**We hereby certify that:**

1. All requirements specified in the tender document have been thoroughly reviewed
2. Our proposed solution achieves **99.1% compliance** (107 of 108 requirements fully compliant)
3. The single "NOTED" item (Section 48 - Indicative Price) is acknowledged as reference only
4. All supporting documentation referenced in this matrix is authentic and available
5. We are fully capable of delivering the solution as specified

**Authorized Signatory:**

_______________________________  
Name: _________________________  
Title: ________________________  
Date: _________________________  
Company Stamp:

---

*Appendix G - Detailed Compliance Matrix for TSH-2607*  
*This document supplements the main COMPLIANCE-TECHNICAL-SCHEDULE.md*
