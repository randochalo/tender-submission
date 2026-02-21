# JADUAL PENENTUAN TEKNIKAL / TECHNICAL COMPLIANCE SCHEDULE

**Tender:** TSH-2613 - Sistem Pengurusan Mesyuarat  
**No. Sebut Harga:** UMPSA/BEND/SH/2026(2)  
**No. JTICT:** JTICT/2025 (29)  
**Jabatan:** DiTec  
**Form:** BEND/UP/007

---

## ARAHAN UMUM / GENERAL INSTRUCTIONS

Dalam menjawab kepada spesifikasi teknikal ini, perkataan seperti "OK", "MAKLUM", "SETUJU", "PATUH", "NOTED", "AGREED", "COMPLY" semata-mata atau yang seumpamanya **tidak boleh digunakan**. Walau bagaimanapun, jika perkataan berkenaan perlu digunakan, rujukan yang jelas hendaklah diberikan.

Petender perlu menyediakan katalog/brosur/risalah/dokumen untuk mengesahkan semua kenyataan pematuhan terhadap spesifikasi teknikal peralatan sebagai dokumen sokongan.

---

## 2.0 SPESIFIKASI TEKNIKAL

### 2.1 SKOP KERJA

#### 2.1.1 Keperluan Teknikal Umum

| No. | Keperluan / Requirement | Maklumbalas Syarikat | Evidence/Rujukan |
|-----|------------------------|---------------------|------------------|
| A | Membangunkan semua modul/menu yang dinyatakan di dalam perkara 2.1.2, merupakan kajian keperluan awal. Dokumen kajian keperluan (user requirement specification) yang akan dimuktamadkan dalam bengkel merupakan dokumen akhir yang akan dijadikan rujukan di dalam pembangunan sistem. Rujuk perkara 2.2.2 | | |
| B | Menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API (application programming interface) untuk setiap modul. Ini termasuk penggunaan Eloquent ORM. | | |
| C | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| D | Integrasi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa. | | |
| D(i) | Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim | | |
| D(ii) | Integrasi dengan keputusan E Voting sedia ada. | | |
| E | Membangunkan antara muka pengguna dalam bentuk responsive web design menggunakan Bootstrap, Tailwind, atau teknologi setara, serta menambah ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| F | Menggunakan pangkalan data Oracle yang sedia ada di UMPSA. | | |
| G | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| H | Menggunakan container technology sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| I | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery yang terdapat di UMPSA. | | |
| J | Petender perlu menyediakan persekitaran pembangunan sistem sendiri bagi tujuan pelaksanaan projek ini. | | |
| K | Konfigurasi hendaklah mematuhi piawaian keselamatan, keperluan ISMS, dan amalan DevOps terbaik. | | |
| L | Mempunyai fungsi memuat naik dokumen dan berupaya menjana laporan. | | |
| M | Menggunakan Power BI dengan memanfaatkan lesen institusi sedia ada, bagi tujuan pembangunan dashboard tanpa melibatkan sebarang kos pelesenan tambahan kepada pihak UMPSA. | | |
| N | Petender hendaklah melaksanakan proses migrasi data daripada sistem sedia ada ke sistem baharu bagi memastikan kesinambungan operasi tanpa gangguan. | | |
| O | Melaksanakan integrasi dengan sistem dalaman berikut: | | |
| O(i) | MyUMPSA-ID Single Sign-On (SSO) | | |
| O(ii) | Redis | | |
| O(iii) | Email gateway | | |
| O(iv) | File storage | | |
| O(v) | API | | |
| O(vi) | Notification | | |
| O(vii) | Modul Executive Approval | | |
| P | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| Q | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| R(i) | Menyediakan latihan kepada pentadbir sistem (IT) | | |
| R(ii) | Menyediakan latihan kepada pengguna akhir (end-users) | | |
| S | Membangun, menguji dan mentauliah sistem yang dibangunkan. | | |
| T | Menyerahkan kod sumber penuh (full source code) sistem beserta dokumentasi berkaitan bagi tujuan pemilikan penuh oleh pihak UMPSA. | | |
| U | Menyediakan dan mengkonfigurasi persekitaran pelayan bagi staging, development, disaster recovery (DR), dan production, mengikut spesifikasi yang ditetapkan. | | |
| V | Melaksanakan proses migrasi dan pelaksanaan penuh sistem baharu sehingga siap sedia untuk operasi secara langsung (go-live), termasuk pengesahan akhir bersama pihak UMPSA. | | |

---

#### 2.1.2 Keperluan Fungsian Modul/Menu

| No. | Modul / Fungsi | Maklumbalas Syarikat | Evidence/Rujukan |
|-----|---------------|---------------------|------------------|
| **2.1.2.1** | **Login** | | |
| | Modul ini mengesahkan identiti pengguna melalui SSO server (Keycloak). Selain itu pengguna boleh juga log masuk aplikasi melalui pengesahan Google. | | |
| **2.1.2.2** | **E-Authorization** | | |
| | Modul ini bertujuan bagi memberi akses kepada keseluruhan sistem mesyuarat. | | |
| a | Memberikan akses kepada pengguna dan pentadbir secara berperingkat (tiering). | | |
| b | Sistem mempunyai keupayaan untuk audit trail. | | |
| c | Integrasi dengan Executive approval / notifikasi / tindakan di dalam ecomm UMPSA bagi semua modul sistem ini yang memerlukan tindakan ahli / staff UMPSA berkaitan mesyuarat | | |
| d | Menu kebenaran berkaitan pemantauan, kelulusan mesyuarat dan penyelenggaraan mesyuarat di bawahnya | | |
| **2.1.2.3** | **Meeting Registration** | | |
| i | **Set up tier of meeting** - Modul ini bertujuan bagi penetapan pengurusan semua mesyuarat-mesyuarat di dalam universiti. | | |
| ii | **Meeting Set-Up: Lazim / Khas & Edaran** | | |
| ii-a | Permohonan pendaftaran mesyuarat | | |
| ii-b | Kelulusan pendaftaran | | |
| ii-c | Penetapan peringkat mesyuarat (peringkat 1, 2,.. n) | | |
| ii-d | Pendaftaran sesi mesyuarat | | |
| ii-e | Memberikan akses kepada pengguna dan pentadbir | | |
| iii | **Panggilan Mesyuarat (Lazim/Khas)** - Modul ini bertujuan bagi pemakluman kepada ahli mesyuarat dan majlis/jk berkenaan cadangan tarikh, tempat dan maklumat lain berkenaan mesyuarat yang akan diadakan melalui e-mel. | | |
| iv | **Mesyuarat Secara Edaran** - Memudahkan proses mesyuarat tanpa kehadiran secara fizikal, membolehkan dokumen diedarkan kepada ahli, dan membolehkan ahli memberi maklum balas, komen atau keputusan dalam tempoh masa ditetapkan secara dalam talian. | | |
| iv-a | Pemakluman Mesyuarat Secara Edaran dan dapatkan keputusan ahli. | | |
| iv-b | Paparan pada modul executive approval sedia ada bagi tindakan ahli Senat / Mesyuarat. | | |
| iv-c | Peringatan tempoh maklumbalas dan tindakan mengikut ketetapan tadbir urus mesyuarat. | | |
| v | **Meeting Notice** - Pengeluaran notis panggilan mesyuarat berdasarkan tempoh yang telah ditetapkan mengikut tadbir urus mesyuarat. | | |
| **2.1.2.4** | **e-Takwim** | | |
| | Kekal menggunakan sistem sedia ada, walau bagaimanapun perlu ada integrasi sistem sedia ada dan sistem baru yang akan dibangunkan. Sistem baru mampu memaparkan jadual mesyuarat dari sistem E Takwim | | |
| i | **Taqwim Set up** | | |
| i-a | Sumber data dari etakwim ecomm/ appointment dalam ecomm.(sistem sedia ada) | | |
| i-b | Paparan di dalam dashboard Menu mesyuarat | | |
| **2.1.2.5** | **Module E-Committee** | | |
| | Menguruskan maklumat keahlian mesyuarat secara berpusat, termasuk daftar, kemas kini, penamatan, rekod sejarah pelantikan dan penjanaan laporan berkaitan. | | |
| i | **Appointment (Perlantikan)** | | |
| i-a | Mendaftarkan keahlian mesyuarat mengikut tempoh pelantikan | | |
| i-b | Integrasi data staf bagi tujuan mendaftarkan keahlian mengikut tempoh pelantikan | | |
| i-c | Perkara yang diperlukan antaranya Nama, Jawatan Hakiki & Jawatan Giliran, ID Staf, Fakulti, Kelulusan Akademik, Tempoh Jawatan dan lain-lain | | |
| i-d | Membantu sekretariat dalam memantau tempoh pelantikan dan penamatan dengan sistem alert | | |
| i-e | Statistik kehadiran / tidak hadir ahli mesyuarat bulanan / tahunan | | |
| i-f | Janaan nama ahli bagi pembangunan minit mesyuarat berdasarkan format minit mesyuarat | | |
| i-g | Integrasi data sistem HoD UMPSA bagi Paparan rujukan didalam Ecomm Sistem HoD | | |
| i-h | Paparan tempoh lantikan | | |
| i-i | Menu yang diperlukan, menyimpan rekod keahlian mesyuarat untuk rujukan masa hadapan. Contoh bagi tujuan audit pematuhan tadbir urus Senat. | | |
| i-j | Boleh menjana dan menghantar surat kepada semua ahli mesyuarat. Penyediaan surat keahlian antaranya pelantikan, penamatan dan penghargaan dan lain-lain secara E-Letter digital. | | |
| ii | **Committee Set-Up** | | |
| ii-a | Modul ini menetapkan keahlian sesuatu mesyuarat berdasarkan ToR Mesyuarat tersebut | | |
| ii-b | Antara ciri-ciri perlu ada ialah: nama, jawatan, id no, tempoh pelantikan dalam jawatankuasa, jawatan gilliran pentadbiran yang disandang dan lain-lain | | |

---

*Nota: Rujuk LAMPIRAN A-01 untuk maklumat lanjut mengenai keperluan fungsian modul.*

---

## RUJUKAN HALAMAN / PAGE REFERENCES

| Seksyen | Muka Surat | Nota |
|---------|-----------|------|
| 2.0 Spesifikasi Teknikal | 14 | Halaman permulaan Section 2.0 |
| 2.1 Skop Kerja | 15-19 | Keperluan teknikal umum |
| 2.1.2 Keperluan Fungsian | 20-25 | Modul/Menu specifications |

---

**Disediakan oleh:**

Tandatangan & Cop: _________________________

Nama: _________________________

Jawatan: _________________________

Tarikh: _________________________
