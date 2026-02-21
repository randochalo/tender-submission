# JADUAL PEMATUHAN TEKNIKAL LENGKAP
## TSH-2613: Sistem Pengurusan Mesyuarat
### UMPSA/BEND/SH/2026(2)

---

## BAHAGIAN 2.1: SKOP KERJA

### 2.1.1 Skop Utama (22 item A-V)

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| A | Petender MESTI membangunkan semua modul/menu yang dinyatakan di dalam perkara 2.1.2, merupakan kajian keperluan awal. Dokumen kajian keperluan (user requirement specification) yang akan dimuktamadkan dalam bengkel merupakan dokumen akhir yang akan dijadikan rujukan di dalam pembangunan sistem. Rujuk perkara 2.2.2 | | |
| B | Petender MESTI menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API (application programming interface) untuk setiap modul. Ini termasuk penggunaan Eloquent ORM. | | |
| C | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| D | Integrasi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa. i) Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim ii) Integrasi dengan keputusan E Voting sedia ada. | | |
| E | Membangunkan antara muka pengguna dalam bentuk responsive web design menggunakan Bootstrap, Tailwind, atau teknologi setara, serta menambah ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| F | Menggunakan pangkalan data Oracle yang sedia ada di UMPSA. | | |
| G | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| H | Menggunakan container technology sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| I | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery yang terdapat di UMPSA. | | |
| J | Petender perlu menyediakan persekitaran pembangunan sistem sendiri bagi tujuan pelaksanaan projek ini. | | |
| K | Konfigurasi hendaklah mematuhi piawaian keselamatan, keperluan ISMS, dan amalan DevOps terbaik. | | |
| L | Mempunyai fungsi memuat naik dokumen dan berupaya menjana laporan. | | |
| M | Menggunakan Power BI dengan memanfaatkan lesen institusi sedia ada, bagi tujuan pembangunan dashboard tanpa melibatkan sebarang kos pelesenan tambahan kepada pihak UMPSA. | | |
| N | Petender hendaklah melaksanakan proses migrasi data daripada sistem sedia ada ke sistem baharu bagi memastikan kesinambungan operasi tanpa gangguan | | |
| O | Melaksanakan integrasi dengan sistem dalaman berikut: i. MyUMPSA-ID Single Sign-On (SSO) ii. Redis iii. Email gateway iv. File storage v. API vi. Notification vii. Modul Executive Approval | | |
| P | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| Q | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| R | Menyediakan latihan: i. Latihan kepada pentadbir sistem (IT) ii. Latihan kepada pengguna akhir (end-users) | | |
| S | Membangun, menguji dan mentauliah sistem yang dibangunkan. | | |
| T | Menyerahkan kod sumber penuh (full source code) sistem beserta dokumentasi berkaitan bagi tujuan pemilikan penuh oleh pihak UMPSA. | | |
| U | Menyediakan dan mengkonfigurasi persekitaran pelayan bagi staging, development, disaster recovery (DR), dan production, mengikut spesifikasi yang ditetapkan. | | |
| V | Melaksanakan proses migrasi dan pelaksanaan penuh sistem baharu sehingga siap sedia untuk operasi secara langsung (go-live), termasuk pengesahan akhir bersama pihak UMPSA. | | |

### 2.1.2 Keperluan Fungsian Modul

#### 2.1.2.1 Login
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Modul ini mengesahkan identiti pengguna melalui SSO server (Keycloak). Selain itu pengguna boleh juga log masuk aplikasi melalui pengesahan Google. | | |

#### 2.1.2.2 E-Authorization
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Modul ini bertujuan bagi memberi akses kepada keseluruhan sistem mesyuarat. | | |
| 2 | Set-up/Review & Approval: Memberikan akses kepada pengguna dan pentadbir secara berperingkat (tiering). | | |
| 3 | Sistem mempunyai keupayaan untuk audit trail. | | |
| 4 | Integrasi dengan Executive approval/notifikasi/tindakan di dalam ecomm UMPSA bagi semua modul sistem ini yang memerlukan tindakan ahli/staff UMPSA berkaitan mesyuarat. | | |
| 5 | Menu kebenaran berkaitan pemantauan, kelulusan mesyuarat dan penyelenggaraan mesyuarat di bawahnya. | | |

#### 2.1.2.3 Meeting Registration
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Set up tier of meeting**: Modul ini bertujuan bagi penetapan pengurusan semua mesyuarat-mesyuarat di dalam universiti. | | |
| 2 | **Meeting Set-Up: Lazim/Khas & Edaran**: Permohonan pendaftaran mesyuarat, Kelulusan pendaftaran, Penetapan peringkat mesyuarat (peringkat 1, 2,..n), Pendaftaran sesi mesyuarat, Memberikan akses kepada pengguna dan pentadbir. | | |
| 3 | **Panggilan Mesyuarat (Lazim/Khas)**: Modul ini bertujuan bagi pemakluman kepada ahli mesyuarat dan majlis/jk berkenaan cadangan tarikh, tempat dan maklumat lain berkenaan mesyuarat yang akan diadakan melalui e-mel. | | |
| 4 | **Mesyuarat Secara Edaran**: Memudahkan proses mesyuarat tanpa kehadiran secara fizikal, membolehkan dokumen diedarkan kepada ahli, dan membolehkan ahli memberi maklum balas, komen atau keputusan dalam tempoh masa ditetapkan secara dalam talian. Pemakluman Mesyuarat Secara Edaran dan dapatkan keputusan ahli. Paparan pada modul executive approval sedia ada bagi tindakan ahli Senat/Mesyuarat. Peringatan tempoh maklumbalas dan tindakan mengikut ketetapan tadbir urus mesyuarat. | | |
| 5 | **Meeting Notice**: Pengeluaran notis panggilan mesyuarat berdasarkan tempoh yang telah ditetapkan mengikut tadbir urus mesyuarat. | | |

#### 2.1.2.4 e-Takwim
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Kekal menggunakan sistem sedia ada, walau bagaimanapun perlu ada integrasi sistem sedia ada dan sistem baru yang akan dibangunkan. | | |
| 2 | Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim. | | |
| 3 | **Taqwim Set up**: Sumber data dari etakwim ecomm/appointment dalam ecomm (sistem sedia ada), Paparan di dalam dashboard Menu mesyuarat. | | |

#### 2.1.2.5 E-Committee
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Menguruskan maklumat keahlian mesyuarat secara berpusat, termasuk daftar, kemas kini, penamatan, rekod sejarah pelantikan dan penjanaan laporan berkaitan. | | |
| 2 | **Appointment (Perlantikan)**: Mendaftarkan keahlian mesyuarat mengikut tempoh pelantikan, Integrasi data staf bagi tujuan mendaftarkan keahlian mengikut tempoh pelantikan, Perkara yang diperlukan antaranya Nama, Jawatan Hakiki & Jawatan Giliran, ID Staf, Fakulti, Kelulusan Akademik, Tempoh Jawatan dan lain-lain, Membantu sekretariat dalam memantau tempoh pelantikan dan penamatan dengan sistem alert, Statistik kehadiran/tidak hadir ahli mesyuarat bulanan/tahunan, Janaan nama ahli bagi pembangunan minit mesyuarat berdasarkan format minit mesyuarat, Integrasi data sistem HoD UMPSA bagi Paparan rujukan didalam Ecomm Sistem HoD, Paparan tempoh lantikan, Menu yang diperlukan menyimpan rekod keahlian mesyuarat untuk rujukan masa hadapan, Boleh menjana dan menghantar surat kepada semua ahli mesyuarat. Penyediaan surat keahlian antaranya pelantikan, penamatan dan penghargaan dan lain-lain secara E-Letter digital. | | |
| 3 | **Committee Set-Up**: Modul ini menetapkan keahlian sesuatu mesyuarat berdasarkan ToR Mesyuarat tersebut, Antara ciri-ciri perlu ada ialah: nama, jawatan, id no, tempoh pelantikan dalam jawatankuasa, jawatan gilliran pentadbiran yang disandang dan lain-lain, Integrasi data dengan modul minit mesyuarat dan sistem sediada (HoD Ecomm). | | |
| 4 | **Attendance**: Pengiraan cukup kuorum keahlian mesyuarat bagi 1/3 ahli untuk mengadakan mesyuarat, Maklumbalas kehadiran mesyuarat melalui sistem oleh Ahli; hadir/tidak hadir berserta sebab ketidakhadiran, Janaan laporan kehadiran mesyuarat mengikut jawatan hieraki tertinggi berdasarkan tadbir urus. | | |

#### 2.1.2.6 E-Paper Meeting
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Menyediakan satu platform berpusat untuk menghantar, mendaftar, menyimpan, mencari, menapis, dan menjejak sejarah kertas kerja yang dibentangkan atau dikemukakan. | | |
| 2 | **Call for Paper**: Mudah diakses melalui fungsi carian, Sesi saringan kertas kerja bagi menentukan dibawa masuk ke mesyuarat semasa atau akan datang atau kemaskini status KIV/digugurkan dan sebagainya, Carian melalui authorize yang dibuka kepada pemohon dan fakulti/pusat yang dibenarkan, Arkib dokumen. | | |
| 3 | **Paper submission**: Pemohon/PTJ/Sekretariat menghantar kertas kerja dengan memuatnaik dalam pelbagai bentuk antaranya documents, imej, pdf, video dan sebagainya bagi permohonan untuk dibentangkan kepada mesyuarat, Sistem hendaklah membolehkan kertas kerja daripada Majlis atau Jawatankuasa lain dibawa ke peringkat kelulusan melalui proses mesyuarat yang diintegrasikan seperti peringkat proses mesyuarat: (i) Perakuan (ii) Kelulusan (iii) Pemakluman, Kertas kerja dari pelbagai peringkat (tier mesyuarat) antaranya: (i) Mesyuarat Unit/Jabatan/Pusat (ii) Jawatankuasa (iii) Majlis (iv) Senat JKPU/LPU (v) Dan lain-lain, Integrasi Mesyuarat Utama/Induk dan Majlis/Jawatankuasa dibawahnya: Sistem hendaklah membolehkan kertas kerja daripada Majlis atau Jawatankuasa lain dibawa ke peringkat atasan untuk dibentangkan melalui proses yang diintegrasikan, Penyelenggaraan jejak audit (audit trail) bagi setiap pergerakan dan pindaan dokumen, Penyelarasan tarikh, agenda, dan item mesyuarat mengikut peringkat proses kelulusan yang ditetapkan. | | |
| 4 | **Meeting Agenda Notice**: Proses penyampaian maklumat berkaitan perkara-perkara yang akan dibincangkan dalam sesuatu mesyuarat kepada semua ahli yang terlibat. Pengeluaran notis agenda mesyuarat yang telah dimuktamadkan selepas Mesyuarat Pra berdasarkan tempoh yang telah ditetapkan berdasarkan tadbir urus mesyuarat, Penghantaran kertas kerja melalui platform sistem oleh pemohon/sekretariat majlis/Jawatankuasa, Sistem hendaklah menghantar notifikasi bagi setiap perubahan status kertas kerja, termasuk KIV, digugurkan, ditangguh, diluluskan dan status lain. | | |

#### 2.1.2.7 E-Decision Meeting
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Modul ini melibatkan sekretariat, ahli mesyuarat dan staf yang perlu mengambil tindakan dari keputusan mesyuarat. | | |
| 2 | Semua keputusan direkod dalam minit mesyuarat sebagai rujukan rasmi. Digunakan untuk memantau tindakan susulan dan tanggungjawab ahli. Boleh dirujuk semula untuk audit, laporan, atau penyelesaian pertikaian. | | |
| 3 | Bagi menu keputusan mesyuarat yang akan dikeluarkan oleh secretariat kepada pemohon kertas kerja atau PIC yang perlu mengambil Tindakan atas keputusan tersebut, ianya adalah bersifat edaran sahaja. Jika berlaku sebarang pindaan (contoh secretariat terkhilaf membuat catatan keputusan, pihak secretariat mempunyai akses bagi meminda di menu keputusan dan akan menghantar semula keputusan yang dipinda). | | |
| 4 | **Distribute (Edaran)**: Penyediaan keputusan 3 hari berkerja selepas mesyuarat diadakan bagi ahli mesyuarat mengambil tindakan dengan efektif, Edaran kepada pic/ptj yang perlu menjalankan tugasan/tindakan tersebut, Format & template berdasarkan format minit yang ditetapkan, Paparan terus kepada Dekan/HOD pemohon. | | |

#### 2.1.2.8 E-Minutes
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Minit mesyuarat adalah dokumen catatan yang direkodkan hasil mesyuarat yang telah diadakan. Modul ini mengurus dan merekod keputusan mesyuarat secara tersusun, dengan keupayaan untuk menjejak status pelaksanaan tindakan, menghasilkan laporan, dan memudahkan capaian oleh pihak berkepentingan. | | |
| 2 | **Draft Minutes**: Merekod/mencatat minit secara terus ke dalam sistem dan paparan dapat dilihat seperti format minit mesyuarat (word document) dengan diintegrasikan input bagi perkara no 6 iaitu keputusan mesyuarat, Catatan minit mesyuarat penuh adalah penggabungan dari modul keputusan dan minit mesyuarat: format catatan minit mesyuarat yang akan ditetapkan, Catatan Mesyuarat mengambil maklum (input perbincangan, isi kandungan kertas kerja, tajuk, no perkara dalam minit dan pic/ptj tindakan. | | |
| 3 | **Review by Comm**: Proses semakan draf minit mesyuarat selama 3 hari, Menu Tindakan dapat dihantar kepada pegawai bertanggungjawab untuk tindakan seterusnya (Dekan/Pengarah/etc). | | |
| 4 | **Amendments**: Menu Tindakan dapat dihantar kepada pegawai bertanggungjawab untuk tindakan seterusnya. | | |
| 5 | **Distribute**: Edaran kepada ahli selepas semakan adalah 14 hari bekerja selepas mesyuarat. | | |

#### 2.1.2.9 E-Progress Minutes
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Menghantar, Memantau, mengumpul, meminda dan menyelaras maklum balas serta pelaksanaan tindakan daripada lebih dari 1 pihak bertanggungjawab terhadap melakukan tindakan kepada sesuatu keputusan, minit atau arahan mesyuarat. | | |
| 2 | Paparan edaran maklum balas mesyuarat, Mengedarkan permohonan maklumbalas mesyuarat kepada pic/ptj, PIC/PTJ memberikan maklumbalas kepada laporan tersebut. Maklum balas boleh dibuat melebihi satu orang dan tidak terhad kepada ahli mesyuarat, Sistem mempunyai fungsi muatnaik dokumen sebagai lampiran kepada maklum balas, Sistem hendaklah membolehkan pemohon memberikan maklum balas secara langsung melalui pautan atau arahan yang diterima dalam alert/notification yang dihantar oleh sistem, Sekretariat mesyuarat akan menyelaras penulisan maklumbalas bagi dokumen rasmi minit mesyuarat, Sekretariat mengumpul jawapan maklum balas yang diterima dan disatukan serta dimurnikan bagi menjadikan dokumen minit yang rasmi bagi mesyuarat yang seterusnya/hadapan, Sistem hendaklah membolehkan maklum balas daripada pihak berkaitan diintegrasikan secara automatik ke dalam minit mesyuarat bagi Perkara Berbangkit, Sistem hendaklah menyediakan fungsi penjejakan (tracking) bagi setiap tindakan susulan yang timbul daripada setiap kertas kerja yang dibentangkan dalam mesyuarat, Laporan penuh bagi perkara berbangkit boleh dijana mengikut format yang ditetapkan. | | |
| 3 | **Call For Progress**: Paparan edaran maklum balas mesyuarat, Mengedarkan permohonan maklumbalas mesyuarat kepada pic/ptj, Paparan terus integrasi maklum balas di dalam minit mesyuarat di perkara berbangkit, Penjejakan tindakan susulan bagi setiap kertas kerja daripada setiap mesyuarat yang dibentangkan. | | |
| 4 | **Progress submission**: PIC/PTJ memberikan maklumbalas kepada laporan tersebut secara web based, Pemohon terus memberikan maklum balas melalui alert/notification. | | |
| 5 | **Amendments**: Sekretariat mesyuarat menyelaras penulisan maklumbalas bagi dokumen rasmi minit mesyuarat, Sekretariat mengumpul jawapan maklum balas yang diterima dan disatukan serta dimurnikan bagi menjadikan dokumen minit yang rasmi bagi mesyuarat yang seterusnya/hadapan, Laporan-laporan penuh mengikut format yang akan diberikan. | | |

#### 2.1.2.10 E-Cabutan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Modul ini membolehkan pengguna memohon, mengakses, mencari, dan menjana cabutan minit mesyuarat berdasarkan kategori, tarikh, kata kunci, dan jenis keputusan bagi tujuan pelaksanaan atau dokumen rujukan rasmi. | | |
| 2 | **Application**: Pemohon mengisi permohonan di dalam sistem, Sekretariat menyemak dan meluluskan permohonan, Pemohon boleh melihat cabutan minit melalui paparan sistem dan janaan PDF, Carian cabutan minit mesyuarat adalah berdasarkan minit mesyuarat dan rekod daftar kertas kerja senat lepas. | | |
| 3 | **Distribute**: Pemohon boleh melihat cabutan minit melalui paparan sistem dan janaan PDF. | | |

---

## BAHAGIAN 2.2: PEMATUHAN & PERKHIDMATAN PROFESIONAL

### 2.2.1 Sesi Taklimat Secara 'Online'
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | UMPSA berhak untuk memanggil petender untuk sesi taklimat secara 'online' (Google Meet, MS Teams atau seumpamanya) sekiranya perlu. Tarikh dan masa (hari bekerja) yang ditetapkan oleh UMPSA mestilah dipatuhi oleh petender. UMPSA berhak tidak menilai tawaran petender jika petender gagal hadir (online) dalam sesi tersebut. | | |

### 2.2.2 Bengkel Kajian Keperluan Projek
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender yang berjaya/dipilih hendaklah melaksanakan bengkel bagi membangunkan pelan pelaksanaan projek ini termasuklah meneliti keperluan sistem, proses yang terlibat serta keperluan persekitaran sistem. Bengkel ini melibatkan pemilik proses, staf teknikal dan petender yang dilantik. | | |
| 2 | **Bengkel**: Tujuan bengkel diadakan untuk mengenalpasti spesifikasi secara terperinci berkenaan sistem/modul yang terlibat. Kekerapan bengkel adalah mengikut keperluan sehingga draf dokumen selesai. | | |
| 3 | Dokumen kajian keperluan (user requirement specification) yang akan dimuktamadkan merupakan dokumen akhir yang akan dijadikan rujukan di dalam pembangunan sistem. Maklumat khusus berkaitan sistem dan modul yang dinyatakan di dalam tender ini merupakan kajian keperluan awal. | | |
| 4 | Bengkel perlu dilakukan secara on-site (dalam UMPSA). | | |
| 5 | Kos pelaksanaan bengkel akan ditanggung oleh petender sepanjang projek berjalan. | | |

### 2.2.3 Penyediaan Pelan Pelaksanaan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Satu pelan pelaksanaan bertulis yang muktamad perlu dihasilkan oleh petender yang berjaya/dipilih selepas bengkel. | | |
| 2 | Pelan ini perlu turut meliputi aspek organisasi projek, penjadualan pelaksanaan aktiviti projek, 'work breakdown structure (WBS)', 'critical path method (CPM)' diagram, jadual PERT serta metodologi pembangunan. Item-item lain yang perlu dikemukakan akan dibincang bersama dalam bengkel. | | |
| 3 | Dokumen pelan pelaksanaan perlu dihantar kepada pihak UMPSA dalam tempoh dua (2) minggu dari tarikh selesai bengkel. | | |
| 4 | UMPSA berhak menolak atau mengarah pemindaan pelan pelaksanaan oleh petender yang didapati tidak bertepatan dengan objektif tender ini atau mempunyai kesilapan. | | |

### 2.2.4 Penyediaan Cadangan Rekabentuk UI/UX
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender yang berjaya/dipilih perlu mencadangkan konsep rekabentuk antaramuka pengguna (user interface UI) yang terkini dan moden. Konsep rekabentuk antaramuka ini perlu dihantar dalam tempoh tiga (3) minggu dari tamat bengkel. | | |
| 2 | Fungsi aplikasi dalam pembangunan modul mestilah bersesuaian dengan kehendak pengguna atau pengalaman pengguna (user experience - UX) supaya setiap modul berfungsi dengan baik dan mesra pengguna. | | |

### 2.2.5 Penerapan Standard
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Pelaksanaan kerja-kerja pembangunan aplikasi dan sistem mestilah mengikut standard terbaik industri dan memenuhi persekitaran UMPSA. | | |
| 2 | Petender perlu menerapkan UMPSA Standard Coding Convention dalam pengaturcaraan semua modul sistem aplikasi yang dipersetujui dalam tender ini. UMPSA akan membekalkan dokumen panduan berkenaan. | | |
| 3 | Sebarang pewujudan 'table' baru atau 'column' baru untuk menyimpan data rekod yang ingin diwujudkan dalam pangkalan data UMPSA perlulah menggunakan 'naming standard' yang betul serta mendapat kelulusan secara bertulis oleh Pentadbir Pangkalan Data UMPSA. Penggunaan 'sequence number' sebagai ID rujukan dalam 'table' perlulah diminimakan. | | |
| 4 | Sebarang 'table' baharu yang ingin diwujudkan dalam pangkalan data UMPSA perlulah telah siap dinormalisasikan (normalization). | | |
| 5 | Petender perlu memastikan perisian atau sistem aplikasi yang dibangunkan atau dibekalkan mematuhi standard terbuka (open standard) semasa dan garis panduan Kerajaan Malaysia seperti Kejuruteraan Sistem Aplikasi Sektor Awam (KRISA), Electronic Government Information Technology Policy and Standards (EGIT), Data Dictionary Sektor Awam (DDSA), Management of Information & Communication Technology Security Handbook (MyMIS), Malaysian Government Interoperability Framework (MyGIF), Malaysian Government Interoperability Framework for Open Source Software (MyGIFOSS) dan Garis Panduan IT Outsourcing Agensi - Agensi Sektor Awam. | | |

### 2.2.6 Pengurusan Kod Sumber
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Semua kod sumber (source code) dan hak cipta sistem aplikasi yang dibangunkan untuk setiap sistem aplikasi melalui tender ini adalah menjadi HAKMILIK UMPSA sepenuhnya. | | |
| 2 | Petender TIDAK dibenarkan membuat edaran, salinan atau salin cetak kepada pihak lain atau; disimpan di tempat yang tidak berkaitan projek/perolehan ini; tanpa apa-apa kebenaran rasmi secara bertulis dari pihak UMPSA. | | |
| 3 | Petender wajib meletakkan/menghoskan kod sumber terkini yang sedang dibangunkan serta kod sumber yang siap dibangunkan untuk pengujian di repository GitLab UMPSA. Kegagalan petender atau sekutu mematuhi terma ini dianggap sebagai pelanggaran syarat kontrak tender ini. | | |
| 4 | UMPSA berhak mengukur status pencapaian kerja dan perkhidmatan petender termasuk bagi tujuan pembayaran berdasarkan tahap kematangan, kesediaan atau keaktifan kod sumber yang diletakkan oleh petender di repository GitLab UMPSA itu. | | |
| 5 | 'Deployment' sebarang sistem aplikasi atau modul dalam tender ini ke server-server aplikasi UMPSA mestilah hanya melalui GitLab UMPSA. 'Deployment' sistem aplikasi secara terus ke server aplikasi tanpa melalui GitLab UMPSA adalah tidak dibenarkan. | | |
| 6 | Petender wajib memastikan kod sumber yang dibangunkan atau dibekalkan adalah selamat, berfungsi dan bebas ralat. | | |
| 7 | Pengurusan repositori GitLab UMPSA adalah di bawah kuasa UMPSA serta petender tertakluk mematuhi syarat-syarat semasa penggunaan repository GitLab UMPSA ataupun syarat-syarat baru dari masa ke semasa. | | |
| 8 | UMPSA tidak mengganggu kod sumber yang sedang dibangunkan oleh petender namun UMPSA berhak melantik wakil penyemak dan penguji kod sumber dalam repositori yang berkaitan bagi tujuan pengujian, kawalan kualiti serta kesinambungan pengetahuan. | | |
| 9 | Apa-apa isu yang timbul berhubung penggunaan atau pengoperasian GitLab UMPSA dalam projek tender ini hendaklah dirujuk kepada Pengurus GitLab UMPSA atau Pengurus Projek tender ini. Pengurus GitLab UMPSA berhak dan boleh memutuskan tatacara atau perubahan tatacara yang perlu diikuti oleh kedua-dua belah pihak. | | |
| 10 | Selepas tempoh jaminan tamat petender perlu menghapuskan segala data, maklumat dan kod sumber (source code) projek/tender ini yang berada di dalam simpanan petender atau sekutu. | | |

### 2.2.7 Pemasangan, Konfigurasi dan Integrasi
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Server (Linux) untuk hos API dan sistem aplikasi sebenar akan dibekalkan oleh UMPSA. Petender bertanggungjawab memasang dan menyediakan 'system environment' yang diperlukan dan sesuai bagi membolehkan sistem aplikasi berfungsi dengan betul serta berkesan. | | |
| 2 | Petender perlu mempunyai 'development environment' server sendiri untuk tujuan pembangunan aplikasi sebagai alternatif sekiranya petender tidak dapat mengakses atau menggunakan server di UMPSA untuk tujuan pembangunan aplikasi-aplikasi dalam projek ini atas sebab-sebab yang diperakui UMPSA. Ini supaya fasa proses pembangunan aplikasi tidak tergendala. Fasa pengujian dan 'production deployment' aplikasi tetap wajib dijalankan/dilakukan di server UMPSA. | | |
| 3 | Petender perlu menyempurnakan kerja-kerja pemasangan dan konfigurasi API di server UMPSA sekiranya ada. | | |
| 4 | Kos pemasangan untuk semua perisian atau 'package' perisian adalah di bawah tanggungjawab pihak petender. | | |
| 5 | Petender perlu patuh dan mengikuti semua peraturan dan prosedur yang ditetapkan oleh UMPSA ketika kerja-kerja proses pembangunan, pemasangan, konfigurasi, integrasi, pengujian dan pentauliahan dijalankan. | | |
| 6 | Petender mesti menyempurnakan proses integrasi melibatkan pemasangan dan konfigurasi API bagi setiap modul berkaitan tender ini di server UMPSA sekiranya ada. | | |
| 7 | Sebarang kerja, pemasangan, konfigurasi dan integrasi sistem aplikasi yang tidak dinyatakan di dalam dokumen tender ini, tetapi perlu ada bagi melengkapkan proses keseluruhan sistem di dalam projek ini dan dianggap perlu oleh pihak UMPSA, pihak petender mesti menyelesaikan skop tersebut tanpa sebarang kos tambahan. | | |
| 8 | Kerja-kerja integrasi komponen baharu mestilah serasi dan boleh berkomunikasi dengan komponen sedia ada tanpa menjejaskan fungsi yang sedang digunakan di UMPSA. | | |

### 2.2.8 Lesen Perisian
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Sebarang perisian yang dibekalkan, dipasang atau digunakan mestilah sah, asli serta mendapat kebenaran (licensed) untuk digunakan di UMPSA daripada penerbitnya. UMPSA tidak bertanggungjawab terhadap sebarang penggunaan perisian 'proprietary' tidak berlesen atau perisian 'public license' yang tidak mematuhi/mendapat kebenaran penerbitnya oleh pihak petender atau sekutu. | | |
| 2 | Sebarang perbekalan, pemasangan atau penggunaan perisian yang melibatkan langganan kos secara bulanan, tahunan atau berkala yang lain perlulah terlebih dahulu dimaklumkan dan mendapat persetujuan bertulis UMPSA. | | |

### 2.2.9 Versi Perisian
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Bagi keadaan di mana versi perisian yang disyaratkan dalam perolehan perkhidmatan ini telah dikira sebagai 'outdated' atau menjadi 'not supported', maka versi yang lebih baru, stabil dan bersesuaian dengan keperluan UMPSA perlu dibekalkan dengan mendapat persetujuan bertulis daripada UMPSA. Penukaran versi adalah tanpa sebarang kos tambahan. | | |

### 2.2.10 Kerja Panggil Balik (Call Back Work)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender dikehendaki menyediakan perkhidmatan "panggil balik" bagi skop "Corrective Maintenance" tanpa sebarang bayaran tambahan bagi perkhidmatan/kerja yang kurang memuaskan dalam tempoh jaminan/waranti. | | |

### 2.2.11 Pengujian (Testing)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender dikehendaki menjalankan dan melepasi ujian-ujian berikut sehingga diperakui oleh pengguna dan pegawai UMPSA yang dipertanggungjawabkan: (a) Ujian Penerimaan Pengguna (User Acceptance Test, UAT) di UMPSA sekurang-kurangnya dua (2) kali. (b) Semakan 'compliance of server setup' bagi mana-mana server yang dipasang atau dikonfigurasi oleh petender. (c) Ujian Penembusan Keselamatan (Security Penetration Test) UMPSA. (d) Ujian Penerimaan Akhir (Final Acceptance Test, FAT). | | |
| 2 | Petender dikehendaki menyediakan skrip pengujian (test script) bagi tujuan pelaksanaan pengujian UAT setiap modul sistem aplikasi di dalam tender/projek ini. Skrip perlu dalam Bahasa Melayu. | | |
| 3 | User Acceptance Test (UAT) mesti dilakukan sekurang-kurangnya dua (2) kali. Lokasi UAT ialah di UMPSA dan pasukan pembangunan petender mesti hadir. | | |
| 4 | Final Acceptance Test (FAT) mestilah dijalankan di production server dengan jayanya. Jika gagal, petender mesti bersedia untuk menjalankan pengujian semula. | | |
| 5 | Petender bertanggungjawab untuk membangun, mengimplementasi dan menguruskan semua prosedur semasa melaksanakan UAT dan FAT. | | |
| 6 | Semua dokumen peringkat pengujian mestilah dipersetujui, disahkan dan ditandatangani oleh pihak UMPSA. | | |

### 2.2.12 Pelaksanaan dan Pentauliahan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti memastikan semua sistem aplikasi yang telah dibangunkan dan diintegrasi dapat berfungsi dengan baik sebelum proses pemasangan (deployment) dijalankan. Ia merangkumi: (a) Bebas ralat (b) Keselamatan sistem dan data (c) Pelan sokongan sekiranya berlaku kegagalan semasa instalasi di server UMPSA. | | |
| 2 | Petender mesti bertanggungjawab memastikan sistem yang ditauliahkan terjamin dari segi prestasi dan keselamatannya dalam tempoh jaminan. | | |
| 3 | Petender mesti memastikan sistem yang dibangunkan mempunyai tahap 'interoperability' dan 'scalability' yang baik bagi menyokong perkembangan penggunaannya pada masa hadapan. | | |

### 2.2.13 Latihan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Tatacara penggunaan sistem bagi setiap modul dalam sistem yang diintegrasikan (berkonsep train-the-trainer) secara dalaman.** | | |
| 2 | **Pemindahan kepakaran (Transfer of Technology) kepada pasukan teknikal UMPSA bagi setiap modul. Ia akan melibatkan:** (a) Aliran Sistem (System Flow) (b) Data Flow Diagram (DFD) dan Entiti Relationship Diagram (ERD) (c) Teknologi dan tools yang digunakan (d) Sumber rujukan (e) Nota lengkap | | |
| 3 | Petender perlu menjadual, menganjur dan melaksanakan aktiviti latihan yang berkaitan dengan pembangunan aplikasi dan sistem secara 'on-site' bagi tujuan penyelenggaraan aplikasi dan sistem yang dibangunkan atau dibekalkan melalui sebutharga ini. Staf yang terlibat akan dinamakan oleh pihak UMPSA. | | |
| 4 | **Latihan ini meliputi penyelenggaraan berikut:** (a) Latihan penyelenggaraan sistem dan pelayan (server). (b) Latihan pembangunan dan penyelenggaraan API (Laravel). | | |

### 2.2.14 Dokumentasi
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Manual dan dokumentasi hendaklah disediakan dalam bentuk hard-copy dan soft-copy. Manual dan dokumentasi perlulah dalam Bahasa Melayu. Istilah-istilah teknikal dalam Bahasa Inggeris boleh digunakan mengikut keperluan untuk penerangan maksud/konsep lebih baik. | | |
| 2 | Semua dokumen teknikal perlu mendapat kelulusan pihak teknikal UMPSA sebelum segala kerja-kerja pembangunan sistem bermula. | | |
| 3 | Petender yang berjaya mesti menyerahkan semua dokumentasi berikut kepada UMPSA sebagai salah satu keperluan dan rujukan projek: (a) Pelan pelaksanaan projek (b) Cadangan rekabentuk UI/UX (c) System Requirement Specification (SRS) (d) User Acceptance Test (UAT) (e) Final Acceptance Test (FAT) (f) Manual Pengguna (g) Lain-lain dokumen yang tidak dinyatakan di atas (yang berkaitan) | | |

### 2.2.15 Pengurusan Projek
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti sedia, komited dan mampu menghadiri mesyuarat pengurusan projek di UMPSA sekurang-kurangnya pada tempoh sebulan sekali ataupun pada mana-mana tarikh dan masa yang ditetapkan oleh UMPSA. Kehadiran ini termasuk bagi mana-mana keperluan pemasangan (setup), pengujian sistem aplikasi mahupun 'production deployment' sistem aplikasi di dalam projek ini. | | |
| 2 | Petender atau ahli pasukan petender yang menghadiri mesyuarat pengurusan projek perlulah berkelayakan, berkemampuan dalam komunikasi profesional, memahami teknikal projek, dapat melapor serta boleh membuat keputusan terus (wakil kuasa penuh) apabila diminta dalam mesyuarat. Kegagalan petender atau sekutu mematuhi terma ini dianggap sebagai pelanggaran kritikal syarat kontrak tender ini dan boleh didenda. | | |
| 3 | Petender mesti menyediakan senarai lengkap pasukan projek yang terlibat beserta peranan setiap ahli. Ahli pasukan mestilah sama atau setara keupayaan kompetensinya sepertimana dalam tawaran dan struktur awal di LAMPIRAN A-02. Sebarang pertukaran ahli pasukan petender semasa projek telah bermula atau sedang berjalan perlu dimaklumkan oleh petender secara rasmi dan mendapat persetujuan bertulis UMPSA. | | |
| 4 | Pengurus projek petender mesti mempunyai pengalaman mengurus sekurang-kurangnya tiga (3) projek yang setara dalam teknologi yang sama dengan tender ini. Sila senaraikan 2 projek berkenaan di sini atau melalui template profil staf/pengurus di LAMPIRAN A-03. | | |
| 5 | Petender perlu menyediakan satu platform yang khusus secara atas talian untuk tujuan pemantauan dan pengurusan projek dan segala kos yang berkaitan adalah dibawah tanggungjawab Petender. | | |
| 6 | UMPSA tidak menyediakan akses VPN kepada petender. Oleh itu petender mestilah merancang pelaksanaan projek ini mengikut kesesuaian perkara ini. Petender mesti menempatkan sekurang-kurangnya satu (1) unit komputer desktop (PC) di premis UMPSA bagi tujuan pengurusan projek atau 'remote access'. Sebarang bentuk kemudahan 'remote access' atau peralatan di UMPSA adalah wajib tertakluk kepada syarat/peraturan penggunaannya di UMPSA yang petender perlu akur akannya. | | |
| 7 | Segala surat-menyurat, mesyuarat serta minit mesyuarat dalam projek ini adalah dalam Bahasa Melayu. Salinan dalam Bahasa Inggeris boleh disediakan jika perlu. | | |

### 2.2.16 Sokongan Teknikal
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti menyediakan sokongan teknikal untuk sebarang pertanyaan dan masalah yang dihadapi oleh UMPSA semasa dalam Tempoh Jaminan. | | |
| 2 | Petender mesti menyediakan dokumen yang memperincikan cadangan Service Level Agreement (SLA) bersama dengan tatacara Pengurusan Aduan. | | |
| 3 | **SLA sokongan teknikal tidak terhad seperti berikut:** (a) Kadar response time dalam tempoh 4 jam melalui telefon dan email. (b) Masa penyelesaian masalah dalam tempoh tiga (3) hari. (c) Lawatan On-site tanpa had bagi Severity 1 (Mengikut keperluan) | | |

---

## BAHAGIAN 3.0: KEUPAYAAN TEKNIKAL SYARIKAT

### 3.1 Pengalaman Syarikat

#### 3.1.1 Pengalaman dalam Laravel framework
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Berapa tahun syarikat/petender telah terlibat dalam membangunkan sistem aplikasi berasaskan Laravel framework? Jawab ringkas di sini serta sila isikan juga dalam lampiran dokumen berasingan di LAMPIRAN A-03. | | |
| 2 | Berapa jumlah projek pembangunan sistem aplikasi berasaskan Laravel framework yang telah dianugerahkan oleh pelanggan atau pihak lain kepada petender dalam tempoh lima (5) tahun lalu? Jawab ringkas di sini serta sila buktikan juga dalam lampiran dokumen berasingan di LAMPIRAN A-03. | | |
| 3 | Berapa jumlah kakitangan petender yang mahir dalam pembangunan aplikasi berasaskan Laravel framework? Jawab ringkas di sini serta sila buktikan juga dalam lampiran dokumen berasingan di LAMPIRAN A-02. | | |

### 3.2 Struktur Organisasi Projek dan Pengalaman Ahli

#### 3.2.1 Struktur Organisasi Projek
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Sila isikan template LAMPIRAN A-04 dengan nama kakitangan/anggota pasukan petender yang akan melaksanakan projek di bawah tender ini nanti. | | |

#### 3.2.2 Pengalaman Ahli Pasukan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Sila isi maklumat pengalaman SETIAP kakitangan/ahli pasukan petender (yang dinyatakan di item 3.2.1) menggunakan template di LAMPIRAN A-02. | | |

---

## BAHAGIAN 4.0: PENGHANTARAN DAN MASA

### 4.1 Technical Deliverables (4.1.1 - 4.1.15)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
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

### 4.2 Tempoh Siap (4.2.1 - 4.2.3)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 4.2.1 | Semua kerja-kerja yang terlibat mestilah dilaksanakan mengikut tempoh yang ditetapkan iaitu lapan bulan (8) bulan. | | |
| 4.2.2 | Petender perlu menghantar pelan dan jadual pelaksanaan keseluruhan projek (menggunakan Gantt Chart) yang merangkumi kerja-kerja: (i) Pelaksanaan projek (ii) Serahan dokumentasi projek (iii) Pelaksanaan latihan (iv) Lain-lain perkara yang tidak dinyatakan di atas (yang berkaitan) | | |
| 4.2.3 | Penetapan tarikh, masa, perlanjutan masa, penamatan tempoh atau seumpamanya berkaitan pelaksanaan projek dalam jadual penentuan teknikal ini mestilah berdasarkan surat rasmi atau dokumen rasmi yang dikeluarkan oleh Jabatan Bendahari UMPSA. Permohonan yang berkaitan perkara ini perlu dikemukakan oleh petender kepada Jabatan Bendahari UMPSA. | | |

### 4.3 Denda (4.3.1 - 4.3.2)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 4.3.1 | UMPSA berhak mendenda petender jika berlaku kelewatan dalam penghantaran mana-mana item di dalam projek/tender ini. | | |
| 4.3.2 | Nilaian denda adalah tertakluk kepada pihak UMPSA. | | |

### 4.4 Tempoh Jaminan (4.4.1 - 4.4.3)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 4.4.1 | Perkara ini perlu dibaca bersama item 1.3 dan meliputi segala aspek 'warranty', 'maintenance' dan 'support'. | | |
| 4.4.2 | Tempoh jaminan bagi kerja-kerja, pemasangan dan konfigurasi, integrasi, pengujian, pelaksanaan dan pentauliahan adalah dua belas (12) bulan bermula setelah penerimaan akhir (Final Acceptance Test - FAT) telah dilakukan dengan jayanya. | | |
| 4.4.3 | Petender perlu menyediakan platform yang terurus secara online bagi tujuan pengurusan aduan dan isu-isu sepanjang tempoh jaminan. | | |

---

**Disediakan oleh:**

_____________________
(Tandatangan & Cop Syarikat)

Nama: 
Jawatan: 
Tarikh: 

**Untuk Kegunaan Jabatan:**

_____________________
Tandatangan Pengerusi
Jawatankuasa Pembuka Sebut Harga
Tarikh:
