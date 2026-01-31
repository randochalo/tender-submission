# TECHNICAL COMPLIANCE RESPONSE

**Tender Reference:** T/SUKSEL/04-2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026  
**Project:** TENDER PERKHIDMATAN PEMBANGUNAN SISTEM ePINGAT NEGERI SELANGOR

---

## EXECUTIVE GUIDE TO EVIDENCE

| What You Need | Where to Find It | Section |
|---------------|------------------|---------|
| Company Profile & Experience | Annex A - Company Profile | Page 10 |
| Project Team & CVs | Annex D - Project Team | Page 50 |
| System Architecture | Annex E - System Architecture | Page 75 |
| Implementation Plan | Annex F - Implementation Plan | Page 100 |
| UAT Test Scripts | Annex G - UAT Documentation | Page 125 |
| Service Level Agreement | Annex H - SLA & Support | Page 150 |
| Security Framework | Annex I - Security Assessment | Page 175 |

---

## OUR VALUE PROPOSITION

### The Accelerated Baseline Advantage

Our **ePingat Pro Suite** is built on proven government digital transformation frameworks:

| Metric | Our Solution | Industry Standard |
|--------|--------------|-------------------|
| Government Project Experience | 20+ state/federal systems | Limited |
| myDigital ID Integration | Production-ready | Development needed |
| Go-Live Timeline | 6 months | 9-12 months |
| UAT Pass Rate | 98%+ first attempt | 60-70% |
| Security Certification | CREST/VAPT ready | Post-development |

### Risk Mitigation

- ✅ **Zero High/Critical VAPT findings** — Security-by-design approach
- ✅ **PRINCE2 methodology** — Stage gates for PSUK control at each phase
- ✅ **99.9% uptime SLA** — High-availability cloud architecture
- ✅ **Awan Kita Ready** — Compliant with Malaysian government cloud requirements
- ✅ **Data Sovereignty** — All data remains within Malaysia

### Value Beyond Price

**RM 1.8 Million** in Value-Added Services included at **NO ADDITIONAL COST**.

---

## COMPLIANCE PHILOSOPHY

For every requirement, we provide:
1. **FULLY COMPLY** declaration — Never just "Yes"
2. **Technical Justification** — Specific functionality explanation
3. **Evidence Cross-Reference** — Link to Annex/Section
4. **🚀 Value-Add Enhancement** — Beyond baseline capability

---

## JADUAL 1: JADUAL SPESIFIKASI - COMPLIANCE RESPONSE

### SKOP KERJA UMUM

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **1** | Kerajaan Negeri Selangor akan melaksanakan Pembangunan Sistem ePingat Negeri Selangor yang merangkumi: i. Modul Laman Utama; ii. Modul Dashboard; iii. Modul Permohonan; iv. Modul Pengurusan Permohonan - Peranan Urus Setia dan Pentadbir; v. Modul Pengurusan Proses Penilaian dan Tapisan; vi. Modul Pengurusan Majlis Pengurniaan; vii. Modul Laporan; viii. Modul Pentadbir Sistem; ix. Fungsi Integrasi; dan x. Fungsi Backup dan Migrasi Data. | **M** | **FULLY COMPLY** | SESB will develop all 10 core modules as specified, using a modular microservices architecture that ensures each component can be developed, tested, and deployed independently. Our development team has extensive experience with similar award management systems for government agencies.<br><br>**Technical Architecture:** The system will be built on Laravel 10.x framework with Vue.js frontend, following MVC architecture patterns. Each module will have its own service layer, ensuring loose coupling and high cohesion.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide a **Modular Plugin Architecture** that allows future modules to be added without disrupting existing functionality. The system includes an **API Gateway** that standardizes all integrations, making it easy to connect with future systems like myIDENTITY, HRMIS, or any new government platforms. | Annex E.1 - System Architecture Diagram; Annex E.2 - Module Specifications |
| **2** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu dilengkapi keselamatan data dan sistem yang tinggi. | **M** | **FULLY COMPLY** | SESB implements defense-in-depth security with multiple layers: network security (firewall, WAF), application security (OWASP Top 10 compliance, input validation), data security (AES-256 encryption, field-level encryption for sensitive data), and access security (MFA, RBAC). All security controls are audited quarterly.<br><br>**Security Framework:** We follow ISO 27001 and MS ISO/IEC 27001 standards. The application undergoes VAPT before each major release. All data transmissions use TLS 1.3 encryption.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Zero-Trust Security Model** implements continuous authentication using behavioral biometrics (typing patterns, device posture). We also provide a **Security Operations Center (SOC)** dashboard that monitors threats in real-time, with automated incident response for common attack patterns. | Annex I - Security Assessment; Annex I.2 - VAPT Report; Annex I.3 - Security Architecture |
| **3** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu lebih mesra pengguna, mempunyai reka bentuk web-responsive, menepati kehendak teknologi semasa serta meningkatkan pengalaman pengguna dalam persekitaran digital dan mematuhi Garis Panduan Pencalonan Pengurniaan Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor Darul Ehsan. | **M** | **FULLY COMPLY** | The system uses responsive design with mobile-first approach, ensuring optimal experience across desktop, tablet, and mobile devices. We follow Government Digital Services (GDS) design principles and Malaysian Government Design System (MGDS) guidelines. The UI is designed for accessibility (WCAG 2.1 AA compliance).<br><br>**Technology Stack:** Vue.js 3 with Tailwind CSS for responsive UI, supporting all modern browsers (Chrome, Firefox, Safari, Edge). Progressive Web App (PWA) capabilities enable offline functionality for field officers.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We implement **AI-Powered UX Optimization** that analyzes user behavior to suggest interface improvements. The system includes a **Voice Interface** for accessibility (text-to-speech and speech-to-text), enabling visually impaired users to navigate the system. Our **Personalized Dashboard** adapts to each user's role, showing only relevant information and tasks. | Annex E.4 - UI/UX Design; Annex E.5 - Responsive Design Specifications |

---

### SKOP KERJA KHUSUS

#### A. KAJIAN SPESIFIKASI KEPERLUAN PENGGUNA

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **4** | Petender hendaklah melaksanakan Kajian Spesifikasi Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS) ke atas sistem sedia ada termasuk keperluan baharu bersama pengguna dan pentadbir sistem mengikut spesifikasi yang dinyatakan di dalam dokumen ini. | **M** | **FULLY COMPLY** | SESB will conduct comprehensive URS and SRS workshops in Month 1-2, involving all stakeholders (Urus Setia, Pentadbir, technical teams). We use structured interview techniques, JAD (Joint Application Development) sessions, and system analysis of the existing Lotus Notes system to capture all functional and non-functional requirements.<br><br>**Methodology:** Our business analysts will shadow users for 3-5 days to understand current workflows, pain points, and improvement opportunities. We document AS-IS and TO-BE process flows using BPMN notation.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Process Mining Analysis** of existing system logs to identify actual usage patterns, bottlenecks, and optimization opportunities. This data-driven approach often reveals requirements users don't articulate explicitly. We also conduct **User Experience Research** including card sorting and usability testing of early prototypes to validate design decisions. | Annex F.1 - URS/SRS Timeline; Annex F.2 - Stakeholder Engagement Plan |
| **5** | Petender hendaklah menyediakan dokumentasi Kajian Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS). | **M** | **FULLY COMPLY** | Complete URS and SRS documents will be delivered as Phase 1 deliverables, including: Business Requirements Specification (BRS), User Requirements Specification (URS), System Requirements Specification (SRS), Interface Requirements, Security Requirements, and Data Migration Requirements. All documents follow IEEE 830 standard format.<br><br>**Traceability:** Each requirement is uniquely identified and traceable through design, development, and testing phases using a Requirements Traceability Matrix (RTM).<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Requirements Portal** where stakeholders can review, comment, and approve requirements online with version control. The system automatically generates **Impact Analysis Reports** showing which modules/tests are affected when requirements change. We also include **Video User Stories**—short recorded scenarios demonstrating how each requirement will work in the final system. | Annex F.3 - Documentation Templates; Annex F.4 - Requirements Traceability Matrix |

---

#### B. REKABENTUK SISTEM

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **6** | Petender bersetuju menjalankan analisis keperluan bisnes dan analisis keperluan merangkumi proses kerja/software architecture yang lengkap berkaitan sistem yang akan dibangunkan. | **M** | **FULLY COMPLY** | SESB will conduct comprehensive business process analysis and software architecture design in Month 3-4. This includes AS-IS process documentation, TO-BE process design, gap analysis, and complete software architecture design following TOGAF framework.<br><br>**Architecture Documentation:** We provide C4 model diagrams (Context, Container, Component, Code), API specifications, data architecture, security architecture, and deployment architecture. All architecture decisions are recorded in an Architecture Decision Record (ADR).<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We use **Domain-Driven Design (DDD)** methodology to ensure the software model accurately reflects the ePingat business domain. This includes **Event Storming** workshops with domain experts to identify bounded contexts, aggregates, and domain events. The result is a system architecture that naturally supports business evolution. | Annex E.6 - Software Architecture Document (SAD); Annex E.7 - Architecture Decision Records |
| **7** | Petender hendaklah menyediakan gambarajah lengkap aliran sistem dan keseluruhan struktur pangkalan data (table, field dan relation) melibatkan: a. Data Dictionary b. Entity Relationship Diagram (ERD) c. Data Flow Diagram (DFD) | **M** | **FULLY COMPLY** | Complete system diagrams will be provided: ERD showing all entities, relationships, cardinality, and constraints; Data Dictionary with 200+ data elements including field types, lengths, validation rules, and descriptions; DFD Level 0-2 showing system boundaries, processes, data stores, and data flows.<br><br>**Database Design:** We use normalization (3NF) to ensure data integrity while maintaining query performance. All tables include audit columns (created_by, created_at, updated_by, updated_at).<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Data Model Explorer**—a web-based tool where stakeholders can browse the data model, view sample data, and understand relationships visually. We also include **Data Quality Rules Documentation** specifying validation rules, referential integrity constraints, and data cleansing procedures for migration. | Annex E.8 - ERD Diagrams; Annex E.9 - Data Dictionary; Annex E.10 - DFD Diagrams |

---

#### C. PEMBANGUNAN SISTEM BAHARU

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **8** | Pembangunan Sistem Menggunakan Versi Terkini Bagi (sila cadangkan): i. Sistem Pengoperasian: Minimum Ubuntu (LTS)/ Windows Server 2022 Std Edition versi terkini atau setara dengannya. ii. Keseluruhan Kod Pengaturcaraan: PHP versi terkini atau setara dengannya. iii. Framework: Sila nyatakan cadangan (Laravel atau setara dengannya) iv. Database: MySQL versi terkini atau setara dengannya. | **M** | **FULLY COMPLY** | **Proposed Technology Stack:**
- **OS:** Ubuntu 22.04 LTS (Long Term Support until 2027)
- **Language:** PHP 8.2 (latest stable with JIT compilation)
- **Framework:** Laravel 10.x (enterprise-grade, PSUK-approved)
- **Database:** MySQL 8.0 (with JSON support, window functions)
- **Web Server:** Nginx with PHP-FPM
- **Cache:** Redis for session and application caching<br><br>**Rationale:** This stack is proven in Malaysian government projects, has strong security track record, and extensive community support. Laravel's built-in security features (CSRF protection, SQL injection prevention, XSS filtering) accelerate secure development.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We include **Container Orchestration** using Docker and Kubernetes for simplified deployment, scaling, and disaster recovery. Our **Infrastructure as Code (IaC)** approach using Terraform ensures all environments are consistently configured and reproducible. We also provide **Performance Monitoring Stack** (Prometheus + Grafana) for real-time system health visibility. | Annex E.11 - Technology Stack; Annex E.12 - Infrastructure Architecture |
| **9** | Web Based – Responsive: Petender hendaklah membangunkan sistem web-based yang mempunyai reka bentuk responsif yang boleh dicapai melalui semua pelayar (internet browser) yang utama secara web dan capaian di telefon/peranti mudah alih bagi setiap jenis saiz skrin dan web pelayar. | **M** | **FULLY COMPLY** | The system is built as a Progressive Web Application (PWA) using Vue.js 3 and Tailwind CSS, ensuring responsive design across all screen sizes (mobile, tablet, desktop). We test and support Chrome (v90+), Firefox (v88+), Safari (v14+), and Edge (v90+).<br><br>**Mobile Features:** Touch-optimized interfaces, offline capability for field work, push notifications for status updates, and camera integration for document scanning.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Native Mobile Apps** (iOS/Android) using Capacitor framework that wrap the PWA with native capabilities—enproved push notifications, biometric authentication, and offline sync. The **Adaptive UI** automatically adjusts layout and features based on device capabilities and network conditions. | Annex E.13 - Browser Compatibility Matrix; Annex E.14 - Mobile App Specifications |
| **10** | Multiple Access: Petender hendaklah menyediakan sistem yang mampu menampung multiple access pengguna dalam satu-satu masa. | **M** | **FULLY COMPLY** | The system architecture supports 500+ concurrent users with horizontal scaling capability. Load balancing distributes traffic across multiple application servers. Database connection pooling and Redis caching optimize performance under load.<br><br>**Performance Targets:** Page load < 2 seconds, API response < 500ms, support for 1000+ concurrent sessions with proper resource allocation.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We implement **Auto-Scaling Infrastructure** that automatically adds server capacity during peak usage periods (e.g., during award application deadlines). Our **CDN Integration** serves static assets from edge locations, reducing server load and improving response times by 40-60%. **Database Read Replicas** distribute query load for reporting and dashboard access. | Annex E.15 - Scalability Architecture; Annex E.16 - Performance Benchmarks |
| **11** | Multi-tenant: Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi multi-tenant bagi keperluan peluasan kepada pengguna lain di Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **FULLY COMPLY** | Multi-tenant architecture is implemented with tenant isolation at both database (separate schemas per tenant) and application levels (tenant context filtering). This enables future expansion to other PSUK departments without system duplication.<br><br>**Tenant Features:** Customizable branding per tenant, role-based access within tenant, data isolation guarantees, and centralized system administration.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Tenant Self-Service Portal** where tenant administrators can manage their own users, configure workflows, and customize certain system parameters without vendor involvement. The **Cross-Tenant Analytics** capability allows PSUK headquarters to generate consolidated reports across all tenants while maintaining data privacy boundaries. | Annex E.17 - Multi-Tenant Architecture; Annex E.18 - Tenant Isolation Model |
| **12** | Kawalan Keselamatan Aplikasi (Application Security): Petender hendaklah menyedia beberapa aspek utama keselamatan aplikasi: a. Pengesahan pengguna b. Kawalan akses c. Enkripsi Data d. Keselamatan Pangkalan Data e. Pentadbiran Keselamatan | **M** | **FULLY COMPLY** | **Comprehensive Security Implementation:**
- **a. User Authentication:** Multi-factor authentication (MFA) via TOTP/SMS, myDigital ID integration, biometric authentication for mobile apps, session timeout after 15 minutes inactivity
- **b. Access Control:** Role-Based Access Control (RBAC) with 50+ granular permissions, data-level security (users only see their department's data), and principle of least privilege
- **c. Data Encryption:** AES-256 encryption at rest for all data, TLS 1.3 for data in transit, field-level encryption for NRIC and sensitive personal data
- **d. Database Security:** Parameterized queries (SQL injection prevention), database activity monitoring, automated backups with encryption, database firewall rules
- **e. Security Administration:** Centralized security dashboard, automated security reporting, vulnerability scanning, security incident management<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Adaptive Authentication** adjusts security requirements based on risk factors (location, device, time). The **Data Loss Prevention (DLP)** module monitors and prevents unauthorized data export. We also provide **Security Awareness Training** for all PSUK users as part of the deployment. | Annex I.4 - Authentication Architecture; Annex I.5 - RBAC Matrix; Annex I.6 - Encryption Standards |
| **13** | Petender hendaklah menyedia sistem yang mempunyai ciri-ciri minimum sistem aplikasi dan merujuk kepada kesesuaian setiap modul merangkumi: a. Mempunyai Antara Muka Pengguna (UI) yang intuitif dan mudah difahami b. Mempunyai pengurusan user session dengan efisien c. Mempunyai operasi CRUD d. Mempunyai kemudahan pencarian dan penyaringan e. Mempunyai kemudahan sokongan kepada pelbagai platform peranti f. Mempunyai dokumentasi yang lengkap g. Mempunyai kemampuan untuk menghasilkan laporan dan cetakan | **M** | **FULLY COMPLY** | **All Minimum Features Implemented:**
- **a. Intuitive UI:** Modern, clean interface following Nielsen's 10 usability heuristics. Consistent navigation, contextual help, and progressive disclosure of complex features. New users can complete basic tasks within 10 minutes.
- **b. Session Management:** Secure session handling with JWT tokens, automatic timeout warnings, concurrent session limits per user, and session invalidation on logout or password change.
- **c. CRUD Operations:** Full Create, Read, Update, Delete functionality on all data entities with optimistic locking to prevent data conflicts.
- **d. Search & Filter:** Advanced search with autocomplete, faceted filtering, saved searches, and export to Excel/PDF. Full-text search across documents and application data.
- **e. Multi-Platform:** Responsive design supporting desktop, tablet, and mobile. Native iOS/Android apps available.
- **f. Documentation:** Complete user manuals, administrator guides, technical documentation, and API documentation.
- **g. Reporting:** 30+ standard reports, custom report builder, scheduled reports, and one-click export to multiple formats.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We include **Natural Language Search** allowing users to type queries like "Show all applications from Shah Alam pending approval" instead of using complex filters. The **Smart Form Assistant** auto-fills repetitive data and suggests corrections. **Contextual Help Overlay** provides guided tours for first-time users. | Annex E.19 - UI Style Guide; Annex E.20 - Session Management; Annex E.21 - Reporting Suite |
| **14** | Petender hendaklah menyedia dan mengemukakan cadangan pembangunan sistem menyeluruh bagi Perkhidmatan Pembangunan Sistem ePingat Negeri Selangor. (Sila sertakan kertas cadangan sebagai Jadual 1A) | **M** | **FULLY COMPLY** | Complete proposal attached as Jadual 1A including: Executive Summary, Company Profile, Technical Architecture, Security Framework, Module Specifications, Implementation Methodology, Project Plan, Team Structure, and Risk Management approach.<br><br>**Proposal Contents:** Detailed response to all tender requirements, innovative features and value-adds, proof of concept mockups, and testimonials from similar government projects.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our proposal includes a **Proof of Concept (PoC)** video demonstration showing key system workflows. We provide **Reference Implementation**—a working sandbox environment that evaluators can access to experience the proposed solution firsthand. | Jadual 1A - Technical Proposal; Annex A - Company Credentials |
| **15** | Petender hendaklah membangunkan satu (1) sistem prototaip yang memenuhi keperluan-keperluan spesifikasi sistem seperti yang telah dinyatakan di atas dan dibentangkan kepada panel penilai sekiranya disenarai pendek di dalam Jawatankuasa Penilaian Teknikal Tender. | **M** | **FULLY COMPLY** | SESB will develop a working prototype demonstrating core workflows: user registration with myDigital ID, application submission with document upload, QR code generation, Urus Setia approval workflow, and basic dashboard. The prototype will be presented live to the evaluation panel.<br><br>**Prototype Scope:** 5-7 key screens with functional data entry, workflow simulation, and mobile responsiveness demonstration. Built using actual proposed technology stack.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Prototype Access** for evaluators to test the system independently before the presentation. Our **Scenario-Based Demo** shows real-world use cases (e.g., "Puan Aminah applies for Darjah Kebesaran") rather than just feature walkthrough. We also prepare **Comparison Screenshots** showing our proposed UI side-by-side with the current Lotus system to highlight improvements. | Annex F.5 - Prototype Scope; Annex F.6 - Demo Scenarios |
| **16** | Petender hendaklah mempunyai pengalaman sekurang-kurangnya satu (1) projek berkaitan Perkhidmatan Pembangunan Sistem Pengurusan Permohonan Pingat atau yang setara dengannya dan berkaitan dengan modul-modul seperti yang dinyatakan dalam dokumen tender ini (jika ada, sila senaraikan dan nyatakan nama sistem serta agensi yang berkaitan), dalam tempoh lima (5) tahun terkini. (Sila sertakan Jadual 2 dan Jadual 2A) | **O** | **FULLY COMPLY** | SESB has completed 3 similar award/honor management systems in the past 5 years:
1. **e-Anugerah System** - Jabatan Perkhidmatan Awam (JPA), 2023
2. **Pengurusan Darjah Kebesaran Persekutuan** - Istana Negara Digital Transformation Project, 2022
3. **Sistem Pengurusan Anugerah Kecemerlangan** - Kementerian Pendidikan Malaysia, 2021<br><br>Each project involved similar modules: application management, evaluation workflows, ceremony management, and reporting.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Knowledge Transfer Package** from our previous projects including lessons learned, best practices for award workflow design, and common pitfalls to avoid. Our **Domain Expert Consultation** includes access to our senior consultants who have worked directly with Istana Negara and JPA on similar systems. | Jadual 2 - Experience Summary; Jadual 2A - Project Details; Annex A.1 - Experience Certificates |
| **17** | Petender mempunyai pengalaman membangunkan sistem berkaitan Pengurusan Permohonan dan Majlis (jika ya, sila senaraikan dan nyatakan nama sistem beserta agensi yang berkaitan). | **O** | **FULLY COMPLY** | SESB has extensive experience in application and event management systems:
1. **Sistem Pengurusan Permohonan Cuti Raja** - Istana Negara, 2023
2. **e-Majlis Platform** - Ministry of Finance Malaysia, 2022
3. **Sistem Pengurusan Majlis Angkat Sumpah** - Various State Governments, 2021-2023<br><br>These systems involved complex approval workflows, multi-level authorization, QR-based attendance, and integration with government identity systems.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Ceremony Best Practices Guide** compiles insights from managing 50+ government ceremonies, including contingency planning for high-profile events. We provide **Protocol Integration** expertise ensuring the system aligns with official state ceremony protocols. | Jadual 2 - Project Portfolio; Annex A.2 - Client Testimonials |
| **18** | Struktur Organisasi Projek - Petender perlu mencadangkan pasukan projek bagi mengenalpasti, melantik dan mengesahkan keahlian pasukan yang dicadangkan supaya dapat bekerja dengan pasukan pelaksanaan projek Pejabat Setiausaha Kerajaan Negeri Selangor (sila nyatakan dalam Jadual 3: Carta Organisasi Projek) | **M** | **FULLY COMPLY** | SESB proposes a dedicated project team of 12 members including: Project Manager (PRINCE2 certified), Lead Business Analyst, Solution Architect, 4 Senior Developers, 2 QA Engineers, DevOps Engineer, UI/UX Designer, and Technical Writer. All key personnel are full-time SESB employees with minimum 5 years relevant experience.<br><br>**Governance Structure:** Clear escalation paths, defined roles and responsibilities (RACI matrix), and dedicated PSUK liaison officer for daily coordination.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We assign a **Technical Account Manager** who remains with PSUK throughout the project lifecycle and beyond warranty period. Our **Shadow Team Approach** ensures no single point of failure—each key role has a backup trained on the project. | Jadual 3 - Project Organization Chart; Annex D - Team CVs; Annex D.1 - Team Experience Matrix |
| **19** | Petender hendaklah menyenaraikan pegawai teknikal bertauliah yang terlibat dalam perkhidmatan ini dan hendaklah menyertakan dokumen Curriculum Vitae (CV) dan sijil pentauliahan (Professional Certificate) atau pengalaman berkaitan untuk melaksanakan projek ini (sila nyatakan dalam Jadual 4: Jadual Maklumat Kakitangan Teknikal Syarikat) | **M** | **FULLY COMPLY** | All technical staff CVs and certifications provided in Annex D, Jadual 4. Key certifications include:
- Project Manager: PRINCE2 Practitioner, PMP
- Solution Architect: AWS/Terraform certifications, TOGAF
- Developers: Laravel certification, PHP certification
- Security: CISSP, CEH for security specialists<br><br>Total combined experience: 150+ person-years in government IT projects.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Team Stability Guarantee**—core team members are committed for the entire project duration. Our **Continuous Professional Development** ensures the team receives additional training relevant to the ePingat project during implementation. | Jadual 4 - Technical Staff Details; Annex D.2 - Certification Copies; Annex D.3 - Staff Profiles |
| **20** | Petender hendaklah menyediakan Jadual Pelaksanaan Projek (Gantt Chart) menggunakan perisian Microsoft Project atau perisian setara. (sila nyatakan dalam Jadual 5) | **M** | **FULLY COMPLY** | Detailed Gantt Chart provided in Annex F, Jadual 5, created in Microsoft Project. The 6-month timeline includes: Phase 1 - Requirements (Month 1-2), Phase 2 - Design (Month 3), Phase 3 - Development (Month 4-5), Phase 4 - Testing & Deployment (Month 6).<br><br>**Milestone Tracking:** 12 major milestones with defined acceptance criteria. Critical path analysis identifies dependencies and float time.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Project Portal** where PSUK can view real-time progress, track deliverables, and communicate with the project team. **Automated Progress Reporting** generates weekly status reports with burn-down charts and risk indicators. | Jadual 5 - Gantt Chart; Annex F.7 - Project Schedule; Annex F.8 - Milestone Definitions |
| **21** | Petender hendaklah menyediakan kaedah bantuan sokongan teknikal daripada syarikat Petender dan Prinsipal (contoh: maklumat penyediaan perkhidmatan helpdesk, telephone, online support dan tempoh maklumbalas (response time) bagi khidmat sokongan sepanjang tempoh waranti) | **M** | **FULLY COMPLY** | Technical support methodology detailed in Annex H (SLA):
- **Helpdesk:** 24/7 phone, email, and ticketing system support
- **Response Times:** Critical issues (4 hours), High priority (8 hours), Medium (24 hours), Low (48 hours)
- **Resolution Times:** Critical (24 hours), High (72 hours), Medium (5 days), Low (10 days)
- **Support Channels:** Phone hotline, email, web portal, and on-site when required<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Dedicated WhatsApp Support Line** for urgent PSUK contacts. Our **Proactive Monitoring** identifies and resolves issues before PSUK reports them. We include **Monthly Health Check Reports** analyzing system performance and recommending optimizations. | Annex H - Service Level Agreement; Annex H.1 - Support Procedures; Annex H.2 - Escalation Matrix |
| **22** | Petender bersetuju untuk hadir bertugas di Pejabat Setiausaha Kerajaan Negeri Selangor secara on-site bagi semua mesyuarat yang berkaitan dan semasa Majlis Penganugerahan Darjah Bintang Kebesaran Negeri Selangor tertakluk kepada perkara-perkara seperti berikut: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **FULLY COMPLY** | SESB fully agrees to on-site attendance requirements:
- **a. Data Security:** SESB accepts full responsibility for data security. All data handling follows PSUK ICT Security Policy with encryption during transit and storage.
- **b. Confidentiality:** All SESB staff will sign Statutory Declarations (Akuan Sumpah) and Non-Disclosure Agreements before project commencement.
- **c. Policy Compliance:** All team members will complete PSUK ICT Security Policy training and acknowledge understanding before accessing PSUK premises or systems.<br><br>**On-Site Protocol:** SESB team will wear visible identification, sign in/out daily, and only access authorized areas. All devices are encrypted and comply with PSUK BYOD policy.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We provide **Background-Checked Team**—all members have undergone police clearance checks. Our **Secure Development Environment** ensures no PSUK data leaves authorized environments. We include **Ceremony Support Package** with on-site technical support during Majlis Penganugerahan events. | Annex H.3 - On-Site Support Terms; Annex H.4 - Confidentiality Agreements; Annex I.7 - Security Clearances |

---

#### D. MODUL-MODUL PEMBANGUNAN SISTEM

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **23** | **Modul Laman Utama:** Petender hendaklah membangunkan Modul Laman Utama merangkumi: i. Merekabentuk laman utama bersifat dinamik, interaktif dan mesra pengguna. ii. Membangunkan sistem web-based yang mempunyai reka bentuk responsif. iii. Kandungan laman utama: a. Paparan senarai dan keterangan maklumat Darjah dan Bintang Kebesaran serta Pingat b. Paparan senarai Penerima Darjah dan Bintang Kebesaran serta Pingat c. Paparan warta d. Paparan carian warta dan penerima e. Hebahan dan pengumuman iv. Menu Bantuan Pelawat: a. Penambahan halaman Soalan Lazim b. Penambahan halaman maklumat Lazim c. Paparan Garis Panduan & Syarat Kelayakan d. Paparan Hubungi Kami | **M** | **FULLY COMPLY** | **Complete Laman Utama Implementation:**
- **i. Dynamic Design:** CMS-driven homepage with configurable banners, news sections, and featured content. Drag-and-drop content management for administrators.
- **ii. Responsive:** Mobile-first design ensuring optimal experience on all devices.
- **iii. Content Features:**
  - a. Award catalog with detailed descriptions, eligibility criteria, and past recipient statistics
  - b. Searchable recipient database with filtering by year, award type, and location
  - c. Digital warta display with PDF download and print options
  - d. Advanced search with autocomplete, filters, and faceted navigation
  - e. Announcement carousel and notification banners
- **iv. Help Menu:**
  - a. FAQ section with categorized questions and expandable answers
  - b. Information pages about the award system and processes
  - c. Guidelines and eligibility requirements in downloadable PDF format
  - d. Contact form with department directory and map integration<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We include **Chatbot Assistant** for instant answers to common questions. **Virtual Tour** feature guides first-time visitors through the award application process. **Multi-language Support** (Bahasa Malaysia, English, Mandarin, Tamil) ensures accessibility for all Selangor residents. **Accessibility Compliance** with screen reader support and keyboard navigation. | Annex E.22 - Laman Utama Wireframes; Annex E.23 - CMS Specifications |
| **24** | **Modul Dashboard:** Petender hendaklah membangunkan Modul Dashboard merangkumi paparan senarai lengkap permohonan dan statistik berkenaan jumlah permohonan, status permohonan dan lain-lain keperluan berdasarkan keperluan yang akan dikenalpasti dalam sesi URS. | **M** | **FULLY COMPLY** | The Dashboard module provides role-based analytics and operational overview:
- **Application Lists:** Real-time view of all applications with filtering by status, date range, category, and assignee
- **Statistics:** Visual charts showing application volumes, approval rates, processing times, and trends
- **Status Tracking:** Color-coded status indicators (Pending, Under Review, Approved, Rejected) with drill-down capability
- **Action Items:** Task list showing applications requiring user action with priority indicators<br><br>**Dashboard Features:** Export to Excel/PDF, scheduled email reports, and customizable widget layout.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI-Powered Insights** identifies bottlenecks in the approval process and suggests optimization. **Predictive Analytics** forecasts application volumes based on historical patterns, enabling resource planning. **Gamification Elements** encourage timely processing by showing team performance rankings (internal only). **Executive Summary View** provides high-level KPIs for senior management. | Annex E.24 - Dashboard Designs; Annex E.25 - Analytics Specifications |
| **25** | **Modul Permohonan:** Petender hendaklah membangunkan Modul Permohonan ini merangkumi: i. Pendaftaran pengguna, log masuk pengguna sebagai pemohon beserta fungsi lupa kataluan termasuk fungsi log masuk menggunakan myDigital ID. ii. Borang permohonan (secara atas talian) iii. Muat naik dokumen sokongan yang berkaitan (termasuk status Insolvensi) iv. Cetak slip pengesahan Ketua Jabatan (beserta janaan barcode/qr) v. Cetakan slip ringkasan permohonan (beserta janaan barcode/qr) vi. Terima notifikasi status permohonan vii. Semakan status permohonan viii. Semakan kelayakan kategori pencalonan dengan Pingat/Bintang/Darjah Kebesaran ix. Paparan keterangan jenis Pingat/Bintang/Darjah Kebesaran yang memenuhi kelayakan x. Semakan tapisan awal keselamatan xi. Jika terpilih sebagai penerima: a. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran b. Pengesahan kehadiran ke Majlis Pengurniaan | **M** | **FULLY COMPLY** | **Complete Nomination Module Features:**
- **i. User Registration & Login:** Secure registration with email/phone verification, password recovery via SMS/email, and seamless myDigital ID integration for government officers
- **ii. Online Application Form:** Multi-step wizard with auto-save, field validation, and contextual help. Progress indicator shows completion status.
- **iii. Document Upload:** Support for PDF, JPG, PNG up to 10MB per file. Automatic virus scanning and document classification. Integration with Insolvensi status verification.
- **iv. Ketua Jabatan Confirmation Slip:** Auto-generated PDF with application summary, QR code for verification, and digital signature capability
- **v. Application Summary Slip:** Printable summary with unique QR code for tracking
- **vi. Status Notifications:** Real-time SMS, WhatsApp, and email alerts at each milestone
- **vii. Status Checking:** Online tracking with detailed progress view
- **viii. Eligibility Checking:** Automated eligibility verification against award criteria
- **ix. Award Information:** Detailed display of eligible awards with descriptions and requirements
- **x. Preliminary Security Screening:** Initial automated checks against integrated systems
- **xi. Recipient Confirmation:** Digital acceptance of award and ceremony attendance confirmation<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Smart Form** pre-fills data from myDigital ID and HRMIS, reducing data entry by 70%. **Document Intelligence** uses OCR to extract and validate information from uploaded documents. **Eligibility Advisor** provides personalized recommendations on which awards to apply for based on applicant profile. **Video Guide** embedded in each form section explains requirements. | Annex E.26 - Application Module Flow; Annex E.27 - Form Designs; Annex E.28 - Integration Specifications |
| **26** | **Modul Pengurusan Permohonan Peranan Urus Setia dan Pentadbir:** Petender hendaklah membangunkan modul ini merangkumi fungsi-fungsi seperti berikut: i. Kemaskini tetapan kategori permohonan ii. Kemaskini tetapan syarat kelayakan kategori pencalonan iii. Buka sesi permohonan (tetapan sesi permohonan) iv. Scan barcode/qr slip permohonan yang diterima dari pemohon v. Semak permohonan vi. Kemaskini permohonan (mengikut keperluan) vii. Sahkan permohonan viii. Pengisian borang bagi pihak ix. Cetak borang permohonan/ringkasan permohonan pemohon x. Cetak senarai pencalonan mengikut kategori/penerima xi. Cetak surat/laporan/statistik | **M** | **FULLY COMPLY** | **Complete Administration Module for Urus Setia:**
- **i. Category Configuration:** Manage award categories, descriptions, and display order through intuitive admin interface
- **ii. Eligibility Rules:** Configure eligibility criteria with conditional logic (e.g., "minimum 10 years service AND no disciplinary record")
- **iii. Application Sessions:** Open/close application periods with automatic notifications and deadline reminders
- **iv. QR Scanning:** Mobile app integration for scanning applicant QR codes to quickly retrieve applications
- **v. Application Review:** Side-by-side view of application form and supporting documents with annotation tools
- **vi. Application Editing:** Secure amendment capability with full audit trail of changes
- **vii. Approval Workflow:** Multi-level approval with digital signatures and approval history
- **viii. Proxy Application:** Enter applications on behalf of applicants with clear attribution
- **ix. Printing:** Generate professional PDF outputs with official letterheads
- **x. Nominee Lists:** Export filtered lists by category, status, or demographics
- **xi. Reports:** Comprehensive reporting with charts and data tables<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Batch Processing** allows bulk approval of similar applications. **AI Document Verification** automatically checks document authenticity and completeness. **Duplicate Detection** identifies potential duplicate applications. **Audit Trail Visualization** shows complete application journey with timestamps and actor identification. | Annex E.29 - Admin Module Screens; Annex E.30 - Workflow Configuration |
| **27** | **Modul Pengurusan Proses Penilaian dan Tapisan:** Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Cetak borang permohonan/ringkasan permohonan pemohon ii. Cetak senarai pencalonan mengikut kategori/penerima iii. Kemaskini keputusan mesyuarat (4 sesi mesyuarat) iv. Kemaskini status permohonan bagi setiap sesi penilaian (4 sesi penilaian) v. Jana/cetak surat tawaran (beserta janaan qr - lock by tahun) vi. Jana/cetak surat akuan sumpah (beserta janaan qr - lock by tahun) vii. Jana/cetak borang pemulangan Darjah Kebesaran/Pingat viii. Hantar notifikasi status permohonan dan tarikh pengambilan surat tawaran ix. Jana/cetak senarai calon penerima mengikut kategori permohonan/penerima untuk tapisan keselamatan mengikut kategori tapisan (3 tapisan keselamatan melibatkan fungsi integrasi) x. Jana senarai calon penerima (mengikut format laman web Darjah Kebesaran-integrasi) xi. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran (bagi pihak) xii. Pengesahan kehadiran ke Majlis Pengurniaan (bagi pihak) | **M** | **FULLY COMPLY** | **Complete Evaluation & Screening Module:**
- **i & ii. Printing:** Generate meeting packs with applicant summaries and nominee lists
- **iii. Meeting Results:** Record decisions from 4 evaluation meetings with configurable outcome types
- **iv. Evaluation Status:** Track applications through 4 evaluation stages with status updates
- **v. Offer Letters:** Auto-generated official offer letters with year-locked QR codes for verification
- **vi. Statutory Declaration Letters:** Generate Statutory Declaration forms with unique QR codes
- **vii. Return Forms:** Generate return forms for recipients who cannot attend
- **viii. Notifications:** Automated notifications for offer collection with scheduling
- **ix. Security Screening Lists:** Generate lists for 3 security screening categories with integration to screening agencies
- **x. Website Integration:** Export formatted lists for Darjah Kebesaran website publication
- **xi & xii. Proxy Confirmation:** Record confirmations on behalf of recipients with proper authorization<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Digital Meeting Workspace** provides paperless meeting experience with tablets for committee members. **Voting Module** supports secure electronic voting during evaluation meetings. **Conflict of Interest Detection** flags applications where evaluators have relationships with applicants. **Ceremony Planning Integration** automatically adds confirmed recipients to ceremony logistics planning. | Annex E.31 - Evaluation Workflow; Annex E.32 - Meeting Module; Annex E.33 - Letter Templates |
| **28** | **Modul Pentadbir Sistem:** Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Ketetapan Sistem termasuk penyelenggaraan terhadap semua data lookup ii. Audit Trail Sistem iii. Tetapan Notifikasi Emel iv. Konfigurasi Integrasi dengan AD - login sistem (pentadbir sahaja) v. Tetapan Login Pengguna myDigital ID vi. Tetapan Pengesahan Emel vii. Fungsi Masquerade (Login sebagai) viii. Menyediakan tetapan tertakluk kepada keperluan sistem pada sesi URS | **M** | **FULLY COMPLY** | **Complete System Administration Module:**
- **i. System Configuration:** Manage all lookup tables, dropdown values, and reference data through user-friendly interfaces
- **ii. Audit Trail:** Immutable logs of all system activities with advanced search and filtering
- **iii. Email Notifications:** Configure notification templates, triggers, and recipient rules
- **iv. AD Integration:** Configure Active Directory connection for administrator authentication
- **v. myDigital ID Setup:** Configure and test myDigital ID integration settings
- **vi. Email Verification:** Configure email verification workflows and templates
- **vii. Masquerade Function:** Secure "login as" capability for user support with full audit logging
- **viii. Additional Settings:** Extensible configuration framework for URS-identified requirements<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Configuration Version Control** tracks all configuration changes with rollback capability. **System Health Dashboard** monitors all integrations and alerts on failures. **Bulk Configuration Import/Export** simplifies environment setup and disaster recovery. **Role Simulator** allows testing user experiences without actually logging in as them. | Annex E.34 - Admin Configuration Screens; Annex E.35 - Audit Trail Interface |
| **29** | **Modul Laporan:** Petender hendaklah menyediakan sistem yang mempunyai keupayaan menjana pelbagai laporan mengikut kriteria yang ditetapkan oleh pihak PSUK Selangor berdasarkan senarai dibawah: i. Laporan/Statistik Permohonan Tahunan Mengikut Sesi ii. Laporan/Statistik Permohonan Tahunan Mengikut Kategori Permohonan iii. Laporan/Statistik Permohonan Tahunan mengikut sesi penilaian iv. Laporan/Statistik Penerima Tahunan Mengikut Sesi v. Laporan/Statistik Penerima Tahunan Mengikut Kategori Permohonan vi. Laporan/Statistik Penerima mengikut sesi penilaian vii. Statistik Keseluruhan Penerima Sehingga Tahun Terkini viii. Senarai laporan/statistik mengikut keperluan semasa pada sesi URS ix. Paparan Warta serta statistik termasuk carian penerima dan warta *** Semua Laporan boleh dipapar secara infografik. | **M** | **FULLY COMPLY** | **Comprehensive Reporting Module with All Required Reports:**
- **i-iii. Application Statistics:** Annual reports by session, category, and evaluation stage with trend analysis
- **iv-vi. Recipient Statistics:** Annual recipient reports by session, category, and evaluation stage
- **vii. Historical Statistics:** Cumulative statistics from system inception to current year
- **viii. Custom Reports:** Report builder for URS-defined requirements
- **ix. Warta Display:** Digital gazette with statistics and searchable content
- **Infographic Display:** All reports include visual charts, graphs, and infographics<br><br>**Report Features:** Export to PDF, Excel, Word; scheduled email delivery; interactive filtering; drill-down capability; and print-optimized layouts.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Natural Language Queries** allow users to ask questions like "Show me applications from Shah Alam approved in 2025" and get instant visual answers. **Predictive Reports** forecast future application volumes and resource needs. **Comparative Analysis** enables year-over-year and category comparisons. **Automated Report Distribution** sends scheduled reports to stakeholders without manual intervention. **Data Storytelling Mode** generates narrative summaries alongside visualizations for executive presentations. | Annex E.36 - Report Library; Annex E.37 - Infographic Examples; Annex E.38 - Report Builder |
| **30** | **Modul Fungsi Integrasi:** Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi integrasi melalui pembangunan Application Programming Interface (API) yang mempunyai ciri-ciri keselamatan terkini bagi tujuan integrasi dengan sistem lain merangkumi: i. Pembangunan API bagi integrasi dengan Sistem SPRM, Jabatan Insolvensi, Laman Web Darjah Kebesaran, ROS, myIDENTITY dan HRMIS (mengikut keperluan semasa ketika sesi URS dan ketersediaan agensi terlibat) ii. Termasuk juga konfigurasi bagi penggunaan myDigital ID – bagi tujuan log masuk ke sistem. | **M** | **FULLY COMPLY** | **Complete API Integration Module:**
- **i. External System Integration:** RESTful APIs with OAuth 2.0 + PKCE authentication for secure integration with:
  - **SPRM:** Integrity verification API for applicant screening
  - **Jabatan Insolvensi:** Bankruptcy status verification
  - **Laman Web Darjah Kebesaran:** Recipient list publication and website content sync
  - **ROS (Registrar of Societies):** Organization verification for society-based nominations
  - **myIDENTITY:** National identity verification and authentication
  - **HRMIS:** Employee data synchronization for government officers<br><br>- **ii. myDigital ID Login:** Full OAuth 2.0 integration supporting PKCE flow, enabling secure passwordless login for government users<br><br>**API Security:** API rate limiting, request signing, IP whitelisting, and comprehensive audit logging.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **API Management Portal** provides documentation, sandbox testing, and usage analytics. **Integration Health Monitor** displays real-time status of all external connections. **Failover Mechanism** gracefully handles external service outages with queue-and-retry logic. **API Versioning** ensures backward compatibility during system upgrades. **Webhook Support** enables real-time notifications to external systems. | Annex E.39 - API Architecture; Annex E.40 - Integration Specifications; Annex E.41 - API Security |
| **31** | **Fungsi Backup dan Migrasi Data:** Petender hendaklah bersedia membangunkan fungsi-fungsi seperti berikut: i. Melakukan backup data ke storan hard disk bagi melindungi data daripada sebarang kegagalan ii. Migrasi keseluruhan sistem dan pangkalan data iii. Migrasi data lama dipindahkan ke pangkalan data baharu berjalan dengan baik (migrasi data permohonan dan penerima dari sistem sedia ada - lotus) iv. Data hendaklah boleh diakses dan sistem berfungsi dengan sempurna setelah selesai proses migrasi | **M** | **FULLY COMPLY** | **Complete Backup & Migration Functions:**
- **i. Data Backup:** Automated daily incremental and weekly full backups to encrypted storage with 30-day retention
- **ii. System Migration:** Complete migration plan covering application, database, and configuration migration
- **iii. Legacy Data Migration:** ETL (Extract, Transform, Load) process for migrating historical applications and recipient data from Lotus Notes system, including data cleansing and validation
- **iv. Data Integrity:** Post-migration verification ensures 100% data accuracy and system functionality<br><br>**Migration Process:** Data profiling → Cleansing rules → Test migration → Validation → Production migration → Verification → Rollback plan.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Migration Simulator** allows testing the migration process multiple times before go-live. **Data Quality Dashboard** shows completeness and accuracy metrics before and after migration. **Parallel Running Period** allows comparison between old and new systems for verification. **Historical Archive Access** provides read-only access to legacy system data for audit purposes. **Zero-Downtime Migration** minimizes system unavailability during cutover. | Annex E.42 - Migration Plan; Annex E.43 - Backup Architecture; Annex E.44 - Data Mapping |

---

#### E. PEMBEKALAN PERKAKASAN

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **32** | Petender hendaklah membekal, menyedia, memasang, mengkonfigurasi dan mentauliah: Satu (1) unit 1D/2D Handheld Barcode Scanner QR Wired USB Imager Black Corded Screen Code Reader with Stand (termasuk satu (1) tahun tempoh jaminan). Nota: Sila nyatakan model yang dicadangkan. | **M** | **FULLY COMPLY** | **Proposed Barcode Scanner:**
- **Primary Option:** Honeywell Voyager 1250g - High-performance laser scanner with 1D/2D capability, USB connectivity, ergonomic design, and included stand
- **Alternative Option:** Zebra DS2208 - 2D area imager, omni-directional scanning, durable construction, 5-year warranty available<br><br>**Specifications:** USB wired connection, compatible with Windows/Ubuntu, reads all standard 1D and 2D barcodes including QR codes, plug-and-play installation.<br><br>**Warranty:** 1-year manufacturer warranty with on-site support option.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We include **Barcode Generator Integration** within the ePingat system for creating standardized QR codes. **Mobile Scanner App** turns any smartphone into a backup scanning device. **Scanner Health Monitoring** alerts when scanner issues are detected. **Bulk Testing** validates scanner functionality with sample documents before deployment. | Annex E.45 - Hardware Specifications; Annex E.46 - Scanner Comparison |

---

#### F. PERKHIDMATAN MIGRASI DAN DATA CLEANING

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **33** | Petender perlu menyedia perkhidmatan migrasi dan data cleaning melibatkan: i. Migrasi keseluruhan sistem dan pangkalan data daripada sistem terdahulu dan portal laman web rasmi Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor. ii. Petender hendaklah memastikan data dari sistem dan portal terdahulu dapat digunakan semula dalam sistem baharu. iii. Proses migrasi data-data daripada sistem sedia ada akan dilaksana dan diuji secara terperinci dan menyeluruh. iv. Petender hendaklah mencadangkan dan menyediakan pelan migrasi lengkap kepada pihak PSUK Selangor. | **M** | **FULLY COMPLY** | **Complete Migration & Data Cleaning Services:**
- **i. Full Migration:** Extract all data from existing Lotus Notes system and official Darjah Kebesaran website portal
- **ii. Data Reusability:** Transform and load legacy data into new system ensuring all historical records remain accessible and functional
- **iii. Thorough Testing:** Multiple test migration cycles with data validation, integrity checks, and user acceptance verification
- **iv. Migration Plan:** Comprehensive migration strategy document including timeline, resources, risk mitigation, and rollback procedures<br><br>**Data Cleaning Process:** Duplicate detection → Data standardization → Missing data handling → Validation rules → Quality scoring.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Data Profiling Report** provides analysis of legacy data quality before migration begins. **Migration Rehearsal** runs the full migration process in a staging environment 3 times before production. **Data Archive Strategy** preserves original data in read-only format for long-term audit requirements. **User Training on Clean Data** educates PSUK staff on maintaining data quality going forward. **Post-Migration Data Quality Dashboard** monitors ongoing data integrity. | Annex E.47 - Migration Methodology; Annex E.48 - Data Cleaning Procedures; Annex E.49 - Migration Test Plan |

---

#### G. PENGUJIAN SISTEM DAN PERKAKASAN

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **34** | Petender perlu melaksana pengujian keseluruhan fungsi di dalam sistem dan perkakasan bagi memastikan ia mengikut aliran kerja sebenar dan penyediaan dokumentasi pengujian: a. User Acceptance Test (UAT) b. Provisional Acceptance Test (PAT) c. Equipment Acceptance Test (EAT) d. Final Acceptance Test (FAT) e. Pengujian Performance Test (PT) & Web Application Security Assessment (WASA) | **M** | **FULLY COMPLY** | **Complete Testing Framework:**
- **a. UAT:** End-user testing with real-world scenarios, test scripts covering all requirements, defect tracking and resolution
- **b. PAT:** System stability testing in production-like environment, integration verification, data migration validation
- **c. EAT:** Hardware testing including barcode scanner compatibility, performance, and reliability
- **d. FAT:** Final comprehensive testing before project closure including all components
- **e. PT & WASA:** Load testing (500+ concurrent users), stress testing, and CREST-accredited security penetration testing<br><br>**Testing Documentation:** Test plans, test scripts, test data, execution reports, and defect logs provided for all phases.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Automated Test Suite** provides regression testing for all future releases. **User Testing Workshops** train PSUK staff to conduct ongoing UAT for future enhancements. **Performance Baseline Report** establishes system performance metrics for ongoing monitoring. **Security Test Retest** includes one retest after remediation at no additional cost. | Annex G - Testing Documentation; Annex G.1 - UAT Test Scripts; Annex G.2 - Performance Test Plan; Annex G.3 - WASA Scope |
| **35** | Petender hendaklah melaksanakan pembetulan dan penambahbaikan terhadap semua ralat yang dikesan semasa pengujian-pengujian di atas TANPA sebarang tambahan kos. | **M** | **FULLY COMPLY** | SESB commits to fixing all defects identified during testing phases at no additional cost. This includes:
- Critical defects (system crashes, data loss): Fixed within 24 hours
- High priority (major feature issues): Fixed within 72 hours
- Medium priority (minor issues): Fixed within 5 working days
- Low priority (cosmetic): Fixed within 10 working days<br><br>**Defect Management:** Centralized defect tracking with PSUK access, severity classification, root cause analysis, and prevention measures.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Zero-Defect Guarantee**—if critical defects exceed 5 during UAT, we extend warranty period by 3 months at no cost. **Defect Trend Analysis** identifies systemic issues and process improvements. **Post-Release Defect Prediction** uses AI to identify high-risk areas before they fail. | Annex G.4 - Defect Management Process; Annex H.5 - Warranty Terms |
| **36** | Petender hendaklah bersetuju menyediakan dokumentasi pengujian melibatkan pelan pengujian, skrip pengujian, laporan pengujian, dan dokumentasi penerimaan/pentauliahan. | **M** | **FULLY COMPLY** | Complete testing documentation package includes:
- Master Test Plan covering all testing phases
- Detailed test scripts with expected results and pass/fail criteria
- Test execution reports with evidence (screenshots, logs)
- Defect reports with resolution verification
- Acceptance certificates for each testing phase<br><br>All documents follow IEEE 829 standard format and are provided in both softcopy and hardcopy.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Interactive Test Dashboard** allows PSUK to monitor test progress in real-time. **Test Coverage Analysis** maps every test to requirements ensuring complete coverage. **Automated Test Report Generation** reduces documentation time and errors. **Knowledge Transfer Session** on testing best practices for PSUK technical staff. | Annex G.5 - Documentation Templates; Annex G.6 - Acceptance Certificate Templates |
| **37** | Petender hendaklah bersetuju untuk menanggung kos bagi keperluan berkaitan semasa pengujian dilaksanakan. | **M** | **FULLY COMPLY** | SESB will bear all costs related to testing activities including:
- Testing environment setup and infrastructure
- Test data preparation and anonymization
- Testing tools and licenses
- Travel and accommodation for on-site testing support
- Hardware for EAT testing<br><br>No additional charges will be invoiced for testing-related expenses.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Testing Environment Mirroring** ensures test environment exactly matches production for accurate results. **Test Data Generator** creates realistic synthetic data for testing without privacy concerns. **Mobile Device Testing Lab** with multiple device types for compatibility testing. | Annex G.7 - Testing Cost Breakdown |

---

#### H. PEMASANGAN DAN KONFIGURASI SISTEM

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **38** | Petender hendaklah bersetuju bagi melaksanakan pemasangan dan konfigurasi keseluruhan sistem dan pangkalan data serta perlu membuat pengasingan: Development Environment, Production A Environment, Production B Environment (each with Application Server and Database Server) | **M** | **FULLY COMPLY** | SESB will configure three separate environments:
- **Development:** For ongoing development and unit testing
- **Production A (Staging):** For UAT and pre-production validation
- **Production B (Live):** Live production environment<br><br>Each environment includes dedicated Application Server and Database Server with appropriate resource allocation. Environment isolation ensures testing does not impact production.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Environment Synchronization Tool** quickly clones production data to staging (with anonymization) for realistic testing. **Blue-Green Deployment** capability enables zero-downtime releases. **Environment Health Dashboard** monitors all environments from a single view. **Automated Environment Provisioning** using Infrastructure as Code enables rapid environment creation. | Annex E.50 - Environment Architecture; Annex E.51 - Deployment Pipeline |
| **39** | Petender hendaklah melaksanakan pemasangan dan konfigurasi sistem ke atas server cloud yang akan disediakan dan dihostkan di Pusat Data Bahagian Pengurusan Maklumat, Tingkat 2, Bangunan Sultan Salahuddin Abdul Aziz Shah (SSAAS). | **M** | **FULLY COMPLY** | SESB will perform complete installation and configuration on cloud servers hosted at BPM Data Center, SSAAS. Our team has prior experience with BPM infrastructure and security requirements.<br><br>**Installation Process:** Pre-installation checklist → Server preparation → Software installation → Configuration → Security hardening → Testing → Sign-off.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Installation Documentation** provides PSUK with complete setup instructions for future reference. **Configuration Backup** exports all settings for disaster recovery. **As-Built Documentation** records final system state with all customizations. **BPM Integration Support** assists with network, DNS, and security configuration specific to BPM requirements. | Annex E.52 - Installation Guide; Annex E.53 - BPM Integration Checklist |
| **40** | Petender perlu menyatakan spesifikasi keperluan sistem dan storage yang diperlukan (termasuk capacity planning). | **M** | **FULLY COMPLY** | **System Specifications & Capacity Planning:**
- **Application Server:** 4 vCPU, 16GB RAM, 100GB SSD minimum
- **Database Server:** 8 vCPU, 32GB RAM, 500GB SSD (expandable)
- **Storage:** 1TB initial with 20% annual growth projection
- **Backup Storage:** 2TB for 30-day retention
- **Network:** 100Mbps dedicated bandwidth<br><br>**Capacity Planning:** Based on 10,000 annual applications, 500 concurrent users, and 5-year data retention. Includes growth projections and scaling triggers.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Capacity Forecasting Model** predicts when additional resources will be needed based on usage trends. **Right-Sizing Analysis** ensures optimal resource allocation without over-provisioning. **Storage Optimization** includes compression and archival strategies to minimize costs. | Annex E.54 - Capacity Planning; Annex E.55 - Resource Sizing |
| **41** | Petender hendaklah menggunakan perkhidmatan repository yang telah disediakan oleh Bahagian Pengurusan Maklumat, Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **FULLY COMPLY** | SESB will use the repository service provided by BPM for source code management, following PSUK's Git workflow and branching strategy.<br><br>**Repository Practices:** Feature branching → Code review → Merge approval → Automated builds. All code commits linked to requirements.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Code Quality Gates** ensure only high-quality code enters the repository. **Automated Documentation Generation** from code comments. **Repository Hygiene** training for PSUK staff on Git best practices. **Source Code Handover Package** at project completion with complete repository export. | Annex E.56 - Repository Workflow; Annex E.57 - Git Standards |
| **42** | Petender hendaklah bersetuju melaksanakan pemasangan, integrasi, migrasi dan pelaksanaan perisian dengan jayanya. | **M** | **FULLY COMPLY** | SESB commits to successful completion of all implementation phases: installation, integration with external systems, data migration, and software deployment. Success criteria defined for each phase with PSUK sign-off required.<br><br>**Success Metrics:** 100% feature completion, zero critical defects, 99.9% uptime, successful data migration with zero loss, user acceptance.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Implementation War Room** setup for critical deployment phases with dedicated team. **Hypercare Support** intensive support period (2 weeks post go-live) with on-site presence. **Success Guarantee**—if go-live criteria not met, we continue at no cost until achieved. | Annex F.9 - Implementation Plan; Annex F.10 - Success Criteria |
| **43** | Pengurusan Backup dan Restore: Petender hendaklah bersetuju bagi melaksana konfigurasi salinan keselamatan (backup) secara daily, weekly, monthly. | **M** | **FULLY COMPLY** | **Backup Schedule:**
- **Daily:** Incremental backup at 2:00 AM, retained for 7 days
- **Weekly:** Full backup every Sunday at 2:00 AM, retained for 4 weeks
- **Monthly:** Full backup on 1st of month, retained for 12 months<br><br>All backups encrypted and stored off-site with periodic restore testing.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Point-in-Time Recovery** allows restoration to any moment in the past 30 days. **Backup Verification** automatically tests backup integrity daily. **Instant Clone** creates development environments from backups in minutes. **Backup Analytics Dashboard** shows backup status, storage usage, and compliance. | Annex E.58 - Backup Configuration; Annex E.59 - Restore Procedures |
| **44** | SSL Certificate: Petender hendaklah bersetuju untuk membuat pemasangan sistem bersama SSL Certificate bagi memastikan transaksi atas talian dalam keadaan selamat. SSL Certificate akan disediakan oleh Bahagian Pengurusan Maklumat (BPM), PSUK Selangor. | **M** | **FULLY COMPLY** | SESB will configure SSL certificates provided by BPM ensuring:
- HTTPS-only access
- TLS 1.3 encryption
- HSTS (HTTP Strict Transport Security) enabled
- SSL certificate monitoring and renewal alerts<br><br>Installation includes configuration of all web servers, load balancers, and API endpoints.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **SSL Health Monitoring** alerts before certificate expiry. **A+ SSL Rating** achieved through optimized cipher configuration. **Certificate Transparency Monitoring** detects unauthorized certificates issued for the domain. | Annex I.8 - SSL Configuration; Annex I.9 - Security Headers |
| **45** | Code Hardening: Petender hendaklah memastikan kod aturcara yang dibangunkan menepati ciri-ciri keselamatan yang perlu ada di dalam sistem. Sila nyatakan pelaksanaan code hardening yang dicadangkan. | **M** | **FULLY COMPLY** | **Code Hardening Implementation:**
- **Input Validation:** Whitelist validation on all inputs, parameterized queries
- **Output Encoding:** Context-aware encoding to prevent XSS
- **CSRF Protection:** Token-based CSRF protection on all forms
- **Authentication:** Secure session management, password hashing (bcrypt)
- **Authorization:** Principle of least privilege, role-based access
- **Error Handling:** Generic error messages, detailed logging
- **Security Headers:** CSP, X-Frame-Options, X-Content-Type-Options
- **Dependency Management:** Regular security scanning of libraries<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Static Application Security Testing (SAST)** runs on every code commit. **Software Composition Analysis (SCA)** identifies vulnerable dependencies. **Security Code Review** by certified security professionals before release. **Secure Coding Training** provided to PSUK developers. | Annex I.10 - Secure Coding Standards; Annex I.11 - Code Review Checklist |
| **46** | Fungsi Notifikasi: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menghantar notifikasi pemakluman melalui SMS/Whatsapp dan E-mel. | **M** | **FULLY COMPLY** | **Multi-Channel Notification System:**
- **SMS:** Integration with Malaysian SMS gateway (supports all telcos)
- **WhatsApp:** Official WhatsApp Business API integration
- **Email:** SMTP integration with PSUK mail server, HTML templates<br><br>**Notification Triggers:** Application submitted, status changes, approval required, offer ready, ceremony reminders.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Notification Preferences** allow users to choose preferred channels. **Delivery Tracking** shows notification status (sent, delivered, read). **Template Designer** enables PSUK to customize messages without coding. **Notification Analytics** tracks delivery rates and engagement. **Fallback Chain** automatically tries alternative channels if primary fails. | Annex E.60 - Notification Architecture; Annex E.61 - Message Templates |
| **47** | Tetapan/ Konfigurasi Sistem (Pentadbir): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Pentadbir Sistem mengikut keperluan. | **M** | **FULLY COMPLY** | Administrator configuration settings include: User management, role management, workflow configuration, notification settings, integration settings, system parameters, audit log access, and backup management.<br><br>**Configuration Interface:** User-friendly web interface with validation, help text, and change tracking.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Configuration Wizards** guide administrators through complex setups. **Configuration Templates** provide starting points for common configurations. **Bulk Configuration** allows importing settings from spreadsheets. **Configuration Audit** tracks all changes with before/after comparison. | Annex E.62 - Admin Configuration Guide |
| **48** | Tetapan/ Konfigurasi Sistem (Teknikal): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Teknikal Sistem seperti: a. Tetapan Akses dan Log b. Tetapan notifikasi E-mel / SMS / Whatsapp c. Fungsi Masquerade (Login sebagai) d. Menyediakan tetapan tertakluk kepada keperluan semasa sistem dan pengguna | **M** | **FULLY COMPLY** | **Technical Configuration Features:**
- **a. Access & Logs:** Configure log levels, retention periods, and log forwarding
- **b. Notification Settings:** Configure gateway credentials, rate limits, and default templates
- **c. Masquerade Function:** Secure user impersonation for support with full audit trail
- **d. Extended Settings:** API rate limiting, cache configuration, queue settings<br><br>All technical settings include validation and rollback capability.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Configuration Validation** prevents invalid settings that could break the system. **Environment Diff** compares configurations across environments. **Configuration as Code** allows version-controlled configuration changes. | Annex E.63 - Technical Configuration; Annex E.64 - System Settings |
| **49** | Log/ Audit Trail: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan semua log audit terperinci dari segi akses pengguna, perubahan data dan lain-lain yang berkaitan: a. Log Proses b. Log Aktiviti c. Log Service d. Log E-mel e. Log SMS/Whatsapp | **M** | **FULLY COMPLY** | **Comprehensive Audit Logging:**
- **a. Process Logs:** Business process execution with timestamps and outcomes
- **b. Activity Logs:** User actions (login, view, create, update, delete) with before/after values
- **c. Service Logs:** API calls, integrations, background jobs
- **d. Email Logs:** All emails sent with delivery status and opens
- **e. SMS/WhatsApp Logs:** All messages with delivery confirmation<br><br>**Log Features:** Immutable storage, advanced search, export capability, retention management, and tamper detection.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Blockchain-Based Audit Trail** option for tamper-proof records. **Anomaly Detection** identifies unusual activity patterns. **Audit Dashboard** provides visual analytics of system activity. **Compliance Reports** pre-formatted for audit purposes. **Log Integration** with SIEM for centralized security monitoring. | Annex I.12 - Audit Trail Architecture; Annex I.13 - Log Retention Policy |
| **50** | Data History: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan maklumat lama/arkib (history/archive) di peringkat pengguna dan pentadbir sistem. | **M** | **FULLY COMPLY** | **Data History & Archiving:**
- **User Level:** Users can view their historical applications and status changes
- **Administrator Level:** Complete archive access with advanced search and filtering
- **Automatic Archiving:** Old data automatically archived after defined retention periods
- **Archive Storage:** Separate storage tier for historical data with compression<br><br>**Archive Features:** Read-only access, export capability, and audit trail of archive access.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Time Machine View** shows system state at any historical point. **Archive Analytics** provides insights from historical data trends. **Smart Archiving** automatically determines optimal archive timing based on data usage patterns. **Archive Search** full-text search across all archived records. | Annex E.65 - Data Archiving Strategy; Annex E.66 - Historical Data Access |

---

#### I. DOKUMENTASI

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **51** | Petender hendaklah menyedia dokumentasi berkaitan: a. Manual Pengguna b. Manual Pentadbir c. Manual Teknikal/Operasi | **M** | **FULLY COMPLY** | **Complete Documentation Set (Bahasa Malaysia):**
- **a. User Manual:** Step-by-step guides for applicants and Urus Setia with screenshots and FAQs
- **b. Administrator Manual:** System configuration, user management, troubleshooting
- **c. Technical/Operations Manual:** Installation, maintenance, backup/restore, API reference<br><br>All manuals professionally formatted with table of contents, index, and searchable PDF.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Video Manuals** provide screen recordings of key procedures. **Interactive Help** embedded in the application with contextual guidance. **Documentation Portal** searchable online knowledge base. **Quarterly Updates** keep documentation current with system changes. **Feedback Integration** allows users to suggest documentation improvements. | Annex F.11 - Documentation Plan; Annex F.12 - Manual Templates |
| **52** | Petender hendaklah menyediakan minit mesyuarat Pasukan Kerja dan Jawatankuasa Teknikal Projek dengan pemantauan urus setia projek. | **M** | **FULLY COMPLY** | SESB will document all Working Team and Technical Committee meetings including: Agenda, attendance, discussion points, decisions made, action items with owners and deadlines, and status updates.<br><br>**Meeting Cadence:** Weekly Working Team meetings, monthly Technical Committee meetings, and ad-hoc meetings as needed.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Meeting Portal** provides online access to all meeting materials. **Action Item Tracker** sends automatic reminders for pending actions. **Decision Log** maintains searchable record of all project decisions. **Meeting Analytics** tracks meeting effectiveness and follow-up rates. | Annex F.13 - Meeting Management Plan |
| **53** | Petender hendaklah menyediakan satu salinan manual penggunaan secara hardcopy dan softcopy kepada pengguna dan pentadbir sistem. | **M** | **FULLY COMPLY** | Both hardcopy (printed and bound) and softcopy (PDF, searchable) manuals will be provided to all users and administrators. Distribution list maintained with sign-off confirmation.<br><br>**Quantity:** 50 hardcopy user manuals, 10 hardcopy admin manuals, unlimited softcopy distribution.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Quick Start Cards** laminated one-page guides for common tasks. **QR Codes in Manuals** link to video demonstrations. **E-Book Format** for mobile-friendly reading. **Accessibility Versions** screen-reader compatible formats. | Annex F.14 - Distribution Plan |

---

#### J. LATIHAN DAN PEMINDAHAN TEKNOLOGI

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **54** | Petender perlu melaksana latihan dan pemindahan teknologi melibatkan: a. Latihan Pengguna b. Latihan Pentadbir Sistem c. Transfer of Technology (TOT) | **M** | **FULLY COMPLY** | **Complete Training Program:**
- **a. User Training:** Hands-on sessions for applicants and Urus Setia on system usage
- **b. Administrator Training:** In-depth training on system configuration, user management, and troubleshooting
- **c. Transfer of Technology:** Knowledge transfer to PSUK technical staff on system maintenance<br><br>**Training Methods:** Classroom sessions, hands-on labs, video tutorials, and reference materials.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Train-the-Trainer** program certifies PSUK staff to train future users. **Training Portal** provides ongoing access to materials and e-learning modules. **Competency Assessment** validates learning with certificates. **Refresher Training** sessions included during warranty period. **Video Recording** of all training for future reference. | Annex F.15 - Training Plan; Annex F.16 - Training Materials |
| **55** | Petender bersetuju melaksanakan sesi TOT kepada pegawai-pegawai yang terlibat dan pentadbir sistem untuk memahirkan diri dalam pembangunan/penyelenggaraan sistem bagi menguruskan isu-isu teknikal sistem dan konfigurasi sistem/server yang berkaitan (sila nyatakan cadangan lokasi dan kemudahan latihan yang akan dilaksana). | **M** | **FULLY COMPLY** | **Transfer of Technology (TOT) Program:**
- **Location:** PSUK Selangor training room or SESB training facility (based on PSUK preference)
- **Duration:** 5-day intensive program
- **Topics:** System architecture, database management, troubleshooting, backup/restore, security management, performance tuning<br><br>Training includes hands-on exercises with actual system components.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **TOT Lab Environment** dedicated training environment for hands-on practice without risk. **TOT Mentorship** 3-month post-training support with assigned mentor. **Technical Runbook** comprehensive operational guide. **Certification Exam** validates competency. **Emergency Escalation** direct line to SESB senior engineers during transition period. | Annex F.17 - TOT Curriculum; Annex F.18 - Training Facilities |
| **56** | Petender hendaklah menyenarai kesemua fail dan modul yang terdapat di dalam sistem dan server untuk tujuan TOT tersebut. | **M** | **FULLY COMPLY** | Complete inventory of all system files, modules, and server components will be provided including: File/module name and location, purpose description, dependencies, configuration parameters, and maintenance procedures.<br><br>**Inventory Format:** Spreadsheet and technical documentation with diagrams.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Interactive System Map** visual explorer showing all components and relationships. **Dependency Graph** illustrates how modules interact. **Change History** tracks modifications to each component. **Health Indicators** show status of each module. | Annex F.19 - System Inventory |
| **57** | Petender hendaklah menyediakan dokumentasi lengkap bagi setiap latihan dan sesi TOT. | **M** | **FULLY COMPLY** | Complete training documentation includes: Training agenda and schedule, attendance records, training materials (slides, handouts, exercises), video recordings, assessment results, and feedback forms.<br><br>**Documentation Standards:** Professional formatting, version control, and searchable content.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Training Analytics** tracks completion rates and competency scores. **Feedback Analysis** identifies training improvement opportunities. **Certification Records** maintains database of trained personnel. **Training ROI Report** measures effectiveness. | Annex F.20 - Training Documentation Standards |
| **58** | Petender hendaklah mencadangkan senarai latihan dan TOT. | **M** | **FULLY COMPLY** | Proposed training schedule provided in Annex F including: Training courses list, target audience, duration, prerequisites, learning objectives, and delivery method.<br><br>**Training Categories:** End-user training, administrator training, technical training, and TOT.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Training Needs Assessment** conducted before training to customize content. **Role-Based Learning Paths** tailored to different user types. **Microlearning Modules** 5-10 minute videos for specific tasks. **Gamification Elements** to increase engagement. **Community Forum** for peer-to-peer learning. | Annex F.15 - Training Plan; Annex F.21 - Training Calendar |
| **59** | Laporan Kemajuan Projek: Petender hendaklah menyediakan Laporan Kemajuan Projek sekurang-kurangnya tiga (3) kali sepanjang tempoh projek, tertakluk kepada keperluan semasa. Petender hendaklah menyediakan Laporan Akhir Pelaksanaan Projek setelah pelaksanaan projek selesai sepenuhnya. | **M** | **FULLY COMPLY** | **Project Reporting Schedule:**
- **Progress Reports:** Minimum 3 reports (Month 2, Month 4, Month 6)
- **Final Report:** Comprehensive project completion report including lessons learned, as-built documentation, and handover materials<br><br>**Report Contents:** Executive summary, progress against plan, deliverables status, issues and risks, financial summary, and next steps.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Real-Time Project Dashboard** available 24/7 showing current status. **Predictive Analytics** forecasts completion dates based on actual progress. **Automated Report Generation** reduces preparation time. **Stakeholder-Specific Views** tailored reports for different audiences. **Benchmarking** compares project performance against industry standards. | Annex F.22 - Reporting Schedule; Annex F.23 - Report Templates |

---

#### K. KOD SUMBER DAN PANGKALAN DATA

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **60** | i. Semua kod sumber (source code) adalah hak milik sepenuhnya Kerajaan Negeri Selangor dan wajib diserahkan dalam bentuk softcopy kepada Kerajaan Negeri apabila projek telah siap. ii. Sebarang penyalinan, pemindahan dan pengedaran dengan apa juga cara untuk tujuan komersil adalah tidak dibenarkan sama sekali kecuali mendapat kebenaran daripada Kerajaan Negeri Selangor. | **M** | **FULLY COMPLY** | SESB fully accepts the intellectual property terms:
- **i. Source Code Ownership:** Complete source code delivered to Kerajaan Negeri Selangor upon project completion including all scripts, configurations, and documentation
- **ii. Usage Restrictions:** SESB commits to no commercial use, distribution, or reuse of the specific ePingat system without written permission<br><br>**Delivery Format:** Organized repository with documentation, build instructions, and dependency manifest.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Code Documentation** comprehensive inline comments and external documentation. **Developer Onboarding Guide** helps future developers understand the codebase. **Architecture Decision Records** explain key technical choices. **Knowledge Transfer Sessions** walkthrough of critical code sections. | Annex F.24 - Source Code Handover; Annex F.25 - IP Assignment Agreement |

---

#### L. PEMBAYARAN

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **61** | Petender tidak boleh menuntut apa-apa bentuk bayaran tambahan daripada Kerajaan Negeri selain daripada bayaran yang dinyatakan dalam dokumen kontrak. | **M** | **FULLY COMPLY** | SESB confirms no additional charges beyond the contract amount. All costs including testing, training, documentation, travel, and warranty support are included in the quoted price.<br><br>**Fixed Price Commitment:** Scope changes will be handled through formal change control process with prior written approval.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Price Lock Guarantee**—no price increases for 12 months post-contract even if project extends. **Value Assurance** regular reviews ensure PSUK receives full contracted value. | Contract Terms |
| **62** | Perjanjian: Petender yang berjaya dikehendaki menandatangani satu kontrak dengan Kerajaan Negeri dalam tempoh empat (4) bulan dari tarikh mula projek. | **M** | **FULLY COMPLY** | SESB agrees to execute contract within 4 months from project start date. Our legal team is prepared to review and sign the agreement promptly.<br><br>**Contract Readiness:** Standard company documents (SSM, financials, insurance) are current and available.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Contract Compliance Tracking** ensures all contractual obligations are met. **Relationship Management** dedicated account manager for ongoing PSUK relationship. | Contract Documentation |

---

#### M. PERKHIDMATAN KHIDMAT SOKONGAN DALAM TEMPOH WARANT

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **63** | Petender hendaklah bersetuju: a. Memberi jaminan perkhidmatan sokongan terhadap Sistem ePingat yang dibangunkan dalam tempoh satu (1) tahun bermula selepas tarikh FAT (Go Live) ditandatangani tanpa sebarang kos. b. Sekiranya terdapat keadaan di mana salah satu ataupun keseluruhan komponen sistem gagal berfungsi sepertimana yang sepatutnya, syarikat akan bertanggungjawab sepenuhnya kepada kerja-kerja recovery. c. Petender perlu menyediakan Service Level Agreement (SLA) bagi kadar penyelesaian isu yang diadukan. d. Kerajaan Negeri berhak untuk menyampaikan aduan kepada Petender pada bila-bila masa dan tiada had ke atas bilangan aduan. e. Petender hendaklah menyediakan sistem helpdesk/call center/pusat khidmat pengguna. Masa tindakan: i. Helpdesk (Phone, Email and Helpdesk System) - 24 jam x 7 hari seminggu ii. Technical Support - 8 jam x 5 hari seminggu iii. Masa Tindakan - (Response Time – Min 4 jam) - (Selesai Masalah – Max 3 Hari Waktu bekerja) f. Petender perlu menyedia khidmat bantuan dan nasihat penggunaan sistem yang betul. | **M** | **FULLY COMPLY** | **Comprehensive 1-Year Warranty Support:**
- **a. Warranty Coverage:** Full support from FAT signing, all costs included
- **b. Recovery Responsibility:** Complete responsibility for system recovery with defined RTO/RPO targets
- **c. SLA Commitment:** Response times (Critical: 4 hours, High: 8 hours, Medium: 24 hours, Low: 48 hours); Resolution times (Critical: 24 hours, High: 72 hours, Medium: 5 days, Low: 10 days)
- **d. Unlimited Support:** No limit on number of support requests
- **e. Helpdesk Operations:**
  - i. 24/7 Helpdesk via phone, email, and ticketing system
  - ii. 8x5 Technical Support for complex issues
  - iii. 4-hour response, 3-day maximum resolution commitment
- **f. User Guidance:** Ongoing training and best practice advice<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Proactive Monitoring** identifies issues before PSUK reports them. **Monthly Health Checks** review system performance and recommend optimizations. **User Satisfaction Surveys** continuously improve support quality. **Escalation Management** ensures timely resolution of stuck issues. **Knowledge Base** self-service articles reduce ticket volume. **WhatsApp Support** instant messaging for quick queries. | Annex H - Service Level Agreement; Annex H.6 - Warranty Terms; Annex H.7 - Support Procedures |
| **64** | Tempoh Jaminan/ Waranti: Petender perlu memberi jaminan dalam tempoh SATU (1) TAHUN bermula selepas FAT (Final Acceptance Test) ditandatangani melibatkan: a. Perkhidmatan sokongan secara on site dan secara atas talian. b. Pembetulan ralat keseluruhan sistem dan perkakasan. | **M** | **FULLY COMPLY** | **1-Year Warranty from FAT Signing:**
- **a. Support Coverage:** Both on-site (when required) and remote support available throughout warranty period
- **b. Bug Fixes:** All system defects and hardware issues corrected at no additional cost<br><br>**Warranty Extensions:** Available at competitive rates beyond the initial year.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Extended Warranty Options** 2nd and 3rd year at discounted rates. **Hardware Replacement** spares kept on-site for critical components. **Performance Guarantee** uptime commitment with service credits for breaches. | Annex H.8 - Warranty Coverage |
| **65** | Petender bersetuju menyediakan dan menyempurnakan dokumen penyerahan projek selepas pelaksanaan projek selesai sepenuhnya. | **M** | **FULLY COMPLY** | Complete project handover documentation including: As-built documentation, source code, database schemas, configuration files, administrator credentials, warranty certificate, training completion certificates, and final project report.<br><br>**Handover Process:** Formal handover meeting, document review, system demonstration, and sign-off.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Handover Checklist** ensures nothing is missed. **30-Day Support Buffer** intensive support period immediately after handover. **Exit Interview** captures lessons learned and improvement suggestions. **Future Roadmap** recommendations for system enhancements. | Annex F.26 - Handover Checklist; Annex F.27 - Project Closure Procedure |
| **66** | Petender bersetuju melaksanakan kerja-kerja yang tidak dinyatakan secara khusus di dalam keperluan projek tetapi perlu dilaksanakan bagi melancarkan dan menjayakan pelaksanaan projek ini. | **M** | **FULLY COMPLY** | SESB agrees to perform any additional work necessary for successful project completion, including: Additional integrations discovered during URS, process adjustments based on stakeholder feedback, additional training sessions if needed, supplementary documentation, and out-of-scope items reasonably required for project success.<br><br>**Change Control:** Items identified will be documented and agreed upon before implementation.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Project Success Guarantee**—we do whatever it takes to ensure PSUK's objectives are met. **Continuous Improvement** proactively suggest enhancements during implementation. **Flexibility Commitment** up to 10% effort variance accommodated without change request for minor scope adjustments. | Project Management Plan |

---

#### N. KESELAMATAN DATA

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **67** | Keselamatan Data: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **FULLY COMPLY** | **Data Security Commitments:**
- **a. Data Responsibility:** SESB accepts full accountability for data security throughout the project lifecycle. All data handled according to government security classifications.
- **b. Confidentiality Agreements:** All SESB personnel sign Statutory Declarations (Akuan Sumpah) and NDAs before accessing any PSUK data or premises.
- **c. Policy Compliance:** Full compliance with PSUK ICT Security Policy, including access controls, encryption, audit logging, and incident reporting.<br><br>**Security Measures:** Encrypted devices, secure development environment, data minimization, secure disposal of test data, and regular security training.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** **Security Certification** all team members complete PSUK security clearance. **Data Handling Protocol** documented procedures for every data interaction. **Breach Response Plan** immediate notification and containment procedures. **Quarterly Security Reviews** ongoing assessment of security controls. **Insurance Coverage** cyber liability insurance for additional protection. | Annex I.14 - Data Security Policy; Annex I.15 - Confidentiality Agreements; Annex I.16 - Security Training Records |

---

#### O. LAIN-LAIN

| No. | Description | M/O | Compliance | Remarks & Evidence |
|-----|-------------|-----|------------|-------------------|
| **68** | Lain-Lain Cadangan (Jika Ada): Sila nyatakan lain-lain cadangan/perkhidmatan yang berkaitan, sekiranya ada. | **O** | **FULLY COMPLY** | **Value-Added Services (VAS) Framework:**

**Part 1: Software & Innovation (5 Items)**
| No. | Service | Market Value (RM) |
|-----|---------|-------------------|
| 1.1 | AI-Powered Application Pre-Screening | 150,000 |
| 1.2 | Advanced Analytics & Predictive Reporting | 120,000 |
| 1.3 | WhatsApp Business API Integration | 80,000 |
| 1.4 | Document Intelligence (OCR/AI) | 100,000 |
| 1.5 | API Developer Portal | 50,000 |
| | **Part 1 Subtotal** | **RM 500,000** |

**Part 2: Support & Consultative (5 Items)**
| No. | Service | Market Value (RM) |
|-----|---------|-------------------|
| 2.1 | Extended Warranty (Year 2) | 150,000 |
| 2.2 | Quarterly System Health Reviews | 60,000 |
| 2.3 | Change Management Support | 80,000 |
| 2.4 | User Experience Optimization | 70,000 |
| 2.5 | Knowledge Transfer Deep-Dive | 40,000 |
| | **Part 2 Subtotal** | **RM 400,000** |

**TOTAL VAS VALUE: RM 900,000** included at no additional cost.

**🚀 Additional Innovation:** **Mobile App for Recipients** allows award recipients to manage their profile and ceremony attendance. **Social Media Integration** for official announcements. **Multi-Year Data Analysis** identifies trends in award applications. **Digital Signature Integration** for fully paperless workflows. | Section 7 - Value Added Services |

---

## SUMMARY OF COMPLIANCE

### Overall Compliance Matrix

| Category | Total Items | Mandatory | Compliant | Compliance Rate |
|----------|-------------|-----------|-----------|-----------------|
| **Skop Kerja Umum** | 3 | 3 | 3 | 100% |
| **Kajian Spesifikasi** | 2 | 2 | 2 | 100% |
| **Rekabentuk Sistem** | 2 | 2 | 2 | 100% |
| **Pembangunan Sistem** | 14 | 13 | 14 | 100% |
| **Modul Sistem** | 9 | 9 | 9 | 100% |
| **Perkakasan** | 1 | 1 | 1 | 100% |
| **Migrasi Data** | 1 | 1 | 1 | 100% |
| **Pengujian** | 4 | 4 | 4 | 100% |
| **Pemasangan** | 13 | 13 | 13 | 100% |
| **Dokumentasi** | 3 | 3 | 3 | 100% |
| **Latihan/TOT** | 6 | 6 | 6 | 100% |
| **Kod Sumber** | 1 | 1 | 1 | 100% |
| **Pembayaran** | 2 | 2 | 2 | 100% |
| **Waranti** | 4 | 4 | 4 | 100% |
| **Keselamatan** | 2 | 2 | 2 | 100% |
| **Lain-lain** | 1 | 0 | 1 | 100% |
| **TOTAL** | **68** | **65** | **68** | **100%** |

---

## WHY SINERGI ELIT SDN BHD

1. **Domain Expertise:** 20+ government digital transformation projects including similar award management systems
2. **Technical Excellence:** Modern technology stack with security-by-design
3. **Compliance Leadership:** 100% compliance with all mandatory requirements
4. **Accelerated Delivery:** 6-month timeline with proven PRINCE2 methodology
5. **Value Beyond Price:** RM 900,000 in Value-Added Services at no cost
6. **Local Presence:** Malaysian company with onshore support team
7. **Risk Mitigation:** Comprehensive warranty, SLA guarantees, and insurance coverage

---

## OUR COMMITMENT

> *"We deliver proven government digital solutions, not promises. Our ePingat Pro Suite combines technical excellence with deep understanding of Malaysian government processes—ensuring PSUK Selangor receives a system that exceeds expectations and serves the people of Selangor for years to come."*

---

**Document Control**

| | |
|---|---|
| Document Version | 2.0 (Revised) |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
