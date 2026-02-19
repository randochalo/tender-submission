# DOCUMENT 08: TECHNICAL COMPLIANCE MATRIX

## TSH-2607: USP Claims Management System (UCMS)
### Tender Reference: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

---

## TECHNICAL REQUIREMENTS COMPLIANCE STATEMENT

This document provides a detailed matrix demonstrating our compliance with all technical requirements specified in the Tender Document Section 5. Each requirement is mapped to our proposed solution with relevant evidence references.

---

## SECTION 40: BACKGROUND & OVERVIEW

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 40.1 | System for multi-stakeholder USP project management | **COMPLY** | Role-based architecture supporting 60 internal + 190 external users with segregated access controls | Annex T17, T18 |
| 40.2 | Oracle-based with Digital Signature, RPA, OCR | **COMPLY** | Oracle 19c database, Oracle WebLogic, MSC TrustSign/Docusign, UiPath RPA, AWS Textract OCR | Annex T2, T29, T31 |
| 40.3 | High-level architecture diagram submission | **COMPLY** | Comprehensive system architecture with 4-tier design (Presentation, Application, Data, Integration) | Annex T1, T2 |
| 40.4 | Single customer-facing digital gateway | **COMPLY** | Responsive web portal integrated with MCMC website via secure APIs with SSO | Annex T3, T27 |

---

## SECTION 41.1.1: SYSTEM ANALYSIS & DESIGN

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.1.a | Requirements gathering workshops | **COMPLY** | JAD sessions with structured workshops, documented outcomes, stakeholder sign-off | Annex T4 |
| 41.1.1.b | Process flowcharts (swimlane) | **COMPLY** | BPMN 2.0 swimlane diagrams for all 10 modules, validated with MCMC | Annex T5 |
| 41.1.1.c | SRS and SDD development | **COMPLY** | KRISA-compliant SRS/SDD with full traceability matrix and design rationale | Annex T6, T9 |
| 41.1.1.d | System architecture design | **COMPLY** | Microservices architecture on Oracle Cloud with horizontal scaling capability | Annex T2 |
| 41.1.1.e | Approval workflows & UI design | **COMPLY** | Configurable workflow engine with drag-and-drop designer, responsive React UI | Annex T7 |

---

## SECTION 41.1.2: SYSTEM DEVELOPMENT (AGILE)

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.2.a | Agile methodology with sprints | **COMPLY** | SCRUM with 2-week sprints, sprint ceremonies, velocity tracking | Annex T8 |
| 41.1.2.b | Sprint planning & reviews with MCMC | **COMPLY** | Bi-weekly sprint demos, MCMC stakeholder participation, feedback incorporation | Annex T8 |
| 41.1.2.c | Requirements traceability | **COMPLY** | JIRA/Azure DevOps linking user stories to acceptance criteria, automated reports | Annex T9 |
| 41.1.2.d | Processing efficiency improvements | **COMPLY** | 70% manual workload reduction, 99.5% data accuracy, full audit transparency | Annex T10 |
| 41.1.2.e | Bilingual support (BM & English) | **COMPLY** | Complete i18n implementation with language toggle, Malaysian formats | Annex T11 |

---

## SECTION 41.1.3: SYSTEM MODULES

### MODULE 1: MASTER DATA

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.1.a | Centralized framework | **COMPLY** | Oracle-based master data hub with governance workflows | Annex T12 |
| 41.1.3.1.b | Data ownership & validation | **COMPLY** | Role-based data ownership with configurable validation rules engine | Annex T12 |
| 41.1.3.1.c | Validation rules integration | **COMPLY** | Rule engine with 50+ configurable validation rules | Annex T12 |
| 41.1.3.1.d | USPFS integration | **COMPLY** | Real-time API synchronization with USPFS/Oracle EBS | Annex T29 |
| 41.1.3.1.d.i | Project ID creation | **COMPLY** | 4-tier hierarchical ID structure (Project→Sub-Project→Cluster→Site) | Annex T13 |
| 41.1.3.1.d.ii | NOA/Contract management | **COMPLY** | Automated NOA recording with USPFS validation, contract OCR extraction | Annex T14 |
| 41.1.3.1.d.iii | Variation Order tracking | **COMPLY** | VO ID with scope/cost/timeline tracking, USPFS-linked validation | Annex T15 |
| 41.1.3.1.d.iv | Cluster ID generation | **COMPLY** | Unique Cluster ID with consolidated claims tracking | Annex T13 |
| 41.1.3.1.d.v | Site ID management | **COMPLY** | Site identifiers with activity tracking and roll-up reporting | Annex T13 |
| 41.1.3.1.d.vi | Item ID definition | **COMPLY** | Deliverable/billable unit definition with budget allocation | Annex T12 |
| 41.1.3.1.d.vii | Performance Bonds | **COMPLY** | Bond recording with automated expiration/EOT/renewal monitoring | Annex T16 |
| 41.1.3.1.d.viii | Technical Self Declaration | **COMPLY** | DUSP declaration capture with NOA milestone validation | Annex T12 |
| 41.1.3.1.d.ix | Extension of Time (EOT) | **COMPLY** | EOT ID creation with structured approval workflows | Annex T12 |
| 41.1.3.1.d.x | Litigation tracking | **COMPLY** | Legal dispute recording with status tracking and risk reporting | Annex T12 |

### MODULE 2: DUSP, SUBCONTRACTORS & USER MANAGEMENT

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.2.xi | Secure Account Creation | **COMPLY** | MFA-enabled provisioning with audit logging | Annex T17 |
| 41.1.3.2.xii | DUSP Account Maintenance | **COMPLY** | Profile management with USPFS integration for payments | Annex T17 |
| 41.1.3.2.xiii | Subcontractor Account | **COMPLY** | Unique subcontractor ID with invoice capture | Annex T17 |
| 41.1.3.2.xiv | User Account Maintenance | **COMPLY** | Full lifecycle management with workflow continuity | Annex T17 |
| 41.1.3.2.xv | User Matrix | **COMPLY** | Comprehensive RBAC with segregation of duties | Annex T18 |

### MODULE 3: BUDGET MANAGEMENT

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.3.a | Approved budget management | **COMPLY** | Budget hub with Oracle EBS integration | Annex T19 |
| 41.1.3.3.b | Capped cost management | **COMPLY** | Automated variance monitoring with alerts | Annex T19 |
| 41.1.3.3.c | Site costing & BOQ | **COMPLY** | Detailed site-level cost capture with reconciliation | Annex T19 |
| 41.1.3.3.d | USPFS integration | **COMPLY** | Real-time synchronization with financial controls | Annex T19 |
| 41.1.3.3.d.i | Financial Control | **COMPLY** | Automated control enforcement with milestone tracking | Annex T19 |
| 41.1.3.3.d.ii | Approved Capped Cost | **COMPLY** | Validation against USPFS with limit alerts | Annex T19 |
| 41.1.3.3.d.iii | Site Costing | **COMPLY** | Detailed cost capture with ledger reconciliation | Annex T19 |
| 41.1.3.3.d.iv | Bill of Quantity | **COMPLY** | Itemized BOQ with claim validation | Annex T19 |
| 41.1.3.3.d.v | Cost Component | **COMPLY** | Standardized category tracking with allocation | Annex T19 |

### MODULE 4: CLAIMS MANAGEMENT

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.4.a | Major contributor claims | **COMPLY** | Automated processing with milestone verification | Annex T20 |
| 41.1.3.4.b | Advance claims processing | **COMPLY** | Oracle/banking integration for advance handling | Annex T20 |
| 41.1.3.4.c | Quarterly claims | **COMPLY** | Consolidated reporting with bond safeguards | Annex T20 |
| 41.1.3.4.d | Yearly claims with audit | **COMPLY** | Subsidiary ledger with auditor templates | Annex T21 |
| 41.1.3.4.d.i | Invoice to MCMC | **COMPLY** | Submission ID with USPFS reconciliation | Annex T20 |
| 41.1.3.4.d.ii | CEO Declaration | **COMPLY** | Authenticated declaration capture | Annex T20 |
| 41.1.3.4.d.iii | Claim processing types | **COMPLY** | Contractual validation with advance recovery | Annex T20 |
| 41.1.3.4.d.iv | Yearly Claim | **COMPLY** | Auditor template with EOT letter generation | Annex T21 |
| 41.1.3.4.d.v | Auditors' Declaration | **COMPLY** | Independent verification capture | Annex T20 |
| 41.1.3.4.d.vi | Auditors' Template | **COMPLY** | Standardized template with claim linkage | Annex T21 |
| 41.1.3.4.d.vii | Supporting Documents | **COMPLY** | Secure upload with validation and archival | Annex T20 |

### MODULE 5: PAYMENT PROCESSING

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.5.a | Memo-based approvals | **COMPLY** | Configurable memo templates with routing | Annex T22 |
| 41.1.3.5.b | Multi-layer approval | **COMPLY** | Minimum 3-layer workflow with digital signatures | Annex T22 |
| 41.1.3.5.c | Voucher generation | **COMPLY** | Automated posting to Oracle EBS | Annex T22 |
| 41.1.3.5.d | USPFS integration | **COMPLY** | Real-time reconciliation and status tracking | Annex T22 |
| 41.1.3.5.d.i | Payment Requisition | **COMPLY** | Configurable templates for all claim types | Annex T22 |
| 41.1.3.5.d.ii | Digital Signature Approval | **COMPLY** | Multi-layer approval with secure authentication | Annex T22 |
| 41.1.3.5.d.iii | Payment Voucher | **COMPLY** | USPFS integration with secure archival | Annex T22 |
| 41.1.3.5.d.iv | DUSP Letter | **COMPLY** | Built-in template with payment advice extraction | Annex T23 |

### MODULE 6: REPORTS

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.6.a | Operational reporting | **COMPLY** | Day-to-day operational metrics and KPIs | Annex T24 |
| 41.1.3.6.b | Financial reporting | **COMPLY** | Fund utilization and budget reports | Annex T24 |
| 41.1.3.6.c | Management reporting | **COMPLY** | Executive dashboards and summary reports | Annex T24 |
| 41.1.3.6.d | Exception reporting | **COMPLY** | RPA-powered anomaly detection reports | Annex T24 |
| 41.1.3.6.d.i | DUSP Reports | **COMPLY** | Financial and performance reports | Annex T24 |
| 41.1.3.6.d.ii | Subcontractor Reports | **COMPLY** | Performance and invoice breakdowns | Annex T24 |
| 41.1.3.6.d.iii | Payment Reports | **COMPLY** | Approved/executed payment tracking | Annex T24 |
| 41.1.3.6.d.iv | Project Progress | **COMPLY** | Status and milestone completion | Annex T24 |
| 41.1.3.6.d.v | Financial Progress | **COMPLY** | Fund utilization and performance | Annex T24 |
| 41.1.3.6.d.vi | Budget Reports | **COMPLY** | Allocation, usage, and forecast | Annex T24 |
| 41.1.3.6.d.vii | Exception Reports | **COMPLY** | Anomaly detection and escalation | Annex T24 |

### MODULE 7: DASHBOARD FUNCTION

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.7.a | Real-time operational view | **COMPLY** | Live operational metrics dashboard | Annex T25 |
| 41.1.3.7.b | RPA consolidation | **COMPLY** | RPA-powered multi-source data aggregation | Annex T25 |
| 41.1.3.7.b.i | Fund Position Dashboard | **COMPLY** | Real-time fund status and projections | Annex T25 |
| 41.1.3.7.b.ii | Project Delivery Dashboard | **COMPLY** | Project progress and milestone tracking | Annex T25 |
| 41.1.3.7.b.iii | Payment Disbursement Dashboard | **COMPLY** | Payment status and reconciliation | Annex T25 |
| 41.1.3.7.b.iv | Compliance & Exception Dashboard | **COMPLY** | Compliance metrics and exceptions | Annex T25 |
| 41.1.3.7.b.v | Integration & System Dashboard | **COMPLY** | System health and integration status | Annex T25 |
| 41.1.3.7.b.vi | Project & Site Monitoring Dashboard | **COMPLY** | Site-level activity monitoring | Annex T25 |
| 41.1.3.7.b.vii | Claims & Payment Status Dashboard | **COMPLY** | End-to-end claim tracking | Annex T25 |
| 41.1.3.7.b.viii | Budget Utilisation Dashboard | **COMPLY** | Budget vs actual analysis | Annex T25 |
| 41.1.3.7.b.ix | DUSP/Subcontractor Performance Dashboard | **COMPLY** | Performance metrics and trends | Annex T25 |
| 41.1.3.7.b.x | Security & Backup Dashboard | **COMPLY** | Security metrics and backup status | Annex T25 |
| 41.1.3.7.b.xi | Exception & Workflow Dashboard | **COMPLY** | Workflow status and bottlenecks | Annex T25 |
| 41.1.3.7.b.xii | Dynamic Excel Export | **COMPLY** | One-click Excel export capability | Annex T25 |

### MODULE 8: AUDIT TRAIL

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.8.a | Timestamped activity log | **COMPLY** | Immutable timestamped records | Annex T26 |
| 41.1.3.8.b | Complete activity capture | **COMPLY** | All user/system activities logged | Annex T26 |
| 41.1.3.8.c | Metadata capture | **COMPLY** | User, action, timestamp, IP, device capture | Annex T26 |
| 41.1.3.8.d | Protected records | **COMPLY** | Tamper-proof audit storage | Annex T26 |
| 41.1.3.8.e | Search & reporting | **COMPLY** | Advanced search and audit reports | Annex T26 |
| 41.1.3.8.f | Compliance verification | **COMPLY** | Governance and compliance audit support | Annex T26 |

### MODULE 9: SELF SERVICE APPLICATION

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.9.a | DUSP self-service | **COMPLY** | 24/7 secure portal access | Annex T27 |
| 41.1.3.9.b | Claim submission | **COMPLY** | Online claim submission with validation | Annex T27 |
| 41.1.3.9.c | Document upload | **COMPLY** | Secure multi-document upload | Annex T27 |
| 41.1.3.9.d | Tracking capability | **COMPLY** | Real-time status tracking | Annex T27 |
| 41.1.3.9.e | Notifications | **COMPLY** | Multi-channel alert system | Annex T27 |
| 41.1.3.9.f | Authentication | **COMPLY** | Centralized SSO with full audit | Annex T27 |

### MODULE 10: VALUE ADDED FUNCTION

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.3.10.a | Intelligent analytics | **COMPLY** | Trend analysis and predictive insights | Annex T28 |
| 41.1.3.10.b | Automation capabilities | **COMPLY** | RPA automation and smart validations | Annex T28 |
| 41.1.3.10.c | Risk detection | **COMPLY** | Anomaly and fraud pattern detection | Annex T28 |
| 41.1.3.10.d | Predictive insights | **COMPLY** | ML-based forecasting | Annex T28 |
| 41.1.3.10.e | Exception handling | **COMPLY** | Configurable exception workflows | Annex T28 |
| 41.1.3.10.f | Smart validations | **COMPLY** | AI-powered data validation | Annex T28 |
| 41.1.3.10.g | Business rules | **COMPLY** | Configurable rules engine | Annex T28 |

---

## SECTION 41.1.4: SYSTEM INTEGRATION

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.4.a | USPFS integration | **COMPLY** | Secure RESTful API with Oracle EBS | Annex T29 |
| 41.1.4.b | Secure API with Azure AD SSO | **COMPLY** | OAuth 2.0 + Azure AD integration | Annex T29 |
| 41.1.4.c | Data integrity | **COMPLY** | End-to-end encryption and validation | Annex T29 |

---

## SECTION 41.1.5: AI-POWERED DOCUMENT VALIDATION

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.5.a | OCR capability | **COMPLY** | AWS Textract + Tesseract OCR | Annex T30 |
| 41.1.5.b | ML document analysis | **COMPLY** | TensorFlow ML models | Annex T30 |
| 41.1.5.c | Fraud detection | **COMPLY** | Pattern recognition algorithms | Annex T30 |
| 41.1.5.d | Tampering detection | **COMPLY** | Image forensics analysis | Annex T30 |
| 41.1.5.e | Duplicate detection | **COMPLY** | Document fingerprinting | Annex T30 |
| 41.1.5.f | Configurable thresholds | **COMPLY** | Admin-configurable rules | Annex T30 |
| 41.1.5.g | Audit logging | **COMPLY** | Complete AI decision logging | Annex T30 |
| 41.1.5.h | Continuous learning | **COMPLY** | Model retraining pipeline | Annex T30 |
| 41.1.5.i | Performance metrics | **COMPLY** | Accuracy and performance tracking | Annex T30 |
| 41.1.5.j | Integration | **COMPLY** | Embedded in workflow | Annex T30 |

---

## SECTION 41.1.6: SECURITY AND COMPLIANCE

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.6.a | Azure AD SSO | **COMPLY** | Full Azure AD integration with MFA | Annex T31 |
| 41.1.6.b | Multi-level access control | **COMPLY** | RBAC with segregation of duties | Annex T31 |
| 41.1.6.c | Encryption | **COMPLY** | AES-256 at rest, TLS 1.3 in transit | Annex T31 |
| 41.1.6.d | Data protection | **COMPLY** | PDPA compliance measures | Annex T31 |
| 41.1.6.e | Audit compliance | **COMPLY** | KRISA and audit-ready design | Annex T31 |
| 41.1.6.f | Security monitoring | **COMPLY** | 24/7 security monitoring | Annex T31 |

---

## SECTION 41.1.7: SYSTEM TESTING

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.7.a | UAT | **COMPLY** | User Acceptance Testing with MCMC | Annex T32 |
| 41.1.7.b | FAT | **COMPLY** | Factory Acceptance Testing | Annex T32 |
| 41.1.7.c | SIT | **COMPLY** | System Integration Testing | Annex T32 |
| 41.1.7.d | Bug fixing | **COMPLY** | Defect tracking and resolution | Annex T32 |

---

## SECTION 41.1.8: PENETRATION TESTING

| Ref | Requirement | Compliance | Our Solution | Evidence |
|-----|-------------|------------|--------------|----------|
| 41.1.8.a | Third-party testing | **COMPLY** | CREST/OWASP certified firm | Annex T33 |
| 41.1.8.b | Blackbox/Whitebox | **COMPLY** | Both testing methodologies | Annex T33 |
| 41.1.8.c | WAPT | **COMPLY** | Web Application Penetration Testing | Annex T33 |
| 41.1.8.d | Signed report | **COMPLY** | Executive report with remediation | Annex T33 |

---

## COMPLIANCE SUMMARY

| Category | Requirements | Compliant | Percentage |
|----------|--------------|-----------|------------|
| Background & Overview | 4 | 4 | 100% |
| System Analysis & Design | 5 | 5 | 100% |
| System Development | 5 | 5 | 100% |
| Master Data Module | 14 | 14 | 100% |
| User Management Module | 5 | 5 | 100% |
| Budget Management Module | 9 | 9 | 100% |
| Claims Management Module | 11 | 11 | 100% |
| Payment Processing Module | 8 | 8 | 100% |
| Reports Module | 11 | 11 | 100% |
| Dashboard Module | 14 | 14 | 100% |
| Audit Trail Module | 6 | 6 | 100% |
| Self-Service Module | 6 | 6 | 100% |
| Value-Added Module | 7 | 7 | 100% |
| System Integration | 3 | 3 | 100% |
| AI/ML Capabilities | 10 | 10 | 100% |
| Security & Compliance | 6 | 6 | 100% |
| Testing | 4 | 4 | 100% |
| Penetration Testing | 4 | 4 | 100% |
| **TOTAL** | **122** | **122** | **100%** |

---

## CERTIFICATION

We hereby certify that:

1. All technical compliance responses in this matrix are accurate and verifiable
2. We possess the technical capability to deliver all stated requirements
3. All referenced annexures contain authentic supporting evidence
4. Our solution meets or exceeds all specified technical requirements

**Submitted by:**

_______________________________  
Technical Lead / Solution Architect

Date: ___________________________

Company Stamp:
