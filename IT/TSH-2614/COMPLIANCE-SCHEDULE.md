# JADUAL PENENTUAN TEKNIKAL / TECHNICAL COMPLIANCE SCHEDULE

**Tender:** TSH-2614 - Sistem Portal Staf (eCommunity)  
**No. Sebut Harga:** UMPSA/BEND/SH/2026(3)  
**No. JTICT:** JTICT/2025 (30)  
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
| a | Menggunakan teknologi Laravel framework (https://laravel.com) versi terkini untuk membangun dan menyediakan modul dan API (application programming interface) untuk setiap modul. Ini termasuk penggunaan Eloquent ORM. | | |
| b | Melanggan Laravel Shift (https://laravelshift.com) edisi Shifty Plan (Latest Single) untuk tempoh tiga (3) tahun dan mengkonfigurasinya di repo sistem dan API berkaitan. | | |
| c | Replikasi, migrasi logik dan fungsi daripada sistem Java JSP kepada PHP Laravel terkini serta ditambahbaik dengan ciri-ciri moden selaras dengan teknologi semasa. | | |
| d | Membangunkan sistem menggunakan teknologi antaramuka pengguna (UI) web dan panel pentadbir yang moden, ciri-lengkap, sumber terbuka (OSS) dan mudah diselenggara, dengan keutamaan menggunakan Filament PHP atau setara. | | |
| e | Sistem ini mestilah mempunyai ciri-ciri kebolehgunaan (usability features) seperti searchable menu, navigasi yang lebih intuitif, dan paparan mesra peranti mudah alih. | | |
| f | Menggunakan pangkalan data Oracle (minimum versi 19c) yang sedia ada di UMPSA. | | |
| g | Menggunakan seni bina MVVM, MVC, atau setara dalam pembangunan sistem dan aplikasi, dengan mengutamakan reliability dan scalability sistem serta aplikasi pada masa akan datang. | | |
| h | Menggunakan teknologi kontena aplikasi (application container technology) sebagai asas dalam pembangunan sistem bagi memastikan kebolehskalaan, kebolehgunaan semula, dan kemudahan penyelenggaraan sistem. | | |
| i | Melaksanakan konfigurasi dan pemasangan pada persekitaran Production, Staging, Development, dan Disaster Recovery. Persekitaran pembangunan sistem perlu disediakan oleh petender. | | |
| j | Melaksanakan integrasi dengan sistem dalaman berikut: | | |
| j-i | MyUMPSA-ID Single Sign-On (SSO) | | |
| j-ii | Redis | | |
| j-iii | Email gateway | | |
| j-iv | File storage | | |
| j-v | API | | |
| j-vi | Notification Mobile | | |
| k | Menjalankan UAT (User Acceptance Test) dan FAT (Final Acceptance Test). Pelan UAT/FAT serta pelaporan mestilah disediakan. | | |
| l | Menyediakan dokumentasi teknikal penuh termasuk seni bina sistem, manual pengguna, manual pentadbir, dan dokumen konfigurasi pelayan. | | |
| l-i | Latihan kepada pentadbir sistem (IT) | | |
| l-ii | Latihan kepada pengguna akhir (end-users) | | |
| m | Membangun, menguji dan mentauliah Sistem Portal Staf. | | |
| m-i | Serahan penuh kod sumber. | | |
| m-ii | Konfigurasi pelayan staging, development, DR dan production. | | |
| m-iii | Migrasi dan pelaksanaan penuh sistem baharu. | | |

---

#### 2.1.2 Keperluan Fungsian

| No. | Modul / Fungsi | Maklumbalas Syarikat | Evidence/Rujukan |
|-----|---------------|---------------------|------------------|
| **a** | **Modul Login** | | |
| | **1. Login (Authentication)** - Modul ini adalah untuk menyemak dan mendapat pengesahan identiti pengguna melalui SSO and Identity Provider (IdP) Keycloak UMPSA sedia ada. Selain itu, pengguna boleh juga log masuk ke aplikasi melalui pengesahan Google Sign-in. | | |
| **b** | **Modul Temujanji dan Kalendar** | | |
| | **i. Pengurusan Temujanji** | | |
| b-i-1 | Pengguna boleh menambah, mengubah, atau memadam temujanji. Senarai peserta perlulah boleh dipilih daripada/mengikut kumpulan pengguna dalam Organizational Unit (OU) atau user groups di Active Directory (AD) UMPSA. | | |
| b-i-2 | Pengguna boleh melihat semula senarai temujanji yang telah dibuat. | | |
| b-i-3 | Sistem memaparkan kalendar bagi memudahkan pemilihan tarikh dan masa. | | |
| b-i-4 | Sistem juga perlu membuat semakan dengan Google Calendar bagi mengelakkan pertindihan jadual sebelum temujanji disimpan. | | |
| | **ii. Papar Kalendar** | | |
| b-ii-1 | Pengguna boleh melihat paparan kalendar dalam format harian, mingguan, atau bulanan. | | |
| b-ii-2 | Paparan kalendar memaparkan semua temujanji yang telah dijadualkan berserta statusnya. | | |
| b-ii-3 | Pengguna boleh menyemak dan melihat temujanji yang diselaraskan (sync) dengan Google Calendar. | | |
| b-ii-4 | Pengguna boleh menjana laporan dalam bentuk pdf. | | |
| **c** | **Modul Memo** | | |
| c-1 | Pengguna boleh melihat senarai memo yang diterima. | | |
| c-2 | Fungsi carian disediakan untuk mencari memo berdasarkan kata kunci, tarikh, atau pengirim/penerima. | | |
| c-3 | Pengguna boleh mengurus memo mengikut folder khas yang dicipta oleh pengguna. | | |
| **d** | **Modul Pengumuman** | | |
| d-1 | Pengguna boleh melihat senarai pengumuman yang aktif. | | |
| d-2 | Pengguna boleh menambah, mengubah, atau memadam pengumuman. | | |
| d-3 | Fungsi carian disediakan untuk mencari pengumuman berdasarkan kata kunci, tarikh, kategori atau pengirim. | | |
| d-4 | Pengumuman yang tidak lagi aktif boleh diarkibkan untuk rujukan pada masa hadapan. | | |
| **e** | **Pengurusan Pengguna** | | |
| | **1. Kebenaran Pengguna (User Authorization)** - Sistem mengesahkan identiti pengguna melalui proses log masuk sebelum membenarkan akses ke dalam sistem. | | |
| | **2. Keistimewaan Pengguna (User Privilege)** - Setiap pengguna diberikan tahap akses tertentu berdasarkan peranan (role) yang ditetapkan, contohnya akses untuk melihat, menambah, mengubah, atau memadam data. | | |
| | **3. Keistimewaan Kumpulan (Group Privilege)** - Pengguna boleh diurus secara berkumpulan dengan pemberian keistimewaan akses yang sama kepada semua ahli kumpulan tersebut. | | |
| | **4. Audit Log Aktiviti Pengguna** - Sistem merekod semua aktiviti pengguna termasuk log masuk, log keluar, penambahan, pengubahan, dan pemadaman data untuk tujuan pengesanan serta keselamatan. Memaparkan laporan atau statistik penggunaan modul dalam sistem. | | |
| | **5. Senarai Pengguna** - Sistem memaparkan senarai semua pengguna beserta maklumat asas. Kemudahahan fungsi carian juga perlu disediakan. | | |
| **f** | **Modul Tetapan** | | |
| | **1. Pengurusan Kumpulan (Group)** - Membolehkan pengguna mengurus kumpulan bagi tujuan pengelompokan pengguna dan | | |

---

## RUJUKAN HALAMAN / PAGE REFERENCES

| Seksyen | Muka Surat | Nota |
|---------|-----------|------|
| 2.0 Spesifikasi Teknikal | 13-14 | Halaman permulaan Section 2.0 |
| 2.1 Skop Kerja | 14-17 | Keperluan teknikal umum |
| 2.1.2 Keperluan Fungsian | 18-22 | Modul/Fungsi specifications |

---

**Disediakan oleh:**

Tandatangan & Cop: _________________________

Nama: _________________________

Jawatan: _________________________

Tarikh: _________________________
