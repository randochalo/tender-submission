# JADUAL PENENTUAN TEKNIKAL / TECHNICAL COMPLIANCE SCHEDULE

## TSH-2613: SISTEM PENGURUSAN MESYUARAT / MEETING MANAGEMENT SYSTEM

---

**No. Sebut Harga / Quotation No:** UMPSA/BEND/SH/2026(2)  
**Tajuk / Title:** Membekal, Membangun, Menghantar, Memasang, Mengintegrasi, Menguji Dan Mentauliah Sistem Pengurusan Mesyuarat Di Universiti Malaysia Pahang Al-Sultan Abdullah  
**Tarikh Buka / Opening Date:** 12 Februari 2026  
**Tarikh Tutup / Closing Date:** 26 Februari 2026  
**Pegawai Bertanggungjawab:** En. Hanizam bin Abdul Kassim (09-431 5232 / hanizam@umpsa.edu.my)

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
| A | Membangunkan semua modul/menu di Perkara 2.1.2. Dokumen kajian keperluan (URS) akan dimuktamadkan dalam bengkel sebagai dokumen akhir rujukan pembangunan. | | |
| B | **MESTI** menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API. Termasuk penggunaan Eloquent ORM. | | |
| C | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| D | Integrasi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa.<br><br>i) Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim<br>ii) Integrasi dengan keputusan E Voting sedia ada. | | |
| E | Membangunkan antara muka pengguna dalam bentuk responsive web design menggunakan Bootstrap, Tailwind, atau teknologi setara, serta menambah ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| F | Menggunakan pangkalan data Oracle yang sedia ada di UMPSA. | | |
| G | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| H | Menggunakan container technology sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| I | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery yang terdapat di UMPSA. | | |
| J | Menyediakan persekitaran pembangunan sistem sendiri bagi tujuan pelaksanaan projek ini. | | |
| K | Konfigurasi hendaklah mematuhi piawaian keselamatan, keperluan ISMS, dan amalan DevOps terbaik. | | |
| L | Mempunyai fungsi memuat naik dokumen dan berupaya menjana laporan. | | |
| M | Menggunakan Power BI dengan memanfaatkan lesen institusi sedia ada, bagi tujuan pembangunan dashboard tanpa melibatkan sebarang kos pelesenan tambahan kepada pihak UMPSA. | | |
| N | Melaksanakan proses migrasi data daripada sistem sedia ada ke sistem baharu bagi memastikan kesinambungan operasi tanpa gangguan. | | |
| O | Melaksanakan integrasi dengan sistem dalaman berikut:<br>i. MyUMPSA-ID Single Sign-On (SSO)<br>ii. Redis<br>iii. Email gateway<br>iv. File storage<br>v. API<br>vi. Notification<br>vii. Modul Executive Approval | | |
| P | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| Q | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| R | Menyediakan latihan:<br>i. Latihan kepada pentadbir sistem (IT)<br>ii. Latihan kepada pengguna akhir (end-users) | | |
| S | Membangun, menguji dan mentauliah sistem yang dibangunkan. | | |
| T | Menyerahkan kod sumber penuh (full source code) sistem beserta dokumentasi berkaitan bagi tujuan pemilikan penuh oleh pihak UMPSA. | | |
| U | Menyediakan dan mengkonfigurasi persekitaran pelayan bagi staging, development, disaster recovery (DR), dan production, mengikut spesifikasi yang ditetapkan. | | |
| V | Melaksanakan proses migrasi dan pelaksanaan penuh sistem baharu sehingga siap sedia untuk operasi secara langsung (go-live), termasuk pengesahan akhir bersama pihak UMPSA. | | |

---

### 2.1.2 KEPERLUAN FUNGSIAN MODUL/MENU / FUNCTIONAL MODULE REQUIREMENTS

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **2.1.2.1** | **MODUL LOGIN / LOGIN MODULE** | | |
| | Modul ini mengesahkan identiti pengguna melalui SSO server (Keycloak). Pengguna boleh juga log masuk aplikasi melalui pengesahan Google. | | |
| **2.1.2.2** | **MODUL E-AUTHORIZATION / E-AUTHORIZATION MODULE** | | |
| | Modul ini bertujuan bagi memberi akses kepada keseluruhan sistem mesyuarat. | | |
| i | Set-up/ Review & Approval:<br>a. Memberikan akses kepada pengguna dan pentadbir secara berperingkat (tiering).<br>b. Sistem mempunyai keupayaan untuk audit trail.<br>c. Integrasi dengan Executive approval / notifikasi / tindakan di dalam ecomm UMPSA bagi semua modul sistem ini yang memerlukan tindakan ahli / staff UMPSA berkaitan mesyuarat.<br>d. Menu kebenaran berkaitan pemantauan, kelulusan mesyuarat dan penyelenggaraan mesyuarat di bawahnya. | | |
| **2.1.2.3** | **MODUL MEETING REGISTRATION / MEETING REGISTRATION MODULE** | | |
| i | Set up tier of meeting:<br>Modul ini bertujuan bagi penetapan pengurusan semua mesyuarat-mesyuarat di dalam universiti. | | |
| ii | Meeting Set-Up: Lazim / Khas & Edaran:<br>a. Permohonan pendaftaran mesyuarat<br>b. Kelulusan pendaftaran<br>c. Penetapan peringkat mesyuarat (peringkat 1, 2,.. n)<br>d. Pendaftaran sesi mesyuarat<br>e. Memberikan akses kepada pengguna dan pentadbir | | |
| iii | Panggilan Mesyuarat (Lazim/Khas):<br>Modul ini bertujuan bagi pemakluman kepada ahli mesyuarat dan majlis/jk berkenaan cadangan tarikh, tempat dan maklumat lain berkenaan mesyuarat yang akan diadakan melalui e-mel. | | |
| iv | Mesyuarat Secara Edaran:<br>Memudahkan proses mesyuarat tanpa kehadiran secara fizikal, membolehkan dokumen diedarkan kepada ahli, dan membolehkan ahli memberi maklum balas, komen atau keputusan dalam tempoh masa ditetapkan secara dalam talian.<br>a. Pemakluman Mesyuarat Secara Edaran dan dapatkan keputusan ahli.<br>b. Paparan pada modul executive approval sedia ada bagi tindakan ahli Senat / Mesyuarat.<br>c. Peringatan tempoh maklumbalas dan tindakan mengikut ketetapan tadbir urus mesyuarat. | | |
| v | Meeting Notice:<br>Pengeluaran notis panggilan mesyuarat berdasarkan tempoh yang telah ditetapkan mengikut tadbir urus mesyuarat. | | |
| **2.1.2.4** | **MODUL E-TAKWIM / E-TAKWIM MODULE** | | |
| | Kekal menggunakan sistem sedia ada, walau bagaimanapun perlu ada integrasi sistem sedia ada dan sistem baru yang akan dibangunkan. Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim.<br><br>i. Taqwim Set up:<br>a. Sumber data dari etakwim ecomm/ appointment dalam ecomm (sistem sedia ada)<br>b. Paparan di dalam dashboard Menu mesyuarat | | |
| **2.1.2.5** | **MODUL E-COMMITTEE / E-COMMITTEE MODULE** | | |
| | Menguruskan maklumat keahlian mesyuarat secara berpusat, termasuk daftar, kemas kini, penamatan, rekod sejarah pelantikan dan penjanaan laporan berkaitan. | | |
| i | Appointment (Perlantikan):<br>a. Mendaftarkan keahlian mesyuarat mengikut tempoh pelantikan<br>b. Integrasi data staf bagi tujuan mendaftarkan keahlian mengikut tempoh pelantikan<br>c. Perkara yang diperlukan: Nama, Jawatan Hakiki & Jawatan Giliran, ID Staf, Fakulti, Kelulusan Akademik, Tempoh Jawatan dan lain-lain<br>d. Membantu sekretariat dalam memantau tempoh pelantikan dan penamatan dengan sistem alert<br>e. Statistik kehadiran / tidak hadir ahli mesyuarat bulanan / tahunan<br>f. Janaan nama ahli bagi pembangunan minit mesyuarat berdasarkan format minit mesyuarat<br>g. Integrasi data sistem HoD UMPSA bagi Paparan rujukan didalam Ecomm Sistem HoD<br>h. Paparan tempoh lantikan<br>i. Menu yang diperlukan, menyimpan rekod keahlian mesyuarat untuk rujukan masa hadapan (audit pematuhan tadbir urus Senat)<br>j. Boleh menjana dan menghantar surat kepada semua ahli mesyuarat (pelantikan, penamatan, penghargaan) secara E-Letter digital | | |
| ii | Committee Set-Up:<br>a. Modul ini menetapkan keahlian sesuatu mesyuarat berdasarkan ToR Mesyuarat tersebut<br>b. Antara ciri-ciri perlu ada: nama, jawatan, id no, tempoh pelantikan dalam jawatankuasa, jawatan gilliran pentadbiran yang disandang dan lain-lain<br>c. Integrasi data dengan modul minit mesyuarat dan sistem sediada (HoD Ecomm) | | |
| iii | Attendance:<br>a. Pengiraan cukup kuorum keahlian mesyuarat bagi 1/3 ahli untuk mengadakan mesyuarat<br>b. Maklumbalas kehadiran mesyuarat melalui sistem oleh Ahli; hadir/tidak hadir berserta sebab ketidakhadiran<br>c. Janaan laporan kehadiran mesyuarat mengikut jawatan hieraki tertinggi berdasarkan tadbir urus | | |
| **2.1.2.6** | **MODUL E-PAPER MEETING / E-PAPER MEETING MODULE** | | |
| | Menyediakan satu platform berpusat untuk menghantar, mendaftar, menyimpan, mencari, menapis, dan menjejak sejarah kertas kerja yang dibentangkan atau dikemukakan. | | |
| i | Call for Paper:<br>a. Mudah diakses melalui fungsi carian<br>b. Sesi saringan kertas kerja bagi menentukan dibawa masuk ke mesyuarat semasa atau akan datang atau kemaskini status KIV / digugurkan dan sebagainya<br>c. Carian melalui authorize yang dibuka kepada pemohon dan fakulti/pusat yang dibenarkan<br>d. Arkib dokumen | | |
| ii | Paper submission:<br>a. Pemohon / PTJ / Sekretariat menghantar kertas kerja dengan memuatnaik dalam pelbagai bentuk (documents, imej, pdf, video)<br>b. Sistem hendaklah membolehkan kertas kerja daripada Majlis atau Jawatankuasa lain dibawa ke peringkat kelulusan melalui proses mesyuarat yang diintegrasikan (Perakuan, Kelulusan, Pemakluman)<br>c. Kertas kerja dari pelbagai peringkat (tier mesyuarat): Mesyuarat Unit/Jabatan/Pusat, Jawatankuasa, Majlis, Senat JKPU/LPU, dan lain-lain<br>d. Integrasi Mesyuarat Utama/Induk dan Majlis/Jawatankuasa dibawahnya:<br>&nbsp;&nbsp;&nbsp;&nbsp;(i) Sistem hendaklah membolehkan kertas kerja daripada Majlis atau Jawatankuasa lain dibawa ke peringkat atasan untuk dibentangkan melalui proses yang diintegrasikan<br>&nbsp;&nbsp;&nbsp;&nbsp;(ii) Penyelenggaraan jejak audit (audit trail) bagi setiap pergerakan dan pindaan dokumen<br>&nbsp;&nbsp;&nbsp;&nbsp;(iii) Penyelarasan tarikh, agenda, dan item mesyuarat mengikut peringkat proses kelulusan yang ditetapkan | | |
| iii | Meeting Agenda Notice:<br>Proses penyampaian maklumat berkaitan perkara-perkara yang akan dibincangkan dalam sesuatu mesyuarat kepada semua ahli yang terlibat.<br>a. Pengeluaran notis agenda mesyuarat yang telah dimuktamadkan selepas Mesyuarat Pra berdasarkan tempoh yang telah ditetapkan berdasarkan tadbir urus mesyuarat<br>b. Penghantaran kertas kerja melalui platform sistem oleh pemohon / sekretariat majlis / Jawatankuasa<br>c. Sistem hendaklah menghantar notifikasi bagi setiap perubahan status kertas kerja (KIV, digugurkan, ditangguh, diluluskan dan status lain) | | |
| **2.1.2.7** | **MODUL E-DECISION MEETING / E-DECISION MEETING MODULE** | | |
| i | Modul ini melibatkan sekretariat, ahli mesyuarat dan staf yang perlu mengambil tindakan dari keputusan mesyuarat.<br>a. Semua keputusan direkod dalam minit mesyuarat sebagai rujukan rasmi. Digunakan untuk memantau tindakan susulan dan tanggungjawab ahli. Boleh dirujuk semula untuk audit, laporan, atau penyelesaian pertikaian.<br>b. Bagi menu keputusan mesyuarat yang akan dikeluarkan oleh secretariat kepada pemohon kertas kerja atau PIC yang perlu mengambil Tindakan atas keputusan tersebut, ianya adalah bersifat edaran sahaja. Jika berlaku sebarang pindaan, pihak secretariat mempunyai akses bagi meminda di menu keputusan dan akan menghantar semula keputusan yang dipinda. | | |
| ii | Distribute (Edaran):<br>a. Penyediaan keputusan 3 hari berkerja selepas mesyuarat diadakan bagi ahli mesyuarat mengambil tindakan dengan efektif<br>b. Edaran kepada pic / ptj yang perlu menjalankan tugasan/tindakan tersebut<br>c. Format & template berdasarkan format minit yang ditetapkan<br>d. Paparan terus kepada Dekan / HOD pemohon<br>e. Format & template berdasarkan format yang akan ditetapkan | | |
| **2.1.2.8** | **MODUL E-MINUTES / E-MINUTES MODULE** | | |
| | Minit mesyuarat adalah dokumen catatan yang direkodkan hasil mesyuarat yang telah diadakan. Modul ini mengurus dan merekod keputusan mesyuarat secara tersusun, dengan keupayaan untuk menjejak status pelaksanaan tindakan, menghasilkan laporan, dan memudahkan capaian oleh pihak berkepentingan. | | |
| i | Draft Minutes:<br>a. Merekod / mencatat minit secara terus ke dalam sistem dan paparan dapat dilihat seperti format minit mesyuarat (word document) dengan diintegrasikan input bagi perkara no 6 iaitu keputusan mesyuarat<br>b. Catatan minit mesyuarat penuh adalah proses penggabungan dari modul keputusan dan minit mesyuarat: format catatan minit mesyuarat yang akan ditetapkan<br>c. Catatan Mesyuarat mengambil maklum (input perbincangan, isi kandungan kertas kerja, tajuk, no perkara dalam minit dan pic/ptj tindakan | | |
| ii | Review by Comm:<br>a. Proses semakan draf minit mesyuarat selama 3 hari<br>b. Menu Tindakan dapat dihantar kepada pegawai bertanggungjawab untuk tindakan seterusnya (Dekan/Pengarah/etc) | | |
| iii | Amendments:<br>Proses pindaan draf minit mesyuarat | | |
| iv | Distribute:<br>a. Edaran kepada ahli selepas semakan adalah 14 hari bekerja selepas mesyuarat | | |
| **2.1.2.9** | **MODUL E-PROGRESS MINUTES / E-PROGRESS MINUTES MODULE** | | |
| | Menghantar, Memantau, mengumpul, meminda dan menyelaras maklum balas serta pelaksanaan tindakan daripada lebih dari 1 pihak bertanggungjawab terhadap melakukan tindakan kepada sesuatu keputusan, minit atau arahan mesyuarat. | | |
| a | Paparan edaran maklum balas mesyuarat | | |
| b | Mengedarkan permohonan maklumbalas mesyuarat kepada pic /ptj | | |
| c | PIC/PTJ memberikan maklumbalas kepada laporan tersebut. Maklum balas boleh dibuat melebihi satu orang dan tidak terhad kepada ahli mesyuarat. | | |
| d | Sistem mempunyai fungsi muatnaik dokumen sebagai lampiran kepada maklum balas | | |
| e | Sistem hendaklah membolehkan pemohon memberikan maklum balas secara langsung melalui pautan atau arahan yang diterima dalam alert/notification yang dihantar oleh sistem | | |
| f | Sekretariat mesyuarat akan menyelaras penulisan maklumbalas bagi dokumen rasmi minit mesyuarat | | |
| g | Sekretariat mengumpul jawapan maklum balas yang diterima dan disatukan serta dimurnikan bagi menjadikan dokumen minit yang rasmi bagi mesyuarat yang seterusnya / hadapan | | |
| h | Sistem hendaklah membolehkan maklum balas daripada pihak berkaitan diintegrasikan secara automatik ke dalam minit mesyuarat bagi Perkara Berbangkit | | |
| i | Sistem hendaklah menyediakan fungsi penjejakan (tracking) bagi setiap tindakan susulan yang timbul daripada setiap kertas kerja yang dibentangkan dalam mesyuarat | | |
| j | Laporan penuh bagi perkara berbangkit boleh dijana mengikut format yang ditetapkan | | |
| i | Call For Progress:<br>a. Paparan edaran maklum balas mesyuarat<br>b. Mengedarkan permohonan maklumbalas mesyuarat kepada pic / ptj<br>c. Paparan terus integrasi maklum balas di dalam minit mesyuarat di perkara berbangkit<br>d. Penjejakan tindakan susulan bagi setiap kertas kerja daripada setiap mesyuarat yang dibentangkan | | |
| ii | Progress submission:<br>a. PIC/PTJ memberikan maklumbalas kepada laporan tersebut secara web based<br>b. Pemohon terus memberikan maklum balas melalui alert/notification | | |
| iii | Amendments:<br>a. Sekretariat mesyuarat menyelaras penulisan maklumbalas bagi dokumen rasmi minit mesyuarat<br>b. Sekretariat mengumpul jawapan maklum balas yang diterima dan disatukan serta dimurnikan bagi menjadikan dokumen minit yang rasmi bagi mesyuarat yang seterusnya / hadapan<br>c. Laporan-laporan penuh mengikut format yang akan diberikan | | |
| **2.1.2.10** | **MODUL E-CABUTAN / E-CABUTAN MODULE** | | |
| | Modul ini membolehkan pengguna memohon, mengakses, mencari, dan menjana cabutan minit mesyuarat berdasarkan kategori, tarikh, kata kunci, dan jenis keputusan bagi tujuan pelaksanaan atau dokumen rujukan rasmi. | | |
| i | Application:<br>a. Pemohon mengisi permohonan di dalam sistem<br>b. Sekretariat menyemak dan meluluskan permohonan<br>c. Pemohon boleh melihat cabutan minit melalui paparan sistem dan janaan PDF<br>d. Carian cabutan minit mesyuarat adalah berdasarkan minit mesyuarat dan rekod daftar kertas kerja senat lepas. | | |
| ii | Distribute:<br>Pemohon boleh melihat cabutan minit melalui paparan sistem dan janaan PDF | | |

---

### 2.2 PEMATUHAN & PERKHIDMATAN PROFESIONAL / COMPLIANCE & PROFESSIONAL SERVICES

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **2.2.1** | **Sesi Taklimat Secara 'Online' / Online Briefing Session** | | |
| | UMPSA berhak untuk memanggil petender untuk sesi taklimat secara 'online' (Google Meet, MS Teams atau seumpamanya) sekiranya perlu. Tarikh dan masa (hari bekerja) yang ditetapkan oleh UMPSA mestilah dipatuhi oleh petender. UMPSA berhak tidak menilai tawaran petender jika petender gagal hadir (online) dalam sesi tersebut. | | |
| **2.2.2** | **Bengkel Kajian Keperluan Projek / Project Requirements Workshop** | | |
| | Petender yang berjaya/dipilih hendaklah melaksanakan bengkel bagi membangunkan pelan pelaksanaan projek ini termasuklah meneliti keperluan sistem, proses yang terlibat serta keperluan persekitaran sistem. Bengkel ini melibatkan pemilik proses, staf teknikal dan petender yang dilantik. | | |
| i | Bengkel:<br>a. Tujuan bengkel diadakan untuk mengenalpasti spesifikasi secara terperinci berkenaan sistem/modul yang terlibat. Kekerapan bengkel adalah mengikut keperluan sehingga draf dokumen selesai.<br>b. Dokumen kajian keperluan (user requirement specification) yang akan dimuktamadkan merupakan dokumen akhir yang akan dijadikan rujukan di dalam pembangunan sistem.<br>c. Bengkel perlu dilakukan secara on-site (dalam UMPSA).<br>d. Kos pelaksanaan bengkel akan ditanggung oleh petender sepanjang projek berjalan. | | |
| **2.2.3** | **Penyediaan Pelan Pelaksanaan / Implementation Plan Preparation** | | |
| i | Satu pelan pelaksanaan bertulis yang muktamad perlu dihasilkan oleh petender yang berjaya/dipilih selepas bengkel | | |
| ii | Pelan ini perlu turut meliputi aspek organisasi projek, penjadualan pelaksanaan aktiviti projek, 'work breakdown structure (WBS)', 'critical path method (CPM)' diagram, jadual PERT serta metodologi pembangunan | | |
| iii | Dokumen pelan pelaksanaan perlu dihantar kepada pihak UMPSA dalam tempoh dua (2) minggu dari tarikh selesai bengkel | | |
| iv | UMPSA berhak menolak atau mengarah pemindaan pelan pelaksanaan oleh petender yang didapati tidak bertepatan dengan objektif tender ini atau mempunyai kesilapan | | |
| **2.2.4** | **Penyediaan Cadangan Rekabentuk UI/UX / UI/UX Design Proposal** | | |
| i | Petender yang berjaya/dipilih perlu mencadangkan konsep rekabentuk antaramuka pengguna (user interface UI) yang terkini dan moden | | |
| ii | Fungsi aplikasi dalam pembangunan modul mestilah bersesuaian dengan kehendak pengguna atau pengalaman pengguna (user experience - UX) supaya setiap modul berfungsi dengan baik dan mesra pengguna | | |
| **2.2.5** | **Penerapan Standard / Standards Implementation** | | |
| i | Pelaksanaan kerja-kerja pembangunan aplikasi dan sistem mestilah mengikut standard terbaik industri dan memenuhi persekitaran UMPSA | | |
| ii | Petender perlu menerapkan UMPSA Standard Coding Convention dalam pengaturcaraan semua modul sistem aplikasi yang dipersetujui dalam tender ini | | |
| iii | Sebarang pewujudan 'table' baru atau 'column' baru untuk menyimpan data rekod yang ingin diwujudkan dalam pangkalan data UMPSA perlulah menggunakan 'naming standard' yang betul serta mendapat kelulusan secara bertulis oleh Pentadbir Pangkalan Data UMPSA. Penggunaan 'sequence number' sebagai ID rujukan dalam 'table' perlulah diminimakan. | | |
| iv | Sebarang 'table' baharu yang ingin diwujudkan dalam pangkalan data UMPSA perlulah telah siap dinormalisasikan (normalization) | | |
| v | Petender perlu memastikan perisian atau sistem aplikasi yang dibangunkan atau dibekalkan mematuhi standard terbuka (open standard) semasa dan garis panduan Kerajaan Malaysia seperti KRISA, EGIT, DDSA, MyMIS, MyGIF, MyGIFOSS dan Garis Panduan IT Outsourcing Agensi-Agensi Sektor Awam | | |
| **2.2.6** | **Pengurusan Kod Sumber / Source Code Management** | | |
| i | Semua kod sumber (source code) dan hak cipta sistem aplikasi yang dibangunkan untuk setiap sistem aplikasi melalui tender ini adalah menjadi HAKMILIK UMPSA sepenuhnya | | |
| ii | Petender TIDAK dibenarkan membuat edaran, salinan atau salin cetak kepada pihak lain tanpa kebenaran rasmi secara bertulis dari pihak UMPSA | | |
| iii | Petender wajib meletakkan/menghoskan kod sumber terkini di repository GitLab UMPSA | | |
| iv | 'Deployment' sebarang sistem aplikasi atau modul dalam tender ini ke server-server aplikasi UMPSA mestilah hanya melalui GitLab UMPSA | | |
| v | Petender wajib memastikan kod sumber yang dibangunkan atau dibekalkan adalah selamat, berfungsi dan bebas ralat | | |
| vi | Pengurusan repositori GitLab UMPSA adalah di bawah kuasa UMPSA | | |
| vii | UMPSA berhak melantik wakil penyemak dan penguji kod sumber dalam repositori yang berkaitan bagi tujuan pengujian, kawalan kualiti serta kesinambungan pengetahuan | | |
| viii | Apa-apa isu yang timbul berhubung penggunaan atau pengoperasian GitLab UMPSA hendaklah dirujuk kepada Pengurus GitLab UMPSA atau Pengurus Projek tender ini | | |
| ix | Selepas tempoh jaminan tamat petender perlu menghapuskan segala data, maklumat dan kod sumber (source code) projek/tender ini yang berada di dalam simpanan petender atau sekutu | | |
| **2.2.7** | **Pemasangan, Konfigurasi dan Integrasi / Installation, Configuration and Integration** | | |
| i | Server (Linux) untuk hos API dan sistem aplikasi sebenar akan dibekalkan oleh UMPSA. Petender bertanggungjawab memasang dan menyediakan 'system environment' yang diperlukan | | |
| ii | Petender perlu mempunyai 'development environment' server sendiri untuk tujuan pembangunan aplikasi | | |
| iii | Petender perlu menyempurnakan kerja-kerja pemasangan dan konfigurasi API di server UMPSA sekiranya ada | | |
| iv | Kos pemasangan untuk semua perisian atau 'package' perisian adalah di bawah tanggungjawab pihak petender | | |
| v | Petender perlu patuh dan mengikuti semua peraturan dan prosedur yang ditetapkan oleh UMPSA | | |
| vi | Petender mesti menyempurnakan proses integrasi melibatkan pemasangan dan konfigurasi API bagi setiap modul berkaitan tender ini di server UMPSA sekiranya ada | | |
| vii | Sebarang kerja, pemasangan, konfigurasi dan integrasi sistem aplikasi yang tidak dinyatakan di dalam dokumen tender ini, tetapi perlu ada bagi melengkapkan proses keseluruhan sistem di dalam projek ini dan dianggap perlu oleh pihak UMPSA, pihak petender mesti menyelesaikan skop tersebut tanpa sebarang kos tambahan | | |
| viii | Kerja-kerja integrasi komponen baharu mestilah serasi dan boleh berkomunikasi dengan komponen sedia ada tanpa menjejaskan fungsi yang sedang digunakan di UMPSA | | |
| **2.2.8** | **Lesen Perisian / Software License** | | |
| | Sebarang perisian yang dibekalkan, dipasang atau digunakan mestilah sah, asli serta mendapat kebenaran (licensed) untuk digunakan di UMPSA daripada penerbitnya. | | |
| **2.2.9** | **Versi Perisian / Software Version** | | |
| | Bagi keadaan di mana versi perisian yang disyaratkan dalam perolehan perkhidmatan ini telah dikira sebagai 'outdated' atau menjadi 'not supported', maka versi yang lebih baru, stabil dan bersesuaian dengan keperluan UMPSA perlu dibekalkan dengan mendapat persetujuan bertulis daripada UMPSA. Penukaran versi adalah tanpa sebarang kos tambahan. | | |
| **2.2.10** | **Kerja Panggil Balik / Call Back Work** | | |
| | Petender dikehendaki menyediakan perkhidmatan "panggil balik" bagi skop "Corrective Maintenance" tanpa sebarang bayaran tambahan bagi perkhidmatan/kerja yang kurang memuaskan dalam tempoh jaminan/waranti. | | |
| **2.2.11** | **Pengujian / Testing** | | |
| i | Petender dikehendaki menjalankan dan melepasi ujian-ujian berikut:<br>a. Ujian Penerimaan Pengguna (User Acceptance Test, UAT) di UMPSA sekurang-kurangnya dua (2) kali<br>b. Semakan 'compliance of server setup' bagi mana-mana server yang dipasang atau dikonfigurasi oleh petender<br>c. Ujian Penembusan Keselamatan (Security Penetration Test) UMPSA<br>d. Ujian Penerimaan Akhir (Final Acceptance Test, FAT) | | |
| ii | Petender dikehendaki menyediakan skrip pengujian (test script) bagi tujuan pelaksanaan pengujian UAT setiap modul sistem aplikasi. Skrip perlu dalam Bahasa Melayu. | | |
| iii | User Acceptance Test (UAT) mesti dilakukan sekurang-kurangnya dua (2) kali. Lokasi UAT ialah di UMPSA dan pasukan pembangunan petender mesti hadir. | | |
| iv | Final Acceptance Test (FAT) mestilah dijalankan di production server dengan jayanya. Jika gagal, petender mesti bersedia untuk menjalankan pengujian semula. | | |
| v | Petender bertanggungjawab untuk membangun, mengimplementasi dan menguruskan semua prosedur semasa melaksanakan UAT dan FAT. | | |
| vi | Semua dokumen peringkat pengujian mestilah dipersetujui, disahkan dan ditandatangani oleh pihak UMPSA. | | |
| **2.2.12** | **Pelaksanaan dan Pentauliahan / Implementation and Certification** | | |
| i | Petender mesti memastikan semua sistem aplikasi yang telah dibangunkan dan diintegrasi dapat berfungsi dengan baik sebelum proses pemasangan (deployment) dijalankan. Ia merangkumi:<br>a. Bebas ralat<br>b. Keselamatan sistem dan data<br>c. Pelan sokongan sekiranya berlaku kegagalan semasa instalasi di server UMPSA. | | |
| ii | Petender mesti bertanggungjawab memastikan sistem yang ditauliahkan terjamin dari segi prestasi dan keselamatannya dalam tempoh jaminan. | | |
| iii | Petender mesti memastikan sistem yang dibangunkan mempunyai tahap 'interoperability' dan 'scalability' yang baik bagi menyokong perkembangan penggunaannya pada masa hadapan. | | |
| **2.2.13** | **Latihan / Training** | | |
| i | Tatacara penggunaan sistem bagi setiap modul dalam sistem yang diintegrasikan (berkonsep train-the-trainer) secara dalaman. | | |
| ii | Petender perlu melakukan pemindahan kepakaran (Transfer of Technology) kepada pasukan teknikal UMPSA bagi setiap modul. Ia akan melibatkan:<br>a. Aliran Sistem (System Flow)<br>b. Data Flow Diagram (DFD) dan Entiti Relationship Diagram (ERD)<br>c. Teknologi dan tools yang digunakan<br>d. Sumber rujukan<br>e. Nota lengkap | | |
| iii | Petender perlu menjadual, menganjur dan melaksanakan aktiviti latihan yang berkaitan dengan pembangunan aplikasi dan sistem secara 'on-site' bagi tujuan penyelenggaraan aplikasi dan sistem yang dibangunkan atau dibekalkan melalui sebutharga ini. Staf yang terlibat akan dinamakan oleh pihak UMPSA. | | |
| | Latihan ini meliputi penyelenggaraan berikut:<br>a. Latihan penyelenggaraan sistem dan pelayan (server)<br>b. Latihan pembangunan dan penyelenggaraan API (Laravel) | | |
| **2.2.14** | **Dokumentasi / Documentation** | | |
| i | Manual dan dokumentasi hendaklah disediakan dalam bentuk hard-copy dan soft-copy. Manual dan dokumentasi perlulah dalam Bahasa Melayu. Istilah-istilah teknikal dalam Bahasa Inggeris boleh digunakan mengikut keperluan. | | |
| ii | Semua dokumen teknikal perlu mendapat kelulusan pihak teknikal UMPSA sebelum segala kerja-kerja pembangunan sistem bermula. | | |
| iii | Petender yang berjaya mesti menyerahkan semua dokumentasi berikut kepada UMPSA:<br>a. Pelan pelaksanaan projek<br>b. Cadangan rekabentuk UI/UX<br>c. System Requirement Specification (SRS)<br>d. User Acceptance Test (UAT)<br>e. Final Acceptance Test (FAT)<br>f. Manual Pengguna<br>g. Lain-lain dokumen yang tidak dinyatakan di atas (yang berkaitan) | | |
| **2.2.15** | **Pengurusan Projek / Project Management** | | |
| i | Petender mesti sedia, komited dan mampu menghadiri mesyuarat pengurusan projek di UMPSA sekurang-kurangnya pada tempoh sebulan sekali ataupun pada mana-mana tarikh dan masa yang ditetapkan oleh UMPSA. | | |
| ii | Petender atau ahli pasukan petender yang menghadiri mesyuarat pengurusan projek perlulah berkelayakan, berkemampuan dalam komunikasi profesional, memahami teknikal projek, dapat melapor serta boleh membuat keputusan terus (wakil kuasa penuh) apabila diminta dalam mesyuarat. | | |
| iii | Petender mesti menyediakan senarai lengkap pasukan projek yang terlibat beserta peranan setiap ahli. Ahli pasukan mestilah sama atau setara keupayaan kompetensinya sepertimana dalam tawaran dan struktur awal di LAMPIRAN A-02. | | |
| iv | Pengurus projek petender mesti mempunyai pengalaman mengurus sekurang-kurangnya tiga (3) projek yang setara dalam teknologi yang sama dengan tender ini. | | |
| v | Petender perlu menyediakan satu platform yang khusus secara atas talian untuk tujuan pemantauan dan pengurusan projek dan segala kos yang berkaitan adalah dibawah tanggungjawab Petender. | | |
| vi | UMPSA tidak menyediakan akses VPN kepada petender. Oleh itu petender mestilah merancang pelaksanaan projek ini mengikut kesesuaian perkara ini. Petender mesti menempatkan sekurang-kurangnya satu (1) unit komputer desktop (PC) di premis UMPSA bagi tujuan pengurusan projek atau 'remote access'. | | |
| vii | Segala surat-menyurat, mesyuarat serta minit mesyuarat dalam projek ini adalah dalam Bahasa Melayu. Salinan dalam Bahasa Inggeris boleh disediakan jika perlu. | | |
| **2.2.16** | **Sokongan Teknikal / Technical Support** | | |
| i | Petender mesti menyediakan sokongan teknikal untuk sebarang pertanyaan dan masalah yang dihadapi oleh UMPSA semasa dalam Tempoh Jaminan. | | |
| ii | Petender mesti menyediakan dokumen yang memperincikan cadangan Service Level Agreement (SLA) bersama dengan tatacara Pengurusan Aduan. | | |
| iii | SLA sokongan teknikal tidak terhad seperti berikut:<br>a. Kadar response time dalam tempoh 4 jam melalui telefon dan email<br>b. Masa penyelesaian masalah dalam tempoh tiga (3) hari<br>c. Lawatan On-site tanpa had bagi Severity 1 (Mengikut keperluan) | | |

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
| i | Sila isikan template LAMPIRAN A-04 dengan nama kakitangan/anggota pasukan petender yang akan melaksanakan projek di bawah tender ini nanti. | | |
| **3.2.2** | **Pengalaman Ahli Pasukan / Team Member Experience** | | |
| i | Sila isi maklumat pengalaman SETIAP kakitangan/ahli pasukan petender (yang dinyatakan di item 3.2.1) menggunakan template di LAMPIRAN A-02. | | |

---

## SEKSYEN 4.0: PENGHANTARAN DAN MASA / DELIVERY AND TIMELINE

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|-------------------------------------|------------------------------------|-----------------|
| **4.1** | **TECHNICAL DELIVERABLES** | | |
| 4.1.1 | Sistem Pengurusan Mesyuarat | | |
| 4.1.2 | Akaun dan credential Laravel Shift | | |
| 4.1.3 | Mesyuarat Kick-off projek/pelaksanaan | | |
| 4.1.4 | Bengkel | | |
| 4.1.5 | Pelan Pelaksanaan | | |
| 4.1.6 | Cadangan Rekabentuk UI/UX | | |
| 4.1.7 | Senarai latihan dan jadual latihan | | |
| 4.1.8 | Dokumen-dokumen kajian dan pematuhan keperluan seperti BRS, SRS dan SDS | | |
| 4.1.9 | Senarai dokumen berkaitan pengujian sistem aplikasi seperti 'test scripts', 'test case', UAT, PenTest, FAT dan seumpamanya | | |
| 4.1.10 | Senarai dokumentasi dan manual pengguna | | |
| 4.1.11 | Dokumen/surat jaminan pematuhan terhadap 'Coding Standard & Convention' oleh petender beserta perincian contoh pelaksanaan | | |
| 4.1.12 | Surat dan dokumen-dokumen pentauliahan | | |
| 4.1.13 | Surat dan dokumen sahjamin serta seumpamanya | | |
| 4.1.14 | Satu (1) unit komputer desktop ditempatkan di premis UMPSA | | |
| 4.1.15 | Lain-lain yang jika ada dinyatakan dalam dokumen tender ini atau diputuskan dalam bengkel tender dengan persetujuan bersama | | |
| **4.2** | **TEMPOH SIAP / COMPLETION PERIOD** | | |
| 4.2.1 | Semua kerja-kerja yang terlibat mestilah dilaksanakan mengikut tempoh yang ditetapkan iaitu lapan bulan (8) bulan. | | |
| 4.2.2 | Petender perlu menghantar pelan dan jadual pelaksanaan keseluruhan projek (menggunakan Gantt Chart) yang merangkumi kerja-kerja:<br>i. Pelaksanaan projek<br>ii. Serahan dokumentasi projek<br>iii. Pelaksanaan latihan<br>iv. Lain-lain perkara yang tidak dinyatakan di atas (yang berkaitan) | | |
| 4.2.3 | Penetapan tarikh, masa, perlanjutan masa, penamatan tempoh atau seumpamanya berkaitan pelaksanaan projek dalam jadual penentuan teknikal ini mestilah berdasarkan surat rasmi atau dokumen rasmi yang dikeluarkan oleh Jabatan Bendahari UMPSA. | | |
| **4.3** | **DENDA / PENALTY** | | |
| 4.3.1 | UMPSA berhak mendenda petender jika berlaku kelewatan dalam penghantaran mana-mana item di dalam projek/tender ini. | | |
| 4.3.2 | Nilaian denda adalah tertakluk kepada pihak UMPSA. | | |
| **4.4** | **TEMPOH JAMINAN / WARRANTY PERIOD** | | |
| 4.4.1 | Perkara ini perlu dibaca bersama item 1.3 dan meliputi segala aspek 'warranty', 'maintenance' dan 'support'. | | |
| 4.4.2 | Tempoh jaminan bagi kerja-kerja, pemasangan dan konfigurasi, integrasi, pengujian, pelaksanaan dan pentauliahan adalah dua belas (12) bulan bermula setelah penerimaan akhir (Final Acceptance Test - FAT) telah dilakukan dengan jayanya. | | |
| 4.4.3 | Petender perlu menyediakan platform yang terurus secara online bagi tujuan pengurusan aduan dan isu-isu sepanjang tempoh jaminan. | | |

---

## RUJUKAN DOKUMEN / DOCUMENT REFERENCES

| Rujukan | Perihal |
|---------|---------|
| Dokumen Asal | DOKUMEN UMPSA BEND SH 2026 (2) - Jilid |
| No. JTICT | JTICT/2025 (29) |
| Jabatan | DiTec (Pusat Teknologi Digital) |
| Muka Surat Spesifikasi | Muka Surat 1 - 71 (FORM/BEND/UP/007) |
| Seksyen 2.0 | Muka Surat 14 - 66 |
| Seksyen 3.0 | Muka Surat 58 - 61 |
| Seksyen 4.0 | Muka Surat 62 - 66 |

---

**Nota:**
- Ruangan "Maklumbalas / Spesifikasi Syarikat" hendaklah diisi oleh pembida
- Ruangan "Bukti / Rujukan" hendaklah merujuk kepada dokumen sokongan yang disertakan
- Semua dokumen sokongan mestilah tanpa nama syarikat (untuk Bahagian C)

---

*Disediakan berdasarkan Dokumen Sebut Harga UMPSA/BEND/SH/2026(2)*  
*Sistem Pengurusan Mesyuarat / Meeting Management System*
