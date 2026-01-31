# TECHNICAL COMPLIANCE RESPONSE

**Tender Reference:** T/SUKSEL/04-2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026  
**Project:** TENDER PERKHIDMATAN PEMBANGUNAN SISTEM ePINGAT NEGERI SELANGOR

---

## JADUAL 1: JADUAL SPESIFIKASI - COMPLIANCE RESPONSE

### SKOP KERJA UMUM

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **1** | Kerajaan Negeri Selangor akan melaksanakan Pembangunan Sistem ePingat Negeri Selangor yang merangkumi: i. Modul Laman Utama; ii. Modul Dashboard; iii. Modul Permohonan; iv. Modul Pengurusan Permohonan - Peranan Urus Setia dan Pentadbir; v. Modul Pengurusan Proses Penilaian dan Tapisan; vi. Modul Pengurusan Majlis Pengurniaan; vii. Modul Laporan; viii. Modul Pentadbir Sistem; ix. Fungsi Integrasi; dan x. Fungsi Backup dan Migrasi Data. | **M** | **Y** | SESB confirms all 10 modules will be developed as specified. See Annex E for detailed module architecture. |
| **2** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu dilengkapi keselamatan data dan sistem yang tinggi. | **M** | **Y** | High security will be implemented including encryption, access control, audit trails, and OWASP compliance. See Item 12 for details. |
| **3** | Pembangunan Sistem ePingat Negeri Selangor yang dibangunkan perlu lebih mesra pengguna, mempunyai reka bentuk web-responsive, menepati kehendak teknologi semasa serta meningkatkan pengalaman pengguna dalam persekitaran digital dan mematuhi Garis Panduan Pencalonan Pengurniaan Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor Darul Ehsan. | **M** | **Y** | Responsive web design using React.js with mobile-first approach. UI/UX will follow government digital guidelines and ePingat specific requirements. |

---

### SKOP KERJA KHUSUS

#### A. KAJIAN SPESIFIKASI KEPERLUAN PENGGUNA

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **4** | Petender hendaklah melaksanakan Kajian Spesifikasi Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS) ke atas sistem sedia ada termasuk keperluan baharu bersama pengguna dan pentadbir sistem mengikut spesifikasi yang dinyatakan di dalam dokumen ini. | **M** | **Y** | URS and SRS will be conducted in Month 1-2 with stakeholder interviews, system analysis, and documentation. |
| **5** | Petender hendaklah menyediakan dokumentasi Kajian Keperluan Pengguna (URS) dan Spesifikasi Keperluan Sistem (SRS). | **M** | **Y** | Complete URS and SRS documents will be delivered as Phase 1 deliverables. |

---

#### B. REKABENTUK SISTEM

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **6** | Petender bersetuju menjalankan analisis keperluan bisnes dan analisis keperluan merangkumi proses kerja/software architecture yang lengkap berkaitan sistem yang akan dibangunkan. | **M** | **Y** | Business process analysis and software architecture design will be conducted in Month 3-4. |
| **7** | Petender hendaklah menyediakan gambarajah lengkap aliran sistem dan keseluruhan struktur pangkalan data (table, field dan relation) melibatkan: a. Data Dictionary b. Entity Relationship Diagram (ERD) c. Data Flow Diagram (DFD) | **M** | **Y** | Complete system diagrams including Data Dictionary, ERD, and DFD will be provided in the Design Document. |

---

#### C. PEMBANGUNAN SISTEM BAHARU

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **8** | Pembangunan Sistem Menggunakan Versi Terkini Bagi (sila cadangkan): i. Sistem Pengoperasian: Minimum Ubuntu (LTS)/ Windows Server 2022 Std Edition versi terkini atau setara dengannya. ii. Keseluruhan Kod Pengaturcaraan: PHP versi terkini atau setara dengannya. iii. Framework: Sila nyatakan cadangan (Laravel atau setara dengannya) iv. Database: MySQL versi terkini atau setara dengannya. | **M** | **Y** | **Proposed Stack:** OS: Ubuntu 22.04 LTS, Language: PHP 8.2, Framework: Laravel 10.x, Database: MySQL 8.0 |
| **9** | Web Based – Responsive: Petender hendaklah membangunkan sistem web-based yang mempunyai reka bentuk responsif yang boleh dicapai melalui semua pelayar (internet browser) yang utama secara web dan capaian di telefon/peranti mudah alih bagi setiap jenis saiz skrin dan web pelayar. | **M** | **Y** | Responsive design using React.js with Bootstrap/Tailwind CSS. Supports Chrome, Firefox, Safari, Edge, and mobile browsers. |
| **10** | Multiple Access: Petender hendaklah menyediakan sistem yang mampu menampung multiple access pengguna dalam satu-satu masa. | **M** | **Y** | System supports 500+ concurrent users with horizontal scaling capability. |
| **11** | Multi-tenant: Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi multi-tenant bagi keperluan peluasan kepada pengguna lain di Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **Y** | Multi-tenant architecture implemented with tenant isolation at database and application level. |
| **12** | Kawalan Keselamatan Aplikasi (Application Security): Petender hendaklah menyedia beberapa aspek utama keselamatan aplikasi: a. Pengesahan pengguna b. Kawalan akses c. Enkripsi Data d. Keselamatan Pangkalan Data e. Pentadbiran Keselamatan | **M** | **Y** | **Security Features:** a. Multi-factor authentication b. Role-based access control (RBAC) c. AES-256 encryption d. Database encryption & access control e. Security monitoring & audit trails |
| **13** | Petender hendaklah menyedia sistem yang mempunyai ciri-ciri minimum sistem aplikasi dan merujuk kepada kesesuaian setiap modul merangkumi: a. Mempunyai Antara Muka Pengguna (UI) yang intuitif dan mudah difahami b. Mempunyai pengurusan user session dengan efisien c. Mempunyai operasi CRUD d. Mempunyai kemudahan pencarian dan penyaringan e. Mempunyai kemudahan sokongan kepada pelbagai platform peranti f. Mempunyai dokumentasi yang lengkap g. Mempunyai kemampuan untuk menghasilkan laporan dan cetakan | **M** | **Y** | All minimum features will be implemented: Intuitive UI, session management, CRUD operations, search/filter, multi-platform support, complete documentation, reporting & printing. |
| **14** | Petender hendaklah menyedia dan mengemukakan cadangan pembangunan sistem menyeluruh bagi Perkhidmatan Pembangunan Sistem ePingat Negeri Selangor. (Sila sertakan kertas cadangan sebagai Jadual 1A) | **M** | **Y** | Complete proposal attached as Jadual 1A including architecture, security, modules, and technical specifications. |
| **15** | Petender hendaklah membangunkan satu (1) sistem prototaip yang memenuhi keperluan-keperluan spesifikasi sistem seperti yang telah dinyatakan di atas dan dibentangkan kepada panel penilai sekiranya disenarai pendek di dalam Jawatankuasa Penilaian Teknikal Tender. | **M** | **Y** | Working prototype will be developed and presented if shortlisted for technical evaluation. |
| **16** | Petender hendaklah mempunyai pengalaman sekurang-kurangnya satu (1) projek berkaitan Perkhidmatan Pembangunan Sistem Pengurusan Permohonan Pingat atau yang setara dengannya dan berkaitan dengan modul-modul seperti yang dinyatakan dalam dokumen tender ini (jika ada, sila senaraikan dan nyatakan nama sistem serta agensi yang berkaitan), dalam tempoh lima (5) tahun terkini. (Sila sertakan Jadual 2 dan Jadual 2A) | **O** | **Y** | Refer to Annex A for project portfolio and Jadual 2/2A for detailed experience documentation. |
| **17** | Petender mempunyai pengalaman membangunkan sistem berkaitan Pengurusan Permohonan dan Majlis (jika ya, sila senaraikan dan nyatakan nama sistem beserta agensi yang berkaitan). | **O** | **Y** | Refer to project portfolio in Annex A. |
| **18** | Struktur Organisasi Projek - Petender perlu mencadangkan pasukan projek bagi mengenalpasti, melantik dan mengesahkan keahlian pasukan yang dicadangkan supaya dapat bekerja dengan pasukan pelaksanaan projek Pejabat Setiausaha Kerajaan Negeri Selangor (sila nyatakan dalam Jadual 3: Carta Organisasi Projek) | **M** | **Y** | Project team structure provided in Annex D with organization chart and key personnel profiles. |
| **19** | Petender hendaklah menyenaraikan pegawai teknikal bertauliah yang terlibat dalam perkhidmatan ini dan hendaklah menyertakan dokumen Curriculum Vitae (CV) dan sijil pentauliahan (Professional Certificate) atau pengalaman berkaitan untuk melaksanakan projek ini (sila nyatakan dalam Jadual 4: Jadual Maklumat Kakitangan Teknikal Syarikat) | **M** | **Y** | Technical team with CVs and certifications listed in Annex D, Jadual 4. |
| **20** | Petender hendaklah menyediakan Jadual Pelaksanaan Projek (Gantt Chart) menggunakan perisian Microsoft Project atau perisian setara. (sila nyatakan dalam Jadual 5) | **M** | **Y** | Gantt Chart implementation plan provided in Annex F, Jadual 5. |
| **21** | Petender hendaklah menyediakan kaedah bantuan sokongan teknikal daripada syarikat Petender dan Prinsipal (contoh: maklumat penyediaan perkhidmatan helpdesk, telephone, online support dan tempoh maklumbalas (response time) bagi khidmat sokongan sepanjang tempoh waranti) | **M** | **Y** | Technical support methodology detailed in Annex H (SLA) including helpdesk, response times, and warranty support. |
| **22** | Petender bersetuju untuk hadir bertugas di Pejabat Setiausaha Kerajaan Negeri Selangor secara on-site bagi semua mesyuarat yang berkaitan dan semasa Majlis Penganugerahan Darjah Bintang Kebesaran Negeri Selangor tertakluk kepada perkara-perkara seperti berikut: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **Y** | SESB agrees to on-site attendance for all meetings and ceremonies. All staff will sign confidentiality agreements and comply with PSUK ICT Security Policy. |

---

#### D. MODUL-MODUL PEMBANGUNAN SISTEM

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **23** | **Modul Laman Utama:** Petender hendaklah membangunkan Modul Laman Utama merangkumi: i. Merekabentuk laman utama bersifat dinamik, interaktif dan mesra pengguna. ii. Membangunkan sistem web-based yang mempunyai reka bentuk responsif. iii. Kandungan laman utama: a. Paparan senarai dan keterangan maklumat Darjah dan Bintang Kebesaran serta Pingat b. Paparan senarai Penerima Darjah dan Bintang Kebesaran serta Pingat c. Paparan warta d. Paparan carian warta dan penerima e. Hebahan dan pengumuman iv. Menu Bantuan Pelawat: a. Penambahan halaman Soalan Lazim b. Penambahan halaman maklumat Lazim c. Paparan Garis Panduan & Syarat Kelayakan d. Paparan Hubungi Kami | **M** | **Y** | All Laman Utama features will be implemented including dynamic content, award listings, recipient search, warta, FAQ, and contact information. |
| **24** | **Modul Dashboard:** Petender hendaklah membangunkan Modul Dashboard merangkumi paparan senarai lengkap permohonan dan statistik berkenaan jumlah permohonan, status permohonan dan lain-lain keperluan berdasarkan keperluan yang akan dikenalpasti dalam sesi URS. | **M** | **Y** | Dashboard with application lists, statistics, charts, and status tracking will be developed based on URS requirements. |
| **25** | **Modul Permohonan:** Petender hendaklah membangunkan Modul Permohonan ini merangkumi: i. Pendaftaran pengguna, log masuk pengguna sebagai pemohon beserta fungsi lupa kataluan termasuk fungsi log masuk menggunakan myDigital ID. ii. Borang permohonan (secara atas talian) iii. Muat naik dokumen sokongan yang berkaitan (termasuk status Insolvensi) iv. Cetak slip pengesahan Ketua Jabatan (beserta janaan barcode/qr) v. Cetakan slip ringkasan permohonan (beserta janaan barcode/qr) vi. Terima notifikasi status permohonan vii. Semakan status permohonan viii. Semakan kelayakan kategori pencalonan dengan Pingat/Bintang/Darjah Kebesaran ix. Paparan keterangan jenis Pingat/Bintang/Darjah Kebesaran yang memenuhi kelayakan x. Semakan tapisan awal keselamatan xi. Jika terpilih sebagai penerima: a. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran b. Pengesahan kehadiran ke Majlis Pengurniaan | **M** | **Y** | Complete nomination module with myDigital ID integration, document upload, QR/barcode generation, status notifications, eligibility checking, and attendance confirmation. |
| **26** | **Modul Pengurusan Permohonan Peranan Urus Setia dan Pentadbir:** Petender hendaklah membangunkan modul ini merangkumi fungsi-fungsi seperti berikut: i. Kemaskini tetapan kategori permohonan ii. Kemaskini tetapan syarat kelayakan kategori pencalonan iii. Buka sesi permohonan (tetapan sesi permohonan) iv. Scan barcode/qr slip permohonan yang diterima dari pemohon v. Semak permohonan vi. Kemaskini permohonan (mengikut keperluan) vii. Sahkan permohonan viii. Pengisian borang bagi pihak ix. Cetak borang permohonan/ringkasan permohonan pemohon x. Cetak senarai pencalonan mengikut kategori/penerima xi. Cetak surat/laporan/statistik | **M** | **Y** | Full application management module for Urus Setia and Admin with QR scanning, approval workflows, and report generation. |
| **27** | **Modul Pengurusan Proses Penilaian dan Tapisan:** Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Cetak borang permohonan/ringkasan permohonan pemohon ii. Cetak senarai pencalonan mengikut kategori/penerima iii. Kemaskini keputusan mesyuarat (4 sesi mesyuarat) iv. Kemaskini status permohonan bagi setiap sesi penilaian (4 sesi penilaian) v. Jana/cetak surat tawaran (beserta janaan qr - lock by tahun) vi. Jana/cetak surat akuan sumpah (beserta janaan qr - lock by tahun) vii. Jana/cetak borang pemulangan Darjah Kebesaran/Pingat viii. Hantar notifikasi status permohonan dan tarikh pengambilan surat tawaran ix. Jana/cetak senarai calon penerima mengikut kategori permohonan/penerima untuk tapisan keselamatan mengikut kategori tapisan (3 tapisan keselamatan melibatkan fungsi integrasi) x. Jana senarai calon penerima (mengikut format laman web Darjah Kebesaran-integrasi) xi. Pengesahan penerimaan Pingat/Bintang/Darjah Kebesaran (bagi pihak) xii. Pengesahan kehadiran ke Majlis Pengurniaan (bagi pihak) | **M** | **Y** | Evaluation and screening module with 4 meeting sessions, 4 evaluation stages, QR-coded letters, security screening integration, and attendance management. |
| **28** | **Modul Pentadbir Sistem:** Petender hendaklah membangunkan Modul ini merangkumi fungsi-fungsi seperti berikut: i. Ketetapan Sistem termasuk penyelenggaraan terhadap semua data lookup ii. Audit Trail Sistem iii. Tetapan Notifikasi Emel iv. Konfigurasi Integrasi dengan AD - login sistem (pentadbir sahaja) v. Tetapan Login Pengguna myDigital ID vi. Tetapan Pengesahan Emel vii. Fungsi Masquerade (Login sebagai) viii. Menyediakan tetapan tertakluk kepada keperluan sistem pada sesi URS | **M** | **Y** | System administration module with lookup data management, audit trails, email notifications, AD integration, myDigital ID configuration, and masquerade functionality. |
| **29** | **Modul Laporan:** Petender hendaklah menyediakan sistem yang mempunyai keupayaan menjana pelbagai laporan mengikut kriteria yang ditetapkan oleh pihak PSUK Selangor berdasarkan senarai dibawah: i. Laporan/Statistik Permohonan Tahunan Mengikut Sesi ii. Laporan/Statistik Permohonan Tahunan Mengikut Kategori Permohonan iii. Laporan/Statistik Permohonan Tahunan mengikut sesi penilaian iv. Laporan/Statistik Penerima Tahunan Mengikut Sesi v. Laporan/Statistik Penerima Tahunan Mengikut Kategori Permohonan vi. Laporan/Statistik Penerima mengikut sesi penilaian vii. Statistik Keseluruhan Penerima Sehingga Tahun Terkini viii. Senarai laporan/statistik mengikut keperluan semasa pada sesi URS ix. Paparan Warta serta statistik termasuk carian penerima dan warta *** Semua Laporan boleh dipapar secara infografik. | **M** | **Y** | Comprehensive reporting module with all specified reports including infographics and statistical visualizations. |
| **30** | **Modul Fungsi Integrasi:** Petender hendaklah menyediakan sistem yang mempunyai ketersediaan fungsi integrasi melalui pembangunan Application Programming Interface (API) yang mempunyai ciri-ciri keselamatan terkini bagi tujuan integrasi dengan sistem lain merangkumi: i. Pembangunan API bagi integrasi dengan Sistem SPRM, Jabatan Insolvensi, Laman Web Darjah Kebesaran, ROS, myIDENTITY dan HRMIS (mengikut keperluan semasa ketika sesi URS dan ketersediaan agensi terlibat) ii. Termasuk juga konfigurasi bagi penggunaan myDigital ID – bagi tujuan log masuk ke sistem. | **M** | **Y** | API development for integration with SPRM, Insolvensi, Darjah Kebesaran website, ROS, myIDENTITY, HRMIS, and myDigital ID login. |
| **31** | **Fungsi Backup dan Migrasi Data:** Petender hendaklah bersedia membangunkan fungsi-fungsi seperti berikut: i. Melakukan backup data ke storan hard disk bagi melindungi data daripada sebarang kegagalan ii. Migrasi keseluruhan sistem dan pangkalan data iii. Migrasi data lama dipindahkan ke pangkalan data baharu berjalan dengan baik (migrasi data permohonan dan penerima dari sistem sedia ada - lotus) iv. Data hendaklah boleh diakses dan sistem berfungsi dengan sempurna setelah selesai proses migrasi | **M** | **Y** | Backup and migration functions including daily backups, full system migration from existing Lotus system, and data integrity verification. |

---

#### E. PEMBEKALAN PERKAKASAN

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **32** | Petender hendaklah membekal, menyedia, memasang, mengkonfigurasi dan mentauliah: Satu (1) unit 1D/2D Handheld Barcode Scanner QR Wired USB Imager Black Corded Screen Code Reader with Stand (termasuk satu (1) tahun tempoh jaminan). Nota: Sila nyatakan model yang dicadangkan. | **M** | **Y** | **Proposed:** Honeywell Voyager 1250g or Zebra DS2208 barcode scanner with 1-year warranty. |

---

#### F. PERKHIDMATAN MIGRASI DAN DATA CLEANING

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **33** | Petender perlu menyedia perkhidmatan migrasi dan data cleaning melibatkan: i. Migrasi keseluruhan sistem dan pangkalan data daripada sistem terdahulu dan portal laman web rasmi Darjah Dan Bintang Kebesaran Serta Pingat Negeri Selangor. ii. Petender hendaklah memastikan data dari sistem dan portal terdahulu dapat digunakan semula dalam sistem baharu. iii. Proses migrasi data-data daripada sistem sedia ada akan dilaksana dan diuji secara terperinci dan menyeluruh. iv. Petender hendaklah mencadangkan dan menyediakan pelan migrasi lengkap kepada pihak PSUK Selangor. | **M** | **Y** | Complete migration plan including data extraction from Lotus system, data cleaning, transformation, loading (ETL), and verification testing. |

---

#### G. PENGUJIAN SISTEM DAN PERKAKASAN

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **34** | Petender perlu melaksana pengujian keseluruhan fungsi di dalam sistem dan perkakasan bagi memastikan ia mengikut aliran kerja sebenar dan penyediaan dokumentasi pengujian: a. User Acceptance Test (UAT) b. Provisional Acceptance Test (PAT) c. Equipment Acceptance Test (EAT) d. Final Acceptance Test (FAT) e. Pengujian Performance Test (PT) & Web Application Security Assessment (WASA) | **M** | **Y** | All testing phases will be conducted: UAT, PAT, EAT, FAT, Performance Testing, and WASA security assessment. |
| **35** | Petender hendaklah melaksanakan pembetulan dan penambahbaikan terhadap semua ralat yang dikesan semasa pengujian-pengujian di atas TANPA sebarang tambahan kos. | **M** | **Y** | All bug fixes and improvements during testing phases are included in the project cost. |
| **36** | Petender hendaklah bersetuju menyediakan dokumentasi pengujian melibatkan pelan pengujian, skrip pengujian, laporan pengujian, dan dokumentasi penerimaan/pentauliahan. | **M** | **Y** | Complete testing documentation including test plans, scripts, reports, and acceptance certificates will be provided. |
| **37** | Petender hendaklah bersetuju untuk menanggung kos bagi keperluan berkaitan semasa pengujian dilaksanakan. | **M** | **Y** | SESB will bear all costs related to testing activities. |

---

#### H. PEMASANGAN DAN KONFIGURASI SISTEM

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **38** | Petender hendaklah bersetuju bagi melaksanakan pemasangan dan konfigurasi keseluruhan sistem dan pangkalan data serta perlu membuat pengasingan: Development Environment, Production A Environment, Production B Environment (each with Application Server and Database Server) | **M** | **Y** | Three environments (Development, Production A, Production B) will be configured as specified. |
| **39** | Petender hendaklah melaksanakan pemasangan dan konfigurasi sistem ke atas server cloud yang akan disediakan dan dihostkan di Pusat Data Bahagian Pengurusan Maklumat, Tingkat 2, Bangunan Sultan Salahuddin Abdul Aziz Shah (SSAAS). | **M** | **Y** | System will be installed and configured on cloud servers at BPM Data Center, SSAAS. |
| **40** | Petender perlu menyatakan spesifikasi keperluan sistem dan storage yang diperlukan (termasuk capacity planning). | **M** | **Y** | System specifications and capacity planning provided in Annex E. |
| **41** | Petender hendaklah menggunakan perkhidmatan repository yang telah disediakan oleh Bahagian Pengurusan Maklumat, Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **Y** | SESB will use the repository service provided by BPM. |
| **42** | Petender hendaklah bersetuju melaksanakan pemasangan, integrasi, migrasi dan pelaksanaan perisian dengan jayanya. | **M** | **Y** | SESB confirms successful completion of installation, integration, migration, and implementation. |
| **43** | Pengurusan Backup dan Restore: Petender hendaklah bersetuju bagi melaksana konfigurasi salinan keselamatan (backup) secara daily, weekly, monthly. | **M** | **Y** | Backup configured: Daily (incremental), Weekly (full), Monthly (archival). |
| **44** | SSL Certificate: Petender hendaklah bersetuju untuk membuat pemasangan sistem bersama SSL Certificate bagi memastikan transaksi atas talian dalam keadaan selamat. SSL Certificate akan disediakan oleh Bahagian Pengurusan Maklumat (BPM), PSUK Selangor. | **M** | **Y** | System will be configured with SSL certificates provided by BPM. |
| **45** | Code Hardening: Petender hendaklah memastikan kod aturcara yang dibangunkan menepati ciri-ciri keselamatan yang perlu ada di dalam sistem. Sila nyatakan pelaksanaan code hardening yang dicadangkan. | **M** | **Y** | Code hardening includes: Input validation, Output encoding, CSRF protection, XSS prevention, SQL injection prevention, secure authentication, session management, and security headers. |
| **46** | Fungsi Notifikasi: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menghantar notifikasi pemakluman melalui SMS/Whatsapp dan E-mel. | **M** | **Y** | Notification system supporting SMS, WhatsApp, and Email alerts. |
| **47** | Tetapan/ Konfigurasi Sistem (Pentadbir): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Pentadbir Sistem mengikut keperluan. | **M** | **Y** | Administrator configuration settings as per requirements. |
| **48** | Tetapan/ Konfigurasi Sistem (Teknikal): Petender hendaklah bersetuju menyedia sistem yang mempunyai tetapan konfigurasi fungsi Teknikal Sistem seperti: a. Tetapan Akses dan Log b. Tetapan notifikasi E-mel / SMS / Whatsapp c. Fungsi Masquerade (Login sebagai) d. Menyediakan tetapan tertakluk kepada keperluan semasa sistem dan pengguna | **M** | **Y** | Technical configuration settings for access logs, notifications, masquerade, and other system settings. |
| **49** | Log/ Audit Trail: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan semua log audit terperinci dari segi akses pengguna, perubahan data dan lain-lain yang berkaitan: a. Log Proses b. Log Aktiviti c. Log Service d. Log E-mel e. Log SMS/Whatsapp | **M** | **Y** | Comprehensive audit trails for all system activities including process logs, activity logs, service logs, email logs, and SMS/WhatsApp logs. |
| **50** | Data History: Petender hendaklah bersetuju menyedia sistem yang berupaya untuk menyimpan maklumat lama/arkib (history/archive) di peringkat pengguna dan pentadbir sistem. | **M** | **Y** | Historical data archiving at both user and administrator levels. |

---

#### I. DOKUMENTASI

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **51** | Petender hendaklah menyedia dokumentasi berkaitan: a. Manual Pengguna b. Manual Pentadbir c. Manual Teknikal/Operasi | **M** | **Y** | Complete documentation set: User Manual, Administrator Manual, Technical/Operations Manual (all in Bahasa Malaysia). |
| **52** | Petender hendaklah menyediakan minit mesyuarat Pasukan Kerja dan Jawatankuasa Teknikal Projek dengan pemantauan urus setia projek. | **M** | **Y** | Meeting minutes for all Working Team and Technical Committee meetings will be documented. |
| **53** | Petender hendaklah menyediakan satu salinan manual penggunaan secara hardcopy dan softcopy kepada pengguna dan pentadbir sistem. | **M** | **Y** | Both hardcopy and softcopy manuals will be provided to users and administrators. |

---

#### J. LATIHAN DAN PEMINDAHAN TEKNOLOGI

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **54** | Petender perlu melaksana latihan dan pemindahan teknologi melibatkan: a. Latihan Pengguna b. Latihan Pentadbir Sistem c. Transfer of Technology (TOT) | **M** | **Y** | Training programs for users, administrators, and Transfer of Technology sessions. |
| **55** | Petender bersetuju melaksanakan sesi TOT kepada pegawai-pegawai yang terlibat dan pentadbir sistem untuk memahirkan diri dalam pembangunan/penyelenggaraan sistem bagi menguruskan isu-isu teknikal sistem dan konfigurasi sistem/server yang berkaitan (sila nyatakan cadangan lokasi dan kemudahan latihan yang akan dilaksana). | **M** | **Y** | TOT sessions will be conducted at PSUK Selangor or SESB training facilities. |
| **56** | Petender hendaklah menyenarai kesemua fail dan modul yang terdapat di dalam sistem dan server untuk tujuan TOT tersebut. | **M** | **Y** | Complete listing of all files and modules for TOT purposes. |
| **57** | Petender hendaklah menyediakan dokumentasi lengkap bagi setiap latihan dan sesi TOT. | **M** | **Y** | Full documentation for all training and TOT sessions. |
| **58** | Petender hendaklah mencadangkan senarai latihan dan TOT. | **M** | **Y** | Proposed training schedule provided in Annex F. |
| **59** | Laporan Kemajuan Projek: Petender hendaklah menyediakan Laporan Kemajuan Projek sekurang-kurangnya tiga (3) kali sepanjang tempoh projek, tertakluk kepada keperluan semasa. Petender hendaklah menyediakan Laporan Akhir Pelaksanaan Projek setelah pelaksanaan projek selesai sepenuhnya. | **M** | **Y** | Minimum 3 progress reports and 1 final project completion report will be submitted. |

---

#### K. KOD SUMBER DAN PANGKALAN DATA

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **60** | i. Semua kod sumber (source code) adalah hak milik sepenuhnya Kerajaan Negeri Selangor dan wajib diserahkan dalam bentuk softcopy kepada Kerajaan Negeri apabila projek telah siap. ii. Sebarang penyalinan, pemindahan dan pengedaran dengan apa juga cara untuk tujuan komersil adalah tidak dibenarkan sama sekali kecuali mendapat kebenaran daripada Kerajaan Negeri Selangor. | **M** | **Y** | Full source code ownership transferred to Kerajaan Negeri Selangor upon project completion. No commercial distribution without permission. |

---

#### L. PEMBAYARAN

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **61** | Petender tidak boleh menuntut apa-apa bentuk bayaran tambahan daripada Kerajaan Negeri selain daripada bayaran yang dinyatakan dalam dokumen kontrak. | **M** | **Y** | No additional charges beyond contract amount. |
| **62** | Perjanjian: Petender yang berjaya dikehendaki menandatangani satu kontrak dengan Kerajaan Negeri dalam tempoh empat (4) bulan dari tarikh mula projek. | **M** | **Y** | Contract signing within 4 months from project start date. |

---

#### M. PERKHIDMATAN KHIDMAT SOKONGAN DALAM TEMPOH WARANT

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **63** | Petender hendaklah bersetuju: a. Memberi jaminan perkhidmatan sokongan terhadap Sistem ePingat yang dibangunkan dalam tempoh satu (1) tahun bermula selepas tarikh FAT (Go Live) ditandatangani tanpa sebarang kos. b. Sekiranya terdapat keadaan di mana salah satu ataupun keseluruhan komponen sistem gagal berfungsi sepertimana yang sepatutnya, syarikat akan bertanggungjawab sepenuhnya kepada kerja-kerja recovery. c. Petender perlu menyediakan Service Level Agreement (SLA) bagi kadar penyelesaian isu yang diadukan. d. Kerajaan Negeri berhak untuk menyampaikan aduan kepada Petender pada bila-bila masa dan tiada had ke atas bilangan aduan. e. Petender hendaklah menyediakan sistem helpdesk/call center/pusat khidmat pengguna. Masa tindakan: i. Helpdesk (Phone, Email and Helpdesk System) - 24 jam x 7 hari seminggu ii. Technical Support - 8 jam x 5 hari seminggu iii. Masa Tindakan - (Response Time – Min 4 jam) - (Selesai Masalah – Max 3 Hari Waktu bekerja) f. Petender perlu menyedia khidmat bantuan dan nasihat penggunaan sistem yang betul. | **M** | **Y** | 1-year warranty support with 24/7 helpdesk, 8x5 technical support, SLA with 4-hour response time and 3-day resolution time. |
| **64** | Tempoh Jaminan/ Waranti: Petender perlu memberi jaminan dalam tempoh SATU (1) TAHUN bermula selepas FAT (Final Acceptance Test) ditandatangani melibatkan: a. Perkhidmatan sokongan secara on site dan secara atas talian. b. Pembetulan ralat keseluruhan sistem dan perkakasan. | **M** | **Y** | 1-year warranty from FAT signing including on-site and online support, bug fixes. |
| **65** | Petender bersetuju menyediakan dan menyempurnakan dokumen penyerahan projek selepas pelaksanaan projek selesai sepenuhnya. | **M** | **Y** | Complete project handover documentation upon project completion. |
| **66** | Petender bersetuju melaksanakan kerja-kerja yang tidak dinyatakan secara khusus di dalam keperluan projek tetapi perlu dilaksanakan bagi melancarkan dan menjayakan pelaksanaan projek ini. | **M** | **Y** | SESB agrees to perform any additional work necessary for successful project completion. |

---

#### N. KESELAMATAN DATA

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **67** | Keselamatan Data: a. Petender mestilah bertanggungjawab ke atas keselamatan data dan kerahsiaan data. b. Semua kakitangan yang dilantik perlu menandatangani akuan sumpah untuk tidak mendedahkan maklumat dalam apa jua bentuk dan format. c. Petender perlu membaca, memahami dan mematuhi Dasar Keselamatan ICT Pejabat Setiausaha Kerajaan Negeri Selangor. | **M** | **Y** | Data security and confidentiality assured. All staff will sign confidentiality agreements and comply with PSUK ICT Security Policy. |

---

#### O. LAIN-LAIN

| No. | Description | M/O | Compliance (Y/N) | Remarks |
|-----|-------------|-----|------------------|---------|
| **68** | Lain-Lain Cadangan (Jika Ada): Sila nyatakan lain-lain cadangan/perkhidmatan yang berkaitan, sekiranya ada. | **O** | **Y** | Additional value-added services proposed in the technical proposal including: Extended warranty options, Knowledge transfer sessions, Post-warranty support packages. |

---

## SUMMARY OF COMPLIANCE

| Category | Total Items | Mandatory | Compliant (Y) | Compliance Rate |
|----------|-------------|-----------|---------------|-----------------|
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

**SESB confirms 100% compliance with all 68 items in Jadual 1, including all 65 Mandatory (M) items and 3 Optional (O) items.**

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
