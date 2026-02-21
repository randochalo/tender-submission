# JADUAL PEMATUHAN TEKNIKAL LENGKAP
## TSH-2614: Sistem Portal Staf (eCommunity)
### UMPSA/BEND/SH/2026(3)

---

## BAHAGIAN 2.1: SKOP KERJA

### 2.1.1 Skop Utama (13 item a-m)

| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| a | Petender mestilah menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API (application programming interface) untuk setiap modul. Ini termasuk penggunaan Eloquent ORM. | | |
| b | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| c | Replikasi, migrasi logik dan fungsi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa. | | |
| d | Membangunkan sistem menggunakan teknologi antaramuka pengguna (UI) web dan panel pentadbir yang moden, ciri-lengkap, sumber terbuka (OSS) dan mudah diselenggara, dengan keutamaan menggunakan Filament PHP atau setara. Sistem ini mestilah mempunyai ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| e | Menggunakan pangkalan data Oracle (minimum versi 19c) yang sedia ada di UMPSA. | | |
| f | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| g | Menggunakan teknologi kontena aplikasi (application container technology) sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| h | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery. Persekitaran pembangunan sistem perlu disediakan oleh petender. | | |
| i | Melaksanakan integrasi dengan sistem dalaman berikut: i. MyUMPSA-ID Single Sign-On (SSO) ii. Redis iii. Email gateway iv. File storage v. API vi. Notification Mobile | | |
| j | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| k | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| l | Menyediakan latihan: i. Latihan kepada pentadbir sistem (IT) ii. Latihan kepada pengguna akhir (end-users) | | |
| m | Membangun, menguji dan mentauliah Sistem Portal Staf: i. Serahan penuh kod sumber ii. Konfigurasi pelayan staging, development, DR dan production iii. Migrasi dan pelaksanaan penuh sistem baharu | | |

### 2.1.2 Keperluan Fungsian Modul

#### 2.1.2.1 Login (Modul Login)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Login (Authentication)**: Modul ini adalah untuk menyemak dan mendapat pengesahan identiti pengguna melalui SSO and Identity Provider (IdP) Keycloak UMPSA sedia ada. Selain itu, pengguna boleh juga log masuk ke aplikasi melalui pengesahan Google Sign-in. | | |

#### 2.1.2.2 Modul Temujanji dan Kalendar
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Pengurusan Temujanji**: Pengguna boleh menambah, mengubah, atau memadam temujanji. Senarai peserta perlulah boleh dipilih daripada/mengikut kumpulan pengguna dalam Organizational Unit (OU) atau user groups di Active Directory (AD) UMPSA. Pengguna boleh melihat semula senarai temujanji yang telah dibuat. Sistem memaparkan kalendar bagi memudahkan pemilihan tarikh dan masa. Sistem juga perlu membuat semakan dengan Google Calendar bagi mengelakkan pertindihan jadual sebelum temujanji disimpan. | | |
| 2 | **Papar Kalendar**: Pengguna boleh melihat paparan kalendar dalam format harian, mingguan, atau bulanan. Paparan kalendar memaparkan semua temujanji yang telah dijadualkan berserta statusnya. Pengguna boleh menyemak dan melihat temujanji yang diselaraskan (sync) dengan Google Calendar. Pengguna boleh menjana laporan dalam bentuk pdf. | | |

#### 2.1.2.3 Modul Memo
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Pengguna boleh melihat senarai memo yang diterima. | | |
| 2 | Fungsi carian disediakan untuk mencari memo berdasarkan kata kunci, tarikh, atau pengirim/penerima. | | |
| 3 | Pengguna boleh mengurus memo mengikut folder khas yang dicipta oleh pengguna. | | |

#### 2.1.2.4 Modul Pengumuman
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Pengguna boleh melihat senarai pengumuman yang aktif. | | |
| 2 | Pengguna boleh menambah, mengubah, atau memadam pengumuman. | | |
| 3 | Fungsi carian disediakan untuk mencari pengumuman berdasarkan kata kunci, tarikh, kategori atau pengirim. | | |
| 4 | Pengumuman yang tidak lagi aktif boleh diarkibkan untuk rujukan pada masa hadapan. | | |

#### 2.1.2.5 Pengurusan Pengguna
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Kebenaran Pengguna (User Authorization)**: Sistem mengesahkan identiti pengguna melalui proses log masuk sebelum membenarkan akses ke dalam sistem. | | |
| 2 | **Keistimewaan Pengguna (User Privilege)**: Setiap pengguna diberikan tahap akses tertentu berdasarkan peranan (role) yang ditapkan, contohnya akses untuk melihat, menambah, mengubah, atau memadam data. | | |
| 3 | **Keistimewaan Kumpulan (Group Privilege)**: Pengguna boleh diurus secara berkumpulan dengan pemberian keistimewaan akses yang sama kepada semua ahli kumpulan tersebut. | | |
| 4 | **Audit Log Aktiviti Pengguna**: Sistem merekod semua aktiviti pengguna termasuk log masuk, log keluar, penambahan, pengubahan, dan pemadaman data untuk tujuan pengesanan serta keselamatan. Memaparkan laporan atau statistik penggunaan modul dalam sistem. | | |
| 5 | **Senarai Pengguna**: Sistem memaparkan senarai semua pengguna beserta maklumat asas. Kemudahan fungsi carian juga perlu disediakan. | | |

#### 2.1.2.6 Modul Tetapan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Pengurusan Kumpulan (Group)**: Membolehkan pengguna mengurus kumpulan bagi tujuan pengelompokan pengguna dan pemberian akses mengikut kumpulan. | | |
| 2 | **Personalisasi Menu (Personalize Menu)**: Pengguna boleh mengubah susunan dan paparan menu mengikut keperluan masing-masing. | | |
| 3 | **Susun Atur & Tema (Layout & Customized Theme)**: Membolehkan pengguna menukar susun atur antaramuka dan memilih tema warna mengikut keselesaan. | | |

#### 2.1.2.7 Modul Notifikasi
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Memaparkan jumlah item yang memerlukan tindakan kelulusan oleh eksekutif secara masa nyata (real-time). | | |
| 2 | Notifikasi dipaparkan di papan pemuka (dashboard) dan/atau melalui ikon amaran di bahagian menu utama. | | |
| 3 | Menyokong pautan terus (direct link) ke item berkenaan untuk memudahkan proses semakan dan kelulusan. | | |
| 4 | Mengintegrasi dengan sistem Notifikasi Mudah Alih (Mobile Notification) sedia ada di UMPSA. | | |

---

## BAHAGIAN 2.2: PEMATUHAN & PERKHIDMATAN PROFESIONAL

### 2.2.1 Sesi Taklimat Secara 'Online'
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | UMPSA berhak untuk memanggil petender untuk sesi taklimat secara dalam talian (Google Meet, MS Teams atau seumpamanya) sekiranya perlu. Tarikh dan masa (hari bekerja) yang ditetapkan oleh UMPSA mestilah dipatuhi oleh petender. UMPSA berhak tidak menilai tawaran petender jika petender gagal hadir dalam sesi tersebut. | | |

### 2.2.2 Bengkel Kajian Keperluan Projek
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender yang berjaya/dipilih hendaklah melaksanakan Bengkel bagi membangunkan pelan pelaksanaan projek ini termasuklah meneliti keperluan sistem, proses yang terlibat serta keperluan persekitaran sistem. Bengkel ini akan melibatkan pemilik proses, staf teknikal dan petender yang dilantik. | | |
| 2 | **Bengkel**: Satu (1) sesi bengkel akan diadakan untuk mengenalpasti spesifikasi secara terperinci berkenaan sistem/modul yang terlibat. | | |
| 3 | Kekerapan perbincangan secara fizikal atau dalam talian adalah mengikut keperluan sehingga draf dokumen selesai. | | |

### 2.2.3 Penyediaan Pelan Pelaksanaan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Satu pelan pelaksanaan bertulis yang muktamad perlu dihasilkan oleh petender yang berjaya/dipilih selepas bengkel item 2.2.2 diadakan. | | |
| 2 | Pelan ini perlu turut meliputi aspek organisasi projek, penjadualan pelaksanaan aktiviti projek, 'work breakdown structure (WBS)', 'critical path method (CPM)' diagram, jadual PERT serta metodologi pembangunan. Item-item lain yang perlu dikemukakan akan dibincang bersama dalam bengkel di item 2.2.2. | | |
| 3 | Dokumen pelan pelaksanaan perlu dihantar kepada pihak UMPSA dalam tempoh dua (2) minggu dari tarikh selesai bengkel di item 2.2.2. | | |
| 4 | UMPSA berhak menolak atau mengarah pemindaan pelan pelaksanaan oleh petender yang didapati bersalahan dengan objektif tender ini atau mempunyai kesilapan. | | |

### 2.2.4 Penyediaan Cadangan Rekabentuk UI/UX
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender yang berjaya/dipilih perlu mencadangkan konsep rekabentuk antaramuka pengguna (user interface UI) yang terkini dan moden bertepatan dengan penggunaan semua jenis peranti masa kini termasuk peranti mudah alih. Konsep rekabentuk antaramuka ini perlu dihantar dalam tempoh tiga (3) minggu dari tamat bengkel. | | |
| 2 | Fungsi aplikasi dalam pembangunan modul mestilah bersesuaian dengan kehendak pengguna atau pengalaman pengguna (user experience - UX) supaya setiap modul berfungsi dengan baik dan mesra pengguna. | | |

### 2.2.5 Penerapan Standard
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Pelaksanaan kerja-kerja pembangunan aplikasi dan sistem mestilah mengikut standard terbaik industri dan memenuhi persekitaran UMPSA. | | |
| 2 | Petender perlu menerapkan UMPSA Standard Coding Convention dalam pengaturcaraan semua modul sistem aplikasi yang dipersetujui dalam tender ini. UMPSA akan membekalkan dokumen panduan berkenaan. | | |
| 3 | Sebarang pewujudan 'table' baru atau 'column' baru untuk menyimpan data rekod yang ingin diwujudkan dalam pangkalan data UMPSA perlulah menggunakan 'naming standard' yang betul serta mendapat kelulusan secara bertulis oleh Pentadbir Pangkalan Data UMPSA. | | |
| 4 | Sebarang 'table' baharu yang ingin diwujudkan dalam pangkalan data UMPSA perlulah telah siap dinormalisasikan (normalization). | | |
| 5 | Petender perlu memastikan perisian atau sistem aplikasi yang dibangunkan atau dibekalkan mematuhi standard terbuka (open standard) semasa dan garis panduan Kerajaan Malaysia seperti Kejuruteraan Sistem Aplikasi Sektor Awam (KRISA), Electronic Government Information Technology Policy and Standards (EGIT), Data Dictionary Sektor Awam (DDSA), Management of Information & Communication Technology Security Handbook (MYMIS), Malaysian Government Interoperability Framework (MyGIF), Malaysian Government Interoperability Framework for Open Source Software (MyGIFOSS) dan Garis Panduan IT Outsourcing Agensi - Agensi Sektor Awam. | | |

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
| 4 | Petender perlu membekalkan perisian atau 'package' perisian yang berkaitan untuk membolehkan aplikasi di item 2.1.1 berfungsi seperti mana keperluan UMPSA. Kos pemasangan untuk semua perisian atau 'package' perisian adalah di bawah tanggungjawab pihak petender. | | |
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

### 2.2.11 Polisi Teknologi ICT Hijau
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Jika pembekalan melibat peranti atau peralatan tambahan, ianya perlulah menyokong kepada Polisi Teknologi ICT Hijau. | | |

### 2.2.12 'Tools' Penyelenggaraan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Pihak petender hendaklah menyediakan set perisian atau 'tools' lengkap untuk penyelenggaraan teknologi yang digunakan sistem aplikasi dan pembaikan sistem aplikasi. Set perisian penyelenggaraan juga perlu dipasang dalam satu netbook atau seumpamanya yang ditempatkan di UMPSA bagi tujuan selenggara dan 'ghost disk cloning' sepanjang penggunaan teknologi itu. Petender hendaklah menjamin ketersediaan perkhidmatan selepas jualan untuk semua perisian yang dibekalkan. UMPSA berhak untuk tidak mempertimbangkan dan menolak tawaran petender secara automatik atau membatalkan sekiranya petender gagal membekal mana-mana item yang dinyatakan di atas. | | |

### 2.2.13 Pengujian (Testing)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender dikehendaki menjalankan dan melepasi ujian-ujian berikut sehingga diperakui oleh pengguna dan pegawai UMPSA yang dipertanggungjawabkan: (a) Ujian Penerimaan Pengguna (User Acceptance Test, UAT) di UMPSA sekurang-kurangnya dua (2) kali (b) Semakan 'compliance of server setup' bagi mana-mana server yang dipasang atau dikonfigurasi oleh petender (c) Ujian Penembusan Keselamatan (Security Penetration Test) UMPSA (d) Ujian Penerimaan Akhir (Final Acceptance Test, FAT) | | |
| 2 | Petender dikehendaki menyediakan skrip pengujian (test script) bagi tujuan pelaksanaan pengujian UAT setiap modul sistem aplikasi di dalam tender/projek ini. Skrip perlu dalam Bahasa Melayu. | | |
| 3 | User Acceptance Test (UAT) mesti dilakukan sekurang-kurangnya dua (2) kali. Lokasi UAT ialah di UMPSA dan pasukan pembangunan petender mesti hadir. | | |
| 4 | Final Acceptance Test (FAT) mestilah dijalankan di production server dengan jayanya. Jika gagal, petender mesti bersedia untuk menjalankan pengujian semula. | | |
| 5 | Petender bertanggungjawab untuk membangun, mengimplementasi dan menguruskan semua prosedur semasa melaksanakan UAT dan FAT. | | |
| 6 | Semua dokumen peringkat pengujian mestilah dipersetujui, disahkan dan ditandatangani oleh pihak UMPSA. | | |

### 2.2.14 Pelaksanaan dan Pentauliahan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti memastikan semua sistem aplikasi yang telah dibangunkan dan diintegrasi dapat berfungsi dengan baik sebelum proses pemasangan (deployment) dijalankan. Ia merangkumi: (a) Bebas ralat (b) Keselamatan sistem dan data (c) Pelan sokongan sekiranya berlaku kegagalan semasa instalasi di server UMPSA. | | |
| 2 | Petender mesti bertanggungjawab memastikan sistem yang ditauliahkan terjamin dari segi prestasi dan keselamatannya dalam tempoh jaminan. | | |
| 3 | Petender mesti memastikan sistem yang dibangunkan mempunyai tahap 'interoperability' dan 'scalability' yang baik bagi menyokong perkembangan penggunaannya pada masa hadapan. | | |

### 2.2.15 Latihan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | **Tatacara penggunaan sistem bagi setiap modul dalam sistem yang diintegrasikan (berkonsep train-the-trainer) secara dalaman.** | | |
| 2 | **Pemindahan kepakaran (Transfer of Technology) kepada pasukan teknikal UMPSA bagi setiap modul. Ia akan melibatkan:** (a) Aliran Sistem (System Flow) (b) Data Flow Diagram (DFD) dan Entiti Relationship Diagram (ERD) (c) Teknologi dan tools yang digunakan (d) Sumber rujukan (e) Nota lengkap | | |
| 3 | Petender perlu menjadual, menganjur dan melaksanakan aktiviti latihan yang berkaitan dengan pembangunan aplikasi dan sistem secara 'on-site' bagi tujuan penyelenggaraan aplikasi dan sistem yang dibangunkan atau dibekalkan melalui tender ini. Staf yang terlibat akan dinamakan oleh pihak UMPSA. | | |
| 4 | **Latihan ini meliputi penyelenggaraan berikut:** (a) Latihan penyelenggaraan Sistem Portal Staf (b) Latihan pembangunan dan penyelenggaraan API (Laravel) | | |

### 2.2.16 Dokumentasi
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Manual dan dokumentasi hendaklah disediakan dalam bentuk hard-copy dan soft-copy. Manual dan dokumentasi perlulah dalam Bahasa Melayu. Istilah-istilah teknikal dalam Bahasa Inggeris boleh digunakan mengikut keperluan untuk penerangan maksud/konsep lebih baik. | | |
| 2 | Semua dokumen teknikal perlu mendapat kelulusan pihak teknikal UMPSA sebelum segala kerja-kerja pembangunan sistem bermula. | | |
| 3 | Petender yang berjaya mesti menyerahkan semua dokumentasi berikut kepada UMPSA sebagai salah satu keperluan dan rujukan projek: (a) Pelan pelaksanaan projek (b) Cadangan rekabentuk UI/UX (c) System Requirement Specification (SRS) (d) User Acceptance Test (UAT) (e) Final Acceptance Test (FAT) (f) Manual Pengguna (g) Lain-lain dokumen yang tidak dinyatakan di atas (yang berkaitan) | | |

### 2.2.17 Pengurusan Projek
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti sedia, komited dan mampu menghadiri mesyuarat pengurusan projek di UMPSA sekurang-kurangnya pada tempoh sebulan sekali ataupun pada mana-mana tarikh dan masa yang ditetapkan oleh UMPSA. Kehadiran ini termasuk bagi mana-mana keperluan pemasangan (setup), pengujian sistem aplikasi mahupun 'production deployment' sistem aplikasi di dalam projek ini. | | |
| 2 | Petender atau ahli pasukan petender yang menghadiri mesyuarat pengurusan projek perlulah berkelayakan, berkemampuan dalam komunikasi profesional, memahami teknikal projek, dapat melapor serta boleh membuat keputusan terus (wakil kuasa penuh) apabila diminta dalam mesyuarat. Kegagalan petender atau sekutu mematuhi terma ini dianggap sebagai pelanggaran kritikal syarat kontrak tender ini dan boleh didenda. | | |
| 3 | Petender mesti menyediakan senarai lengkap pasukan projek yang terlibat beserta peranan setiap ahli. Ahli pasukan mestilah sama atau setara keupayaan kompetensinya sepertimana dalam tawaran dan struktur awal di LAMPIRAN A-01. Sebarang pertukaran ahli pasukan petender semasa projek telah bermula atau sedang berjalan perlu dimaklumkan oleh petender secara rasmi dan mendapat persetujuan bertulis UMPSA. | | |
| 4 | Pengurus projek petender mesti mempunyai pengalaman mengurus sekurang-kurangnya tiga (3) projek yang setara dalam teknologi yang sama dengan tender ini. Sila senaraikan 3 projek berkenaan di sini atau melalui template profil staf/pengurus di LAMPIRAN A-02. | | |
| 5 | Petender mesti mempunyai staf yang berpengalaman dalam menganalisa serta membangunkan pelan pelaksanaan projek. Sila jawab di sini dan melalui template profil staf di LAMPIRAN A-02. | | |
| 6 | Petender perlu menyediakan satu platform yang khusus secara atas talian untuk tujuan pemantauan dan pengurusan projek dan segala kos yang berkaitan adalah dibawah tanggungjawab Petender. | | |
| 7 | UMPSA tidak menyediakan akses VPN kepada petender. Oleh itu petender mestilah merancang pelaksanaan projek ini mengikut kesesuaian perkara ini. | | |
| 8 | Petender mesti menempatkan sekurang-kurangnya satu (1) unit komputer desktop (PC) di premis UMPSA bagi tujuan pengurusan projek atau 'remote access'. | | |
| 9 | Sebarang bentuk kemudahan 'remote access' atau peralatan di UMPSA adalah wajib tertakluk kepada syarat/peraturan penggunaannya di UMPSA yang petender perlu akur akannya. | | |
| 10 | Segala surat-menyurat, mesyuarat serta minit mesyuarat dalam projek ini adalah dalam Bahasa Melayu. Salinan dalam Bahasa Inggeris boleh disediakan jika perlu. | | |

### 2.2.18 Sokongan Teknikal
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Petender mesti menyediakan sokongan teknikal untuk sebarang pertanyaan dan masalah yang dihadapi oleh UMPSA semasa dalam Tempoh Jaminan. | | |
| 2 | Petender mesti menyediakan dokumen yang memperincikan cadangan Service Level Agreement (SLA) bersama dengan tatacara Pengurusan Aduan. | | |
| 3 | **SLA sokongan teknikal tidak terhad seperti berikut:** (a) Kadar response time dalam tempoh 4 jam melalui telefon dan email (b) Masa penyelesaian masalah dalam tempoh tiga (3) hari (c) Lawatan On-site tanpa had bagi Severity 1 (Mengikut keperluan) | | |

### 2.2.19 Penukaran Modul Yang Setara
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Bagi mana-mana modul sistem yang dipersetujui dalam sebutharga ini yang sepatutnya dibangunkan oleh pentender tetapi telah dibangunkan secara dalaman oleh pihak teknikal UMPSA, maka UMPSA berhak membuat sebarang penukaran dengan mana-mana modul/sistem yang setara. | | |

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
| 1 | Sila isikan template LAMPIRAN A-01 dengan nama kakitangan/anggota pasukan petender yang akan melaksanakan projek di bawah tender ini nanti. | | |

#### 3.2.2 Pengalaman Ahli Pasukan
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 1 | Sila isi maklumat pengalaman SETIAP kakitangan/ahli pasukan petender (yang dinyatakan di item 3.2.1) menggunakan template di LAMPIRAN A-02. | | |

---

## BAHAGIAN 4.0: PENGHANTARAN DAN MASA

### 4.1 Technical Deliverables (4.1.1 - 4.1.14)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
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

### 4.2 Tempoh Siap (4.2.1 - 4.2.3)
| BIL | BUTIRAN KERJA / SPESIFIKASI JABATAN | MAKLUMBALAS / SPESIFIKASI SYARIKAT | BUKTI / RUJUKAN |
|-----|--------------------------------------|-------------------------------------|-----------------|
| 4.2.1 | Semua kerja-kerja yang terlibat mestilah dilaksanakan mengikut tempoh yang ditetapkan iaitu maksimum lapan bulan (8) bulan. | | |
| 4.2.2 | Petender perlu menghantar pelan dan jadual pelaksanaan keseluruhan projek (menggunakan Gantt Chart) yang merangkumi kerja-kerja: (i) Pelaksanaan projek (ii) Pelaksanaan latihan (iii) Serahan dokumentasi projek (iv) Lain-lain perkara yang tidak dinyatakan di atas (yang berkaitan) | | |
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
| 4.4.2 | Tempoh jaminan bagi kerja-kerja, pemasangan dan konfigurasi, integrasi, pengujian, pelaksanaan dan pentauliahan adalah satu (1) tahun bermula setelah penerimaan akhir (Final Acceptance Test FAT) telah dilakukan dengan jayanya. | | |
| 4.4.3 | Petender perlu menyediakan platform yang terurus secara atas talian bagi tujuan pengurusan aduan dan isu-isu sepanjang tempoh jaminan. | | |

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
