# TSH-2607: COMPLIANCE TECHNICAL SCHEDULE
## Statement of Compliance to Scope of Work and Specification

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Project:** Universal Service Provision (USP) Claims Management System (UCMS)  
**Date:** February 2026  

---

## SECTION 40: BACKGROUND

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 40.1 | MCMC manages USP projects and financials involving internal departments and external DUSP entities | **COMPLY** | Understood. Our solution is designed specifically for multi-stakeholder environments with role-based access distinguishing internal MCMC users from external DUSP/contractor users. | - |
| 40.2 | UCMS shall be Oracle-based, integrated with USP Financial System, featuring Digital Signature, RPA, and OCR capabilities | **COMPLY** | We propose an Oracle-based middleware architecture with certified digital signature integration (e.g., MSC TrustSign/Docusign), RPA automation using UiPath/Blue Prism, and OCR processing via Tesseract/AWS Textract for document validation. The system supports 60 internal and 120 external users as specified. | Annex T1: Architecture Diagram |
| 40.3 | Proposed UCMS overview diagram | **COMPLY** | Our proposed architecture follows the high-level diagram structure with web-based frontend, Oracle middleware layer, and secure API integration to USPFS/Oracle EBS. Please refer to system architecture documentation. | Annex T2: System Architecture |
| 40.4 | UCMS serves as single customer-facing digital gateway via MCMC website for end-to-end lifecycle management | **COMPLY** | We will deliver a responsive web application accessible via MCMC portal with SSO integration, providing complete project tracking, submission, verification, approval workflows, and payment processing with full audit trails. | Annex T3: Portal Interface Mockups |

---

## SECTION 41: SCOPE OF WORK

### 41.1.1 SYSTEM ANALYSIS AND DESIGN

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.1.a | Conduct requirements gathering workshops with MCMC (functional and non-functional) | **COMPLY** | Our PRINCE2-based approach includes structured requirements workshops using JAD (Joint Application Development) sessions, documented in approved SRS. We assign a dedicated Business Analyst with 5+ years claims system experience. | Annex T4: Requirements Methodology |
| 41.1.1.b | Develop process flowcharts (swimlane) for each major module | **COMPLY** | We will deliver comprehensive swimlane diagrams for all 10 system modules using BPMN 2.0 notation, validated with MCMC during requirements phase and updated per approved SRS. | Annex T5: Sample Process Flowcharts |
| 41.1.1.c | Develop and submit SRS and SDD | **COMPLY** | Our deliverables include comprehensive System Requirements Specification (SRS) and System Design Document (SDD) following KRISA documentation standards with full traceability matrix. | Annex T6: SRS/SDD Templates |
| 41.1.1.d | Design system architecture with modularity, scalability, integration readiness | **COMPLY** | We propose microservices-based architecture on Oracle Cloud Infrastructure with containerized deployment (Docker/Kubernetes), supporting horizontal scaling and API-first integration design. | Annex T2: Architecture Diagram |
| 41.1.1.e | Define approval workflows and user interface | **COMPLY** | Our solution includes configurable multi-layer approval workflows (min 3 layers as required) with drag-and-drop workflow designer and responsive UI built on React/Angular framework. | Annex T7: Workflow Configurations |

### 41.1.2 SYSTEM DEVELOPMENT (AGILE)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.2.a | Develop using Agile methodology with sprint iterations | **COMPLY** | We employ SCRUM methodology with 2-week sprints, daily standups, sprint planning/reviews with MCMC participation, and backlog grooming sessions. | Annex T8: Agile Project Plan |
| 41.1.2.b | Conduct sprint planning and reviews with MCMC | **COMPLY** | Each sprint includes planning session, mid-sprint review, and sprint demo with MCMC stakeholders. Sprint retrospectives drive continuous improvement. | Annex T8: Sprint Schedule |
| 41.1.2.c | Ensure traceability of business requirements through user stories | **COMPLY** | We maintain full requirements traceability using JIRA/Azure DevOps linking user stories to acceptance criteria and test cases with automated traceability reports. | Annex T9: Traceability Matrix |
| 41.1.2.d | Include processing efficiency, reduced manual workload, data accuracy, transparency, compliance | **COMPLY** | Our solution targets 70% reduction in manual processing, 99.5% data accuracy through automated validations, and full compliance with Malaysian financial regulations and audit requirements. | Annex T10: Efficiency Metrics |
| 41.1.2.e | Full bilingual support (Bahasa Malaysia and English) | **COMPLY** | Complete i18n implementation with language toggle across all modules. All UI labels, reports, notifications, and documentation available in both languages with Malaysian date/number formats. | Annex T11: Bilingual Interface Samples |

### 41.1.3 SYSTEM MODULES (WEB APPLICATION)

#### 1. MASTER DATA (Digital Signature, RPA and OCR)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.1.a-d | Master Data Module with centralized framework, data ownership, validation rules, USPFS integration | **COMPLY** | Centralized master data hub with Oracle EBS integration via secure APIs, featuring data governance workflows, validation rules engine, and automated synchronization with USPFS. | Annex T12: Master Data Architecture |
| 41.1.3.1.d.i | Approved Universal Service Plan/Project ID creation | **COMPLY** | Automated Project ID generation with hierarchical structure (4-tier: Project → Sub-Project → Cluster → Site) with digital repository and cross-referencing capabilities. | Annex T13: ID Structure Diagram |
| 41.1.3.1.d.ii | NOA/Contract/Sub Project ID management | **COMPLY** | NOA recording with automated validation against USPFS, contract document management with OCR extraction, and Sub Project ID creation linked to parent Project ID. | Annex T14: NOA Workflow |
| 41.1.3.1.d.iii | Variation Order (VO) tracking | **COMPLY** | VO ID creation with scope/cost/timeline tracking, USPFS-linked validation for controlled variations, and integration with claims processing. | Annex T15: VO Process Flow |
| 41.1.3.1.d.iv | Cluster ID generation | **COMPLY** | Unique Cluster ID generation for USP project clusters with streamlined claims tracking and consolidated reporting across related projects. | - |
| 41.1.3.1.d.v | Site ID management | **COMPLY** | Individual site identifier creation within clusters, detailed activity tracking, and consolidated roll-up reporting for cluster-level visibility. | - |
| 41.1.3.1.d.vi | Item ID definition | **COMPLY** | Project deliverable/billable unit definition for budget allocation with claim validation and cost control auditing. | - |
| 41.1.3.1.d.vii | Performance Bonds management | **COMPLY** | Performance bond recording with automated monitoring for expiration/EOT/renewal, validation check integration with USPFS prior to disbursement, and cross-checking against claims. | Annex T16: Bond Management Screen |
| 41.1.3.1.d.viii | Technical Self Declaration | **COMPLY** | DUSP self-declaration capture with validation against NOA milestones, integrated approval workflows, and secure storage for governance/audit. | - |
| 41.1.3.1.d.ix | Extension of Time (EOT) | **COMPLY** | EOT request capture with EOT ID creation, structured approval workflows, and integration with project progress/milestones and claims processing. | - |
| 41.1.3.1.d.x | Litigation tracking | **COMPLY** | Legal dispute recording for all USP projects with status tracking, resolution monitoring, and integration with project/claims modules for legal risk reporting. | - |

#### 2. DUSP, SUBCONTRACTORS & USER MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.2.xi | Secure Account Creation, Delegation & Monitoring | **COMPLY** | Role-based secure account provisioning with MFA, delegation tracking with audit logs, and governance compliance monitoring dashboards. | Annex T17: User Management Module |
| 41.1.3.2.xii | DUSP Account Maintenance | **COMPLY** | DUSP profile management including business registration, bank account info, key personnel records with USPFS integration for payment transactions. | - |
| 41.1.3.2.xiii | Subcontractor Account Maintenance | **COMPLY** | Unique subcontractor ID creation with invoice capture and salient details recording for downstream processing. | - |
| 41.1.3.2.xiv | User Account Maintenance (Internal/External) | **COMPLY** | Comprehensive user lifecycle management (create, update, suspend, terminate) with workflow continuity assurance and approval matrix integration. | - |
| 41.1.3.2.xv | User Matrix | **COMPLY** | Comprehensive role-based access control (RBAC) matrix defining all internal/external user permissions with segregation of duties enforcement and governance audit capabilities. | Annex T18: RBAC Matrix |

#### 3. BUDGET MANAGEMENT (Digital Signature, RPA and OCR)

| Para | Requirement | Remarks | Response | Annex |
|------|-------------|---------|----------|-------|
| 41.1.3.3.a-d | Budget Module with approved budgets, capped costs, site costing, BOQ, USPFS integration | **COMPLY** | Comprehensive budget management with Oracle EBS integration, automated variance monitoring, and workflow-governed budget changes. | Annex T19: Budget Module Design |
| 41.1.3.3.d.i | Financial Control | **COMPLY** | Automated financial control enforcement comparing approved capped cost vs proposed expenditure, physical vs financial milestones with integrated alerts. | - |
| 41.1.3.3.d.ii | Approved Capped Cost | **COMPLY** | Capped cost listing with automated validation against USPFS, claim submission validation, and alert generation for approaching/exceeding limits. | - |
| 41.1.3.3.d.iii | Site Costing | **COMPLY** | Detailed site-level cost capture with reconciliation capabilities between budget and subsidiary ledgers. | - |
| 41.1.3.3.d.iv | Bill of Quantity (BOQ) | **COMPLY** | Itemized BOQ maintenance with quantity/cost definitions, claim validation against BOQ, and automated linkage to project deliverables. | - |
| 41.1.3.3.d.v | Cost Component | **COMPLY** | Standardized cost category tracking (preliminaries, CME works, software cost, shared cost) with allocation capabilities and analysis reporting. | - |

#### 4. CLAIMS MANAGEMENT (Digital Signature, RPA and OCR)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.4.a-d | Claims Module for major contributors, advance, quarterly, yearly claims with automated validations | **COMPLY** | End-to-end claims processing with automated rule-based validation, milestone verification, and integration with Oracle/banking for advance claims. | Annex T20: Claims Workflow |
| 41.1.3.4.d.i | Invoice to MCMC (USPFS) | **COMPLY** | Submission ID generation upon master invoice submission with USPFS integration, validation against approved capped cost, and real-time status reconciliation. | - |
| 41.1.3.4.d.ii | Financial Self Declaration / CEO Declaration | **COMPLY** | CEO declaration capture for claim authenticity with integrated approval workflows and secure storage as governance records. | - |
| 41.1.3.4.d.iii | Advance/Quarterly/Major Contributor Claim | **COMPLY** | Processing with contractual validation, performance bond safeguards, consolidated quarterly reporting, and automated advance recovery tracking. | - |
| 41.1.3.4.d.iv | Yearly Claim | **COMPLY** | Subsidiary ledger concept for annual claim tracking with built-in auditor template, verification against supporting documents, and EOT request processing with official letter generation. | Annex T21: Yearly Claim Template |
| 41.1.3.4.d.v | Auditors' Declaration | **COMPLY** | Independent auditor verification capture as compliance checkpoint before disbursement with secure storage and retrieval. | - |
| 41.1.3.4.d.vi | Auditors' Working Template | **COMPLY** | Standardized template for audit review with consistency across projects and linkage to claims for traceability. | - |
| 41.1.3.4.d.vii | Supporting Document | **COMPLY** | Upload and management of POs, invoices, payment advice, receipts, reports with validation, secure archival, and audit retrieval. | - |

#### 5. PAYMENT PROCESSING (Digital Signature)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.5.a-d | Payment Processing with memo approvals, voucher generation, digital signatures, Oracle integration | **COMPLY** | Secure payment workflow with embedded digital signatures (min 3 layers), automated voucher posting to Oracle EBS, and complete audit trails. | Annex T22: Payment Workflow |
| 41.1.3.5.d.i | Memorandum – Payment Requisition (Preparation) | **COMPLY** | Built-in configurable templates for Advance, Quarterly/Major Contribution, and Yearly Claims with customization capabilities. | - |
| 41.1.3.5.d.ii | Memorandum – Approval (Digital Signature) | **COMPLY** | Multi-layer approval workflow (minimum 3 layers) with digital signature integration for secure authentication and non-repudiation. | - |
| 41.1.3.5.d.iii | Payment Voucher (USPFS) | **COMPLY** | USPFS integration for voucher generation and accounting entries with real-time reconciliation and secure archival. | - |
| 41.1.3.5.d.iv | Letter to DUSP | **COMPLY** | Built-in acknowledgement letter template with register maintenance, payment advice extraction from principal bank via API, and email delivery with audit logging. | Annex T23: Letter Templates |

#### 6. REPORTS (Digital Signature and RPA)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.6.a-d | Reporting Module with operational/financial/management reporting, dashboards, exception reporting | **COMPLY** | Comprehensive reporting with real-time dashboards, RPA-powered exception detection, and automated report distribution. | Annex T24: Report Catalog |
| 41.1.3.6.d.i | DUSP Reports | **COMPLY** | Key financial and performance reports for DUSP with integration to overall project/fund dashboards. | - |
| 41.1.3.6.d.ii | Subcontractor Reports | **COMPLY** | Subcontractor performance reports with detailed invoice breakdowns by unique identifiers. | - |
| 41.1.3.6.d.iii | Payment Reports | **COMPLY** | Approved/executed payment reports with USPFS reconciliation and status tracking for audit. | - |
| 41.1.3.6.d.iv | Project Progress Reports | **COMPLY** | Project status, deliverables, and milestone completion reporting for monitoring purposes. | - |
| 41.1.3.6.d.v | Financial Progress Reports | **COMPLY** | Fund utilization and financial performance reports with budget vs actual comparison. | - |
| 41.1.3.6.d.vi | Budget Reports | **COMPLY** | Budget allocation, usage, and remaining capped cost reports with 5-year forecast template and variance analysis. | - |
| 41.1.3.6.d.vii | Exception Reports | **COMPLY** | Automated exception highlighting with RPA-powered anomaly detection and escalation workflows. | - |

#### 7. DASHBOARD FUNCTION (RPA)

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.7.a-b | Dashboard with real-time operational/financial/compliance views, RPA consolidation | **COMPLY** | RPA-powered dashboards consolidating multi-source data with actionable insights and proactive monitoring. | Annex T25: Dashboard Designs |
| 41.1.3.7.b.i-xii | All 12 dashboard features | **COMPLY** | All required dashboards implemented: Fund Position, Project Delivery, Payment Disbursement, Compliance & Exception, Integration & System, Project & Site Monitoring, Claims & Payment Status, Budget Utilisation, DUSP/Subcontractor Performance, Security & Backup, Exception & Workflow, Dynamic Excel Export. | - |

#### 8. AUDIT TRAIL

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.8.a-f | Complete secure timestamped log of all activities | **COMPLY** | Comprehensive audit trail capturing all user/system activities with immutable timestamps, metadata capture, protected records, and search/reporting capabilities for governance and compliance verification. | Annex T26: Audit Trail Design |

#### 9. SELF SERVICE APPLICATION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.9.a-f | Self-service for DUSPs, subcontractors, internal users | **COMPLY** | Secure role-based self-service portal with claim submission, document upload, approval/payment tracking, real-time notifications, guided workflows, and centralized authentication with full audit capture. | Annex T27: Self-Service Portal |

#### 10. VALUE ADDED FUNCTION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.3.10.a-g | Intelligent analytics, automation, governance capabilities | **COMPLY** | Advanced analytics with trend analysis, predictive insights, risk detection, RPA automation, smart validations, exception handling, and configurable business rules for long-term scalability. | Annex T28: Value-Added Features |

### 41.1.4 SYSTEM INTEGRATION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.4.a-c | USPFS integration, secure API, Azure AD SSO, Digital Signature, data integrity | **COMPLY** | Secure RESTful API integration with USPFS/Oracle EBS, Azure AD SSO implementation, certified digital signature integration, and end-to-end encryption for data integrity and synchronization. | Annex T29: Integration Architecture |

### 41.1.5 AI-POWERED DOCUMENT VALIDATION AND FRAUD DETECTION

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.5.a-j | AI/ML document analysis, OCR, fraud detection, tampering detection | **COMPLY** | AI-powered document validation using ML models for OCR extraction, tampering/forgery detection, duplicate identification, and fraud pattern recognition with configurable thresholds and audit logging. | Annex T30: AI/ML Architecture |

### 41.1.6 SECURITY AND COMPLIANCE

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.6.a | Azure AD SSO, multi-level access control, encryption | **COMPLY** | Enterprise security with Azure AD SSO, role-based access control (RBAC), AES-256 encryption at rest, TLS 1.3 in transit, and compliance with Malaysian data protection regulations. | Annex T31: Security Framework |

### 41.1.7 SYSTEM TESTING AND ACCEPTANCE

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.7.a-c | UAT, FAT, SIT phases with bug fixing | **COMPLY** | Comprehensive 3-phase testing approach with documented test plans, MCMC participation, defect tracking, and resolution within agreed timelines. | Annex T32: Testing Strategy |

### 41.1.8 PENETRATION TESTING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.8.a-d | Pentest by recognized company, Blackbox/Whitebox, WAPT, signed report | **COMPLY** | Third-party penetration testing by certified CREST/OWASP testing firm including Blackbox and Whitebox testing, WAPT with full vulnerability assessment, and signed executive report with remediation evidence. | Annex T33: VAPT Plan |

### 41.1.9 CHANGE MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.9.a-c | Change plan documentation, Steering Committee/CAB approval, as-is/to-be analysis | **COMPLY** | Structured change management with documentation, checklist, and reports. Pre Go-Live: Steering Committee approval. Post Go-Live: CAB approval. Includes as-is/to-be process mapping and resource allocation planning. | Annex T34: Change Management Plan |

### 41.1.10 DEPLOYMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.10.a-b | Staging/production deployment, Go-Live commissioning | **COMPLY** | Phased deployment on MCMC-compliant hosting with staging environment for UAT, production deployment with zero-downtime approach, and Go-Live commissioning with data validation. | Annex T35: Deployment Plan |

### 41.1.11 DOCUMENTATION AND HANDOVER

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.11.a-c | Technical documentation, user manuals, training materials, source code handover | **COMPLY** | Complete documentation package including technical docs, administrator/end-user manuals, training materials, and full source code handover upon CFA issuance as per intellectual property requirements. | Annex T36: Documentation Plan |

### 41.1.12 BACKUP AND RESTORE REQUIREMENTS

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.12.a-c | Backup storage recommendation, procedures, daily/weekly/monthly/yearly schedules | **COMPLY** | Comprehensive backup strategy with automated daily incremental, weekly full, monthly archival, and yearly retention backups. Includes documented restoration procedures with RPO/RTO definitions. | Annex T37: Backup & Recovery Plan |

### 41.1.13 TRAINING

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.13.a-e | User manuals, training materials, end-user training, feedback collection, knowledge transfer | **COMPLY** | Comprehensive training program with manuals, materials, hands-on sessions for administrators and end-users, feedback-driven enhancements during warranty, and full knowledge transfer including product, system admin, and infrastructure training. | Annex T38: Training Plan |

### 41.1.14 LICENSE MANAGEMENT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.14.a-f | Software licensing, 60 internal + 180-250 external user licenses, application server, reporting tool, integration tools, customization | **COMPLY** | Complete licensing proposal including Oracle database, application server (WebLogic/Tomcat), reporting tool (Oracle BI/Power BI), integration middleware, digital signature licenses, and 250 user licenses (60 internal + 190 external) with customization feasibility. | Annex T39: License Schedule |

### 41.1.15 POST-IMPLEMENTATION SUPPORT

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 41.1.15.a-c | 12 months warranty + 36 months extended support, Resident Engineer, SLA compliance | **COMPLY** | 48-month total support (12 months warranty + 36 months extended) with Resident Engineer stationed at MCMC HQ, 24/7 on-call support, and adherence to specified SLAs: 99.9% uptime, 30-min response for Critical/High, 4-hour resolution Critical, with monthly performance reports. | Annex T40: Support Plan |

---

## SECTION 42-50: OTHER REQUIREMENTS

| Para | Requirement | Response | Remarks | Annex |
|------|-------------|----------|---------|-------|
| 42.1 | Project kick-off and progress meetings, MoM | **COMPLY** | Structured project governance with kick-off session, weekly sprint reviews, monthly steering committee meetings, and documented minutes of meeting for all sessions. | - |
| 42.2 | Dedicated Project Manager | **COMPLY** | PMP/PRINCE2 certified Project Manager with 7+ years IT/financial system experience assigned full-time for coordination, stakeholder engagement, and issue escalation. | Annex H: CV |
| 43.1 | Key personnel (PM, Solution Architect, System Analyst, UI/UX, Developer, QA, Security) | **COMPLY** | All required key personnel provided with qualifications and experience as specified in Table 4. Full CVs attached in Appendix H. | Annex H: Personnel CVs |
| 43.2-43.3 | Qualified personnel, CV submission | **COMPLY** | All personnel meet minimum experience requirements. Comprehensive CVs provided in Appendix H. | Annex H |
| 44.1 | Equipment and software supply | **COMPLY** | All development, testing, and deployment equipment, licensed software, cloud infrastructure, and third-party services provided at our cost. | - |
| 45.1 | Past project experience (last 5 years) | **COMPLY** | Detailed project experience provided in Appendix H with client references, project values, and relevance to claims/financial systems. | Annex H: Experience |
| 46.1-46.3 | Reports and presentations, detailed documentation | **COMPLY** | All required reports, presentations, and component documentation (timeline, design, hardware, software, license) delivered within specified timelines. | - |
| 47.1-47.2 | 67 months duration, milestones | **COMPLY** | Project delivery within 67 months: 16 months development, 3 months testing, 12 months warranty, 36 months extended support. Detailed timeline with milestones provided. | Annex T41: Project Timeline |
| 48.1-48.3 | Indicative price acknowledgment | **NOTED** | Indicative price of RM3,500,000 noted as reference only. Our comprehensive quotation provided in Financial Submission (Appendix D). | Appendix D |
| 49.1-49.2 | Intellectual property assignment | **COMPLY** | Full assignment of all customizations, source code, and documentation to MCMC upon CFA issuance. All IP rights transferred as stipulated. | - |
| 50.1-50.2 | Standby availability, comprehensive quotation | **COMPLY** | Team available for ad-hoc queries with timely response. Comprehensive 67-month implementation and support quotation provided in Appendix D. | Appendix D |

---

## VALUE ADDED SERVICES (VAS) FRAMEWORK

In addition to core requirements, we propose the following **10+10 Value Added Services** at **No Additional Cost**:

### Part 1: Software & Innovation (10 Items)

| # | VAS Item | Description | Value (RM) |
|---|----------|-------------|------------|
| 1 | AI-Powered Document Intelligence | Advanced ML models for document classification and data extraction beyond basic OCR | 45,000 |
| 2 | Predictive Analytics Dashboard | Trend forecasting for claims patterns and budget utilization using historical data | 35,000 |
| 3 | Mobile Responsive Self-Service | Native mobile app or PWA for DUSP on-the-go access | 40,000 |
| 4 | Chatbot Virtual Assistant | AI-powered chatbot for user queries and guided claim submission | 30,000 |
| 5 | Advanced Data Visualization | Interactive charts, graphs, and geospatial mapping for project monitoring | 25,000 |
| 6 | Automated Reconciliation Engine | RPA-powered automated reconciliation between UCMS and USPFS | 35,000 |
| 7 | Document Version Control | Full versioning for all uploaded documents with comparison capabilities | 20,000 |
| 8 | Bulk Upload Capability | Excel/CSV bulk upload for mass data entry with validation | 15,000 |
| 9 | Notification Engine | Multi-channel alerts (email, SMS, in-app) for deadlines and approvals | 25,000 |
| 10 | API Gateway Management | Centralized API management portal for integration monitoring | 30,000 |
| | **Part 1 Subtotal** | | **300,000** |

### Part 2: Support & Consultative (10 Items)

| # | VAS Item | Description | Value (RM) |
|---|----------|-------------|------------|
| 1 | Executive Dashboard | C-level summary dashboard with KPIs and trend indicators | 25,000 |
| 2 | Change Management Workshop | Structured organizational change management program | 35,000 |
| 3 | Process Optimization Review | Quarterly business process improvement recommendations | 20,000 |
| 4 | System Health Monitoring | 24/7 proactive system monitoring with alerting | 30,000 |
| 5 | User Adoption Metrics | Analytics on user engagement and system utilization | 15,000 |
| 6 | Knowledge Base Portal | Self-service knowledge base with FAQs and guides | 20,000 |
| 7 | Annual System Health Check | Comprehensive annual technical assessment | 25,000 |
| 8 | Disaster Recovery Testing | Bi-annual DR drill and failover testing | 30,000 |
| 9 | Regulatory Compliance Updates | Updates to maintain compliance with changing regulations | 25,000 |
| 10 | Strategic Consultation | Quarterly strategic review sessions with senior architects | 35,000 |
| | **Part 2 Subtotal** | | **260,000** |
| | **TOTAL VAS VALUE** | | **RM560,000** |

---

## ANNEXURE CROSS-REFERENCE INDEX

| Annex ID | Description | Location |
|----------|-------------|----------|
| T1 | Architecture Diagram | Part 2, Section 3 |
| T2 | System Architecture | Part 2, Section 3 |
| T3 | Portal Interface Mockups | Part 2, Section 4 |
| T4 | Requirements Methodology | Part 2, Section 5 |
| T5 | Sample Process Flowcharts | Part 2, Section 5 |
| T6 | SRS/SDD Templates | Part 2, Section 5 |
| T7 | Workflow Configurations | Part 2, Section 6 |
| T8 | Agile Project Plan | Part 2, Section 7 |
| T9 | Traceability Matrix | Part 2, Section 5 |
| T10 | Efficiency Metrics | Part 2, Section 8 |
| T11 | Bilingual Interface Samples | Part 2, Section 4 |
| T12 | Master Data Architecture | Part 2, Section 9 |
| T13 | ID Structure Diagram | Part 2, Section 9 |
| T14 | NOA Workflow | Part 2, Section 9 |
| T15 | VO Process Flow | Part 2, Section 9 |
| T16 | Bond Management Screen | Part 2, Section 9 |
| T17 | User Management Module | Part 2, Section 9 |
| T18 | RBAC Matrix | Part 2, Section 9 |
| T19 | Budget Module Design | Part 2, Section 9 |
| T20 | Claims Workflow | Part 2, Section 9 |
| T21 | Yearly Claim Template | Part 2, Section 9 |
| T22 | Payment Workflow | Part 2, Section 9 |
| T23 | Letter Templates | Part 2, Section 9 |
| T24 | Report Catalog | Part 2, Section 9 |
| T25 | Dashboard Designs | Part 2, Section 9 |
| T26 | Audit Trail Design | Part 2, Section 9 |
| T27 | Self-Service Portal | Part 2, Section 9 |
| T28 | Value-Added Features | Part 2, Section 10 |
| T29 | Integration Architecture | Part 2, Section 11 |
| T30 | AI/ML Architecture | Part 2, Section 11 |
| T31 | Security Framework | Part 2, Section 12 |
| T32 | Testing Strategy | Part 2, Section 13 |
| T33 | VAPT Plan | Part 2, Section 13 |
| T34 | Change Management Plan | Part 2, Section 14 |
| T35 | Deployment Plan | Part 2, Section 15 |
| T36 | Documentation Plan | Part 2, Section 16 |
| T37 | Backup & Recovery Plan | Part 2, Section 17 |
| T38 | Training Plan | Part 2, Section 18 |
| T39 | License Schedule | Part 2, Section 19 |
| T40 | Support Plan | Part 2, Section 20 |
| T41 | Project Timeline | Part 2, Section 21 |
| H | Personnel CVs & Experience | Appendix H |

---

## CERTIFICATION

We hereby certify that:

1. All responses in this Statement of Compliance are true and accurate to the best of our knowledge
2. We have thoroughly reviewed and understood all requirements in Section 5 of the Tender Document
3. We possess the capability, resources, and expertise to deliver the Work as specified
4. All supporting evidence referenced in the Annexures is authentic and verifiable
5. We agree to be bound by this Statement of Compliance upon contract award

---

**Submitted by:**

_______________________________
Authorized Signatory

Company Name: _______________________________

Date: _______________________________

Company Stamp:
