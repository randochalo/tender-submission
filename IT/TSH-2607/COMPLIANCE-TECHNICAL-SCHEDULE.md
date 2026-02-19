# TSH-2607: COMPLIANCE TECHNICAL SCHEDULE
## Statement of Compliance to Scope of Work and Specification

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Project:** Universal Service Provision (USP) Claims Management System (UCMS)  
**Date:** February 2026  
**Version:** 2.0 (Revised)

---

## EXECUTIVE SUMMARY

| Metric | Value |
|--------|-------|
| **Total Requirements** | 120+ |
| **Compliant** | 119 |
| **Noted** | 1 (Price Indicative) |
| **Overall Compliance** | **99%+** |

---

## SECTION 40: BACKGROUND

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 40.1 | MCMC manages USP projects with internal/external stakeholders | **COMPLY** | RBAC distinguishes MCMC internal vs DUSP/contractor users | - |
| 40.2 | Oracle-based system with Digital Signature, RPA, OCR for 60+120 users | **COMPLY** | Oracle middleware + MSC TrustSign + UiPath + Tesseract/AWS Textract | T1-T2 |
| 40.3 | UCMS overview diagram | **COMPLY** | Web frontend + Oracle middleware + USPFS API integration | T2 |
| 40.4 | Single customer-facing digital gateway via MCMC portal | **COMPLY** | Responsive web app with SSO, project tracking, approval workflows | T3 |

---

## SECTION 41: SCOPE OF WORK

### 41.1.1 SYSTEM ANALYSIS AND DESIGN

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.1.a | Requirements gathering workshops | **COMPLY** | JAD sessions with dedicated BA (5+ years exp) | T4 |
| 41.1.1.b | Process flowcharts (swimlane) per module | **COMPLY** | BPMN 2.0 diagrams for all 10 modules | T5 |
| 41.1.1.c | Develop and submit SRS and SDD | **COMPLY** | KRISA-compliant SRS/SDD with traceability matrix | T6 |
| 41.1.1.d | System architecture (modular, scalable) | **COMPLY** | Microservices on OCI with Docker/K8s | T2 |
| 41.1.1.e | Approval workflows and UI | **COMPLY** | Configurable 3-layer workflows, React/Angular UI | T7 |

### 41.1.2 SYSTEM DEVELOPMENT (AGILE)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.2.a | Agile methodology with sprints | **COMPLY** | SCRUM with 2-week sprints | T8 |
| 41.1.2.b | Sprint planning/reviews with MCMC | **COMPLY** | Bi-weekly demos + retrospectives | T8 |
| 41.1.2.c | Traceability via user stories | **COMPLY** | JIRA linking stories to acceptance criteria | T9 |
| 41.1.2.d | Efficiency, accuracy, compliance targets | **COMPLY** | 70% manual reduction, 99.5% accuracy | T10 |
| 41.1.2.e | Bilingual support (EN/BM) | **COMPLY** | i18n with Malaysian formats | T11 |

### 41.1.3 SYSTEM MODULES

#### 1. MASTER DATA

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.1.a-d | Master Data Module framework | **COMPLY** | Centralized hub with USPFS sync | T12 |
| 41.1.3.1.d.i-x | ID Management (Project, NOA, VO, Cluster, Site, Item, Bond, Declaration, EOT, Litigation) | **COMPLY** | All 10 ID types supported with automated workflows | T13-T16 |

#### 2. USER MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.2.xi-xv | Account creation, delegation, DUSP/Subcontractor maintenance, RBAC | **COMPLY** | MFA + RBAC + audit logging for all user types | T17-T18 |

#### 3. BUDGET MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.3.a-d | Budget Module with capped costs, BOQ, USPFS integration | **COMPLY** | Automated variance monitoring | T19 |
| 41.1.3.3.d.i-v | Financial control, capped cost, site costing, BOQ, cost components | **COMPLY** | All 5 budget functions implemented | T19 |

#### 4. CLAIMS MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.4.a-d | Claims processing (Advance, Quarterly, Yearly) | **COMPLY** | Rule-based validation + milestone verification | T20 |
| 41.1.3.4.d.i-vii | Invoice, CEO Declaration, Advance/Quarterly/Yearly Claims, Auditor Declaration/Template, Supporting Docs | **COMPLY** | All 7 claim document types supported | T20-T21 |

#### 5. PAYMENT PROCESSING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.5.a-d | Payment with memo, voucher, digital signature, Oracle integration | **COMPLY** | 3-layer approval with digital signatures | T22 |
| 41.1.3.5.d.i-iv | Payment requisition, approval, voucher, DUSP letter | **COMPLY** | All 4 payment workflows | T22-T23 |

#### 6. REPORTS

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.6.a-d | Reporting module (operational/financial/management) | **COMPLY** | Real-time dashboards + RPA exception detection | T24 |
| 41.1.3.6.d.i-vii | DUSP, Subcontractor, Payment, Project Progress, Financial Progress, Budget, Exception reports | **COMPLY** | All 7 report types | T24 |

#### 7. DASHBOARD

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.7.a-b | Dashboard with real-time views, RPA consolidation | **COMPLY** | RPA-powered multi-source dashboards | T25 |
| 41.1.3.7.b.i-xii | All 12 dashboard features | **COMPLY** | Fund, Project, Payment, Compliance, Integration, Monitoring, Claims, Budget, Performance, Security, Exception, Excel Export | T25 |

#### 8. AUDIT TRAIL

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.8.a-f | Complete timestamped activity log | **COMPLY** | Immutable audit trail with metadata | T26 |

#### 9. SELF SERVICE

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.9.a-f | Self-service for DUSPs, subcontractors, internal users | **COMPLY** | Role-based portal with guided workflows | T27 |

#### 10. VALUE ADDED

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.10.a-g | Analytics, automation, governance | **COMPLY** | AI/ML analytics + RPA automation | T28 |

### 41.1.4 SYSTEM INTEGRATION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.4.a-c | USPFS integration, Azure AD SSO, Digital Signature, data integrity | **COMPLY** | REST APIs + SSO + encryption | T29-T31 |

### 41.1.5 AI-POWERED DOCUMENT VALIDATION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.5.a-j | AI/ML document analysis, OCR, fraud/tampering detection | **COMPLY** | ML models for OCR + fraud detection | T30 |

### 41.1.6 SECURITY AND COMPLIANCE

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.6.a | Azure AD SSO, multi-level access, encryption | **COMPLY** | AES-256 + TLS 1.3 + RBAC | T31 |

### 41.1.7 SYSTEM TESTING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.7.a-c | UAT, FAT, SIT phases | **COMPLY** | 3-phase testing with MCMC participation | T32 |

### 41.1.8 PENETRATION TESTING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.8.a-d | Pentest by certified company (Blackbox/Whitebox/WAPT) | **COMPLY** | CREST/OWASP certified testing | T33 |

### 41.1.9 CHANGE MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.9.a-c | Change plan, CAB approval, as-is/to-be analysis | **COMPLY** | Structured CAB process | T34 |

### 41.1.10 DEPLOYMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.10.a-b | Staging/production deployment, Go-Live | **COMPLY** | Phased zero-downtime deployment | T35 |

### 41.1.11 DOCUMENTATION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.11.a-c | Technical docs, manuals, training materials, source code | **COMPLY** | Complete documentation package | T36 |

### 41.1.12 BACKUP AND RESTORE

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.12.a-c | Backup storage, procedures, schedules | **COMPLY** | Daily/weekly/monthly/yearly backup | T37 |

### 41.1.13 TRAINING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.13.a-e | Manuals, materials, training, feedback, knowledge transfer | **COMPLY** | Comprehensive training program | T38 |

### 41.1.14 LICENSE MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.14.a-f | Software licenses (60+180-250 users), servers, tools | **COMPLY** | Oracle + middleware + 250 user licenses | T39 |

### 41.1.15 POST-IMPLEMENTATION SUPPORT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.15.a-c | 48-month support (12 warranty + 36 extended), Resident Engineer | **COMPLY** | Resident Engineer + 24/7 support | T40 |

---

## SECTION 42-50: OTHER REQUIREMENTS

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 42.1 | Progress meetings with MoM | **COMPLY** | Weekly sprint reviews + monthly steering | - |
| 42.2 | Dedicated Project Manager | **COMPLY** | PMP/PRINCE2 certified PM assigned | H |
| 43.1 | Key personnel (PM, Architect, Analyst, UI/UX, Dev, QA, Security) | **COMPLY** | All 7 roles with qualified personnel | H |
| 43.2-43.3 | Qualified personnel, CV submission | **COMPLY** | CVs provided in Appendix H | H |
| 44.1 | Equipment and software supply | **COMPLY** | All equipment/software at our cost | - |
| 45.1 | Past project experience (5 years) | **COMPLY** | References in Appendix H | H |
| 46.1-46.3 | Reports, presentations, documentation | **COMPLY** | Delivered per timelines | - |
| 47.1-47.2 | 67-month duration with milestones | **COMPLY** | 16 dev + 3 test + 12 warranty + 36 support | T41 |
| 48.1-48.3 | Indicative price (RM3.5M) acknowledged | **NOTED** | Reference only; actual quote in Appendix D | D |
| 49.1-49.2 | IP assignment to MCMC | **COMPLY** | Full IP transfer upon CFA | - |
| 50.1-50.2 | Standby availability, comprehensive quotation | **COMPLY** | Ad-hoc support + 67-month quotation | D |

---

## VALUE ADDED SERVICES (VAS)

### Part 1: Software & Innovation (RM300,000 Value)

| # | VAS Item | Value (RM) |
|---|----------|------------|
| 1 | AI-Powered Document Intelligence | 45,000 |
| 2 | Predictive Analytics Dashboard | 35,000 |
| 3 | Mobile Responsive Self-Service | 40,000 |
| 4 | Chatbot Virtual Assistant | 30,000 |
| 5 | Advanced Data Visualization | 25,000 |
| 6 | Automated Reconciliation Engine | 35,000 |
| 7 | Document Version Control | 20,000 |
| 8 | Bulk Upload Capability | 15,000 |
| 9 | Notification Engine | 25,000 |
| 10 | API Gateway Management | 30,000 |

### Part 2: Support & Consultative (RM260,000 Value)

| # | VAS Item | Value (RM) |
|---|----------|------------|
| 1 | Executive Dashboard | 25,000 |
| 2 | Change Management Workshop | 35,000 |
| 3 | Process Optimization Review | 20,000 |
| 4 | System Health Monitoring | 30,000 |
| 5 | User Adoption Metrics | 15,000 |
| 6 | Knowledge Base Portal | 20,000 |
| 7 | Annual System Health Check | 25,000 |
| 8 | Disaster Recovery Testing | 30,000 |
| 9 | Regulatory Compliance Updates | 25,000 |
| 10 | Strategic Consultation | 35,000 |

**TOTAL VAS VALUE: RM560,000** (No additional cost)

---

## CERTIFICATION

We hereby certify that:

1. All responses are true and accurate to the best of our knowledge
2. We have reviewed and understood all requirements in Section 5
3. We possess capability, resources, and expertise to deliver
4. Supporting evidence referenced is authentic and verifiable
5. We agree to be bound by this Statement upon contract award

**Submitted by:**

_______________________________  
Authorized Signatory

Company Name: _______________________________

Date: _______________________________

Company Stamp:

---

*Revised Compliance Technical Schedule - TSH-2607*
