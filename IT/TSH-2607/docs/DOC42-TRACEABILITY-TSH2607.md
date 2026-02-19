# DOC42-TRACEABILITY-TSH2607.md
# Requirements Traceability Matrix
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC42-TRACEABILITY-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Requirements Traceability Matrix (RTM) establishes traceability between MCMC requirements, system design, development, and testing for the UCMS project.

### 1.2 Traceability Levels

| Level | Description | Artifacts |
|-------|-------------|-----------|
| L1 | Business Requirements | BRD, Stakeholder needs |
| L2 | Functional Requirements | FRD, Use Cases |
| L3 | Technical Requirements | System Design, Architecture |
| L4 | Implementation | Code, Configuration |
| L5 | Testing | Test Cases, Test Results |

---

## 2.0 TRACEABILITY MATRIX

### 2.1 Functional Requirements Traceability

| Req ID | Requirement Description | Source | Design Ref | Module | Test Case | Status |
|--------|------------------------|--------|------------|--------|-----------|--------|
| **AUTHENTICATION & ACCESS CONTROL** |
| AUTH-001 | System shall support user authentication via username/password | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-AUTH-001 | □ Not Started |
| AUTH-002 | System shall enforce password complexity policy | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-AUTH-002 | □ Not Started |
| AUTH-003 | System shall support Multi-Factor Authentication | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-AUTH-004 | □ Not Started |
| AUTH-004 | System shall implement session timeout after 30 min inactivity | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-AUTH-005 | □ Not Started |
| AUTH-005 | System shall support Role-Based Access Control | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-AUTH-003 | □ Not Started |
| AUTH-006 | System shall maintain audit log of all login attempts | Tender Sec 4.2 | DOC22-SDD | Audit Module | TC-AUTH-006 | □ Not Started |
| AUTH-007 | System shall integrate with MCMC Active Directory | Tender Sec 4.1 | DOC22-SDD | Auth Module | TC-ADM-003 | □ Not Started |
| **APPLICANT MANAGEMENT** |
| APP-001 | System shall allow registration of individual applicants | Tender Sec 5.1 | DOC22-SDD | Applicant Module | TC-APP-001 | □ Not Started |
| APP-002 | System shall allow registration of corporate applicants | Tender Sec 5.1 | DOC22-SDD | Applicant Module | TC-APP-002 | □ Not Started |
| APP-003 | System shall verify applicant identity via MyIDENTITY | Tender Sec 5.1 | DOC26-ICD | Applicant Module | TC-APP-005 | □ Not Started |
| APP-004 | System shall validate Malaysian IC number format | Tender Sec 5.1 | DOC27-DD | Applicant Module | TC-APP-001 | □ Not Started |
| APP-005 | System shall verify company registration via SSM | Tender Sec 5.1 | DOC26-ICD | Applicant Module | TC-APP-002 | □ Not Started |
| APP-006 | System shall support applicant eligibility checking | Tender Sec 5.2 | DOC22-SDD | Applicant Module | TC-APP-007 | □ Not Started |
| APP-007 | System shall maintain applicant demographic data | Tender Sec 5.1 | DOC27-DD | Applicant Module | TC-APP-004 | □ Not Started |
| APP-008 | System shall support B40 status verification | Tender Sec 5.2 | DOC22-SDD | Applicant Module | TC-APP-007 | □ Not Started |
| APP-009 | System shall support rural area classification | Tender Sec 5.2 | DOC22-SDD | Applicant Module | TC-APP-007 | □ Not Started |
| APP-010 | System shall support Orang Asli status tracking | Tender Sec 5.2 | DOC22-SDD | Applicant Module | TC-APP-007 | □ Not Started |
| APP-011 | System shall allow document upload for applicants | Tender Sec 5.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| APP-012 | System shall provide applicant search functionality | Tender Sec 5.1 | DOC22-SDD | Applicant Module | TC-APP-003 | □ Not Started |
| **CLAIMS PROCESSING** |
| CLM-001 | System shall support creation of new claims | Tender Sec 6.1 | DOC22-SDD | Claims Module | TC-CLM-001 | □ Not Started |
| CLM-002 | System shall support multiple USP schemes | Tender Sec 6.1 | DOC22-SDD | Claims Module | TC-ADM-002 | □ Not Started |
| CLM-003 | System shall calculate claim amounts automatically | Tender Sec 6.1 | DOC22-SDD | Claims Module | TC-CLM-001 | □ Not Started |
| CLM-004 | System shall enforce claim amount limits per scheme | Tender Sec 6.1 | DOC22-SDD | Claims Module | TC-CLM-001 | □ Not Started |
| CLM-005 | System shall support multi-level approval workflow | Tender Sec 6.2 | DOC22-SDD | Workflow Module | TC-CLM-002 | □ Not Started |
| CLM-006 | System shall track claim status throughout lifecycle | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-007 | □ Not Started |
| CLM-007 | System shall support document attachment to claims | Tender Sec 6.1 | DOC22-SDD | Document Module | TC-CLM-001 | □ Not Started |
| CLM-008 | System shall send notifications on status changes | Tender Sec 6.2 | DOC22-SDD | Notification Module | TC-CLM-002 | □ Not Started |
| CLM-009 | System shall support claim rejection with reasons | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-003 | □ Not Started |
| CLM-010 | System shall support request for additional documents | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-004 | □ Not Started |
| CLM-011 | System shall support claim cancellation | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-010 | □ Not Started |
| CLM-012 | System shall support claim amendment requests | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-009 | □ Not Started |
| CLM-013 | System shall support claim appeals process | Tender Sec 6.2 | DOC22-SDD | Claims Module | TC-CLM-011 | □ Not Started |
| CLM-014 | System shall provide claim search and filtering | Tender Sec 6.3 | DOC22-SDD | Claims Module | TC-CLM-006 | □ Not Started |
| CLM-015 | System shall generate claim reference numbers | Tender Sec 6.1 | DOC22-SDD | Claims Module | TC-CLM-001 | □ Not Started |
| **PAYMENT PROCESSING** |
| PAY-001 | System shall support payment processing for approved claims | Tender Sec 7.1 | DOC22-SDD | Payment Module | TC-CLM-005 | □ Not Started |
| PAY-002 | System shall integrate with bank payment systems | Tender Sec 7.1 | DOC26-ICD | Payment Module | TC-CLM-005 | □ Not Started |
| PAY-003 | System shall support multiple payment methods | Tender Sec 7.1 | DOC22-SDD | Payment Module | TC-CLM-005 | □ Not Started |
| PAY-004 | System shall track payment status | Tender Sec 7.1 | DOC22-SDD | Payment Module | TC-CLM-005 | □ Not Started |
| PAY-005 | System shall support payment authorization workflow | Tender Sec 7.1 | DOC22-SDD | Payment Module | TC-CLM-005 | □ Not Started |
| PAY-006 | System shall generate payment reports | Tender Sec 7.2 | DOC22-SDD | Report Module | TC-RPT-002 | □ Not Started |
| PAY-007 | System shall handle payment failures and retries | Tender Sec 7.1 | DOC22-SDD | Payment Module | TC-CLM-005 | □ Not Started |
| **REPORTING & ANALYTICS** |
| RPT-001 | System shall provide standard reports | Tender Sec 8.1 | DOC22-SDD | Report Module | TC-RPT-001 | □ Not Started |
| RPT-002 | System shall support custom report generation | Tender Sec 8.1 | DOC22-SDD | Report Module | TC-RPT-001 | □ Not Started |
| RPT-003 | System shall provide dashboard with KPIs | Tender Sec 8.2 | DOC22-SDD | Report Module | TC-RPT-003 | □ Not Started |
| RPT-004 | System shall support data export to Excel/PDF | Tender Sec 8.1 | DOC22-SDD | Report Module | TC-RPT-001 | □ Not Started |
| RPT-005 | System shall generate scheme utilization reports | Tender Sec 8.1 | DOC22-SDD | Report Module | TC-RPT-001 | □ Not Started |
| RPT-006 | System shall support scheduled report generation | Tender Sec 8.1 | DOC22-SDD | Report Module | TC-RPT-001 | □ Not Started |
| **DOCUMENT MANAGEMENT** |
| DOC-001 | System shall support document upload | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| DOC-002 | System shall support multiple file formats | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| DOC-003 | System shall enforce file size limits | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| DOC-004 | System shall scan uploaded files for malware | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| DOC-005 | System shall maintain document versioning | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| DOC-006 | System shall support document download | Tender Sec 9.1 | DOC22-SDD | Document Module | TC-APP-006 | □ Not Started |
| **NOTIFICATION** |
| NOT-001 | System shall send email notifications | Tender Sec 10.1 | DOC26-ICD | Notification Module | TC-CLM-002 | □ Not Started |
| NOT-002 | System shall send SMS notifications | Tender Sec 10.1 | DOC26-ICD | Notification Module | TC-CLM-002 | □ Not Started |
| NOT-003 | System shall support notification templates | Tender Sec 10.1 | DOC22-SDD | Notification Module | TC-CLM-002 | □ Not Started |
| **SECURITY** |
| SEC-001 | System shall encrypt data at rest | Tender Sec 11.1 | DOC22-SDD | Security Module | TC-SEC-001 | □ Not Started |
| SEC-002 | System shall encrypt data in transit | Tender Sec 11.1 | DOC22-SDD | Security Module | TC-SEC-001 | □ Not Started |
| SEC-003 | System shall implement input validation | Tender Sec 11.2 | DOC22-SDD | Security Module | TC-SEC-002 | □ Not Started |
| SEC-004 | System shall protect against SQL injection | Tender Sec 11.2 | DOC22-SDD | Security Module | TC-SEC-003 | □ Not Started |
| SEC-005 | System shall protect against XSS | Tender Sec 11.2 | DOC22-SDD | Security Module | TC-SEC-004 | □ Not Started |
| SEC-006 | System shall implement secure session management | Tender Sec 11.2 | DOC22-SDD | Security Module | TC-AUTH-005 | □ Not Started |
| SEC-007 | System shall maintain comprehensive audit logs | Tender Sec 11.3 | DOC22-SDD | Audit Module | TC-ADM-004 | □ Not Started |
| SEC-008 | System shall support data retention policies | Tender Sec 11.3 | DOC22-SDD | Data Module | TC-ADM-005 | □ Not Started |

### 2.2 Non-Functional Requirements Traceability

| Req ID | Requirement | Design Ref | Test Type | Test Case | Status |
|--------|-------------|------------|-----------|-----------|--------|
| NFR-001 | System shall support 1000+ concurrent users | DOC28-IDD | Performance | PERF-LOAD-001 | □ Not Started |
| NFR-002 | Average response time < 2 seconds | DOC28-IDD | Performance | PERF-RESP-001 | □ Not Started |
| NFR-003 | 99.9% uptime availability | DOC28-IDD | Availability | PERF-AVA-001 | □ Not Started |
| NFR-004 | Support 100 TPS throughput | DOC28-IDD | Performance | PERF-TPS-001 | □ Not Started |
| NFR-005 | Data backup every 24 hours | DOC28-IDD | Operational | OP-BKP-001 | □ Not Started |
| NFR-006 | RTO < 4 hours, RPO < 1 hour | DOC28-IDD | DR Test | DR-TEST-001 | □ Not Started |
| NFR-007 | Support 500,000+ applicant records | DOC28-IDD | Scalability | PERF-SCL-001 | □ Not Started |
| NFR-008 | PCI DSS compliance for payments | DOC22-SDD | Security | VAPT-PAY-001 | □ Not Started |
| NFR-009 | PDPA compliance for personal data | DOC22-SDD | Security | AUDIT-PDPA-001 | □ Not Started |
| NFR-010 | MyGPSS compliance | DOC28-IDD | Security | AUDIT-MGPSS-001 | □ Not Started |

---

## 3.0 REQUIREMENT COVERAGE ANALYSIS

### 3.1 Coverage Summary

| Category | Total Req | Design Coverage | Test Coverage | % Complete |
|----------|-----------|-----------------|---------------|------------|
| Authentication | 7 | | | |
| Applicant Management | 12 | | | |
| Claims Processing | 15 | | | |
| Payment Processing | 7 | | | |
| Reporting | 6 | | | |
| Document Management | 6 | | | |
| Notification | 3 | | | |
| Security | 8 | | | |
| Non-Functional | 10 | | | |
| **TOTAL** | **74** | | | |

### 3.2 Test Coverage Matrix

| Test Phase | Test Cases | Requirements Covered | Coverage % |
|------------|------------|---------------------|------------|
| Unit Testing | | | |
| Integration Testing | | | |
| System Testing | | | |
| UAT | | | |
| Performance Testing | | | |
| Security Testing | | | |

---

## 4.0 CHANGE TRACKING

| Change ID | Date | Requirement | Change Type | Impact | Approved By |
|-----------|------|-------------|-------------|--------|-------------|
| | | | □ Add □ Modify □ Remove | | |
| | | | □ Add □ Modify □ Remove | | |

---

## 5.0 DEFECT TRACKING

| Defect ID | Requirement | Severity | Status | Resolution |
|-----------|-------------|----------|--------|------------|
| | | □ Critical □ High □ Medium □ Low | □ Open □ Fixed □ Closed | |
| | | □ Critical □ High □ Medium □ Low | □ Open □ Fixed □ Closed | |

---

## 6.0 SIGN-OFF

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Business Analyst | | | |
| Technical Lead | | | |
| QA Lead | | | |
| Project Manager | | | |
| MCMC Representative | | | |

---

**Document Control:** This RTM is a living document updated throughout the project lifecycle. Changes require approval from the Project Manager and MCMC Representative.
