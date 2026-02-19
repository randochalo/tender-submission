# DOCUMENT 09: FUNCTIONAL COMPLIANCE MATRIX

## TSH-2607: USP Claims Management System (UCMS)
### Tender Reference: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

---

## FUNCTIONAL REQUIREMENTS COMPLIANCE STATEMENT

This document provides detailed mapping of functional requirements to our proposed UCMS solution features, demonstrating comprehensive compliance with MCMC's business needs.

---

## 1.0 FUNCTIONAL REQUIREMENTS OVERVIEW

### 1.1 Scope Definition

The UCMS functional scope encompasses end-to-end management of USP claims, payments, and related processes across the complete project lifecycle.

### 1.2 User Categories

| User Type | Count | Access Level | Modules |
|-----------|-------|--------------|---------|
| Internal MCMC Users | 60 | Full Access | All Modules |
| DUSP Representatives | ~120 | Restricted | Claims, Self-Service, Reports |
| Subcontractors | ~70 | Limited | Document Upload, Status View |
| System Administrators | 5 | Administrative | Configuration, User Management |

---

## 2.0 MASTER DATA MANAGEMENT - FUNCTIONAL COMPLIANCE

### 2.1 Project Hierarchy Management

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| MD-F-001 | Create multi-tier Project ID structure | High | ✓ | 4-tier hierarchy with auto-generation |
| MD-F-002 | Support Project → Sub-Project relationship | High | ✓ | Parent-child linking with inheritance |
| MD-F-003 | Cluster ID generation within projects | High | ✓ | Unique cluster identifiers |
| MD-F-004 | Site ID assignment to clusters | High | ✓ | Site registration with geo-tagging |
| MD-F-005 | Item ID definition for deliverables | Medium | ✓ | BOQ item catalog |

### 2.2 Contract & Agreement Management

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| MD-F-006 | NOA (Notice of Award) recording | High | ✓ | Digital NOA capture with validation |
| MD-F-007 | Contract document storage | High | ✓ | Document repository with version control |
| MD-F-008 | Contract terms extraction | Medium | ✓ | OCR + ML extraction |
| MD-F-009 | Variation Order tracking | High | ✓ | VO workflow with approval chain |
| MD-F-010 | Extension of Time management | High | ✓ | EOT request and approval workflow |

### 2.3 Financial Instruments

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| MD-F-011 | Performance Bond recording | High | ✓ | Bond registration with expiry alerts |
| MD-F-012 | Bond validation before disbursement | Critical | ✓ | Automated bond status check |
| MD-F-013 | Bond renewal tracking | Medium | ✓ | Automated renewal notifications |

### 2.4 Self-Declaration Management

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| MD-F-014 | Technical Self-Declaration capture | High | ✓ | DUSP declaration form with validation |
| MD-F-015 | CEO Declaration for claims | Critical | ✓ | Authenticated declaration capture |
| MD-F-016 | Auditors' Declaration recording | High | ✓ | Auditor verification workflow |

### 2.5 Risk & Compliance Tracking

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| MD-F-017 | Litigation record management | Medium | ✓ | Legal case tracking module |
| MD-F-018 | Dispute status monitoring | Medium | ✓ | Status updates and resolution tracking |

---

## 3.0 USER MANAGEMENT - FUNCTIONAL COMPLIANCE

### 3.1 Account Lifecycle

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| UM-F-001 | DUSP account creation | High | ✓ | Self-registration + approval workflow |
| UM-F-002 | Subcontractor account creation | High | ✓ | DUSP-initiated registration |
| UM-F-003 | Internal user provisioning | High | ✓ | HR-driven auto-provisioning |
| UM-F-004 | Account suspension/deactivation | High | ✓ | Admin controls with audit |
| UM-F-005 | Account termination | High | ✓ | Secure deactivation with data retention |

### 3.2 Profile Management

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| UM-F-006 | DUSP profile maintenance | High | ✓ | Company info, bank details, contacts |
| UM-F-007 | User delegation capability | Medium | ✓ | Temporary delegation with audit |
| UM-F-008 | Role-based permissions | Critical | ✓ | Granular RBAC system |
| UM-F-009 | User matrix visualization | Medium | ✓ | Access matrix report |

### 3.3 Authentication & Security

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| UM-F-010 | Azure AD SSO integration | Critical | ✓ | SAML/OAuth integration |
| UM-F-011 | Multi-factor authentication | High | ✓ | MFA for external users |
| UM-F-012 | Password policy enforcement | High | ✓ | Configurable complexity rules |
| UM-F-013 | Session management | High | ✓ | Timeout and concurrent session control |

---

## 4.0 BUDGET MANAGEMENT - FUNCTIONAL COMPLIANCE

### 4.1 Budget Structure

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| BM-F-001 | Approved budget recording | High | ✓ | Budget master with USPFS sync |
| BM-F-002 | Capped cost definition | Critical | ✓ | Ceiling amount enforcement |
| BM-F-003 | Site-level budget allocation | High | ✓ | Site costing breakdown |
| BM-F-004 | BOQ management | High | ✓ | Bill of Quantity catalog |
| BM-F-005 | Cost component categorization | Medium | ✓ | Preliminaries, CME, Software, Shared |

### 4.2 Budget Control

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| BM-F-006 | Real-time budget checking | Critical | ✓ | Automated validation on claim submission |
| BM-F-007 | Variance monitoring | High | ✓ | Budget vs actual tracking |
| BM-F-008 | Approaching limit alerts | High | ✓ | Threshold-based notifications |
| BM-F-009 | Budget change workflow | High | ✓ | Approval-required modifications |
| BM-F-010 | Budget utilization reports | High | ✓ | Multi-dimensional analysis |

### 4.3 Financial Integration

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| BM-F-011 | USPFS budget sync | Critical | ✓ | Real-time API synchronization |
| BM-F-012 | Subsidiary ledger reconciliation | High | ✓ | Automated reconciliation engine |

---

## 5.0 CLAIMS MANAGEMENT - FUNCTIONAL COMPLIANCE

### 5.1 Claim Types

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| CM-F-001 | Advance claim processing | High | ✓ | Advance request with recovery tracking |
| CM-F-002 | Quarterly claim processing | High | ✓ | Quarterly consolidated submission |
| CM-F-003 | Major contributor claims | High | ✓ | High-value claim workflow |
| CM-F-004 | Yearly claim with audit | High | ✓ | Annual submission with auditor template |

### 5.2 Claim Submission

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| CM-F-005 | Online claim submission | Critical | ✓ | Self-service portal submission |
| CM-F-006 | Supporting document upload | Critical | ✓ | Multi-file upload with validation |
| CM-F-007 | Invoice attachment | Critical | ✓ | Invoice OCR and validation |
| CM-F-008 | Milestone linkage | High | ✓ | Progress milestone validation |
| CM-F-009 | Submission ID generation | High | ✓ | Auto-generated unique identifiers |

### 5.3 Claim Validation

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| CM-F-010 | Capped cost validation | Critical | ✓ | Real-time budget limit check |
| CM-F-011 | Performance bond validation | Critical | ✓ | Bond status verification |
| CM-F-012 | Milestone completion check | High | ✓ | Progress validation against plan |
| CM-F-013 | Document completeness check | High | ✓ | Required document validation |
| CM-F-014 | Duplicate claim detection | Critical | ✓ | AI-powered duplicate detection |
| CM-F-015 | Fraud pattern detection | High | ✓ | ML-based anomaly detection |

### 5.4 Claim Processing

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| CM-F-016 | Multi-stage verification | High | ✓ | Configurable verification stages |
| CM-F-017 | Approval routing | High | ✓ | Workflow-based routing |
| CM-F-018 | Rejection with reasons | High | ✓ | Structured rejection workflow |
| CM-F-019 | Resubmission handling | High | ✓ | Correction and resubmission |
| CM-F-020 | Status tracking | Critical | ✓ | Real-time status visibility |

---

## 6.0 PAYMENT PROCESSING - FUNCTIONAL COMPLIANCE

### 6.1 Payment Requisition

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| PP-F-001 | Memo generation | Critical | ✓ | Auto-generated payment memos |
| PP-F-002 | Template-based memos | High | ✓ | Configurable memo templates |
| PP-F-003 | Claim-to-payment linking | Critical | ✓ | End-to-end traceability |

### 6.2 Approval Workflow

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| PP-F-004 | Minimum 3-layer approval | Critical | ✓ | Configurable approval hierarchy |
| PP-F-005 | Digital signature integration | Critical | ✓ | MSC TrustSign/DocuSign integration |
| PP-F-006 | Approval delegation | Medium | ✓ | Temporary delegation capability |
| PP-F-007 | Escalation rules | High | ✓ | Auto-escalation on timeout |

### 6.3 Payment Execution

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| PP-F-008 | Voucher generation | Critical | ✓ | USPFS voucher creation |
| PP-F-009 | Payment advice generation | High | ✓ | Automated advice letters |
| PP-F-010 | Bank integration | Medium | ✓ | Payment file generation |
| PP-F-011 | DUSP notification | High | ✓ | Automated email notifications |

### 6.4 Payment Tracking

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| PP-F-012 | Payment status tracking | High | ✓ | End-to-end payment visibility |
| PP-F-013 | Reconciliation | High | ✓ | Bank reconciliation automation |
| PP-F-014 | Payment history | Medium | ✓ | Complete payment records |

---

## 7.0 REPORTING - FUNCTIONAL COMPLIANCE

### 7.1 Standard Reports

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| RP-F-001 | DUSP performance reports | High | ✓ | Performance analytics |
| RP-F-002 | Subcontractor reports | High | ✓ | Subcontractor activity reports |
| RP-F-003 | Payment reports | Critical | ✓ | Payment status and history |
| RP-F-004 | Project progress reports | High | ✓ | Milestone and progress tracking |
| RP-F-005 | Financial progress reports | High | ✓ | Financial KPIs and metrics |
| RP-F-006 | Budget utilization reports | High | ✓ | Budget vs actual analysis |

### 7.2 Exception Reports

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| RP-F-007 | Delayed claims report | High | ✓ | Aging and delay analysis |
| RP-F-008 | Budget variance report | High | ✓ | Variance analysis with drill-down |
| RP-F-009 | Compliance exception report | High | ✓ | Non-compliance identification |
| RP-F-010 | Fraud alert report | Critical | ✓ | ML-generated risk alerts |

### 7.3 Report Distribution

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| RP-F-011 | Scheduled report generation | Medium | ✓ | Automated scheduling |
| RP-F-012 | Email distribution | Medium | ✓ | Automated email delivery |
| RP-F-013 | Export formats (PDF, Excel) | High | ✓ | Multiple export options |

---

## 8.0 DASHBOARD - FUNCTIONAL COMPLIANCE

### 8.1 Operational Dashboards

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| DB-F-001 | Fund position dashboard | Critical | ✓ | Real-time fund status |
| DB-F-002 | Project delivery dashboard | High | ✓ | Project progress visualization |
| DB-F-003 | Payment disbursement dashboard | High | ✓ | Payment pipeline view |
| DB-F-004 | Claims status dashboard | High | ✓ | End-to-end claim tracking |

### 8.2 Management Dashboards

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| DB-F-005 | Budget utilization dashboard | Critical | ✓ | Budget performance KPIs |
| DB-F-006 | DUSP performance dashboard | High | ✓ | Performance scorecards |
| DB-F-007 | Compliance dashboard | High | ✓ | Compliance status overview |
| DB-F-008 | Executive summary dashboard | High | ✓ | C-level KPI summary |

### 8.3 Technical Dashboards

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| DB-F-009 | System health dashboard | Medium | ✓ | Infrastructure monitoring |
| DB-F-010 | Integration status dashboard | Medium | ✓ | API health and status |
| DB-F-011 | Security dashboard | High | ✓ | Security metrics and alerts |

### 8.4 Dashboard Features

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| DB-F-012 | Real-time data refresh | High | ✓ | Live data updates |
| DB-F-013 | Drill-down capability | High | ✓ | Hierarchical exploration |
| DB-F-014 | Dynamic Excel export | High | ✓ | One-click Excel download |
| DB-F-015 | Customizable widgets | Medium | ✓ | User-configurable layout |

---

## 9.0 SELF-SERVICE - FUNCTIONAL COMPLIANCE

### 9.1 DUSP Self-Service

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| SS-F-001 | Claim submission portal | Critical | ✓ | Intuitive submission interface |
| SS-F-002 | Document upload | Critical | ✓ | Drag-and-drop upload |
| SS-F-003 | Submission status tracking | Critical | ✓ | Real-time status updates |
| SS-F-004 | Payment status view | High | ✓ | Payment tracking |
| SS-F-005 | Historical claim access | High | ✓ | Archive and history view |

### 9.2 Subcontractor Self-Service

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| SS-F-006 | Invoice submission | High | ✓ | Simplified invoice upload |
| SS-F-007 | Payment advice view | Medium | ✓ | Payment notification |

### 9.3 Internal Self-Service

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| SS-F-008 | Claim verification | High | ✓ | Online verification tools |
| SS-F-009 | Approval actions | Critical | ✓ | Mobile-responsive approvals |
| SS-F-010 | Report access | High | ✓ | Self-service reporting |

---

## 10.0 AUDIT TRAIL - FUNCTIONAL COMPLIANCE

### 10.1 Activity Logging

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| AT-F-001 | User action logging | Critical | ✓ | Complete activity capture |
| AT-F-002 | Timestamp recording | Critical | ✓ | Immutable timestamps |
| AT-F-003 | Data change tracking | Critical | ✓ | Before/after values |
| AT-F-004 | Session logging | High | ✓ | Login/logout tracking |

### 10.2 Audit Features

| Req ID | Functional Requirement | Priority | Compliance | Solution Feature |
|--------|----------------------|----------|------------|------------------|
| AT-F-005 | Audit report generation | High | ✓ | Filterable audit reports |
| AT-F-006 | Data export | Medium | ✓ | CSV/PDF export |
| AT-F-007 | Tamper-proof storage | Critical | ✓ | Write-once audit log |
| AT-F-008 | Audit query interface | High | ✓ | Advanced search capabilities |

---

## COMPLIANCE SUMMARY

| Functional Area | Requirements | Compliant | Partial | Non-Compliant | Coverage |
|-----------------|--------------|-----------|---------|---------------|----------|
| Master Data Management | 18 | 18 | 0 | 0 | 100% |
| User Management | 13 | 13 | 0 | 0 | 100% |
| Budget Management | 12 | 12 | 0 | 0 | 100% |
| Claims Management | 20 | 20 | 0 | 0 | 100% |
| Payment Processing | 14 | 14 | 0 | 0 | 100% |
| Reporting | 13 | 13 | 0 | 0 | 100% |
| Dashboard | 15 | 15 | 0 | 0 | 100% |
| Self-Service | 10 | 10 | 0 | 0 | 100% |
| Audit Trail | 8 | 8 | 0 | 0 | 100% |
| **TOTAL** | **123** | **123** | **0** | **0** | **100%** |

---

## PRIORITY BREAKDOWN

| Priority Level | Requirements | Compliant | Coverage |
|----------------|--------------|-----------|----------|
| Critical | 32 | 32 | 100% |
| High | 67 | 67 | 100% |
| Medium | 24 | 24 | 100% |
| **TOTAL** | **123** | **123** | **100%** |

---

## CERTIFICATION

We hereby certify that:

1. All functional requirements have been thoroughly analyzed and addressed
2. Our solution provides 100% compliance with all stated functional requirements
3. All features are demonstrable and will be validated during UAT
4. We commit to delivering all functional capabilities as specified

**Submitted by:**

_______________________________  
Business Analyst / Functional Lead

Date: ___________________________

Company Stamp:
