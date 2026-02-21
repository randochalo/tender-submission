# JADUAL PENENTUAN TEKNIKAL / TECHNICAL COMPLIANCE SCHEDULE

## TSH-2614: SISTEM PORTAL STAF (eCommunity) / STAFF PORTAL SYSTEM

---

**No. Sebut Harga / Quotation No:** UMPSA/BEND/SH/2026(3)  
**Tajuk / Title:** Membekal, Membangun, Menghantar, Memasang, Mengintegrasi, Memindah, Menguji Dan Mentauliah Sistem Portal Staf (eCommunity) Di Universiti Malaysia Pahang Al-Sultan Abdullah  
**Tarikh Buka / Opening Date:** 12 Februari 2026  
**Tarikh Tutup / Closing Date:** 26 Februari 2026  
**Pegawai Bertanggungjawab:** En. Mohd Roslan bin Muhamad (09-431 5212 / mroslan@umpsa.edu.my)

---

## ARAHAN / INSTRUCTIONS

1. **Jangan** gunakan perkataan seperti "OK", "MAKLUM", "SETUJU", "PATUH", "NOTED", "AGREED", "COMPLY" semata-mata. Jika perlu, berikan rujukan yang jelas.
2. Setiap item **MESTI** dijawab dalam ruangan "Maklumbalas / Spesifikasi Syarikat".
3. Sertakan katalog/brosur/dokumen sokongan untuk mengesahkan pematuhan.
4. Ketidakpatuhan akan menyebabkan penyingkiran / Non-compliance will result in disqualification.
5. Semua pemilikan data dan kod sumber adalah milik UMPSA sepenuhnya.

---

## SEKSYEN 2.0: SPESIFIKASI TEKNIKAL / TECHNICAL SPECIFICATIONS

---

### 2.1 SKOP KERJA / SCOPE OF WORK

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **2.1.1** | **SKOP UTAMA / MAIN SCOPE** | | |
| a | Petender mestilah menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API (application programming interface) untuk setiap modul. Ini termasuk penggunaan Eloquent ORM. | | |
| b | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| c | Replikasi, migrasi logik dan fungsi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa. | | |
| d | Membangunkan sistem menggunakan teknologi antaramuka pengguna (UI) web dan panel pentadbir yang moden, ciri-lengkap, sumber terbuka (OSS) dan mudah diselenggara, dengan keutamaan menggunakan Filament PHP atau setara. Sistem ini mestilah mempunyai ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| e | Menggunakan pangkalan data Oracle (minimum versi 19c) yang sedia ada di UMPSA. | | |
| f | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| g | Menggunakan teknologi kontena aplikasi (application container technology) sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| h | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery. Persekitaran pembangunan sistem perlu disediakan oleh petender. | | |
| i | Melaksanakan integrasi dengan sistem dalaman berikut:<br>&nbsp;&nbsp;&nbsp;&nbsp;i. MyUMPSA-ID Single Sign-On (SSO)<br>&nbsp;&nbsp;&nbsp;&nbsp;ii. Redis<br>&nbsp;&nbsp;&nbsp;&nbsp;iii. Email gateway<br>&nbsp;&nbsp;&nbsp;&nbsp;iv. File storage<br>&nbsp;&nbsp;&nbsp;&nbsp;v. API<br>&nbsp;&nbsp;&nbsp;&nbsp;vi. Notification Mobile | | |
| j | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| k | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| l | Menyediakan latihan:<br>&nbsp;&nbsp;&nbsp;&nbsp;i. Latihan kepada pentadbir sistem (IT)<br>&nbsp;&nbsp;&nbsp;&nbsp;ii. Latihan kepada pengguna akhir (end-users) | | |
| m | Membangun, menguji dan mentauliah Sistem Portal Staf:<br>&nbsp;&nbsp;&nbsp;&nbsp;i. Serahan penuh kod sumber<br>&nbsp;&nbsp;&nbsp;&nbsp;ii. Konfigurasi pelayan staging, development, DR dan production<br>&nbsp;&nbsp;&nbsp;&nbsp;iii. Migrasi dan pelaksanaan penuh sistem baharu | | |

---

### 2.1.2 KEPERLUAN FUNGSIAN / FUNCTIONAL REQUIREMENTS

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **a** | **MODUL LOGIN / LOGIN MODULE** | | |
| 1 | **Login (Authentication)** | | |
| | Modul ini adalah untuk menyemak dan mendapat pengesahan identiti pengguna melalui SSO and Identity Provider (IdP) Keycloak UMPSA sedia ada. Selain itu, pengguna boleh juga log masuk ke aplikasi melalui pengesahan Google Sign-in. | | |
| **b** | **MODUL TEMUJANJI DAN KALENDAR / APPOINTMENT AND CALENDAR MODULE** | | |
| i | **Pengurusan Temujanji / Appointment Management** | | |
| 1 | Pengguna boleh menambah, mengubah, atau memadam temujanji. Senarai peserta perlulah boleh dipilih daripada/mengikut kumpulan pengguna dalam Organizational Unit (OU) atau user groups di Active Directory (AD) UMPSA. | | |
| 2 | Pengguna boleh melihat semula senarai temujanji yang telah dibuat. | | |
| 3 | Sistem memaparkan kalendar bagi memudahkan pemilihan tarikh dan masa. | | |
| 4 | Sistem juga perlu membuat semakan dengan Google Calendar bagi mengelakkan pertindihan jadual sebelum temujanji disimpan. | | |
| ii | **Papar Kalendar / Calendar View** | | |
| 1 | Pengguna boleh melihat paparan kalendar dalam format harian, mingguan, atau bulanan. | | |
| 2 | Paparan kalendar memaparkan semua temujanji yang telah dijadualkan berserta statusnya. | | |
| 3 | Pengguna boleh menyemak dan melihat temujanji yang diselaraskan (sync) dengan Google Calendar. | | |
| 4 | Pengguna boleh menjana laporan dalam bentuk pdf. | | |
| **c** | **MODUL MEMO / MEMO MODULE** | | |
| 1 | Pengguna boleh melihat senarai memo yang diterima. | | |
| 2 | Fungsi carian disediakan untuk mencari memo berdasarkan kata kunci, tarikh, atau pengirim/penerima. | | |
| 3 | Pengguna boleh mengurus memo mengikut folder khas yang dicipta oleh pengguna. | | |
| **d** | **MODUL PENGUMUMAN / ANNOUNCEMENT MODULE** | | |
| 1 | Pengguna boleh melihat senarai pengumuman yang aktif. | | |
| 2 | Pengguna boleh menambah, mengubah, atau memadam pengumuman. | | |
| 3 | Fungsi carian disediakan untuk mencari pengumuman berdasarkan kata kunci, tarikh, kategori atau pengirim. | | |
| 4 | Pengumuman yang tidak lagi aktif boleh diarkibkan untuk rujukan pada masa hadapan. | | |
| **e** | **PENGURUSAN PENGGUNA / USER MANAGEMENT** | | |
| 1 | **Kebenaran Pengguna (User Authorization)** | | |
| | Sistem mengesahkan identiti pengguna melalui proses log masuk sebelum membenarkan akses ke dalam sistem. | | |
| 2 | **Keistimewaan Pengguna (User Privilege)** | | |
| | Setiap pengguna diberikan tahap akses tertentu berdasarkan peranan (role) yang ditapkan, contohnya akses untuk melihat, menambah, mengubah, atau memadam data. | | |
| 3 | **Keistimewaan Kumpulan (Group Privilege)** | | |
| | Pengguna boleh diurus secara berkumpulan dengan pemberian keistimewaan akses yang sama kepada semua ahli kumpulan tersebut. | | |
| 4 | **Audit Log Aktiviti Pengguna** | | |
| | Sistem merekod semua aktiviti pengguna termasuk log masuk, log keluar, penambahan, pengubahan, dan pemadaman data untuk tujuan pengesanan serta keselamatan. Memaparkan laporan atau statistik penggunaan modul dalam sistem. | | |
| 5 | **Senarai Pengguna** | | |
| | Sistem memaparkan senarai semua pengguna beserta maklumat asas. Kemudahan fungsi carian juga perlu disediakan. | | |
| **f** | **MODUL TETAPAN / SETTINGS MODULE** | | |
| 1 | **Pengurusan Kumpulan (Group)** | | |
| | Membolehkan pengguna mengurus kumpulan bagi tujuan pengelompokan pengguna dan pemberian akses mengikut kumpulan. | | |
| 2 | **Personalisasi Menu (Personalize Menu)** | | |
| | Pengguna boleh mengubah susunan dan paparan menu mengikut keperluan masing-masing. | | |
| 3 | **Susun Atur & Tema (Layout & Customized Theme)** | | |
| | Membolehkan pengguna menukar susun atur antaramuka dan memilih tema warna mengikut keselesaan. | | |
| **g** | **MODUL NOTIFIKASI / NOTIFICATION MODULE** | | |
| 1 | Memaparkan jumlah item yang memerlukan tindakan kelulusan oleh eksekutif secara masa nyata (real-time). | | |
| 2 | Notifikasi dipaparkan di papan pemuka (dashboard) dan/atau melalui ikon amaran di bahagian menu utama. | | |
| 3 | Menyokong pautan terus (direct link) ke item berkenaan untuk memudahkan proses semakan dan kelulusan. | | |
| 4 | Mengintegrasi dengan sistem Notifikasi Mudah Alih (Mobile Notification) sedia ada di UMPSA. | | |

---

### 2.2 PEMATUHAN & PERKHIDMATAN PROFESIONAL / COMPLIANCE & PROFESSIONAL SERVICES

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **2.2.1** | **Sesi Taklimat Secara Dalam Talian / Online Briefing Session** | | |
| | UMPSA berhak untuk memanggil petender untuk sesi taklimat secara dalam talian (Google Meet, MS Teams atau seumpamanya) sekiranya perlu. Tarikh dan masa (hari bekerja) yang ditetapkan oleh UMPSA mestilah dipatuhi oleh petender. UMPSA berhak tidak menilai tawaran petender jika petender gagal hadir dalam sesi tersebut. | | |
| **2.2.2** | **Bengkel / Workshop** | | |
| | Petender yang berjaya/dipilih hendaklah melaksanakan Bengkel bagi membangunkan pelan pelaksanaan projek ini termasuklah meneliti keperluan sistem, proses yang terlibat serta keperluan persekitaran sistem. Bengkel ini akan melibatkan pemilik proses, staf teknikal dan petender yang dilantik. | | |
| i | Satu (1) sesi bengkel akan diadakan untuk mengenalpasti spesifikasi secara terperinci berkenaan sistem/modul yang terlibat. Kekerapan perbincangan secara fizikal atau dalam talian adalah mengikut keperluan sehingga draf dokumen selesai. | | |
| ii | Penyediaan Pelan Pelaksanaan | | |
| | Satu pelan pelaksanaan bertulis yang muktamad perlu dihasilkan oleh petender yang berjaya/dipilih selepas bengkel item 2.2.2 diadakan. Pelan ini perlu turut meliputi aspek organisasi projek, penjadualan pelaksanaan aktiviti projek, 'work breakdown structure (WBS)', 'critical path method (CPM)' diagram, jadual PERT serta metodologi pembangunan. | | |
| iii | Dokumen pelan pelaksanaan perlu dihantar kepada pihak UMPSA dalam tempoh dua (2) minggu dari tarikh selesai bengkel di item 2.2.2. | | |
| iv | UMPSA berhak menolak atau mengarah pemindaan pelan pelaksanaan oleh petender yang didapati bersalahan dengan objektif tender ini atau mempunyai kesilapan. | | |
| **2.2.3** | **Penyediaan Cadangan Rekabentuk UI/UX / UI/UX Design Proposal** | | |
| i | Petender yang berjaya/dipilih perlu mencadangkan konsep rekabentuk antaramuka pengguna (user interface UI) yang terkini dan moden bertepatan dengan penggunaan semua jenis peranti masa kini termasuk peranti mudah alih. Konsep rekabentuk antaramuka ini perlu dihantar dalam tempoh tiga (3) minggu dari tamat bengkel. | | |
| ii | Fungsi aplikasi dalam pembangunan modul mestilah bersesuaian dengan kehendak pengguna atau pengalaman pengguna (user experience - UX) supaya setiap modul berfungsi dengan baik dan mesra pengguna. | | |
| **2.2.4** | **Penerapan Standard / Standards Implementation** | | |
| i | Pelaksanaan kerja-kerja pembangunan aplikasi dan sistem mestilah mengikut standard terbaik industri dan memenuhi persekitaran UMPSA. | | |
| ii | Petender perlu menerapkan UMPSA Standard Coding Convention dalam pengaturcaraan semua modul sistem aplikasi yang dipersetujui dalam tender ini. UMPSA akan membekalkan dokumen panduan berkenaan. | | |
| iii | Sebarang pewujudan 'table' baru atau 'column' baru untuk menyimpan data rekod yang ingin diwujudkan dalam pangkalan data UMPSA perlulah menggunakan 'naming standard' yang betul serta mendapat kelulusan secara bertulis oleh Pentadbir Pangkalan Data UMPSA. | | |
| iv | Sebarang 'table' baharu yang ingin diwujudkan dalam pangkalan data UMPSA perlulah telah siap dinormalisasikan (normalization). | | |
| v | Petender perlu memastikan perisian atau sistem aplikasi yang dibangunkan atau dibekalkan mematuhi standard terbuka (open standard) semasa dan garis panduan Kerajaan Malaysia seperti Kejuruteraan Sistem Aplikasi Sektor Awam (KRISA), Electronic Government Information Technology Policy and Standards (EGIT), Data Dictionary Sektor Awam (DDSA), Management of Information & Communication Technology Security Handbook (MYMIS), Malaysian Government Interoperability Framework (MyGIF), Malaysian Government Interoperability Framework for Open Source Software (MyGIFOSS) dan Garis Panduan IT Outsourcing Agensi - Agensi Sektor Awam. | | |
| **2.2.5** | **Pengurusan Kod Sumber / Source Code Management** | | |
| i | Semua kod sumber (source code) dan hak cipta sistem aplikasi yang dibangunkan untuk setiap sistem aplikasi melalui tender ini adalah menjadi HAKMILIK UMPSA sepenuhnya. | | |
| ii | Petender TIDAK dibenarkan membuat edaran, salinan atau salin cetak kepada pihak lain atau; disimpan di tempat yang tidak berkaitan projek/perolehan ini; tanpa apa-apa kebenaran rasmi secara bertulis dari pihak UMPSA. | | |
| iii | Petender wajib meletakkan/menghoskan kod sumber terkini yang sedang dibangunkan serta kod sumber yang siap dibangunkan untuk pengujian di repository GitLab UMPSA. Kegagalan petender atau sekutu mematuhi terma ini dianggap sebagai pelanggaran syarat kontrak tender ini. | | |
| iv | UMPSA berhak mengukur status pencapaian kerja dan perkhidmatan petender termasuk bagi tujuan pembayaran berdasarkan tahap kematangan, kesediaan atau keaktifan kod sumber yang diletakkan oleh petender di repository GitLab UMPSA itu. | | |
| v | 'Deployment' sebarang sistem aplikasi atau modul dalam tender ini ke server-server aplikasi UMPSA mestilah hanya melalui GitLab UMPSA. 'Deployment' sistem aplikasi secara terus ke server aplikasi tanpa melalui GitLab UMPSA adalah tidak dibenarkan. | | |
| vi | Petender wajib memastikan kod sumber yang dibangunkan atau dibekalkan adalah selamat, berfungsi dan bebas ralat. | | |
| vii | Pengurusan repositori GitLab UMPSA adalah di bawah kuasa UMPSA serta petender tertakluk mematuhi syarat-syarat semasa penggunaan repository GitLab UMPSA ataupun syarat-syarat baru dari masa ke semasa. | | |
| viii | UMPSA tidak mengganggu kod sumber yang sedang dibangunkan oleh petender namun UMPSA berhak melantik wakil penyemak dan penguji kod sumber dalam repositori yang berkaitan bagi tujuan pengujian, kawalan kualiti serta kesinambungan pengetahuan. | | |
| ix | Apa-apa isu yang timbul berhubung penggunaan atau pengoperasian GitLab UMPSA dalam projek tender ini hendaklah dirujuk kepada Pengurus GitLab UMPSA atau Pengurus Projek tender ini. Pengurus GitLab UMPSA berhak dan boleh memutuskan tatacara atau perubahan tatacara yang perlu diikuti oleh kedua-dua belah pihak. | | |
| x | Selepas tempoh jaminan tamat petender perlu menghapuskan segala data, maklumat dan kod sumber (source code) projek/tender ini yang berada di dalam simpanan petender atau sekutu. | | |
| **2.2.6** | **Pemasangan, Konfigurasi dan Integrasi / Installation, Configuration and Integration** | | |
| i | Server (Linux) untuk hos API dan sistem aplikasi sebenar akan dibekalkan oleh UMPSA. Petender bertanggungjawab memasang dan menyediakan 'system environment' yang diperlukan dan sesuai bagi membolehkan sistem aplikasi berfungsi dengan betul serta berkesan. | | |
| ii | Petender perlu mempunyai 'development environment' server sendiri untuk tujuan pembangunan aplikasi sebagai alternatif sekiranya petender tidak dapat mengakses atau menggunakan server di UMPSA untuk tujuan pembangunan aplikasi-aplikasi dalam projek ini atas sebab-sebab yang diperakui UMPSA. Ini supaya fasa proses pembangunan aplikasi tidak tergendala. Fasa pengujian dan 'production deployment' aplikasi tetap wajib dijalankan/dilakukan di server UMPSA. | | |
| iii | Petender perlu menyempurnakan kerja-kerja pemasangan dan konfigurasi API di server UMPSA sekiranya ada. | | |
| iv | Petender perlu membekalkan perisian atau 'package' perisian yang berkaitan untuk membolehkan aplikasi di item 2.1.1 berfungsi seperti mana keperluan UMPSA. Kos pemasangan untuk semua perisian atau 'package' perisian adalah di bawah tanggungjawab pihak petender. | | |
| v | Petender perlu patuh dan mengikuti semua peraturan dan prosedur yang ditetapkan oleh UMPSA ketika kerja-kerja proses pembangunan, pemasangan, konfigurasi, integrasi, pengujian dan pentauliahan dijalankan. | | |
| vi | Petender mesti menyempurnakan proses integrasi melibatkan pemasangan dan konfigurasi API bagi setiap modul berkaitan tender ini di server UMPSA sekiranya ada. | | |
| vii | Sebarang kerja, pemasangan, konfigurasi dan integrasi sistem aplikasi yang tidak dinyatakan di dalam dokumen tender ini, tetapi perlu ada bagi melengkapkan proses keseluruhan sistem di dalam projek ini dan dianggap perlu oleh pihak UMPSA, pihak petender mesti menyelesaikan skop tersebut tanpa sebarang kos tambahan. | | |
| viii | Kerja-kerja integrasi komponen baharu mestilah serasi dan boleh berkomunikasi dengan komponen sedia ada tanpa menjejaskan fungsi yang sedang digunakan di UMPSA. | | |
| **2.2.7** | **Lesen Perisian / Software License** | | |
| | Sebarang perisian yang dibekalkan, dipasang atau digunakan mestilah sah, asli serta mendapat kebenaran (licensed) untuk digunakan di UMPSA daripada penerbitnya. UMPSA tidak bertanggungjawab terhadap sebarang penggunaan perisian 'proprietary' tidak berlesen atau perisian 'public license' yang tidak mematuhi/mendapat kebenaran penerbitnya oleh pihak petender atau sekutu. Sebarang perbekalan, pemasangan atau penggunaan perisian yang melibatkan langganan kos secara bulanan, tahunan atau berkala yang lain perlulah terlebih dahulu dimaklumkan dan mendapat persetujuan bertulis UMPSA. | | |
| **2.2.8** | **Versi Perisian / Software Version** | | |
| | Bagi keadaan di mana versi perisian yang disyaratkan dalam perolehan perkhidmatan ini telah dikira sebagai 'outdated' atau menjadi 'not supported', maka versi yang lebih baru, stabil dan bersesuaian dengan keperluan UMPSA perlu dibekalkan dengan mendapat persetujuan bertulis daripada UMPSA. Penukaran versi adalah tanpa sebarang kos tambahan. | | |
| **2.2.9** | **Kerja Panggil Balik / Call Back Work** | | |
| | Petender dikehendaki menyediakan perkhidmatan "panggil balik" bagi skop "Corrective Maintenance" tanpa sebarang bayaran tambahan bagi perkhidmatan/kerja yang kurang memuaskan dalam tempoh jaminan/waranti. | | |
| **2.2.10** | **Polisi Teknologi ICT Hijau / Green ICT Policy** | | |
| | Jika pembekalan melibat peranti atau peralatan tambahan, ianya perlulah menyokong kepada Polisi Teknologi ICT Hijau. | | |
| **2.2.11** | **'Tools' Penyelenggaraan / Maintenance Tools** | | |
| | Pihak petender hendaklah menyediakan set perisian atau 'tools' lengkap untuk penyelenggaraan teknologi yang digunakan sistem aplikasi dan pembaikan sistem aplikasi. Set perisian penyelenggaraan juga perlu dipasang dalam satu netbook atau seumpamanya yang ditempatkan di UMPSA bagi tujuan selenggara dan 'ghost disk cloning' sepanjang penggunaan teknologi itu. Petender hendaklah menjamin ketersediaan perkhidmatan selepas jualan untuk semua perisian yang dibekalkan. | | |
| **2.2.12** | **Pengujian / Testing** | | |
| i | Petender dikehendaki menjalankan dan melepasi ujian-ujian berikut:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Ujian Penerimaan Pengguna (User Acceptance Test, UAT) di UMPSA sekurang-kurangnya dua (2) kali<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Semakan 'compliance of server setup' bagi mana-mana server yang dipasang atau dikonfigurasi oleh petender<br>&nbsp;&nbsp;&nbsp;&nbsp;c. Ujian Penembusan Keselamatan (Security Penetration Test) UMPSA<br>&nbsp;&nbsp;&nbsp;&nbsp;d. Ujian Penerimaan Akhir (Final Acceptance Test, FAT) | | |
| ii | Petender dikehendaki menyediakan skrip pengujian (test script) bagi tujuan pelaksanaan pengujian UAT setiap modul sistem aplikasi di dalam tender/projek ini. Skrip perlu dalam Bahasa Melayu. | | |
| iii | User Acceptance Test (UAT) mesti dilakukan sekurang-kurangnya dua (2) kali. Lokasi UAT ialah di UMPSA dan pasukan pembangunan petender mesti hadir. | | |
| iv | Final Acceptance Test (FAT) mestilah dijalankan di production server dengan jayanya. Jika gagal, petender mesti bersedia untuk menjalankan pengujian semula. | | |
| v | Petender bertanggungjawab untuk membangun, mengimplementasi dan menguruskan semua prosedur semasa melaksanakan UAT dan FAT. | | |
| vi | Semua dokumen peringkat pengujian mestilah dipersetujui, disahkan dan ditandatangani oleh pihak UMPSA. | | |
| **2.2.13** | **Pelaksanaan dan Pentauliahan / Implementation and Certification** | | |
| i | Petender mesti memastikan semua sistem aplikasi yang telah dibangunkan dan diintegrasi dapat berfungsi dengan baik sebelum proses pemasangan (deployment) dijalankan. Ia merangkumi:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Bebas ralat<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Keselamatan sistem dan data<br>&nbsp;&nbsp;&nbsp;&nbsp;c. Pelan sokongan sekiranya berlaku kegagalan semasa instalasi di server UMPSA. | | |
| ii | Petender mesti bertanggungjawab memastikan sistem yang ditauliahkan terjamin dari segi prestasi dan keselamatannya dalam tempoh jaminan. | | |
| iii | Petender mesti memastikan sistem yang dibangunkan mempunyai tahap 'interoperability' dan 'scalability' yang baik bagi menyokong perkembangan penggunaannya pada masa hadapan. | | |
| **2.2.14** | **Latihan / Training** | | |
| i | Tatacara penggunaan sistem bagi setiap modul dalam sistem yang diintegrasikan (berkonsep train-the-trainer) secara dalaman. | | |
| ii | Petender perlu melakukan pemindahan kepakaran (Transfer of Technology) kepada pasukan teknikal UMPSA bagi setiap modul. Ia akan melibatkan:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Aliran Sistem (System Flow)<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Data Flow Diagram (DFD) dan Entiti Relationship Diagram (ERD)<br>&nbsp;&nbsp;&nbsp;&nbsp;c. Teknologi dan tools yang digunakan<br>&nbsp;&nbsp;&nbsp;&nbsp;d. Sumber rujukan<br>&nbsp;&nbsp;&nbsp;&nbsp;e. Nota lengkap | | |
| iii | Petender perlu menjadual, menganjur dan melaksanakan aktiviti latihan yang berkaitan dengan pembangunan aplikasi dan sistem secara 'on-site' bagi tujuan penyelenggaraan aplikasi dan sistem yang dibangunkan atau dibekalkan melalui tender ini. Staf yang terlibat akan dinamakan oleh pihak UMPSA. | | |
| | Latihan ini meliputi penyelenggaraan berikut:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Latihan penyelenggaraan Sistem Portal Staf<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Latihan pembangunan dan penyelenggaraan API (Laravel) | | |
| **2.2.15** | **Dokumentasi / Documentation** | | |
| i | Manual dan dokumentasi hendaklah disediakan dalam bentuk hard-copy dan soft-copy. Manual dan dokumentasi perlulah dalam Bahasa Melayu. Istilah-istilah teknikal dalam Bahasa Inggeris boleh digunakan mengikut keperluan untuk penerangan maksud/konsep lebih baik. | | |
| ii | Semua dokumen teknikal perlu mendapat kelulusan pihak teknikal UMPSA sebelum segala kerja-kerja pembangunan sistem bermula. | | |
| iii | Petender yang berjaya mesti menyerahkan semua dokumentasi berikut kepada UMPSA:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Pelan pelaksanaan projek<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Cadangan rekabentuk UI/UX<br>&nbsp;&nbsp;&nbsp;&nbsp;c. System Requirement Specification (SRS)<br>&nbsp;&nbsp;&nbsp;&nbsp;d. User Acceptance Test (UAT)<br>&nbsp;&nbsp;&nbsp;&nbsp;e. Final Acceptance Test (FAT)<br>&nbsp;&nbsp;&nbsp;&nbsp;f. Manual Pengguna<br>&nbsp;&nbsp;&nbsp;&nbsp;g. Lain-lain dokumen yang tidak dinyatakan di atas (yang berkaitan) | | |
| **2.2.16** | **Pengurusan Projek / Project Management** | | |
| i | Petender mesti sedia, komited dan mampu menghadiri mesyuarat pengurusan projek di UMPSA sekurang-kurangnya pada tempoh sebulan sekali ataupun pada mana-mana tarikh dan masa yang ditetapkan oleh UMPSA. Kehadiran ini termasuk bagi mana-mana keperluan pemasangan (setup), pengujian sistem aplikasi mahupun 'production deployment' sistem aplikasi di dalam projek ini. | | |
| ii | Petender atau ahli pasukan petender yang menghadiri mesyuarat pengurusan projek perlulah berkelayakan, berkemampuan dalam komunikasi profesional, memahami teknikal projek, dapat melapor serta boleh membuat keputusan terus (wakil kuasa penuh) apabila diminta dalam mesyuarat. Kegagalan petender atau sekutu mematuhi terma ini dianggap sebagai pelanggaran kritikal syarat kontrak tender ini dan boleh didenda. | | |
| iii | Petender mesti menyediakan senarai lengkap pasukan projek yang terlibat beserta peranan setiap ahli. Ahli pasukan mestilah sama atau setara keupayaan kompetensinya sepertimana dalam tawaran dan struktur awal di LAMPIRAN A-01. | | |
| iv | Pengurus projek petender mesti mempunyai pengalaman mengurus sekurang-kurangnya tiga (3) projek yang setara dalam teknologi yang sama dengan tender ini. | | |
| v | Petender mesti mempunyai staf yang berpengalaman dalam menganalisa serta membangunkan pelan pelaksanaan projek. | | |
| vi | Petender perlu menyediakan satu platform yang khusus secara atas talian untuk tujuan pemantauan dan pengurusan projek dan segala kos yang berkaitan adalah dibawah tanggungjawab Petender. | | |
| vii | UMPSA tidak menyediakan akses VPN kepada petender. Oleh itu petender mestilah merancang pelaksanaan projek ini mengikut kesesuaian perkara ini. Petender mesti menempatkan sekurang-kurangnya satu (1) unit komputer desktop (PC) di premis UMPSA bagi tujuan pengurusan projek atau 'remote access'. | | |
| viii | Sebarang bentuk kemudahan 'remote access' atau peralatan di UMPSA adalah wajib tertakluk kepada syarat/peraturan penggunaannya di UMPSA yang petender perlu akur akannya. | | |
| ix | Segala surat-menyurat, mesyuarat serta minit mesyuarat dalam projek ini adalah dalam Bahasa Melayu. Salinan dalam Bahasa Inggeris boleh disediakan jika perlu. | | |
| **2.2.17** | **Sokongan Teknikal / Technical Support** | | |
| i | Petender mesti menyediakan sokongan teknikal untuk sebarang pertanyaan dan masalah yang dihadapi oleh UMPSA semasa dalam Tempoh Jaminan. | | |
| ii | Petender mesti menyediakan dokumen yang memperincikan cadangan Service Level Agreement (SLA) bersama dengan tatacara Pengurusan Aduan. | | |
| iii | SLA sokongan teknikal tidak terhad seperti berikut:<br>&nbsp;&nbsp;&nbsp;&nbsp;a. Kadar response time dalam tempoh 4 jam melalui telefon dan email<br>&nbsp;&nbsp;&nbsp;&nbsp;b. Masa penyelesaian masalah dalam tempoh tiga (3) hari<br>&nbsp;&nbsp;&nbsp;&nbsp;c. Lawatan On-site tanpa had bagi Severity 1 (Mengikut keperluan) | | |
| **2.2.18** | **Penukaran Modul Yang Setara / Module Replacement** | | |
| | Bagi mana-mana modul sistem yang dipersetujui dalam sebutharga ini yang sepatutnya dibangunkan oleh pentender tetapi telah dibangunkan secara dalaman oleh pihak teknikal UMPSA, maka UMPSA berhak membuat sebarang penukaran dengan mana-mana modul/sistem yang setara. | | |

---

## SEKSYEN 3.0: KEUPAYAAN TEKNIKAL SYARIKAT / TECHNICAL COMPANY CAPABILITIES

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **3.1** | **PENGALAMAN SYARIKAT / COMPANY EXPERIENCE** | | |
| **3.1.1** | **Pengalaman Syarikat dalam Laravel framework** | | |
| i | (a) Berapa tahun syarikat/petender telah terlibat dalam membangunkan sistem aplikasi berasaskan Laravel framework? | | |
| | (b) Berapa jumlah projek pembangunan sistem aplikasi berasaskan Laravel framework yang telah dianugerahkan oleh pelanggan atau pihak lain kepada petender dalam tempoh lima (5) tahun lalu? | | |
| | (c) Berapa jumlah kakitangan petender yang mahir dalam pembangunan aplikasi berasaskan Laravel framework? | | |
| **3.2** | **STRUKTUR ORGANISASI PROJEK DAN PENGALAMAN AHLI / PROJECT ORGANIZATION STRUCTURE AND TEAM EXPERIENCE** | | |
| **3.2.1** | **Struktur Organisasi Projek / Project Organization Structure** | | |
| i | Sila isikan template LAMPIRAN A-01 dengan nama kakitangan/anggota pasukan petender yang akan melaksanakan projek di bawah tender ini nanti. | | |
| **3.2.2** | **Pengalaman Ahli Pasukan / Team Member Experience** | | |
| i | Sila isi maklumat pengalaman SETIAP kakitangan/ahli pasukan petender (yang dinyatakan di item 3.2.1) menggunakan template di LAMPIRAN A-02. | | |

---

## SEKSYEN 4.0: PENGHANTARAN DAN MASA / DELIVERY AND TIMELINE

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **4.1** | **TECHNICAL DELIVERABLES** | | |
| 4.1.1 | Sistem aplikasi Portal Staf | | |
| 4.1.2 | Mesyuarat Kick-off projek/pelaksanaan tender | | |
| 4.1.3 | Akaun dan credential Laravel Shift | | |
| 4.1.4 | Pelan Pelaksanaan | | |
| 4.1.5 | Cadangan Rekabentuk UI/UX | | |
| 4.1.6 | Senarai latihan dan jadual latihan | | |
| 4.1.7 | Dokumen-dokumen kajian dan pematuhan keperluan seperti BRS, SRS dan SDS | | |
| 4.1.8 | Senarai dokumen berkaitan pengujian sistem aplikasi seperti 'test scripts', 'test case', UAT, PenTest, FAT dan seumpamanya | | |
| 4.1.9 | Senarai dokumentasi dan manual pengguna | | |
| 4.1.10 | Dokumen/surat jaminan pematuhan terhadap 'Coding Standard & Convention' oleh petender beserta perincian contoh pelaksanaan | | |
| 4.1.11 | Surat dan dokumen-dokumen pentauliahan | | |
| 4.1.12 | Surat dan dokumen sahjamin serta seumpamanya | | |
| 4.1.13 | Satu (1) unit komputer desktop ditempatkan di premis UMPSA | | |
| 4.1.14 | Lain-lain yang jika ada dinyatakan dalam dokumen tender ini atau diputuskan dalam bengkel pelaksanaan tender dengan persetujuan bersama | | |
| **4.2** | **TEMPOH SIAP / COMPLETION PERIOD** | | |
| 4.2.1 | Semua kerja-kerja yang terlibat mestilah dilaksanakan mengikut tempoh yang ditetapkan iaitu maksimum lapan bulan (8) bulan. | | |
| 4.2.2 | Petender perlu menghantar pelan dan jadual pelaksanaan keseluruhan projek (menggunakan Gantt Chart) yang merangkumi kerja-kerja:<br>&nbsp;&nbsp;&nbsp;&nbsp;i. Pelaksanaan projek<br>&nbsp;&nbsp;&nbsp;&nbsp;ii. Pelaksanaan latihan<br>&nbsp;&nbsp;&nbsp;&nbsp;iii. Serahan dokumentasi projek<br>&nbsp;&nbsp;&nbsp;&nbsp;iv. Lain-lain perkara yang tidak dinyatakan di atas (yang berkaitan) | | |
| 4.2.3 | Penetapan tarikh, masa, perlanjutan masa, penamatan tempoh atau seumpamanya berkaitan pelaksanaan projek dalam jadual penentuan teknikal ini mestilah berdasarkan surat rasmi atau dokumen rasmi yang dikeluarkan oleh Jabatan Bendahari UMPSA. Permohonan yang berkaitan perkara ini perlu dikemukakan oleh petender kepada Jabatan Bendahari UMPSA. | | |
| **4.3** | **DENDA / PENALTY** | | |
| 4.3.1 | UMPSA berhak mendenda petender jika berlaku kelewatan dalam penghantaran mana-mana item di dalam projek/tender ini. | | |
| 4.3.2 | Nilaian denda adalah tertakluk kepada pihak UMPSA. | | |
| **4.4** | **TEMPOH JAMINAN / WARRANTY PERIOD** | | |
| 4.4.1 | Perkara ini perlu dibaca bersama item 1.3 dan meliputi segala aspek 'warranty', 'maintenance' dan 'support'. | | |
| 4.4.2 | Tempoh jaminan bagi kerja-kerja, pemasangan dan konfigurasi, integrasi, pengujian, pelaksanaan dan pentauliahan adalah satu (1) tahun bermula setelah penerimaan akhir (Final Acceptance Test FAT) telah dilakukan dengan jayanya. | | |
| 4.4.3 | Petender perlu menyediakan platform yang terurus secara atas talian bagi tujuan pengurusan aduan dan isu-isu sepanjang tempoh jaminan. | | |

---

## RUJUKAN DOKUMEN / DOCUMENT REFERENCES

| Rujukan | Perihal |
|---------|---------|
| Dokumen Asal | DOKUMEN UMPSA BEND SH 2026 (3) - Jilid 1 |
| No. JTICT | JTICT/2025 (30) |
| Jabatan | DiTec (Pusat Teknologi Digital) |
| Muka Surat Spesifikasi | Muka Surat 1 - 60 (FORM/BEND/UP/007) |
| Seksyen 2.0 | Muka Surat 13 - 55 |
| Seksyen 3.0 | Muka Surat 46 - 50 |
| Seksyen 4.0 | Muka Surat 51 - 55 |

---

**Nota:**
- Ruangan "Maklumbalas / Spesifikasi Syarikat" hendaklah diisi oleh pembida
- Ruangan "Bukti / Rujukan" hendaklah merujuk kepada dokumen sokongan yang disertakan
- Semua dokumen sokongan mestilah tanpa nama syarikat (untuk Bahagian C)

---

*Disediakan berdasarkan Dokumen Sebut Harga UMPSA/BEND/SH/2026(3)*  
*Sistem Portal Staf (eCommunity) / Staff Portal System*
