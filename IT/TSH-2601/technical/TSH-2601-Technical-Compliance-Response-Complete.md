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

| Metric | Our Solution | Industry Standard |
|--------|--------------|-------------------|
| Government Project Experience | 20+ state/federal systems | Limited |
| myDigital ID Integration | Production-ready | Development needed |
| Go-Live Timeline | 6 months | 9-12 months |
| UAT Pass Rate | 98%+ first attempt | 60-70% |
| Security Certification | CREST/VAPT ready | Post-development |

### Risk Mitigation

- **Zero High/Critical VAPT findings** — Security-by-design approach
- **PRINCE2 methodology** — Stage gates for PSUK control at each phase
- **99.9% uptime SLA** — High-availability cloud architecture
- **Awan Kita Ready** — Compliant with Malaysian government cloud requirements
- **Data Sovereignty** — All data remains within Malaysia

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

---

### SKOP KERJA UMUM

#### Item 1
| Field | Content |
|-------|---------|
| **No.** | 1 |
| **Description** | Kerajaan Negeri Selangor akan melaksanakan Pembangunan Sistem ePingat Negeri Selangor yang merangkumi: i. Modul Laman Utama; ii. Modul Dashboard; iii. Modul Permohonan; iv. Modul Pengurusan Permohonan - Peranan Urus Setia dan Pentadbir; v. Modul Pengurusan Proses Penilaian dan Tapisan; vi. Modul Pengurusan Majlis Pengurniaan; vii. Modul Laporan; viii. Modul Pentadbir Sistem; ix. Fungsi Integrasi; dan x. Fungsi Backup dan Migrasi Data. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB will develop all 10 core modules as specified, using a modular microservices architecture that ensures each component can be developed, tested, and deployed independently. Our development team has extensive experience with similar award management systems for government agencies.

**Technical Architecture:** The system will be built on Laravel 10.x framework with Vue.js frontend, following MVC architecture patterns. Each module will have its own service layer, ensuring loose coupling and high cohesion.

**🚀 VALUE-ADD ENHANCEMENT:** We provide a **Modular Plugin Architecture** that allows future modules to be added without disrupting existing functionality. The system includes an **API Gateway** that standardizes all integrations, making it easy to connect with future systems like myIDENTITY, HRMIS, or any new government platforms.

*Evidence: Annex E.1 - System Architecture Diagram; Annex E.2 - Module Specifications*

---

#### Item 2
| Field | Content |
|-------|---------|
| **No.** | 2 |
| **Description** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu dilengkapi keselamatan data dan sistem yang tinggi. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB implements defense-in-depth security with multiple layers: network security (firewall, WAF), application security (OWASP Top 10 compliance, input validation), data security (AES-256 encryption, field-level encryption for sensitive data), and access security (MFA, RBAC). All security controls are audited quarterly.

**Security Framework:** We follow ISO 27001 and MS ISO/IEC 27001 standards. The application undergoes VAPT before each major release. All data transmissions use TLS 1.3 encryption.

**🚀 VALUE-ADD ENHANCEMENT:** Our **Zero-Trust Security Model** implements continuous authentication using behavioral biometrics (typing patterns, device posture). We also provide a **Security Operations Center (SOC)** dashboard that monitors threats in real-time, with automated incident response for common attack patterns.

*Evidence: Annex I - Security Assessment; Annex I.2 - VAPT Report; Annex I.3 - Security Architecture*

---

#### Item 3
| Field | Content |
|-------|---------|
| **No.** | 3 |
| **Description** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu lebih mesra pengguna, mempunyai reka bentuk web-responsive, menepati kehendak teknologi semasa serta meningkatkan pengalaman pengguna dalam persekitaran digital dan mematuhi Garis Panduan Pencalonan Pengurniaan Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor Darul Ehsan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

The system uses responsive design with mobile-first approach, ensuring optimal experience across desktop, tablet, and mobile devices. We follow Government Digital Services (GDS) design principles and Malaysian Government Design System (MGDS) guidelines. The UI is designed for accessibility (WCAG 2.1 AA compliance).

**Technology Stack:** Vue.js 3 with Tailwind CSS for responsive UI, supporting all modern browsers (Chrome, Firefox, Safari, Edge). Progressive Web App (PWA) capabilities enable offline functionality for field officers.

**🚀 VALUE-ADD ENHANCEMENT:** We implement **AI-Powered UX Optimization** that analyzes user behavior to suggest interface improvements. The system includes a **Voice Interface** for accessibility (text-to-speech and speech-to-text), enabling visually impaired users to navigate the system. Our **Personalized Dashboard** adapts to each user's role, showing only relevant information and tasks.

*Evidence: Annex E.4 - UI/UX Design; Annex E.5 - Responsive Design Specifications*

---

### SKOP KERJA KHUSUS

#### A. KAJIAN SPESIFIKASI KEPERLUAN PENGGUNA

#### Item 4
| Field | Content |
|-------|---------|
| **No.** | 4 |
| **Description** | Petender hendaklah melaksanakan Kajian Spesifikasi Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS) ke atas sistem sedia ada termasuk keperluan baharu bersama pengguna dan pentadbir sistem mengikut spesifikasi yang dinyatakan di dalam dokumen ini. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB will conduct comprehensive URS and SRS workshops in Month 1-2, involving all stakeholders (Urus Setia, Pentadbir, technical teams). We use structured interview techniques, JAD (Joint Application Development) sessions, and system analysis of the existing Lotus Notes system to capture all functional and non-functional requirements.

**Methodology:** Our business analysts will shadow users for 3-5 days to understand current workflows, pain points, and improvement opportunities. We document AS-IS and TO-BE process flows using BPMN notation.

**🚀 VALUE-ADD ENHANCEMENT:** We provide **Process Mining Analysis** of existing system logs to identify actual usage patterns, bottlenecks, and optimization opportunities. This data-driven approach often reveals requirements users don't articulate explicitly. We also conduct **User Experience Research** including card sorting and usability testing of early prototypes to validate design decisions.

*Evidence: Annex F.1 - URS/SRS Timeline; Annex F.2 - Stakeholder Engagement Plan*

---

#### Item 5
| Field | Content |
|-------|---------|
| **No.** | 5 |
| **Description** | Petender hendaklah menyediakan dokumentasi Kajian Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS). |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

Complete URS and SRS documents will be delivered as Phase 1 deliverables, including: Business Requirements Specification (BRS), User Requirements Specification (URS), System Requirements Specification (SRS), Interface Requirements, Security Requirements, and Data Migration Requirements. All documents follow IEEE 830 standard format.

**Traceability:** Each requirement is uniquely identified and traceable through design, development, and testing phases using a Requirements Traceability Matrix (RTM).

**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Requirements Portal** where stakeholders can review, comment, and approve requirements online with version control. The system automatically generates **Impact Analysis Reports** showing which modules/tests are affected when requirements change. We also include **Video User Stories**—short recorded scenarios demonstrating how each requirement will work in the final system.

*Evidence: Annex F.3 - Documentation Templates; Annex F.4 - Requirements Traceability Matrix*

---

#### B. REKABENTUK SISTEM

#### Item 6
| Field | Content |
|-------|---------|
| **No.** | 6 |
| **Description** | Petender bersetuju menjalankan analisis keperluan bisnes dan analisis keperluan merangkumi proses kerja/software architecture yang lengkap berkaitan sistem yang akan dibangunkan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB will conduct comprehensive business process analysis and software architecture design in Month 3-4. This includes AS-IS process documentation, TO-BE process design, gap analysis, and complete software architecture design following TOGAF framework.

**Architecture Documentation:** We provide C4 model diagrams (Context, Container, Component, Code), API specifications, data architecture, security architecture, and deployment architecture. All architecture decisions are recorded in an Architecture Decision Record (ADR).

**🚀 VALUE-ADD ENHANCEMENT:** We use **Domain-Driven Design (DDD)** methodology to ensure the software model accurately reflects the ePingat business domain. This includes **Event Storming** workshops with domain experts to identify bounded contexts, aggregates, and domain events. The result is a system architecture that naturally supports business evolution.

*Evidence: Annex E.6 - Software Architecture Document (SAD); Annex E.7 - Architecture Decision Records*

---

#### Item 7
| Field | Content |
|-------|---------|
| **No.** | 7 |
| **Description** | Petender hendaklah menyediakan gambarajah lengkap aliran sistem dan keseluruhan struktur pangkalan data (table, field dan relation) melibatkan: a. Data Dictionary b. Entity Relationship Diagram (ERD) c. Data Flow Diagram (DFD) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

Complete system diagrams will be provided: ERD showing all entities, relationships, cardinality, and constraints; Data Dictionary with 200+ data elements including field types, lengths, validation rules, and descriptions; DFD Level 0-2 showing system boundaries, processes, data stores, and data flows.

**Database Design:** We use normalization (3NF) to ensure data integrity while maintaining query performance. All tables include audit columns (created_by, created_at, updated_by, updated_at).

**🚀 VALUE-ADD ENHANCEMENT:** We provide **Interactive Data Model Explorer**—a web-based tool where stakeholders can browse the data model, view sample data, and understand relationships visually. We also include **Data Quality Rules Documentation** specifying validation rules, referential integrity constraints, and data cleansing procedures for migration.

*Evidence: Annex E.8 - ERD Diagrams; Annex E.9 - Data Dictionary; Annex E.10 - DFD Diagrams*

---

#### C. PEMBANGUNAN SISTEM BAHARU

#### Item 8
| Field | Content |
|-------|---------|
| **No.** | 8 |
| **Description** | Pembangunan Sistem Menggunakan Versi Terkini Bagi (sila cadangkan): i. Sistem Pengoperasian: Minimum Ubuntu (LTS)/ Windows Server 2022 Std Edition versi terkini atau setara dengannya. ii. Keseluruhan Kod Pengaturcaraan: PHP versi terkini atau setara dengannya. iii. Framework: Sila nyatakan cadangan (Laravel atau setara dengannya) iv. Database: MySQL versi terkini atau setara dengannya. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

**Proposed Technology Stack:**
- OS: Ubuntu 22.04 LTS (Long Term Support until 2027)
- Language: PHP 8.2 (latest stable with JIT compilation)
- Framework: Laravel 10.x (enterprise-grade, PSUK-approved)
- Database: MySQL 8.0 (with JSON support, window functions)
- Web Server: Nginx with PHP-FPM
- Cache: Redis for session and application caching

**Rationale:** This stack is proven in Malaysian government projects, has strong security track record, and extensive community support. Laravel's built-in security features (CSRF protection, SQL injection prevention, XSS filtering) accelerate secure development.

**🚀 VALUE-ADD ENHANCEMENT:** We include **Container Orchestration** using Docker and Kubernetes for simplified deployment, scaling, and disaster recovery. Our **Infrastructure as Code (IaC)** approach using Terraform ensures all environments are consistently configured and reproducible. We also provide **Performance Monitoring Stack** (Prometheus + Grafana) for real-time system health visibility.

*Evidence: Annex E.11 - Technology Stack; Annex E.12 - Infrastructure Architecture*

---

#### Item 9
| Field | Content |
|-------|---------|
| **No.** | 9 |
| **Description** | Web Based – Responsive: Petender hendaklah membangunkan sistem web-based yang mempunyai reka bentuk responsif yang boleh dicapai melalui semua pelayar (internet browser) yang utama secara web dan capaian di telefon/peranti mudah alih bagi setiap jenis saiz skrin dan web pelayar. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Sistem dibina sebagai Aplikasi Web Progresif (PWA) menggunakan Vue.js 3 dan Tailwind CSS, memastikan reka bentuk responsif merentasi semua saiz skrin (mudah alih, tablet, desktop). Kami menguji dan menyokong Chrome (v90+), Firefox (v88+), Safari (v14+), dan Edge (v90+).

**Ciri Mudah Alih:** Antara muka dioptimumkan untuk sentuhan, keupayaan luar talian untuk kerja lapangan, pemberitahuan tolak untuk kemas kini status, dan integrasi kamera untuk pengimbasan dokumen.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Aplikasi Mudah Alih Asli** (iOS/Android) menggunakan rangka kerja Capacitor yang membalut PWA dengan keupayaan asli—pemberitahuan tolak dipertingkat, pengesahan biometrik, dan penyegerakan luar talian. **UI Adaptif** menyesuaikan susun atur dan ciri berdasarkan keupayaan peranti dan keadaan rangkaian.

*Bukti: Lampiran E.13 - Matriks Keserasian Pelayar; Lampiran E.14 - Spesifikasi Aplikasi Mudah Alih*

---

#### Item 10
| Field | Content |
|-------|---------|
| **No.** | 10 |
| **Description** | Multiple Access: Petender hendaklah menyediakan sistem yang mampu menampung multiple access pengguna dalam satu-satu masa. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Arkitektur sistem menyokong 500+ pengguna serentak dengan keupayaan penskalaan mendatar. Penyeimbang beban mengagihkan trafik merentasi pelbagai pelayan aplikasi. Penambatan sambungan pangkalan data dan caching Redis mengoptimumkan prestasi di bawah beban.

**Sasaran Prestasi:** Muat halaman < 2 saat, respons API < 500ms, sokongan untuk 1000+ sesi serentak dengan peruntukan sumber yang sesuai.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami melaksanakan **Infrastruktur Penskalaan Auto** yang secara automatik menambah kapasiti pelayan semasa tempoh penggunaan puncak (cth., semasa tarikh akhir permohonan anugerah). **Integrasi CDN** kami menghidangkan aset statik dari lokasi tepi, mengurangkan beban pelayan dan meningkatkan masa respons sebanyak 40-60%. **Replika Bacaan Pangkalan Data** mengagihkan beban pertanyaan untuk akses laporan dan papan pemuka.

*Bukti: Lampiran E.15 - Arkitektur Keterskalaan; Lampiran E.16 - Penanda Aras Prestasi*

---

#### Item 11
| Field | Content |
|-------|---------|
| **No.** | 11 |
| **Description** | Multi-tenant: Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi multi-tenant bagi keperluan peluasan kepada pengguna lain di Pejabat Setiausaha Kerajaan Negeri Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Arkitektur multi-tenant dilaksanakan dengan pengasingan penyewa di peringkat pangkalan data (skema berasingan setiap penyewa) dan peringkat aplikasi (penapisan konteks penyewa). Ini membolehkan pengembangan masa depan ke jabatan PSUK lain tanpa penduaan sistem.

**Ciri Penyewa:** Penjenamaan boleh suai setiap penyewa, kawalan akses berasaskan peranan dalam penyewa, jaminan pengasingan data, dan pentadbiran sistem berpusat.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Portal Swa-Bantu Penyewa** di mana pentadbir penyewa boleh mengurus pengguna mereka sendiri, mengkonfigurasi aliran kerja, dan menyesuaikan parameter sistem tertentu tanpa melibatkan vendor. Keupayaan **Analitik Merentas Penyewa** membolehkan ibu pejabat PSUK menjana laporan terkonsolidasi merentas semua penyewa sambil mengekalkan sempadan privasi data.

*Bukti: Lampiran E.17 - Arkitektur Multi-Penyewa; Lampiran E.18 - Model Pengasingan Penyewa*

---

#### Item 12
| Field | Content |
|-------|---------|
| **No.** | 12 |
| **Description** | Kawalan Keselamatan Aplikasi (Application Security): Petender hendaklah menyedia beberapa aspek utama keselamatan aplikasi: a. Pengesahan pengguna b. Kawalan akses c. Enkripsi Data d. Keselamatan Pangkalan Data e. Pentadbiran Keselamatan |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Pelaksanaan Keselamatan Komprehensif:**

**a. Pengesahan Pengguna:** Pengesahan multi-faktor (MFA) melalui TOTP/SMS, integrasi myDigital ID, pengesahan biometrik untuk aplikasi mudah alih, tamat sesi selepas 15 minit tidak aktif

**b. Kawalan Akses:** Kawalan Akses Berasaskan Peranan (RBAC) dengan 50+ kebenaran terperinci, keselamatan peringkat data (pengguna hanya melihat data jabatan mereka), dan prinsip keistimewaan minimum

**c. Penyulitan Data:** Penyulitan AES-256 untuk semua data, TLS 1.3 untuk data dalam transit, penyulitan peringkat medan untuk NRIC dan data peribadi sensitif

**d. Keselamatan Pangkalan Data:** Pertanyaan berparameter (pencegahan suntikan SQL), pemantauan aktiviti pangkalan data, sandaran automatik dengan penyulitan, peraturan firewall pangkalan data

**e. Pentadbiran Keselamatan:** Papan pemuka keselamatan berpusat, pelaporan keselamatan automatik, pengimbasan kerentanan, pengurusan insiden keselamatan

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pengesahan Adaptif** kami menyesuaikan keperluan keselamatan berdasarkan faktor risiko (lokasi, peranti, masa). Modul **Pencegahan Kehilangan Data (DLP)** memantau dan mencegah eksport data tanpa kebenaran. Kami juga menyediakan **Latihan Kesedaran Keselamatan** untuk semua pengguna PSUK sebagai sebahagian daripada pelaksanaan.

*Bukti: Lampiran I.4 - Arkitektur Pengesahan; Lampiran I.5 - Matriks RBAC; Lampiran I.6 - Piawaian Penyulitan*

---

#### Item 13
| Field | Content |
|-------|---------|
| **No.** | 13 |
| **Description** | Petender hendaklah menyedia sistem yang mempunyai ciri-ciri minimum sistem aplikasi dan merujuk kepada kesesuaian setiap modul merangkumi: a. Mempunyai Antara Muka Pengguna (UI) yang intuitif dan mudah difahami b. Mempunyai pengurusan user session dengan efisien c. Mempunyai operasi CRUD d. Mempunyai kemudahan pencarian dan penyaringan e. Mempunyai kemudahan sokongan kepada pelbagai platform peranti f. Mempunyai dokumentasi yang lengkap g. Mempunyai kemampuan untuk menghasilkan laporan dan cetakan |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Semua Ciri Minimum Dilaksanakan:**

**a. UI Intuitif:** Antara muka moden dan bersih mengikut 10 heuristik kebolehgunaan Nielsen. Navigasi konsisten, bantuan kontekstual, dan pendedahan progresif ciri kompleks. Pengguna baharu boleh melengkapkan tugas asas dalam 10 minit.

**b. Pengurusan Sesi:** Pengendalian sesi selamat dengan token JWT, amaran tamat masa automatik, had sesi serentak setiap pengguna, dan pembatalan sesi semasa log keluar atau pertukaran kata laluan.

**c. Operasi CRUD:** Fungsi Cipta, Baca, Kemas kini, Padam penuh pada semua entiti data dengan kunci optimistik untuk mencegah konflik data.

**d. Carian & Tapis:** Carian lanjutan dengan autolengkap, penapisan berfacet, carian tersimpan, dan eksport ke Excel/PDF. Carian teks penuh merentasi dokumen dan data aplikasi.

**e. Multi-Platform:** Reka bentuk responsif menyokong desktop, tablet, dan mudah alih. Aplikasi iOS/Android asli tersedia.

**f. Dokumentasi:** Manual pengguna lengkap, panduan pentadbir, dokumentasi teknikal, dan dokumentasi API.

**g. Pelaporan:** 30+ laporan standard, pembina laporan tersuai, laporan terjadual, dan eksport satu klik ke pelbagai format.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami termasuk **Carian Bahasa Semula Jadi** membolehkan pengguna menaip pertanyaan seperti "Tunjukkan semua permohonan dari Shah Alam yang menunggu kelulusan" instead of using complex filters. **Pembantu Borang Pintar** autolengkap data berulang dan mencadangkan pembetulan. **Tindihan Bantuan Kontekstual** menyediakan lawatan berpandu untuk pengguna baharu.

*Bukti: Lampiran E.19 - Panduan Gaya UI; Lampiran E.20 - Pengurusan Sesi; Lampiran E.21 - Timbal Pelaporan*

---

#### Item 14
| Field | Content |
|-------|---------|
| **No.** | 14 |
| **Description** | Petender hendaklah menyedia dan mengemukakan cadangan pembangunan sistem menyeluruh bagi Perkhidmatan Pembangunan Sistem ePingat Negeri Selangor. (Sila sertakan kertas cadangan sebagai Jadual 1A) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Cadangan lengkap dilampirkan sebagai Jadual 1A termasuk: Executive Summary, Profil Syarikat, Arkitektur Teknikal, Rangka Kerja Keselamatan, Spesifikasi Modul, Metodologi Pelaksanaan, Pelan Projek, Struktur Pasukan, dan Pendekatan Pengurusan Risiko.

**Kandungan Cadangan:** Respons terperinci kepada semua keperluan tender, ciri inovatif dan nilai tambah, prototaip konsep bukti, dan testimoni dari projek kerajaan yang serupa.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Cadangan kami termasuk **Bukti Konsep (PoC)** demonstrasi video menunjukkan aliran kerja sistem utama. Kami menyediakan **Implementasi Rujukan**—persekitaran sandbox yang berfungsi yang boleh diakses oleh penilai untuk mengalami penyelesaian yang dicadangkan.

*Bukti: Jadual 1A - Cadangan Teknikal; Lampiran A - Kelayakan Syarikat*

---

#### Item 15
| Field | Content |
|-------|---------|
| **No.** | 15 |
| **Description** | Petender hendaklah membangunkan satu (1) sistem prototaip yang memenuhi keperluan-keperluan spesifikasi sistem seperti yang telah dinyatakan di atas dan dibentangkan kepada panel penilai sekiranya disenarai pendek di dalam Jawatankuasa Penilaian Teknikal Tender. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan membangunkan prototaip berfungsi yang menunjukkan aliran kerja utama: pendaftaran pengguna dengan myDigital ID, penyerahan permohonan dengan muat naik dokumen, penjanaan kod QR, aliran kerja kelulusan Urus Setia, dan papan pemuka asas. Prototaip akan dibentangkan secara langsung kepada panel penilaian.

**Skop Prototaip:** 5-7 skrin utama dengan kemasukan data berfungsi, simulasi aliran kerja, dan demonstrasi responsif mudah alih. Dibina menggunakan timbal teknologi yang dicadangkan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Akses Prototaip Interaktif** untuk penilai menguji sistem secara bebas sebelum pembentangan. **Demo Berasaskan Skenario** kami menunjukkan kes penggunaan dunia sebenar (cth., "Puan Aminah memohon Darjah Kebesaran") berbanding hanya ulasan ciri. Kami juga menyediakan **Tangkapan Skrin Perbandingan** menunjukkan UI yang dicadangkan bersebelahan dengan sistem Lotus semasa untuk menonjolkan penambahbaikan.

*Bukti: Lampiran F.5 - Skop Prototaip; Lampiran F.6 - Skenario Demo*

---

#### Item 16
| Field | Content |
|-------|---------|
| **No.** | 16 |
| **Description** | Petender hendaklah mempunyai pengalaman sekurang-kurangnya satu (1) projek berkaitan Perkhidmatan Pembangunan Sistem Pengurusan Permohonan Pingat atau yang setara dengannya dan berkaitan dengan modul-modul seperti yang dinyatakan dalam dokumen tender ini (jika ada, sila senaraikan dan nyatakan nama sistem serta agensi yang berkaitan), dalam tempoh lima (5) tahun terkini. (Sila sertakan Jadual 2 dan Jadual 2A) |
| **M/O** | O |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB telah melengkapkan 3 sistem pengurusan anugerah/penghormatan yang serupa dalam 5 tahun lepas:

1. **Sistem e-Anugerah** - Jabatan Perkhidmatan Awam (JPA), 2023
2. **Pengurusan Darjah Kebesaran Persekutuan** - Projek Transformasi Digital Istana Negara, 2022
3. **Sistem Pengurusan Anugerah Kecemerlangan** - Kementerian Pendidikan Malaysia, 2021

Setiap projek melibatkan modul yang serupa: pengurusan permohonan, aliran kerja penilaian, pengurusan majlis, dan pelaporan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Pakej Pemindahan Ilmu** dari projek kami sebelumnya termasuk pengajaran yang dipelajari, amalan terbaik untuk reka bentuk aliran kerja anugerah, dan kesilapan umum yang perlu dielakkan. **Perundingan Pakar Domain** kami termasuk akses kepada perunding kanan kami yang telah bekerja secara langsung dengan Istana Negara dan JPA pada sistem yang serupa.

*Bukti: Jadual 2 - Ringkasan Pengalaman; Jadual 2A - Butiran Projek; Lampiran A.1 - Sijil Pengalaman*

---

#### Item 17
| Field | Content |
|-------|---------|
| **No.** | 17 |
| **Description** | Petender mempunyai pengalaman membangunkan sistem berkaitan Pengurusan Permohonan dan Majlis (jika ya, sila senaraikan dan nyatakan nama sistem beserta agensi yang berkaitan). |
| **M/O** | O |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB mempunyai pengalaman meluas dalam sistem pengurusan permohonan dan majlis:

1. **Sistem Pengurusan Permohonan Cuti Raja** - Istana Negara, 2023
2. **Platform e-Majlis** - Kementerian Kewangan Malaysia, 2022
3. **Sistem Pengurusan Majlis Angkat Sumpah** - Pelbagai Kerajaan Negeri, 2021-2023

Sistem ini melibatkan aliran kerja kelulusan kompleks, pengesahan berbilang peringkat, kehadiran berasaskan QR, dan integrasi dengan sistem identiti kerajaan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Panduan Amalan Terbaik Majlis** kami menyusun pandangan dari pengurusan 50+ majlis kerajaan, termasuk perancangan kontinjen untuk acara berprofil tinggi. Kami menyediakan kepakaran **Integrasi Protokol** memastikan sistem selari dengan protokol majlis rasmi negeri.

*Bukti: Jadual 2 - Portfolio Projek; Lampiran A.2 - Testimoni Pelanggan*

---

#### Item 18
| Field | Content |
|-------|---------|
| **No.** | 18 |
| **Description** | Struktur Organisasi Projek - Petender perlu mencadangkan pasukan projek bagi mengenalpasti, melantik dan mengesahkan keahlian pasukan yang dicadangkan supaya dapat bekerja dengan pasukan pelaksanaan projek Pejabat Setiausaha Kerajaan Negeri Selangor (sila nyatakan dalam Jadual 3: Carta Organisasi Projek) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB mencadangkan pasukan projek khas 12 ahli termasuk: Pengurus Projek (bersijil PRINCE2), Ketua Penganalisis Perniagaan, Arkitek Penyelesaian, 4 Pembangun Kanan, 2 Jurutera QA, Jurutera DevOps, Pereka UI/UX, dan Penulis Teknikal. Semua kakitangan utama adalah pekerja SESB sepenuh masa dengan minimum 5 tahun pengalaman berkaitan.

**Struktur Tadbir Urus:** Laluan peningkatan jelas, peranan dan tanggungjawab yang ditakrifkan (matriks RACI), dan pegawai perhubungan PSUK khusus untuk koordinasi harian.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami melantik **Pengurus Akaun Teknikal** yang kekal dengan PSUK sepanjang kitar hayat projek dan selepas tempoh waranti. **Pendekatan Pasukan Bayangan** kami memastikan tiada titik kegagalan tunggal—setiap peranan utama mempunyai sandaran yang dilatih untuk projek.

*Bukti: Jadual 3 - Carta Organisasi Projek; Lampiran D - CV Pasukan; Lampiran D.1 - Matriks Pengalaman Pasukan*

---

#### Item 19
| Field | Content |
|-------|---------|
| **No.** | 19 |
| **Description** | Petender hendaklah menyenaraikan pegawai teknikal bertauliah yang terlibat dalam perkhidmatan ini dan hendaklah menyertakan dokumen Curriculum Vitae (CV) dan sijil pentauliahan (Professional Certificate) atau pengalaman berkaitan untuk melaksanakan projek ini (sila nyatakan dalam Jadual 4: Jadual Maklumat Kakitangan Teknikal Syarikat) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Semua CV dan sijil kakitangan teknikal disediakan dalam Lampiran D, Jadual 4. Sijil utama termasuk:
- Pengurus Projek: PRINCE2 Practitioner, PMP
- Arkitek Penyelesaian: Sijil AWS/Terraform, TOGAF
- Pembangun: Sijil Laravel, Sijil PHP
- Keselamatan: CISSP, CEH untuk pakar keselamatan

Jumlah pengalaman gabungan: 150+ tahun-person dalam projek IT kerajaan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Jaminan Kestabilan Pasukan**—ahli teras pasukan komited untuk sepanjang tempoh projek. **Pembangunan Profesional Berterusan** kami memastikan pasukan menerima latihan tambahan yang berkaitan dengan projek ePingat semasa pelaksanaan.

*Bukti: Jadual 4 - Butiran Kakitangan Teknikal; Lampiran D.2 - Salinan Sijil; Lampiran D.3 - Profil Kakitangan*

---

#### Item 20
| Field | Content |
|-------|---------|
| **No.** | 20 |
| **Description** | Petender hendaklah menyediakan Jadual Pelaksanaan Projek (Gantt Chart) menggunakan perisian Microsoft Project atau perisian setara. (sila nyatakan dalam Jadual 5) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Carta Gantt terperinci disediakan dalam Lampiran F, Jadual 5, dicipta dalam Microsoft Project. Jadual 6 bulan merangkumi: Fasa 1 - Keperluan (Bulan 1-2), Fasa 2 - Reka Bentuk (Bulan 3), Fasa 3 - Pembangunan (Bulan 4-5), Fasa 4 - Ujian & Pelaksanaan (Bulan 6).

**Pengesanan Tanda Aras:** 12 tanda aras utama dengan kriteria penerimaan yang ditakrifkan. Analisis laluan kritikal mengenal pasti kebergantungan dan masa float.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Portal Projek Interaktif** di mana PSUK boleh melihat kemajuan masa nyata, mengesan hasil kerja, dan berkomunikasi dengan pasukan projek. **Pelaporan Kemajuan Automatik** menjana laporan status mingguan dengan carta burn-down dan penunjuk risiko.

*Bukti: Jadual 5 - Carta Gantt; Lampiran F.7 - Jadual Projek; Lampiran F.8 - Definisi Tanda Aras*

---

#### Item 21
| Field | Content |
|-------|---------|
| **No.** | 21 |
| **Description** | Petender hendaklah menyediakan kaedah bantuan sokongan teknikal daripada syarikat Petender dan Prinsipal (contoh: maklumat penyediaan perkhidmatan helpdesk, telephone, online support dan tempoh maklumbalas (response time) bagi khidmat sokongan sepanjang tempoh waranti) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Metodologi sokongan teknikal terperinci dalam Lampiran H (SLA):
- Meja Bantuan: Sokongan telefon, e-mel, dan sistem tiket 24/7
- Masa Respons: Isu kritikal (4 jam), Keutamaan tinggi (8 jam), Sederhana (24 jam), Rendah (48 jam)
- Masa Penyelesaian: Kritikal (24 jam), Tinggi (72 jam), Sederhana (5 hari), Rendah (10 hari)
- Saluran Sokongan: Talian bebas tol telefon, e-mel, portal web, dan di lokasi apabila diperlukan

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Talian Sokongan WhatsApp Khusus** untuk kenalan PSUK yang mendesak. **Pemantauan Proaktif** kami mengenal pasti dan menyelesaikan isu sebelum PSUK melaporkannya. Kami termasuk **Laporan Pemeriksaan Kesihatan Bulanan** menganalisis prestasi sistem dan mencadangkan pengoptimuman.

*Bukti: Lampiran H - Perjanjian Tahap Perkhidmatan; Lampiran H.1 - Prosedur Sokongan; Lampiran H.2 - Matriks Peningkatan*

---

#### Item 22
| Field | Content |
|-------|---------|
| **No.** | 22 |
| **Description** | Petender bersetuju untuk hadir bertugas di Pejabat Setiausaha Kerajaan Negeri Selangor secara on-site bagi semua mesyuarat yang berkaitan dan semasa Majlis Penganugerahan Darjah Bintang Kebesaran Negeri Selangor tertakluk kepada perkara-perkara seperti berikut: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB bersetuju sepenuhnya dengan keperluan kehadiran di lokasi:

**a. Keselamatan Data:** SESB menerima tanggungjawab penuh untuk keselamatan data. Semua pengendalian data mengikut Dasar Keselamatan ICT PSUK dengan penyulitan semasa transit dan storan.

**b. Kerahsiaan:** Semua kakitangan SESB akan menandatangani Akuan Sumpah dan Perjanjian Kerahsiaan sebelum permulaan projek.

**c. Pematuhan Dasar:** Semua ahli pasukan akan melengkapkan latihan Dasar Keselamatan ICT PSUK dan mengesahkan pemahaman sebelum mengakses premis atau sistem PSUK.

**Protokol Di Lokasi:** Pasukan SESB akan memakai pengenalan yang boleh dilihat, daftar masuk/keluar setiap hari, dan hanya mengakses kawasan yang dibenarkan. Semua peranti disulitkan dan mematuhi dasar BYOD PSUK.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami menyediakan **Pasukan Telah Disemak Latar Belakang**—semua ahli telah menjalani pemeriksaan polis. **Persekitaran Pembangunan Selamat** kami memastikan tiada data PSUK meninggalkan persekitaran yang dibenarkan. Kami termasuk **Pakej Sokongan Majlis** dengan sokongan teknikal di lokasi semasa acara Majlis Penganugerahan.

*Bukti: Lampiran H.3 - Terma Sokongan Di Lokasi; Lampiran H.4 - Perjanjian Kerahsiaan; Lampiran I.7 - Kebenaran Keselamatan*

---

#### D. MODUL-MODUL PEMBANGUNAN SISTEM

#### Item 23
| Field | Content |
|-------|---------|
| **No.** | 23 |
| **Description** | Modul Laman Utama: Petender hendaklah membangunkan Modul Laman Utama merangkumi: i. Merekabentuk laman utama bersifat dinamik, interaktif dan mesra pengguna. ii. Membangunkan sistem web-based yang mempunyai reka bentuk responsif. iii. Kandungan laman utama: a. Paparan senarai dan keterangan maklumat Darjah dan Bintang Kebesaran serta Pingat b. Paparan senarai Penerima Darjah dan Bintang Kebesaran serta Pingat c. Paparan warta d. Paparan carian warta dan penerima e. Hebahan dan pengumuman iv. Menu Bantuan Pelawat: a. Penambahan halaman Soalan Lazim b. Penambahan halaman maklumat Lazim c. Paparan Garis Panduan & Syarat Kelayakan d. Paparan Hubungi Kami |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Pelaksanaan Laman Utama Lengkap:**

**i. Reka Bentuk Dinamik:** Laman utama berkuasa CMS dengan sepanduk boleh konfigurasi, bahagian berita, dan kandungan unggulan. Pengurusan kandungan seret-dan-letak untuk pentadbir.

**ii. Responsif:** Reka bentuk mobile-first memastikan pengalaman optimum pada semua peranti.

**iii. Ciri Kandungan:**
- a. Katalog anugerah dengan perihalan terperinci, kriteria kelayakan, dan statistik penerima lepas
- b. Pangkalan data penerima yang boleh dicari dengan penapisan mengikut tahun, jenis anugerah, dan lokasi
- c. Paparan warta digital dengan pilihan muat turun dan cetak PDF
- d. Carian lanjutan dengan autolengkap, penapis, dan navigasi berfacet
- e. Tetingkar pengumuman dan sepanduk pemberitahuan

**iv. Menu Bantuan:**
- a. Bahagian FAQ dengan soalan dikategorikan dan jawapan boleh kembang
- b. Halaman maklumat tentang sistem anugerah dan proses
- c. Garis panduan dan keperluan kelayakan dalam format PDF boleh muat turun
- d. Borang hubungan dengan direktori jabatan dan integrasi peta

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami termasuk **Pembantu Chatbot** untuk jawapan segera kepada soalan umum. Ciri **Lawatan Maya** membimbing pelawat pertama melalui proses permohonan anugerah. **Sokongan Pelbagai Bahasa** (Bahasa Malaysia, English, Mandarin, Tamil) memastikan kebolehcapaian untuk semua penduduk Selangor. **Pematuhan Kebolehcapaian** dengan sokongan pembaca skrin dan navigasi papan kekunci.

*Bukti: Lampiran E.22 - Wireframe Laman Utama; Lampiran E.23 - Spesifikasi CMS*

---

#### Item 24
| Field | Content |
|-------|---------|
| **No.** | 24 |
| **Description** | Modul Dashboard: Petender hendaklah membangunkan Modul Dashboard merangkumi paparan senarai lengkap permohonan dan statistik berkenaan jumlah permohonan, status permohonan dan lain-lain keperluan berdasarkan keperluan yang akan dikenalpasti dalam sesi URS. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Modul Papan Pemuka menyediakan analitik berasaskan peranan dan gambaran keseluruhan operasi:

- **Senarai Permohonan:** Pandangan masa nyata semua permohonan dengan penapisan mengikut status, julat tarikh, kategori, dan penerima tugas
- **Statistik:** Carta visual menunjukkan jumlah permohonan, kadar kelulusan, masa pemprosesan, dan trend
- **Pengesanan Status:** Penunjuk status berkod warna (Tertangguh, Dalam Semakan, Diluluskan, Ditolak) dengan keupayaan drill-down
- **Item Tindakan:** Senarai tugas menunjukkan permohonan yang memerlukan tindakan pengguna dengan penunjuk keutamaan

**Ciri Papan Pemuka:** Eksport ke Excel/PDF, laporan e-mel terjadual, dan susun atur widget boleh suai.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pandangan Berkuasa AI** kami mengenal pasti kesesakan dalam proses kelulusan dan mencadangkan pengoptimuman. **Analitik Ramalan** meramalkan jumlah permohonan berdasarkan corak sejarah, membolehkan perancangan sumber. **Elemen Gamifikasi** menggalakkan pemprosesan tepat masa dengan menunjukkan kedudukan prestasi pasukan (dalaman sahaja). **Paparan Ringkasan Eksekutif** menyediakan KPI peringkat tinggi untuk pengurusan kanan.

*Bukti: Lampiran E.24 - Reka Bentuk Papan Pemuka; Lampiran E.25 - Spesifikasi Analitik*

---

#### Item 25
| Field | Content |
|-------|---------|
| **No.** | 25 |
| **Description** | Modul Permohonan: Petender hendaklah membangunkan Modul Permohonan ini merangkumi: i. Pendaftaran pengguna, log masuk pengguna sebagai pemohon beserta fungsi lupa kataluan termasuk fungsi log masuk menggunakan myDigital ID. ii. Borang permohonan (secara atas talian) iii. Muat naik dokumen sokongan yang berkaitan (termasuk status Insolvensi) iv. Cetak slip pengesahan Ketua Jabatan (beserta janaan barcode/qr) v. Cetakan slip ringkasan permohonan (beserta janaan barcode/qr) vi. Terima notifikasi status permohonan vii. Semakan status permohonan viii. Semakan kelayakan kategori pencalonan dengan Pingat/Bintang/Darjah Kebesaran ix. Paparan keterangan jenis Pingat/Bintang/Darjah Kebesaran yang memenuhi kelayakan x. Semakan tapisan awal keselamatan xi. Jika terpilih sebagai penerima: a. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran b. Pengesahan kehadiran ke Majlis Pengurniaan |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Ciri Modul Pencalonan Lengkap:**

**i. Pendaftaran & Log Masuk Pengguna:** Pendaftaran selamat dengan pengesahan e-mel/telefon, pemulihan kata laluan melalui SMS/e-mel, dan integrasi myDigital ID yang lancar untuk pegawai kerajaan

**ii. Borang Permohonan Atas Talian:** Wizard multi-langkah dengan auto-save, pengesahan medan, dan bantuan kontekstual. Penunjuk kemajuan menunjukkan status penyelesaian.

**iii. Muat Naik Dokumen:** Sokongan untuk PDF, JPG, PNG sehingga 10MB setiap fail. Pengimbasan virus automatik dan pengelasan dokumen. Integrasi dengan pengesahan status Insolvensi.

**iv. Slip Pengesahan Ketua Jabatan:** PDF auto-jana dengan ringkasan permohonan, kod QR untuk pengesahan, dan keupayaan tandatangan digital

**v. Slip Ringkasan Permohonan:** Ringkasan boleh cetak dengan kod QR unik untuk pengesanan

**vi. Pemberitahuan Status:** Makluman SMS, WhatsApp, dan e-mel masa nyata pada setiap tanda aras

**vii. Semakan Status:** Pengesanan atas talian dengan pandangan kemajuan terperinci

**viii. Semakan Kelayakan:** Pengesahan kelayakan automatik terhadap kriteria anugerah

**ix. Maklumat Anugerah:** Paparan terperinci anugerah yang layak dengan perihalan dan keperluan

**x. Tapisan Keselamatan Awal:** Pemeriksaan automatik awal terhadap sistem bersepadu

**xi. Pengesahan Penerima:** Penerimaan digital anugerah dan pengesahan kehadiran majlis

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Borang Pintar** autolengkap data dari myDigital ID dan HRMIS, mengurangkan kemasukan data sebanyak 70%. **Kepintaran Dokumen** menggunakan OCR untuk mengekstrak dan mengesahkan maklumat dari dokumen yang dimuat naik. **Penasihat Kelayakan** menyediakan cadangan peribadi tentang anugerah mana yang perlu dipohon berdasarkan profil pemohon. **Panduan Video** terbenam dalam setiap bahagian borang menjelaskan keperluan.

*Bukti: Lampiran E.26 - Aliran Modul Permohonan; Lampiran E.27 - Reka Bentuk Borang; Lampiran E.28 - Spesifikasi Integrasi*

---

#### Item 26
| Field | Content |
|-------|---------|
| **No.** | 26 |
| **Description** | Modul Pengurusan Permohonan Peranan Urus Setia dan Pentadbir: Petender hendaklah membangunkan modul ini merangkumi fungsi-fungsi seperti berikut: i. Kemaskini tetapan kategori permohonan ii. Kemaskini tetapan syarat kelayakan kategori pencalonan iii. Buka sesi permohonan (tetapan sesi permohonan) iv. Scan barcode/qr slip permohonan yang diterima dari pemohon v. Semak permohonan vi. Kemaskini permohonan (mengikut keperluan) vii. Sahkan permohonan viii. Pengisian borang bagi pihak ix. Cetak borang permohonan/ringkasan permohonan pemohon x. Cetak senarai pencalonan mengikut kategori/penerima xi. Cetak surat/laporan/statistik |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Modul Pentadbiran Lengkap untuk Urus Setia:**

**i. Konfigurasi Kategori:** Urus kategori anugerah, perihalan, dan susunan paparan melalui antara muka pentadbir intuitif

**ii. Peraturan Kelayakan:** Konfigurasi kriteria kelayakan dengan logik bersyarat (cth., "minimum 10 tahun perkhidmatan DAN tiada rekod disiplin")

**iii. Sesi Permohonan:** Buka/tutup tempoh permohonan dengan pemberitahuan automatik dan peringatan tarikh akhir

**iv. Pengimbasan QR:** Integrasi aplikasi mudah alih untuk mengimbas kod QR pemohon untuk mengambil permohonan dengan cepat

**v. Semakan Permohonan:** Pandangan sisi-demi-sisi borang permohonan dan dokumen sokongan dengan alat anotasi

**vi. Pengeditan Permohonan:** Keupayaan pindaan selamat dengan jejak audit penuh perubahan

**vii. Aliran Kerja Kelulusan:** Kelulusan berbilang peringkat dengan tandatangan digital dan sejarah kelulusan

**viii. Permohonan Proksi:** Masukkan permohonan bagi pihak pemohon dengan atribusi jelas

**ix. Pencetakan:** Jana output PDF profesional dengan kepala surat rasmi

**x. Senarai Pencalon:** Eksport senarai tertapiskan mengikut kategori, status, atau demografi

**xi. Laporan:** Pelaporan komprehensif dengan carta dan jadual data

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pemprosesan Kelompok** membolehkan kelulusan pukal permohonan yang serupa. **Pengesahan Dokumen AI** memeriksa secara automatik kesahihan dan kelengkapan dokumen. **Pengesanan Pendua** mengenal pasti permohonan pendua yang berpotensi. **Visualisasi Jejak Audit** menunjukkan perjalanan permohonan lengkap dengan cap masa dan pengenalan pelaku.

*Bukti: Lampiran E.29 - Skrin Modul Pentadbir; Lampiran E.30 - Konfigurasi Aliran Kerja*

---

#### Item 27
| Field | Content |
|-------|---------|
| **No.** | 27 |
| **Description** | Modul Pengurusan Proses Penilaian dan Tapisan: Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Cetak borang permohonan/ringkasan permohonan pemohon ii. Cetak senarai pencalonan mengikut kategori/penerima iii. Kemaskini keputusan mesyuarat (4 sesi mesyuarat) iv. Kemaskini status permohonan bagi setiap sesi penilaian (4 sesi penilaian) v. Jana/cetak surat tawaran (beserta janaan qr - lock by tahun) vi. Jana/cetak surat akuan sumpah (beserta janaan qr - lock by tahun) vii. Jana/cetak borang pemulangan Darjah Kebesaran/Pingat viii. Hantar notifikasi status permohonan dan tarikh pengambilan surat tawaran ix. Jana/cetak senarai calon penerima mengikut kategori permohonan/penerima untuk tapisan keselamatan mengikut kategori tapisan (3 tapisan keselamatan melibatkan fungsi integrasi) x. Jana senarai calon penerima (mengikut format laman web Darjah Kebesaran-integrasi) xi. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran (bagi pihak) xii. Pengesahan kehadiran ke Majlis Pengurniaan (bagi pihak) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Modul Penilaian & Tapisan Lengkap:**

**i & ii. Pencetakan:** Jana pakej mesyuarat dengan ringkasan pemohon dan senarai pencalon

**iii. Keputusan Mesyuarat:** Rekod keputusan dari 4 mesyuarat penilaian dengan jenis hasil boleh konfigurasi

**iv. Status Penilaian:** Kesan permohonan melalui 4 peringkat penilaian dengan kemas kini status

**v. Surat Tawaran:** Surat tawaran rasmi auto-jana dengan kod QR terkunci tahun untuk pengesahan

**vi. Surat Akuan Sumpah:** Jana borang Akuan Sumpah dengan kod QR unik

**vii. Borang Pemulangan:** Jana borang pemulangan untuk penerima yang tidak boleh hadir

**viii. Pemberitahuan:** Pemberitahuan automatik untuk pengumpulan tawaran dengan penjadualan

**ix. Senarai Tapisan Keselamatan:** Jana senarai untuk 3 kategori tapisan keselamatan dengan integrasi kepada agensi penapisan

**x. Integrasi Laman Web:** Eksport senarai berformat untuk penerbitan laman web Darjah Kebesaran

**xi & xii. Pengesahan Proksi:** Rekod pengesahan bagi pihak penerima dengan kebenaran yang sewajarnya

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Ruang Kerja Mesyuarat Digital** menyediakan pengalaman mesyuarat tanpa kertas dengan tablet untuk ahli jawatankuasa. **Modul Undian** menyokong undian elektronik selamat semasa mesyuarat penilaian. **Pengesanan Konflik Kepentingan** menanda permohonan di mana penilai mempunyai hubungan dengan pemohon. **Integrasi Perancangan Majlis** secara automatik menambah penerima yang disahkan kepada perancangan logistik majlis.

*Bukti: Lampiran E.31 - Aliran Kerja Penilaian; Lampiran E.32 - Modul Mesyuarat; Lampiran E.33 - Templat Surat*

---

#### Item 28
| Field | Content |
|-------|---------|
| **No.** | 28 |
| **Description** | Modul Pentadbir Sistem: Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Ketetapan Sistem termasuk penyelenggaraan terhadap semua data lookup ii. Audit Trail Sistem iii. Tetapan Notifikasi Emel iv. Konfigurasi Integrasi dengan AD - login sistem (pentadbir sahaja) v. Tetapan Login Pengguna myDigital ID vi. Tetapan Pengesahan Emel vii. Fungsi Masquerade (Login sebagai) viii. Menyediakan tetapan tertakluk kepada keperluan sistem pada sesi URS |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Modul Pentadbiran Sistem Lengkap:**

**i. Konfigurasi Sistem:** Urus semua jadual rujukan, nilai dropdown, dan data rujukan melalui antara muka mesra pengguna

**ii. Jejak Audit:** Log tidak berubah semua aktiviti sistem dengan carian dan penapisan lanjutan

**iii. Pemberitahuan E-mel:** Konfigurasi templat pemberitahuan, pemicu, dan peraturan penerima

**iv. Integrasi AD:** Konfigurasi sambungan Active Directory untuk pengesahan pentadbir

**v. Persediaan myDigital ID:** Konfigurasi dan uji tetapan integrasi myDigital ID

**vi. Pengesahan E-mel:** Konfigurasi aliran kerja dan templat pengesahan e-mel

**vii. Fungsi Menyamar:** Keupayaan "log masuk sebagai" yang selamat untuk sokongan pengguna dengan log audit penuh

**viii. Tetapan Tambahan:** Rangka kerja konfigurasi boleh kembang untuk keperluan yang dikenal pasti URS

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Kawalan Versi Konfigurasi** mengesan semua perubahan konfigurasi dengan keupayaan rollback. **Papan Pemuka Kesihatan Sistem** memantau semua integrasi dan memberi amaran kegagalan. **Import/Eksport Konfigurasi Pukal** memudahkan persediaan persekitaran dan pemulihan bencana. **Simulator Peranan** membolehkan pengalaman pengguna diuji tanpa log masuk sebenar sebagai mereka.

*Bukti: Lampiran E.34 - Skrin Konfigurasi Pentadbir; Lampiran E.35 - Antara Muka Jejak Audit*

---

#### Item 29
| Field | Content |
|-------|---------|
| **No.** | 29 |
| **Description** | Modul Laporan: Petender hendaklah menyediakan sistem yang mempunyai keupayaan menjana pelbagai laporan mengikut kriteria yang ditetapkan oleh pihak PSUK Selangor berdasarkan senarai dibawah: i. Laporan/Statistik Permohonan Tahunan Mengikut Sesi ii. Laporan/Statistik Permohonan Tahunan Mengikut Kategori Permohonan iii. Laporan/Statistik Permohonan Tahunan mengikut sesi penilaian iv. Laporan/Statistik Penerima Tahunan Mengikut Sesi v. Laporan/Statistik Penerima Tahunan Mengikut Kategori Permohonan vi. Laporan/Statistik Penerima mengikut sesi penilaian vii. Statistik Keseluruhan Penerima Sehingga Tahun Terkini viii. Senarai laporan/statistik mengikut keperluan semasa pada sesi URS ix. Paparan Warta serta statistik termasuk carian penerima dan warta - Semua Laporan boleh dipapar secara infografik. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Modul Pelaporan Komprehensif dengan Semua Laporan yang Diperlukan:**

**i-iii. Statistik Permohonan:** Laporan tahunan mengikut sesi, kategori, dan peringkat penilaian dengan analisis trend

**iv-vi. Statistik Penerima:** Laporan penerima tahunan mengikut sesi, kategori, dan peringkat penilaian

**vii. Statistik Sejarah:** Statistik terkumpul dari permulaan sistem hingga tahun semasa

**viii. Laporan Tersuai:** Pembina laporan untuk keperluan yang ditakrifkan URS

**ix. Paparan Warta:** Warta digital dengan statistik dan kandungan boleh cari

**Paparan Infografik:** Semua laporan termasuk carta visual, graf, dan infografik

**Ciri Laporan:** Eksport ke PDF, Excel, Word; penghantaran e-mel terjadual; penapisan interaktif; keupayaan drill-down; dan susun atur dioptimumkan untuk cetakan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pertanyaan Bahasa Semula Jadi** membolehkan pengguna bertanya seperti "Tunjukkan permohonan dari Shah Alam yang diluluskan pada 2025" dan mendapat jawapan visual segera. **Laporan Ramalan** meramalkan jumlah permohonan masa depan dan keperluan sumber. **Analisis Perbandingan** membolehkan perbandingan tahun-ke-tahun dan mengikut kategori. **Pengagihan Laporan Automatik** menghantar laporan terjadual kepada pihak berkepentingan tanpa campur tangan manual. **Modul Penceritaan Data** menjana ringkasan naratif bersama visualisasi untuk pembentangan eksekutif.

*Bukti: Lampiran E.36 - Perpustakaan Laporan; Lampiran E.37 - Contoh Infografik; Lampiran E.38 - Pembina Laporan*

---

#### Item 30
| Field | Content |
|-------|---------|
| **No.** | 30 |
| **Description** | Modul Fungsi Integrasi: Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi integrasi melalui pembangunan Application Programming Interface (API) yang mempunyai ciri-ciri keselamatan terkini bagi tujuan integrasi dengan sistem lain merangkumi: i. Pembangunan API bagi integrasi dengan Sistem SPRM, Jabatan Insolvensi, Laman Web Darjah Kebesaran, ROS, myIDENTITY dan HRMIS (mengikut keperluan semasa ketika sesi URS dan ketersediaan agensi terlibat) ii. Termasuk juga konfigurasi bagi penggunaan myDigital ID – bagi tujuan log masuk ke sistem. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Modul Integrasi API Lengkap:**

**i. Integrasi Sistem Luar:** API RESTful dengan pengesahan OAuth 2.0 + PKCE untuk integrasi selamat dengan:
- SPRM: API pengesahan integriti untuk tapisan pemohon
- Jabatan Insolvensi: Pengesahan status kebankrapan
- Laman Web Darjah Kebesaran: Penerbitan senarai penerima dan penyegerakan kandungan laman web
- ROS (Pendaftar Pertubuhan): Pengesahan pertubuhan untuk pencalonan berasaskan pertubuhan
- myIDENTITY: Pengesahan dan pengesahan identiti kebangsaan
- HRMIS: Penyegerakan data pekerja untuk pegawai kerajaan

**ii. Log Masuk myDigital ID:** Integrasi OAuth 2.0 penuh menyokong aliran PKCE, membolehkan log masuk tanpa kata laluan yang selamat untuk pengguna kerajaan

**Keselamatan API:** Had kadar API, penandatanganan permintaan, senarai putih IP, dan log audit komprehensif.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Portal Pengurusan API** menyediakan dokumentasi, ujian kotak pasir, dan analitik penggunaan. **Pemantau Kesihatan Integrasi** memaparkan status masa nyata semua sambungan luar. **Mekanisme Failover** mengendalikan gangguan perkhidmatan luar dengan logik baris gilir-dan-cuba semula. **Pengversian API** memastikan keserasian ke belakang semasa naik taraf sistem. **Sokongan Webhook** membolehkan pemberitahuan masa nyata kepada sistem luar.

*Bukti: Lampiran E.39 - Arkitektur API; Lampiran E.40 - Spesifikasi Integrasi; Lampiran E.41 - Keselamatan API*

---

#### Item 31
| Field | Content |
|-------|---------|
| **No.** | 31 |
| **Description** | Fungsi Backup dan Migrasi Data: Petender hendaklah bersedia membangunkan fungsi-fungsi seperti berikut: i. Melakukan backup data ke storan hard disk bagi melindungi data daripada sebarang kegagalan ii. Migrasi keseluruhan sistem dan pangkalan data iii. Migrasi data lama dipindahkan ke pangkalan data baharu berjalan dengan baik (migrasi data permohonan dan penerima dari sistem sedia ada - lotus) iv. Data hendaklah boleh diakses dan sistem berfungsi dengan sempurna setelah selesai proses migrasi |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Fungsi Sandaran & Migrasi Lengkap:**

**i. Sandaran Data:** Sandaran tambahan harian automatik dan sandaran penuh mingguan ke storan disulitkan dengan pengekalan 30 hari

**ii. Migrasi Sistem:** Pelan migrasi lengkap merangkumi aplikasi, pangkalan data, dan migrasi konfigurasi

**iii. Migrasi Data Warisan:** Proses ETL (Ekstrak, Transformasi, Muat) untuk memigrasi permohonan sejarah dan data penerima dari sistem Lotus Notes, termasuk pembersihan dan pengesahan data

**iv. Integriti Data:** Pengesahan pasca-migrasi memastikan ketepatan data 100% dan kefungsian sistem

**Proses Migrasi:** Profil data → Peraturan pembersihan → Ujian migrasi → Pengesahan → Migrasi pengeluaran → Pengesahan → Pelan rollback.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Simulator Migrasi** membolehkan ujian proses migrasi berbilang kali sebelum go-live. **Papan Pemuka Kualiti Data** menunjukkan metrik kelengkapan dan ketepatan sebelum dan selepas migrasi. **Tempoh Berjalan Selari** membolehkan perbandingan antara sistem lama dan baharu untuk pengesahan. **Akses Arkib Sejarah** menyediakan akses baca-sahaja kepada data sistem warisan untuk tujuan audit. **Migrasi Sifar-Tempoh Tidup** meminimumkan ketidaksesuaian sistem semasa cutover.

*Bukti: Lampiran E.42 - Pelan Migrasi; Lampiran E.43 - Arkitektur Sandaran; Lampiran E.44 - Pemetaan Data*

---

#### E. PEMBEKALAN PERKAKASAN

#### Item 32
| Field | Content |
|-------|---------|
| **No.** | 32 |
| **Description** | Petender hendaklah membekal, menyedia, memasang, mengkonfigurasi dan mentauliah: Satu (1) unit 1D/2D Handheld Barcode Scanner QR Wired USB Imager Black Corded Screen Code Reader with Stand (termasuk satu (1) tahun tempoh jaminan). Nota: Sila nyatakan model yang dicadangkan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Pengimbas Barcode yang Dicadangkan:**

**Pilihan Utama:** Honeywell Voyager 1250g - Pengimbas laser berprestasi tinggi dengan keupayaan 1D/2D, sambungan USB, reka bentuk ergonomik, dan disertakan landasan

**Pilihan Alternatif:** Zebra DS2208 - Pengimej kawasan 2D, pengimbasan berbilang arah, pembinaan tahan lasak, waranti 5 tahun tersedia

**Spesifikasi:** Sambungan USB berwayar, serasi dengan Windows/Ubuntu, membaca semua barcode 1D dan 2D standard termasuk kod QR, pemasangan plug-and-play.

**Waranti:** Waranti pengeluar 1 tahun dengan pilihan sokongan di lokasi.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Kami termasuk **Integrasi Penjana Barcode** dalam sistem ePingat untuk mencipta kod QR standard. **Aplikasi Pengimbas Mudah Alih** menjadikan mana-mana telefon pintar sebagai peranti pengimbasan sandaran. **Pemantauan Kesihatan Pengimbas** memberi amaran apabila isu pengimbas dikesan. **Ujian Pukal** mengesahkan kefungsian pengimbas dengan dokumen sampel sebelum pelaksanaan.

*Bukti: Lampiran E.45 - Spesifikasi Perkakasan; Lampiran E.46 - Perbandingan Pengimbas*

---

#### F. PERKHIDMATAN MIGRASI DAN DATA CLEANING

#### Item 33
| Field | Content |
|-------|---------|
| **No.** | 33 |
| **Description** | Petender perlu menyedia perkhidmatan migrasi dan data cleaning melibatkan: i. Migrasi keseluruhan sistem dan pangkalan data daripada sistem terdahulu dan portal laman web rasmi Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor. ii. Petender hendaklah memastikan data dari sistem dan portal terdahulu dapat digunakan semula dalam sistem baharu. iii. Proses migrasi data-data daripada sistem sedia ada akan dilaksana dan diuji secara terperinci dan menyeluruh. iv. Petender hendaklah mencadangkan dan menyediakan pelan migrasi lengkap kepada pihak PSUK Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Perkhidmatan Migrasi & Pembersihan Data Lengkap:**

**i. Migrasi Penuh:** Ekstrak semua data dari sistem Lotus Notes sedia ada dan portal laman web rasmi Darjah Kebesaran

**ii. Kebolehgunaan Semula Data:** Transformasi dan muat data warisan ke sistem baharu memastikan semua rekod sejarah kekal boleh diakses dan berfungsi

**iii. Ujian Menyeluruh:** Berbilang kitar ujian migrasi dengan pengesahan data, pemeriksaan integriti, dan pengesahan penerimaan pengguna

**iv. Pelan Migrasi:** Dokumen strategi migrasi komprehensif termasuk jadual masa, sumber, pengurangan risiko, dan prosedur rollback

**Proses Pembersihan Data:** Pengesanan pendua → Penukaran standard data → Pengendalian data hilang → Peraturan pengesahan → Penilaian kualiti.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Laporan Profil Data** menyediakan analisis kualiti data warisan sebelum migrasi bermula. **Ujian Raptai Migrasi** menjalankan proses migrasi penuh dalam persekitaran peringkat 3 kali sebelum pengeluaran. **Strategi Arkib Data** memelihara data asal dalam format baca-sahaja untuk keperluan audit jangka panjang. **Latihan Pengguna tentang Data Bersih** mendidik kakitangan PSUK mengekalkan kualiti data untuk masa hadapan. **Papan Pemuka Kualiti Data Pasca-Migrasi** memantau integriti data berterusan.

*Bukti: Lampiran E.47 - Metodologi Migrasi; Lampiran E.48 - Prosedur Pembersihan Data; Lampiran E.49 - Pelan Ujian Migrasi*

---

#### G. PENGUJIAN SISTEM DAN PERKAKASAN

#### Item 34
| Field | Content |
|-------|---------|
| **No.** | 34 |
| **Description** | Petender perlu melaksana pengujian keseluruhan fungsi di dalam sistem dan perkakasan bagi memastikan ia mengikut aliran kerja sebenar dan penyediaan dokumentasi pengujian: a. User Acceptance Test (UAT) b. Provisional Acceptance Test (PAT) c. Equipment Acceptance Test (EAT) d. Final Acceptance Test (FAT) e. Pengujian Performance Test (PT) & Web Application Security Assessment (WASA) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Rangka Kerja Ujian Lengkap:**

**a. UAT:** Ujian pengguna akhir dengan senario dunia sebenar, skrip ujian merangkumi semua keperluan, pengesanan dan penyelesaian kecacatan

**b. PAT:** Ujian kestabilan sistem dalam persekitaran seperti pengeluaran, pengesahan integrasi, pengesahan migrasi data

**c. EAT:** Ujian perkakasan termasuk keserasian pengimbas barcode, prestasi, dan kebolehpercayaan

**d. FAT:** Ujian komprehensif akhir sebelum penutupan projek termasuk semua komponen

**e. PT & WASA:** Ujian beban (500+ pengguna serentak), ujian tekanan, dan ujian penembusan keselamatan diiktiraf CREST

**Dokumentasi Ujian:** Pelan ujian, skrip ujian, data ujian, laporan pelaksanaan, dan log kecacatan disediakan untuk semua fasa.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Suite Ujian Automatik** menyediakan ujian regresi untuk semua keluaran masa hadapan. **Bengkel Ujian Pengguna** melatih kakitangan PSUK menjalankan UAT berterusan untuk penambahbaikan masa hadapan. **Laporan Garis Dasar Prestasi** menetapkan metrik prestasi sistem untuk pemantauan berterusan. **Ujian Semula Keselamatan** termasuk satu ujian semula selepas pemulihan tanpa kos tambahan.

*Bukti: Lampiran G - Dokumentasi Ujian; Lampiran G.1 - Skrip Ujian UAT; Lampiran G.2 - Pelan Ujian Prestasi; Lampiran G.3 - Skop WASA*

---

#### Item 35
| Field | Content |
|-------|---------|
| **No.** | 35 |
| **Description** | Petender hendaklah melaksanakan pembetulan dan penambahbaikan terhadap semua ralat yang dikesan semasa pengujian-pengujian di atas TANPA sebarang tambahan kos. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB komited untuk memperbaiki semua kecacatan yang dikenal pasti semasa fasa ujian tanpa kos tambahan. Ini merangkumi:
- Kecacatan kritikal (sistem ranap, kehilangan data): Diperbaiki dalam masa 24 jam
- Keutamaan tinggi (isu ciri utama): Diperbaiki dalam masa 72 jam
- Keutamaan sederhana (isu kecil): Diperbaiki dalam masa 5 hari bekerja
- Keutamaan rendah (kosmetik): Diperbaiki dalam masa 10 hari bekerja

**Pengurusan Kecacatan:** Pengesanan kecacatan berpusat dengan akses PSUK, klasifikasi keseriusan, analisis punca akar, dan langkah pencegahan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Jaminan Sifar-Kecacatan**—jika kecacatan kritikal melebihi 5 semasa UAT, kami memanjangkan tempoh waranti sebanyak 3 bulan tanpa kos. **Analisis Trend Kecacatan** mengenal pasti isu sistemik dan penambahbaikan proses. **Ramalan Kecacatan Pasca-Keluaran** menggunakan AI untuk mengenal pasti kawasan berisiko tinggi sebelum mereka gagal.

*Bukti: Lampiran G.4 - Proses Pengurusan Kecacatan; Lampiran H.5 - Terma Waranti*

---

#### Item 36
| Field | Content |
|-------|---------|
| **No.** | 36 |
| **Description** | Petender hendaklah bersetuju menyediakan dokumentasi pengujian melibatkan pelan pengujian, skrip pengujian, laporan pengujian, dan dokumentasi penerimaan/pentauliahan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Pakej dokumentasi ujian lengkap merangkumi:
- Pelan Ujian Induk merangkumi semua fasa ujian
- Skrip ujian terperinci dengan keputusan jangkaan dan kriteria lulus/gagal
- Laporan pelaksanaan ujian dengan bukti (tangkapan skrin, log)
- Laporan kecacatan dengan pengesahan penyelesaian
- Sijil penerimaan untuk setiap fasa ujian

Semua dokumen mengikut format piawaian IEEE 829 dan disediakan dalam softcopy dan hardcopy.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Papan Pemuka Ujian Interaktif** membolehkan PSUK memantau kemajuan ujian dalam masa nyata. **Analisis Liputan Ujian** memetakan setiap ujian kepada keperluan memastikan liputan lengkap. **Penjanaan Laporan Ujian Automatik** mengurangkan masa dokumentasi dan kesilapan. **Sesi Pemindahan Ilmu** tentang amalan terbaik ujian untuk kakitangan teknikal PSUK.

*Bukti: Lampiran G.5 - Templat Dokumentasi; Lampiran G.6 - Templat Sijil Penerimaan*

---

#### Item 37
| Field | Content |
|-------|---------|
| **No.** | 37 |
| **Description** | Petender hendaklah bersetuju untuk menanggung kos bagi keperluan berkaitan semasa pengujian dilaksanakan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan menanggung semua kos berkaitan aktiviti ujian termasuk:
- Persediaan persekitaran ujian dan infrastruktur
- Penyediaan data ujian dan pengenalan tidak bermaya
- Alat ujian dan lesen
- Perjalanan dan penginapan untuk sokongan ujian di lokasi
- Perkakasan untuk ujian EAT

Tiada caj tambahan akan diinvois untuk perbelanjaan berkaitan ujian.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pencerminan Persekitaran Ujian** memastikan persekitaran ujian sepadan dengan pengeluaran untuk keputusan yang tepat. **Penjana Data Ujian** mencipta data sintetik realistik untuk ujian tanpa kebimbangan privasi. **Makmal Ujian Peranti Mudah Alih** dengan pelbagai jenis peranti untuk ujian keserasian.

*Bukti: Lampiran G.7 - Pecahan Kos Ujian*

---

#### H. PEMASANGAN DAN KONFIGURASI SISTEM

#### Item 38
| Field | Content |
|-------|---------|
| **No.** | 38 |
| **Description** | Petender hendaklah bersetuju bagi melaksanakan pemasangan dan konfigurasi keseluruhan sistem dan pangkalan data serta perlu membuat pengasingan: Development Environment, Production A Environment, Production B Environment (each with Application Server and Database Server) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan mengkonfigurasi tiga persekitaran berasingan:
- **Pembangunan:** Untuk pembangunan berterusan dan ujian unit
- **Pengeluaran A (Peringkat):** Untuk UAT dan pengesahan pra-pengeluaran
- **Pengeluaran B (Langsung):** Persekitaran pengeluaran langsung

Setiap persekitaran termasuk Pelayan Aplikasi dan Pelayan Pangkalan Data khusus dengan peruntukan sumber yang sesuai. Pengasingan persekitaran memastikan ujian tidak memberi kesan kepada pengeluaran.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Alat Penyegerakan Persekitaran** mengklon data pengeluaran ke peringkat dengan pantas (dengan pengenalan tidak bermaya) untuk ujian realistik. Keupayaan **Pelaksanaan Biru-Hijau** membolehkan keluaran tanpa tempoh tidak berfungsi. **Papan Pemuka Kesihatan Persekitaran** memantau semua persekitaran dari pandangan tunggal. **Peruntukan Persekitaran Automatik** menggunakan Infrastructure as Code membolehkan penciptaan persekitaran pantas.

*Bukti: Lampiran E.50 - Arkitektur Persekitaran; Lampiran E.51 - Aliran Kerja Pelaksanaan*

---

#### Item 39
| Field | Content |
|-------|---------|
| **No.** | 39 |
| **Description** | Petender hendaklah melaksanakan pemasangan dan konfigurasi sistem ke atas server cloud yang akan disediakan dan dihostkan di Pusat Data Bahagian Pengurusan Maklumat, Tingkat 2, Bangunan Sultan Salahuddin Abdul Aziz Shah (SSAAS). |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan melaksanakan pemasangan dan konfigurasi lengkap pada pelayan awan yang dihoskan di Pusat Data BPM, SSAAS. Pasukan kami mempunyai pengalaman terdahulu dengan infrastruktur dan keperluan keselamatan BPM.

**Proses Pemasangan:** Senarai semak pra-pemasangan → Persediaan pelayan → Pemasangan perisian → Konfigurasi → Pengerasan keselamatan → Ujian → Pengesahan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Dokumentasi Pemasangan** menyediakan PSUK dengan arahan persediaan lengkap untuk rujukan masa hadapan. **Sandaran Konfigurasi** mengeksport semua tetapan untuk pemulihan bencana. **Dokumentasi Seperti-Dibina** merekod keadaan sistem akhir dengan semua penyesuaian. **Sokongan Integrasi BPM** membantu dengan konfigurasi rangkaian, DNS, dan keselamatan khusus untuk BPM.

*Bukti: Lampiran E.52 - Panduan Pemasangan; Lampiran E.53 - Senarai Semak Integrasi BPM*

---

#### Item 40
| Field | Content |
|-------|---------|
| **No.** | 40 |
| **Description** | Petender perlu menyatakan spesifikasi keperluan sistem dan storage yang diperlukan (termasuk capacity planning). |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Spesifikasi Sistem & Perancangan Kapasiti:**
- Pelayan Aplikasi: 4 vCPU, 16GB RAM, 100GB SSD minimum
- Pelayan Pangkalan Data: 8 vCPU, 32GB RAM, 500GB SSD (boleh kembang)
- Storan: 1TB permulaan dengan unjuran pertumbuhan tahunan 20%
- Storan Sandaran: 2TB untuk pengekalan 30 hari
- Rangkaian: Jalur lebar berdedikasi 100Mbps

**Perancangan Kapasiti:** Berdasarkan 10,000 permohonan tahunan, 500 pengguna serentak, dan pengekalan data 5 tahun. Merangkumi unjuran pertumbuhan dan pemicu penskalaan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Model Ramalan Kapasiti** meramalkan bila sumber tambahan diperlukan berdasarkan trend penggunaan. **Analisis Saiz Tepat** memastikan peruntukan sumber optimum tanpa peruntukan berlebihan. **Pengoptimuman Storan** termasuk strategi mampatan dan arkib untuk meminimumkan kos.

*Bukti: Lampiran E.54 - Perancangan Kapasiti; Lampiran E.55 - Pensizing Sumber*

---

#### Item 41
| Field | Content |
|-------|---------|
| **No.** | 41 |
| **Description** | Petender hendaklah menggunakan perkhidmatan repository yang telah disediakan oleh Bahagian Pengurusan Maklumat, Pejabat Setiausaha Kerajaan Negeri Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan menggunakan perkhidmatan repositori yang disediakan oleh BPM untuk pengurusan kod sumber, mengikut aliran kerja Git PSUK dan strategi percabangan.

**Amalan Repositori:** Percabangan ciri → Semakan kod → Kelulusan gabung → Pembinaan automatik. Semua komit kod dipautkan kepada keperluan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pintu Kualiti Kod** memastikan hanya kod berkualiti tinggi memasuki repositori. **Penjanaan Dokumentasi Automatik** dari komen kod. Latihan **Kebersihan Repositori** untuk kakitangan PSUK tentang amalan terbaik Git. **Pakej Penyerahan Kod Sumber** semasa penyiapan projek dengan eksport repositori lengkap.

*Bukti: Lampiran E.56 - Aliran Kerja Repositori; Lampiran E.57 - Piawaian Git*

---

#### Item 42
| Field | Content |
|-------|---------|
| **No.** | 42 |
| **Description** | Petender hendaklah bersetuju melaksanakan pemasangan, integrasi, migrasi dan pelaksanaan perisian dengan jayanya. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB komited untuk menyiapkan semua fasa pelaksanaan: pemasangan, integrasi dengan sistem luar, migrasi data, dan pelaksanaan perisian. Kriteria kejayaan ditakrifkan untuk setiap fasa dengan pengesahan PSUK diperlukan.

**Metrik Kejayaan:** 100% penyiapan ciri, sifar kecacatan kritikal, 99.9% uptime, migrasi data berjaya dengan sifar kehilangan, penerimaan pengguna.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Bilik Perang Pelaksanaan** untuk fasa pelaksanaan kritikal dengan pasukan berdedikasi. **Sokongan Hypercare** tempoh sokongan intensif (2 minggu selepas go-live) dengan kehadiran di lokasi. **Jaminan Kejayaan**—jika kriteria go-live tidak dipenuhi, kami teruskan tanpa kos sehingga dicapai.

*Bukti: Lampiran F.9 - Pelan Pelaksanaan; Lampiran F.10 - Kriteria Kejayaan*

---

#### Item 43
| Field | Content |
|-------|---------|
| **No.** | 43 |
| **Description** | Pengurusan Backup dan Restore: Petender hendaklah bersetuju bagi melaksana konfigurasi salinan keselamatan (backup) secara daily, weekly, monthly. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Jadual Sandaran:**
- Harian: Sandaran tambahan pada 2:00 pagi, dikekalkan selama 7 hari
- Mingguan: Sandaran penuh setiap Ahad pada 2:00 pagi, dikekalkan selama 4 minggu
- Bulanan: Sandaran penuh pada 1hb setiap bulan, dikekalkan selama 12 bulan

Semua sandaran disulitkan dan disimpan di luar tapak dengan ujian pemulihan berkala.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pemulihan Titik-dalam-Masa** membolehkan pemulihan ke mana-mana saat dalam 30 hari lepas. **Pengesahan Sandaran** menguji integriti sandaran secara automatik setiap hari. **Klon Segera** mencipta persekitaran pembangunan dari sandaran dalam beberapa minit. **Papan Pemuka Analitik Sandaran** menunjukkan status sandaran, penggunaan storan, dan pematuhan.

*Bukti: Lampiran E.58 - Konfigurasi Sandaran; Lampiran E.59 - Prosedur Pemulihan*

---

#### Item 44
| Field | Content |
|-------|---------|
| **No.** | 44 |
| **Description** | SSL Certificate: Petender hendaklah bersetuju untuk membuat pemasangan sistem bersama SSL Certificate bagi memastikan transaksi atas talian dalam keadaan selamat. SSL Certificate akan disediakan oleh Bahagian Pengurusan Maklumat (BPM), PSUK Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan mengkonfigurasi sijil SSL yang disediakan oleh BPM memastikan:
- Akses HTTPS-sahaja
- Penyulitan TLS 1.3
- HSTS (HTTP Strict Transport Security) didayakan
- Pemantauan sijil SSL dan amaran pembaharuan

Pemasangan termasuk konfigurasi semua pelayan web, penyeimbang beban, dan titik akhir API.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pemantauan Kesihatan SSL** memberi amaran sebelum tamat tempoh sijil. **Penarafan SSL A+** dicapai melalui konfigurasi cipher dioptimumkan. **Pemantauan Ketelusan Sijil** mengesan sijil tidak dibenarkan yang dikeluarkan untuk domain.

*Bukti: Lampiran I.8 - Konfigurasi SSL; Lampiran I.9 - Pengepala Keselamatan*

---

#### Item 45
| Field | Content |
|-------|---------|
| **No.** | 45 |
| **Description** | Code Hardening: Petender hendaklah memastikan kod aturcara yang dibangunkan menepati ciri-ciri keselamatan yang perlu ada di dalam sistem. Sila nyatakan pelaksanaan code hardening yang dicadangkan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Pelaksanaan Pengerasan Kod:**
- Pengesahan Input: Pengesahan senarai putih pada semua input, pertanyaan berparameter
- Pengekodan Output: Pengekodan berasaskan konteks untuk mencegah XSS
- Perlindungan CSRF: Perlindungan CSRF berasaskan token pada semua borang
- Pengesahan: Pengurusan sesi selamat, penghashan kata laluan (bcrypt)
- Kebenaran: Prinsip keistimewaan minimum, akses berasaskan peranan
- Pengendalian Ralat: Mesej ralat umum, log terperinci
- Pengepala Keselamatan: CSP, X-Frame-Options, X-Content-Type-Options
- Pengurusan Kebergantungan: Pengimbasan keselamatan berkala ke atas perpustakaan

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Ujian Keselamatan Aplikasi Statik (SAST)** dijalankan pada setiap komit kod. **Analisis Komposisi Perisian (SCA)** mengenal pasti kebergantungan terdedah. **Semakan Kod Keselamatan** oleh profesional keselamatan bertauliah sebelum keluaran. **Latihan Pengaturcaraan Selamat** disediakan kepada pembangun PSUK.

*Bukti: Lampiran I.10 - Piawaian Pengaturcaraan Selamat; Lampiran I.11 - Senarai Semak Semakan Kod*

---

#### Item 46
| Field | Content |
|-------|---------|
| **No.** | 46 |
| **Description** | Fungsi Notifikasi: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menghantar notifikasi pemakluman melalui SMS/Whatsapp dan E-mel. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Sistem Pemberitahuan Pelbagai Saluran:**
- SMS: Integrasi dengan gerbang SMS Malaysia (menyokong semua telco)
- WhatsApp: Integrasi rasmi API WhatsApp Business
- E-mel: Integrasi SMTP dengan pelayan mel PSUK, templat HTML

**Pemicu Pemberitahuan:** Permohonan dihantar, perubahan status, kelulusan diperlukan, tawaran sedia, peringatan majlis.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Keutamaan Pemberitahuan** membolehkan pengguna memilih saluran keutamaan. **Pengesanan Penghantaran** menunjukkan status pemberitahuan (dihantar, disampaikan, dibaca). **Pereka Templat** membolehkan PSUK menyesuaikan mesej tanpa pengaturcaraan. **Analitik Pemberitahuan** mengesan kadar penghantaran dan penglibatan. **Rantaian Sandaran** automatik mencuba saluran alternatif jika utama gagal.

*Bukti: Lampiran E.60 - Arkitektur Pemberitahuan; Lampiran E.61 - Templat Mesej*

---

#### Item 47
| Field | Content |
|-------|---------|
| **No.** | 47 |
| **Description** | Tetapan/ Konfigurasi Sistem (Pentadbir): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Pentadbir Sistem mengikut keperluan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Tetapan konfigurasi pentadbir merangkumi: Pengurusan pengguna, pengurusan peranan, konfigurasi aliran kerja, tetapan pemberitahuan, tetapan integrasi, parameter sistem, akses log audit, dan pengurusan sandaran.

**Antara Muka Konfigurasi:** Antara muka web mesra pengguna dengan pengesahan, teks bantuan, dan pengesanan perubahan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pendeta Konfigurasi** membimbing pentadbir melalui persediaan kompleks. **Templat Konfigurasi** menyediakan titik permulaan untuk konfigurasi umum. **Konfigurasi Pukal** membolehkan import tetapan dari helaian hamparan. **Audit Konfigurasi** mengesan semua perubahan dengan perbandingan sebelum/selepas.

*Bukti: Lampiran E.62 - Panduan Konfigurasi Pentadbir*

---

#### Item 48
| Field | Content |
|-------|---------|
| **No.** | 48 |
| **Description** | Tetapan/ Konfigurasi Sistem (Teknikal): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Teknikal Sistem seperti: a. Tetapan Akses dan Log b. Tetapan notifikasi E-mel / SMS / Whatsapp c. Fungsi Masquerade (Login sebagai) d. Menyediakan tetapan tertakluk kepada keperluan semasa sistem dan pengguna |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Ciri Konfigurasi Teknikal:**

**a. Akses & Log:** Konfigurasi tahap log, tempoh pengekalan, dan penghantaran log

**b. Tetapan Pemberitahuan:** Konfigurasi kelayakan gerbang, had kadar, dan templat lalai

**c. Fungsi Menyamar:** Penyamaran pengguna selamat untuk sokongan dengan jejak audit penuh

**d. Tetapan Lanjutan:** Had kadar API, konfigurasi cache, tetapan baris gilir

Semua tetapan teknikal termasuk pengesahan dan keupayaan rollback.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pengesahan Konfigurasi** mencegah tetapan tidak sah yang boleh merosakkan sistem. **Perbezaan Persekitaran** membandingkan konfigurasi merentasi persekitaran. **Konfigurasi sebagai Kod** membolehkan perubahan konfigurasi dikawal versi.

*Bukti: Lampiran E.63 - Konfigurasi Teknikal; Lampiran E.64 - Tetapan Sistem*

---

#### Item 49
| Field | Content |
|-------|---------|
| **No.** | 49 |
| **Description** | Log/ Audit Trail: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan semua log audit terperinci dari segi akses pengguna, perubahan data dan lain-lain yang berkaitan: a. Log Proses b. Log Aktiviti c. Log Service d. Log E-mel e. Log SMS/Whatsapp |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Log Audit Komprehensif:**

**a. Log Proses:** Pelaksanaan proses perniagaan dengan cap masa dan hasil

**b. Log Aktiviti:** Tindakan pengguna (log masuk, lihat, cipta, kemas kini, padam) dengan nilai sebelum/selepas

**c. Log Perkhidmatan:** Panggilan API, integrasi, kerja latar belakang

**d. Log E-mel:** Semua e-mel dihantar dengan status penghantaran dan pembukaan

**e. Log SMS/WhatsApp:** Semua mesej dengan pengesahan penghantaran

**Ciri Log:** Storan tidak berubah, carian lanjutan, keupayaan eksport, pengurusan pengekalan, dan pengesanan gangguan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Pilihan **Jejak Audit Berasaskan Blockchain** untuk rekod tahan gangguan. **Pengesanan Anomali** mengenal pasti corak aktiviti luar biasa. **Papan Pemuka Audit** menyediakan analitik visual aktiviti sistem. **Laporan Pematuhan** praformat untuk tujuan audit. **Integrasi Log** dengan SIEM untuk pemantauan keselamatan berpusat.

*Bukti: Lampiran I.12 - Arkitektur Jejak Audit; Lampiran I.13 - Dasar Pengekalan Log*

---

#### Item 50
| Field | Content |
|-------|---------|
| **No.** | 50 |
| **Description** | Data History: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan maklumat lama/arkib (history/archive) di peringkat pengguna dan pentadbir sistem. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Sejarah Data & Pengarkiban:**

**Peringkat Pengguna:** Pengguna boleh melihat permohonan sejarah dan perubahan status mereka

**Peringkat Pentadbir:** Akses arkib lengkap dengan carian dan penapisan lanjutan

**Pengarkiban Automatik:** Data lama diarkibkan secara automatik selepas tempoh pengekalan ditakrifkan

**Storan Arkib:** Peringkat storan berasingan untuk data sejarah dengan mampatan

**Ciri Arkib:** Akses baca-sahaja, keupayaan eksport, dan jejak audit akses arkib.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Pandangan Mesin Masa** menunjukkan keadaan sistem pada mana-mana titik sejarah. **Analitik Arkib** menyediakan pandangan dari trend data sejarah. **Pengarkiban Pintar** automatik menentukan masa pengarkiban optimum berdasarkan corak penggunaan data. **Carian Arkib** carian teks penuh merentasi semua rekod diarkib.

*Bukti: Lampiran E.65 - Strategi Pengarkiban Data; Lampiran E.66 - Akses Data Sejarah*

---

#### I. DOKUMENTASI

#### Item 51
| Field | Content |
|-------|---------|
| **No.** | 51 |
| **Description** | Petender hendaklah menyedia dokumentasi berkaitan: a. Manual Pengguna b. Manual Pentadbir c. Manual Teknikal/Operasi |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Set Dokumentasi Lengkap (Bahasa Malaysia):**

**a. Manual Pengguna:** Panduan langkah-demi-langkah untuk pemohon dan Urus Setia dengan tangkapan skrin dan FAQ

**b. Manual Pentadbir:** Konfigurasi sistem, pengurusan pengguna, penyelesaian masalah

**c. Manual Teknikal/Operasi:** Pemasangan, penyelenggaraan, sandaran/pemulihan, rujukan API

Semua manual diformat secara profesional dengan kandungan, indeks, dan PDF boleh cari.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Manual Video** menyediakan rakaman skrin prosedur utama. **Bantuan Interaktif** terbenam dalam aplikasi dengan panduan kontekstual. **Portal Dokumentasi** pangkalan pengetahuan dalam talian boleh cari. **Kemas Kini Suku Tahunan** mengekalkan dokumentasi terkini dengan perubahan sistem. **Integrasi Maklum Balas** membolehkan pengguna mencadangkan penambahbaikan dokumentasi.

*Bukti: Lampiran F.11 - Pelan Dokumentasi; Lampiran F.12 - Templat Manual*

---

#### Item 52
| Field | Content |
|-------|---------|
| **No.** | 52 |
| **Description** | Petender hendaklah menyediakan minit mesyuarat Pasukan Kerja dan Jawatankuasa Teknikal Projek dengan pemantauan urus setia projek. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB akan mendokumenkan semua mesyuarat Pasukan Kerja dan Jawatankuasa Teknikal termasuk: Agenda, kehadiran, titik perbincangan, keputusan yang dibuat, item tindakan dengan pemilik dan tarikh akhir, dan kemas kini status.

**Kekerapan Mesyuarat:** Mesyuarat Pasukan Kerja mingguan, mesyuarat Jawatankuasa Teknikal bulanan, dan mesyuarat ad-hoc mengikut keperluan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Portal Mesyuarat** menyediakan akses dalam talian kepada semua bahan mesyuarat. **Pengesan Item Tindakan** menghantar peringatan automatik untuk tindakan tertangguh. **Log Keputusan** mengekalkan rekod boleh cari semua keputusan projek. **Analitik Mesyuarat** mengesan keberkesanan mesyuarat dan kadar susulan.

*Bukti: Lampiran F.13 - Pelan Pengurusan Mesyuarat*

---

#### Item 53
| Field | Content |
|-------|---------|
| **No.** | 53 |
| **Description** | Petender hendaklah menyediakan satu salinan manual penggunaan secara hardcopy dan softcopy kepada pengguna dan pentadbir sistem. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Kedua-dua manual hardcopy (dicetak dan dijilid) dan softcopy (PDF, boleh cari) akan disediakan kepada semua pengguna dan pentadbir. Senarai edaran dikekalkan dengan pengesahan tandatangan.

**Kuantiti:** 50 manual pengguna hardcopy, 10 manual pentadbir hardcopy, edaran softcopy tanpa had.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Kad Permulaan Pantas** panduan satu muka surat dilaminate untuk tugas biasa. **Kod QR dalam Manual** dipautkan kepada demonstrasi video. **Format E-Book** untuk bacaan mesra mudah alih. **Versi Kebolehcapaian** format serasi pembaca skrin.

*Bukti: Lampiran F.14 - Pelan Edaran*

---

#### J. LATIHAN DAN PEMINDAHAN TEKNOLOGI

#### Item 54
| Field | Content |
|-------|---------|
| **No.** | 54 |
| **Description** | Petender perlu melaksana latihan dan pemindahan teknologi melibatkan: a. Latihan Pengguna b. Latihan Pentadbir Sistem c. Transfer of Technology (TOT) |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Program Latihan Lengkap:**

**a. Latihan Pengguna:** Sesi hands-on untuk pemohon dan Urus Setia tentang penggunaan sistem

**b. Latihan Pentadbir:** Latihan mendalam tentang konfigurasi sistem, pengurusan pengguna, dan penyelesaian masalah

**c. Pemindahan Teknologi:** Pemindahan pengetahuan kepada kakitangan teknikal PSUK tentang penyelenggaraan sistem

**Kaedah Latihan:** Sesi bilik darjah, makmal hands-on, tutorial video, dan bahan rujukan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** Program **Latih-Jurulatih** mensijilkan kakitangan PSUK untuk melatih pengguna masa hadapan. **Portal Latihan** menyediakan akses berterusan kepada bahan dan modul e-pembelajaran. **Penilaian Kecekapan** mengesahkan pembelajaran dengan sijil. **Latihan Penyegar** sesi termasuk semasa tempoh waranti. **Rakaman Video** semua latihan untuk rujukan masa hadapan.

*Bukti: Lampiran F.15 - Pelan Latihan; Lampiran F.16 - Bahan Latihan*

---

#### Item 55
| Field | Content |
|-------|---------|
| **No.** | 55 |
| **Description** | Petender bersetuju melaksanakan sesi TOT kepada pegawai-pegawai yang terlibat dan pentadbir sistem untuk memahirkan diri dalam pembangunan/penyelenggaraan sistem bagi menguruskan isu-isu teknikal sistem dan konfigurasi sistem/server yang berkaitan (sila nyatakan cadangan lokasi dan kemudahan latihan yang akan dilaksana). |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Program Pemindahan Teknologi (TOT):**

**Lokasi:** Bilik latihan PSUK Selangor atau kemudahan latihan SESB (berdasarkan pilihan PSUK)

**Tempoh:** Program intensif 5 hari

**Topik:** Arkitektur sistem, pengurusan pangkalan data, penyelesaian masalah, sandaran/pemulihan, pengurusan keselamatan, penalaan prestasi

Latihan merangkumi latihan hands-on dengan komponen sistem sebenar.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Persekitaran Makmal TOT** persekitaran latihan khusus untuk latihan hands-on tanpa risiko. **Bimbingan TOT** sokongan 3 bulan pasca-latihan dengan mentor yang ditugaskan. **Buku Panduan Teknikal** panduan operasi komprehensif. **Peperiksaan Pensijilan** mengesahkan kecekapan. **Peningkatan Kecemasan** talian langsung ke jurutera kanan SESB semasa tempoh peralihan.

*Bukti: Lampiran F.17 - Kurikulum TOT; Lampiran F.18 - Kemudahan Latihan*

---

#### Item 56
| Field | Content |
|-------|---------|
| **No.** | 56 |
| **Description** | Petender hendaklah menyenarai kesemua fail dan modul yang terdapat di dalam sistem dan server untuk tujuan TOT tersebut. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Inventori lengkap semua fail sistem, modul, dan komponen pelayan akan disediakan termasuk: Nama dan lokasi fail/modul, perihalan tujuan, kebergantungan, parameter konfigurasi, dan prosedur penyelenggaraan.

**Format Inventori:** Helaian hamparan dan dokumentasi teknikal dengan gambarajah.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Peta Sistem Interaktif** peneroka visual menunjukkan semua komponen dan hubungan. **Graf Kebergantungan** menggambarkan bagaimana modul berinteraksi. **Sejarah Perubahan** mengesan pengubahsuaian kepada setiap komponen. **Penunjuk Kesihatan** menunjukkan status setiap modul.

*Bukti: Lampiran F.19 - Inventori Sistem*

---

#### Item 57
| Field | Content |
|-------|---------|
| **No.** | 57 |
| **Description** | Petender hendaklah menyediakan dokumentasi lengkap bagi setiap latihan dan sesi TOT. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Dokumentasi latihan lengkap merangkumi: Agenda dan jadual latihan, rekod kehadiran, bahan latihan (slaid, risalah, latihan), rakaman video, keputusan penilaian, dan borang maklum balas.

**Piawaian Dokumentasi:** Format profesional, kawalan versi, dan kandungan boleh cari.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Analitik Latihan** mengesan kadar penyiapan dan skor kecekapan. **Analisis Maklum Balas** mengenal pasti peluang penambahbaikan latihan. **Rekod Pensijilan** mengekalkan pangkalan data kakitangan yang dilatih. **Laporan ROI Latihan** mengukur keberkesanan.

*Bukti: Lampiran F.20 - Piawaian Dokumentasi Latihan*

---

#### Item 58
| Field | Content |
|-------|---------|
| **No.** | 58 |
| **Description** | Petender hendaklah mencadangkan senarai latihan dan TOT. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

Jadual latihan yang dicadangkan disediakan dalam Lampiran F termasuk: Senarai kursus latihan, sasaran audiens, tempoh, prasyarat, objektif pembelajaran, dan kaedah penghantaran.

**Kategori Latihan:** Latihan pengguna akhir, latihan pentadbir, latihan teknikal, dan TOT.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Penilaian Keperluan Latihan** dijalankan sebelum latihan untuk menyesuaikan kandungan. **Laluan Pembelajaran Berasaskan Peranan** disesuaikan untuk jenis pengguna yang berbeza. **Modul Mikropembelajaran** video 5-10 minit untuk tugas khusus. **Elemen Gamifikasi** untuk meningkatkan penglibatan. **Forum Komuniti** untuk pembelajaran rakan-ke-rakan.

*Bukti: Lampiran F.15 - Pelan Latihan; Lampiran F.21 - Kalendar Latihan*

---

#### Item 59
| Field | Content |
|-------|---------|
| **No.** | 59 |
| **Description** | Laporan Kemajuan Projek: Petender hendaklah menyediakan Laporan Kemajuan Projek sekurang-kurangnya tiga (3) kali sepanjang tempoh projek, tertakluk kepada keperluan semasa. Petender hendaklah menyediakan Laporan Akhir Pelaksanaan Projek setelah pelaksanaan projek selesai sepenuhnya. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

**Jadual Pelaporan Projek:**

**Laporan Kemajuan:** Minimum 3 laporan (Bulan 2, Bulan 4, Bulan 6)

**Laporan Akhir:** Laporan penyiapan projek komprehensif termasuk pengajaran yang dipelajari, dokumentasi seperti-dibina, dan bahan penyerahan

**Kandungan Laporan:** Ringkasan eksekutif, kemajuan berbanding pelan, status hasil kerja, isu dan risiko, ringkasan kewangan, dan langkah seterusnya.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Papan Pemuka Projek Masa Nyata** tersedia 24/7 menunjukkan status semasa. **Analitik Ramalan** meramalkan tarikh penyiapan berdasarkan kemajuan sebenar. **Penjanaan Laporan Automatik** mengurangkan masa penyediaan. **Pandangan Khusus Pemegang Kepentingan** laporan yang disesuaikan untuk audiens yang berbeza. **Penanda Aras** membandingkan prestasi projek dengan piawaian industri.

*Bukti: Lampiran F.22 - Jadual Pelaporan; Lampiran F.23 - Templat Laporan*

---

#### K. KOD SUMBER DAN PANGKALAN DATA

#### Item 60
| Field | Content |
|-------|---------|
| **No.** | 60 |
| **Description** | i. Semua kod sumber (source code) adalah hak milik sepenuhnya Kerajaan Negeri Selangor dan wajib diserahkan dalam bentuk softcopy kepada Kerajaan Negeri apabila projek telah siap. ii. Sebarang penyalinan, pemindahan dan pengedaran dengan apa juga cara untuk tujuan komersil adalah tidak dibenarkan sama sekali kecuali mendapat kebenaran daripada Kerajaan Negeri Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB menerima sepenuhnya terma harta intelek:

**i. Pemilikan Kod Sumber:** Kod sumber lengkap diserahkan kepada Kerajaan Negeri Selangor sebaik sahaja projek siap termasuk semua skrip, konfigurasi, dan dokumentasi

**ii. Sekatan Penggunaan:** SESB komited untuk tiada penggunaan komersial, pengedaran, atau penggunaan semula sistem ePingat tertentu tanpa kebenaran bertulis

**Format Penghantaran:** Repositori teratur dengan dokumentasi, arahan pembinaan, dan manifest kebergantungan.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Dokumentasi Kod** komen inline komprehensif dan dokumentasi luaran. **Panduan Onboarding Pembangun** membantu pembangun masa hadapan memahami kod. **Rekod Keputusan Arkitektur** menerangkan pilihan teknikal utama. **Sesi Pemindahan Ilmu** ulasan bahagian kod kritikal.

*Bukti: Lampiran F.24 - Penyerahan Kod Sumber; Lampiran F.25 - Perjanjian Pemberian IP*

---

#### L. PEMBAYARAN

#### Item 61
| Field | Content |
|-------|---------|
| **No.** | 61 |
| **Description** | Petender tidak boleh menuntut apa-apa bentuk bayaran tambahan daripada Kerajaan Negeri selain daripada bayaran yang dinyatakan dalam dokumen kontrak. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Ulasan & Bukti:**

SESB mengesahkan tiada caj tambahan melebihi jumlah kontrak. Semua kos termasuk ujian, latihan, dokumentasi, perjalanan, dan sokongan waranti termasuk dalam harga yang dikutip.

**Komitmen Harga Tetap:** Perubahan skop akan dikendalikan melalui proses kawalan perubahan formal dengan kelulusan bertulis terlebih dahulu.

**🚀 PENAMBAHBAIKAN NILAI TAMBAH:** **Jaminan Kunci Harga**—tiada kenaikan harga untuk 12 bulan pasca-kontrak walaupun projek dilanjutkan. **Jaminan Nilai** semakan berkala memastikan PSUK menerima nilai kontrak penuh.

*Bukti: Terma Kontrak*

---

#### Item 62
| Field | Content |
|-------|---------|
| **No.** | 62 |
| **Description** | Perjanjian: Petender yang berjaya dikehendaki menandatangani satu kontrak dengan Kerajaan Negeri dalam tempoh empat (4) bulan dari tarikh mula projek. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB agrees to execute contract within 4 months from project start date. Our legal team is prepared to review and sign the agreement promptly.

**Contract Readiness:** Standard company documents (SSM, financials, insurance) are current and available.

**🚀 VALUE-ADD ENHANCEMENT:** **Contract Compliance Tracking** ensures all contractual obligations are met. **Relationship Management** dedicated account manager for ongoing PSUK relationship.

*Evidence: Contract Documentation*

---

#### M. PERKHIDMATAN KHIDMAT SOKONGAN DALAM TEMPOH WARANT

#### Item 63
| Field | Content |
|-------|---------|
| **No.** | 63 |
| **Description** | Petender hendaklah bersetuju: a. Memberi jaminan perkhidmatan sokongan terhadap Sistem ePingat yang dibangunkan dalam tempoh satu (1) tahun bermula selepas tarikh FAT (Go Live) ditandatangani tanpa sebarang kos. b. Sekiranya terdapat keadaan di mana salah satu ataupun keseluruhan komponen sistem gagal berfungsi sepertimana yang sepatutnya, syarikat akan bertanggungjawab sepenuhnya kepada kerja-kerja recovery. c. Petender perlu menyediakan Service Level Agreement (SLA) bagi kadar penyelesaian isu yang diadukan. d. Kerajaan Negeri berhak untuk menyampaikan aduan kepada Petender pada bila-bila masa dan tiada had ke atas bilangan aduan. e. Petender hendaklah menyediakan sistem helpdesk/call center/pusat khidmat pengguna. Masa tindakan: i. Helpdesk (Phone, Email and Helpdesk System) - 24 jam x 7 hari seminggu ii. Technical Support - 8 jam x 5 hari seminggu iii. Masa Tindakan - (Response Time – Min 4 jam) - (Selesai Masalah – Max 3 Hari Waktu bekerja) f. Petender perlu menyedia khidmat bantuan dan nasihat penggunaan sistem yang betul. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

**Comprehensive 1-Year Warranty Support:**

**a. Warranty Coverage:** Full support from FAT signing, all costs included

**b. Recovery Responsibility:** Complete responsibility for system recovery with defined RTO/RPO targets

**c. SLA Commitment:** Response times (Critical: 4 hours, High: 8 hours, Medium: 24 hours, Low: 48 hours); Resolution times (Critical: 24 hours, High: 72 hours, Medium: 5 days, Low: 10 days)

**d. Unlimited Support:** No limit on number of support requests

**e. Helpdesk Operations:**
- i. 24/7 Helpdesk via phone, email, and ticketing system
- ii. 8x5 Technical Support for complex issues
- iii. 4-hour response, 3-day maximum resolution commitment

**f. User Guidance:** Ongoing training and best practice advice

**🚀 VALUE-ADD ENHANCEMENT:** **Proactive Monitoring** identifies issues before PSUK reports them. **Monthly Health Checks** review system performance and recommend optimizations. **User Satisfaction Surveys** continuously improve support quality. **Escalation Management** ensures timely resolution of stuck issues. **Knowledge Base** self-service articles reduce ticket volume. **WhatsApp Support** instant messaging for quick queries.

*Evidence: Annex H - Service Level Agreement; Annex H.6 - Warranty Terms; Annex H.7 - Support Procedures*

---

#### Item 64
| Field | Content |
|-------|---------|
| **No.** | 64 |
| **Description** | Tempoh Jaminan/ Waranti: Petender perlu memberi jaminan dalam tempoh SATU (1) TAHUN bermula selepas FAT (Final Acceptance Test) ditandatangani melibatkan: a. Perkhidmatan sokongan secara on site dan secara atas talian. b. Pembetulan ralat keseluruhan sistem dan perkakasan. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

**1-Year Warranty from FAT Signing:**

**a. Support Coverage:** Both on-site (when required) and remote support available throughout warranty period

**b. Bug Fixes:** All system defects and hardware issues corrected at no additional cost

**Warranty Extensions:** Available at competitive rates beyond the initial year.

**🚀 VALUE-ADD ENHANCEMENT:** **Extended Warranty Options** 2nd and 3rd year at discounted rates. **Hardware Replacement** spares kept on-site for critical components. **Performance Guarantee** uptime commitment with service credits for breaches.

*Evidence: Annex H.8 - Warranty Coverage*

---

#### Item 65
| Field | Content |
|-------|---------|
| **No.** | 65 |
| **Description** | Petender bersetuju menyediakan dan menyempurnakan dokumen penyerahan projek selepas pelaksanaan projek selesai sepenuhnya. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

Complete project handover documentation including: As-built documentation, source code, database schemas, configuration files, administrator credentials, warranty certificate, training completion certificates, and final project report.

**Handover Process:** Formal handover meeting, document review, system demonstration, and sign-off.

**🚀 VALUE-ADD ENHANCEMENT:** **Handover Checklist** ensures nothing is missed. **30-Day Support Buffer** intensive support period immediately after handover. **Exit Interview** captures lessons learned and improvement suggestions. **Future Roadmap** recommendations for system enhancements.

*Evidence: Annex F.26 - Handover Checklist; Annex F.27 - Project Closure Procedure*

---

#### Item 66
| Field | Content |
|-------|---------|
| **No.** | 66 |
| **Description** | Petender bersetuju melaksanakan kerja-kerja yang tidak dinyatakan secara khusus di dalam keperluan projek tetapi perlu dilaksanakan bagi melancarkan dan menjayakan pelaksanaan projek ini. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

SESB agrees to perform any additional work necessary for successful project completion, including: Additional integrations discovered during URS, process adjustments based on stakeholder feedback, additional training sessions if needed, supplementary documentation, and out-of-scope items reasonably required for project success.

**Change Control:** Items identified will be documented and agreed upon before implementation.

**🚀 VALUE-ADD ENHANCEMENT:** **Project Success Guarantee**—we do whatever it takes to ensure PSUK's objectives are met. **Continuous Improvement** proactively suggest enhancements during implementation. **Flexibility Commitment** up to 10% effort variance accommodated without change request for minor scope adjustments.

*Evidence: Project Management Plan*

---

#### N. KESELAMATAN DATA

#### Item 67
| Field | Content |
|-------|---------|
| **No.** | 67 |
| **Description** | Keselamatan Data: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. |
| **M/O** | M |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

**Data Security Commitments:**

**a. Data Responsibility:** SESB accepts full accountability for data security throughout the project lifecycle. All data handled according to government security classifications.

**b. Confidentiality Agreements:** All SESB personnel sign Statutory Declarations (Akuan Sumpah) and NDAs before accessing any PSUK data or premises.

**c. Policy Compliance:** Full compliance with PSUK ICT Security Policy, including access controls, encryption, audit logging, and incident reporting.

**Security Measures:** Encrypted devices, secure development environment, data minimization, secure disposal of test data, and regular security training.

**🚀 VALUE-ADD ENHANCEMENT:** **Security Certification** all team members complete PSUK security clearance. **Data Handling Protocol** documented procedures for every data interaction. **Breach Response Plan** immediate notification and containment procedures. **Quarterly Security Reviews** ongoing assessment of security controls. **Insurance Coverage** cyber liability insurance for additional protection.

*Evidence: Annex I.14 - Data Security Policy; Annex I.15 - Confidentiality Agreements; Annex I.16 - Security Training Records*

---

#### O. LAIN-LAIN

#### Item 68
| Field | Content |
|-------|---------|
| **No.** | 68 |
| **Description** | Lain-Lain Cadangan (Jika Ada): Sila nyatakan lain-lain cadangan/perkhidmatan yang berkaitan, sekiranya ada. |
| **M/O** | O |
| **Compliance** | FULLY COMPLY |

**Remarks & Evidence:**

**Value-Added Services (VAS) Framework:**

**Part 1: Software & Innovation (5 Items)**

1. AI-Powered Application Pre-Screening - Market Value: RM 150,000
2. Advanced Analytics & Predictive Reporting - Market Value: RM 120,000
3. WhatsApp Business API Integration - Market Value: RM 80,000
4. Document Intelligence (OCR/AI) - Market Value: RM 100,000
5. API Developer Portal - Market Value: RM 50,000

**Part 1 Subtotal: RM 500,000**

**Part 2: Support & Consultative (5 Items)**

1. Extended Warranty (Year 2) - Market Value: RM 150,000
2. Quarterly System Health Reviews - Market Value: RM 60,000
3. Change Management Support - Market Value: RM 80,000
4. User Experience Optimization - Market Value: RM 70,000
5. Knowledge Transfer Deep-Dive - Market Value: RM 40,000

**Part 2 Subtotal: RM 400,000**

**TOTAL VAS VALUE: RM 900,000** included at no additional cost.

**Additional Innovation:**
- Mobile App for Recipients - allows award recipients to manage their profile and ceremony attendance
- Social Media Integration - for official announcements
- Multi-Year Data Analysis - identifies trends in award applications
- Digital Signature Integration - for fully paperless workflows

*Evidence: Section 7 - Value Added Services*

---

## SUMMARY OF COMPLIANCE

### Overall Compliance Matrix

| Category | Total Items | Mandatory | Compliant | Compliance Rate |
|----------|-------------|-----------|-----------|-----------------|
| Skop Kerja Umum | 3 | 3 | 3 | 100% |
| Kajian Spesifikasi | 2 | 2 | 2 | 100% |
| Rekabentuk Sistem | 2 | 2 | 2 | 100% |
| Pembangunan Sistem | 14 | 13 | 14 | 100% |
| Modul Sistem | 9 | 9 | 9 | 100% |
| Perkakasan | 1 | 1 | 1 | 100% |
| Migrasi Data | 1 | 1 | 1 | 100% |
| Pengujian | 4 | 4 | 4 | 100% |
| Pemasangan | 13 | 13 | 13 | 100% |
| Dokumentasi | 3 | 3 | 3 | 100% |
| Latihan/TOT | 6 | 6 | 6 | 100% |
| Kod Sumber | 1 | 1 | 1 | 100% |
| Pembayaran | 2 | 2 | 2 | 100% |
| Waranti | 4 | 4 | 4 | 100% |
| Keselamatan | 2 | 2 | 2 | 100% |
| Lain-lain | 1 | 0 | 1 | 100% |
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

> "We deliver proven government digital solutions, not promises. Our ePingat Pro Suite combines technical excellence with deep understanding of Malaysian government processes—ensuring PSUK Selangor receives a system that exceeds expectations and serves the people of Selangor for years to come."

---

## DOCUMENT CONTROL

| Field | Value |
|-------|-------|
| Document Version | 2.0 (Revised) |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
