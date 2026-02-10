# JADUAL 1A: KERTAS CADANGAN PEMBANGUNAN SISTEM ePINGAT NEGERI SELANGOR

**No. Tender:** T/SUKSEL/04-2026  
**Petender:** Sinergi Elit Sdn Bhd (SESB)  
**Tarikh:** 31 Januari 2026

---

## 1.0 OBJEKTIF

### 1.1 Objektif Utama Projek

Pembangunan Sistem ePingat Negeri Selangor bertujuan untuk memodenkan dan mengautomasikan proses pengurusan pencalonan, penilaian, dan pengurniaan Darjah Kebesaran, Bintang Kebesaran, serta Pingat Negeri Selangor. Sistem ini akan menjadi tunjang digitalisasi pengurusan anugerah kerajaan negeri yang cekap, telus, dan berintegriti tinggi.

### 1.2 Objektif Strategik

| Objektif | Penerangan | Penanda Aras Kejayaan |
|----------|------------|----------------------|
| **O1: Digitalisasi Penuh** | Memindahkan keseluruhan proses permohonan daripada berasaskan kertas kepada atas talian | 100% permohonan diterima secara digital |
| **O2: Efisiensi Proses** | Mengurangkan masa pemprosesan permohonan daripada permohonan hingga pengurniaan | Pengurangan 60% masa pemprosesan |
| **O3: Integriti Data** | Memastikan ketepatan dan keselamatan data penerima serta rekod pengurniaan | Zero data loss, 99.9% ketepatan migrasi |
| **O4: Kebolehcapaian** | Menyediakan sistem yang mudah diakses oleh semua pihak berkepentingan | Sokongan 24/7, responsif merentasi peranti |
| **O5: Integrasi Kerajaan** | Sambungan dengan sistem kerajaan sedia ada untuk pengesahan dan tapisan | Integrasi 6 sistem utama (SPRM, Insolvensi, ROS, HRMIS, myIDENTITY, Laman Web Darjah Kebesaran) |
| **O6: Pematuhan Perundangan** | Memastikan sistem mematuhi Garis Panduan Pencalonan serta dasar keselamatan ICT | 100% pematuhan garis panduan dan dasar keselamatan |

### 1.3 Matlamat Teknikal

1. **Kebolehgunaan (Usability):** Mewujudkan antara muka pengguna yang intuitif dengan kadar pembelajaran minimum
2. **Keselamatan (Security):** Melaksanakan pertahanan mendalam (defense-in-depth) dengan pensijilan VAPT CREST
3. **Ketersediaan (Availability):** Menjamin ketersediaan sistem 99.9% dengan SLA yang ketat
4. **Keterskalaan (Scalability):** Membolehkan sokongan 1000+ pengguna serentak dan peluasan masa depan
5. **Kebolehpeliharaan (Maintainability):** Menyediakan dokumentasi lengkap dan TOT untuk kakitangan PSUK

---

## 2.0 CADANGAN FRAMEWORK / REKABENTUK SISTEM / PROTOTAIP

### 2.1 Pendekatan Reka Bentuk: "Accelerated Baseline"

Kami mengamalkan pendekatan **Accelerated Baseline** di mana 90% sistem telah direka bentuk dan diuji dalam projek kerajaan yang serupa. Ini bermakna:
- **Bukan projek dari sifar** — Kami membangun atas asas sistem pengurusan anugerah yang telah terbukti
- **Risiko dikurangkan** — Komponen utama telah digunakan dalam persekitaran pengeluaran
- **Masa ke pasaran lebih pantas** — Fokus kepada penyesuaian bukannya pembangunan asas

### 2.2 Arkitektur Sistem Keseluruhan

```
┌─────────────────────────────────────────────────────────────────┐
│                        PRESENTATION LAYER                       │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐  │
│  │ Web Browser  │  │ Mobile App   │  │ Admin Dashboard      │  │
│  │ (Responsive) │  │ (PWA/iOS/    │  │ (Vue.js + Tailwind)  │  │
│  │              │  │  Android)    │  │                      │  │
│  └──────────────┘  └──────────────┘  └──────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│                      APPLICATION LAYER                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              API Gateway (Kong/AWS API GW)              │   │
│  │         Rate Limiting │ Auth │ Logging │ Routing         │   │
│  └─────────────────────────────────────────────────────────┘   │
│                              │                                  │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┐ │
│  │   Modul      │    Modul     │    Modul     │    Modul     │ │
│  │   Laman      │    Urus      │    Penilaian │    Laporan   │ │
│  │   Utama      │    Setia     │    & Tapisan │              │ │
│  └──────────────┴──────────────┴──────────────┴──────────────┘ │
│                              │                                  │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │     Service Layer (Business Logic - Laravel 10.x)       │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │   │
│  │  │ Workflow │ │ Notification│ │ Audit   │ │ Report  │   │   │
│  │  │ Engine   │ │ Service    │ │ Service │ │ Engine  │   │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│                        DATA LAYER                               │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────────┐  │
│  │ MySQL 8.0    │  │ Redis Cache  │  │ File Storage         │  │
│  │ (Primary DB) │  │ (Session/    │  │ (Documents/Images)   │  │
│  │              │  │  Cache)      │  │                      │  │
│  └──────────────┘  └──────────────┘  └──────────────────────┘  │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              Read Replicas (Reporting)                  │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│                    INTEGRATION LAYER                            │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌────────┐ │
│  │  SPRM    │ │Insolvensi│ │   ROS    │ │ HRMIS    │ │myIDENTITY│
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘ └────────┘ │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                        │
│  │ Laman Web│ │myDigital │ │  SMS/    │                        │
│  │ Darjah   │ │   ID     │ │ WhatsApp │                        │
│  │Kebesaran │ │          │ │ Gateway  │                        │
│  └──────────┘ └──────────┘ └──────────┘                        │
└─────────────────────────────────────────────────────────────────┘
```

### 2.3 Pola Reka Bentuk (Design Patterns)

| Pola | Penggunaan | Faedah |
|------|------------|--------|
| **MVC (Model-View-Controller)** | Struktur aplikasi utama | Pemisahan kebimbangan, penyelenggaraan mudah |
| **Repository Pattern** | Akses data | Pengujian unit mudah, tukar pangkalan data tanpa impak |
| **Service Layer** | Logik perniagaan | Penggunaan semula kod, dokumentasi automatik |
| **Event-Driven** | Proses latar belakang | Kadar tindak balas pantas, skalabiliti |
| **CQRS** | Laporan vs Transaksi | Prestasi bacaan dioptimumkan |
| **Multi-Tenant** | Pengasingan penyewa | Peluasan masa depan ke jabatan lain |

### 2.4 Prototaip Sistem

Kami akan membangunkan prototaip interaktif yang merangkumi:

#### 2.4.1 Skop Prototaip
1. **Modul Laman Utama** — Paparan responsif dengan navigasi utama
2. **Modul Permohonan** — Aliran pendaftaran dan penghantaran permohonan
3. **Modul Dashboard Urus Setia** — Paparan statistik dan senarai permohonan
4. **Proses Penilaian** — Aliran kelulusan 4 peringkat

#### 2.4.2 Teknologi Prototaip
- **Frontend:** Figma untuk wireframe, Vue.js 3 untuk prototaip interaktif
- **Backend:** Laravel 10.x dengan pangkalan data sementara
- **Hosting:** VPS staging untuk akses panel penilai
- **Tempoh:** 2 minggu sebelum pembentangan

#### 2.4.3 Kriteria Penilaian Prototaip
| Kriteria | Penjelasan |
|----------|------------|
| **Fungi Keseluruhan** | Samada aliran kerja utama boleh dilaksanakan |
| **Kebolehgunaan** | Tahap kemudahan penggunaan oleh panel |
| **Prestasi** | Kelajuan tindak balas dan muatan |
| **Keselamatan** | Kawalan akses dan pengesahan |
| **Responsif** | Paparan merentasi peranti berbeza |

---

## 3.0 CADANGAN OPERASI TEKNIKAL SERVER

### 3.1 Senarai Timbal Teknologi

| Komponen | Cadangan | Versi | Justifikasi |
|----------|----------|-------|-------------|
| **Sistem Pengoperasian** | Ubuntu Server | 22.04 LTS | Sokongan jangka panjang (sehingga 2027), kestabilan terbukti dalam persekitaran kerajaan |
| **Bahasa Pengaturcaraan** | PHP | 8.2.x | Prestasi JIT, keselamatan lanjutan, sokongan jenis |  
| **Framework Aplikasi** | Laravel | 10.x | Gred perusahaan, ekosistem kaya, sokongan keselamatan terbina |
| **Pangkalan Data** | MySQL | 8.0 | Sokongan JSON, enjin penyimpanan InnoDB, replikasi asli |
| **Pelayan Web** | Nginx | 1.24.x | Prestasi tinggi, penggunaan sumber rendah, kebolehan pengendalian konkurensi |
| **Cache & Session** | Redis | 7.x | Kelajuan ultra-pantas, struktur data kaya, ketekalan |
| **Pengurus Pakej** | Composer | 2.6.x | Pengurusan pergantungan PHP standard industri |
| **Pensijian SSL** | Let's Encrypt | Auto-renewal | Percuma, automatik, dipercayai semua pelayar |

### 3.2 Keperluan Spesifikasi Server

#### 3.2.1 Persekitaran Pembangunan (Development)
| Komponen | Spesifikasi Minimum |
|----------|---------------------|
| Server Aplikasi | 2 vCPU, 4GB RAM, 50GB SSD |
| Server Pangkalan Data | 2 vCPU, 4GB RAM, 50GB SSD |
| Sistem Pengoperasian | Ubuntu 22.04 LTS |
| Tujuan | Pembangunan fitur, ujian unit, integrasi |

#### 3.2.2 Persekitaran Pengeluaran A (Production A)
| Komponen | Spesifikasi Minimum |
|----------|---------------------|
| Load Balancer | Nginx, 2 vCPU, 2GB RAM |
| Server Aplikasi (x2) | 4 vCPU, 8GB RAM, 100GB SSD setiap satu |
| Server Pangkalan Data (Master) | 4 vCPU, 16GB RAM, 200GB SSD |
| Redis Cache Server | 2 vCPU, 4GB RAM, 20GB SSD |
| Backup Storage | 500GB (NAS/S3-compatible) |

#### 3.2.3 Persekitaran Pengeluaran B (Production B - DR)
| Komponen | Spesifikasi Minimum |
|----------|---------------------|
| Konfigurasi | Sama seperti Production A |
| Lokasi | Pusat Data sekunder |
| Fungsi | Disaster Recovery, failover automatik |

### 3.3 Capacity Planning

| Aspek | Analisis | Projeksi |
|-------|----------|----------|
| **Pengguna Berdaftar** | 5,000 pengguna aktif tahun pertama | Pertumbuhan 20% setahun |
| **Pengguna Serentak** | 500 pengguna puncak | Penskalaan kepada 1000+ |
| **Permohonan Tahunan** | 10,000 permohonan | Peningkatan 15% setahun |
| **Storan Dokumen** | 100GB tahun pertama | Peningkatan 50GB/tahun |
| **Lebar Jalur** | 100Mbps dedikasi | Kebolehan peningkatan |
| **Backup** | Daily: 50GB, Weekly: 200GB, Monthly: 500GB | 5 tahun retention |

### 3.4 Diagram Infrastruktur

```
                                    INTERNET
                                       │
                    ┌──────────────────┼──────────────────┐
                    │                  │                  │
              [Firewall]         [Firewall]         [WAF/CDN]
                    │                  │                  │
              [SSL/TLS]            [SSL/TLS]          [SSL/TLS]
                    │                  │                  │
            ┌───────┴───────┐   ┌──────┴──────┐   ┌──────┴──────┐
            │   PRODUCTION  │   │ PRODUCTION  │   │    DR       │
            │       A       │   │     B       │   │   SITE      │
            │  (Primary)    │   │  (Backup)   │   │ (Secondary) │
            └───────┬───────┘   └──────┬──────┘   └──────┬──────┘
                    │                  │                  │
         ┌──────────┴──────────┐       │       ┌──────────┴──────────┐
         │   Load Balancer     │◄──────┼──────►│   Load Balancer     │
         │   (Nginx/HAProxy)   │       │       │   (Nginx/HAProxy)   │
         └──────────┬──────────┘       │       └──────────┬──────────┘
                    │                  │                  │
       ┌────────────┼────────────┐     │     ┌────────────┼────────────┐
       │            │            │     │     │            │            │
  [App Svr 1] [App Svr 2]  [App Svr 3] │  [App Svr 1] [App Svr 2]  [App Svr 3]
       │            │            │     │     │            │            │
       └────────────┼────────────┘     │     └────────────┼────────────┘
                    │                  │                  │
            ┌───────┴───────┐   ┌──────┴──────┐   ┌───────┴───────┐
            │ MySQL Primary │◄──►│ MySQL Replica│◄──►│ MySQL Replica │
            │   (Master)    │   │   (Hot)      │   │   (DR Site)   │
            └───────┬───────┘   └──────┬──────┘   └───────────────┘
                    │                  │
            ┌───────┴───────┐   ┌──────┴──────┐
            │ Redis Cluster │   │ Redis Sentinel│
            │  (Session/    │   │  (Failover)  │
            │   Cache)      │   │              │
            └───────────────┘   └─────────────┘
                    │
            ┌───────┴───────┐
            │ Backup Server │
            │ (Daily/Weekly/│
            │   Monthly)    │
            └───────────────┘
```

### 3.5 Rancangan Pelepasan (Deployment Strategy)

| Fasa | Aktiviti | Persekitaran | Tempoh |
|------|----------|--------------|--------|
| **Fasa 1** | Pembangunan & Ujian Unit | Development | Bulan 1-6 |
| **Fasa 2** | Integrasi & Ujian Sistem | Staging | Bulan 4-8 |
| **Fasa 3** | UAT dengan Pengguna | UAT | Bulan 7-9 |
| **Fasa 4** | PAT & EAT | Pre-Production | Bulan 9-10 |
| **Fasa 5** | Go-Live & FAT | Production | Bulan 11 |
| **Fasa 6** | Waranti & Sokongan | Production | Bulan 12-23 |

---

## 4.0 CADANGAN KAWALAN KESELAMATAN APLIKASI (APPLICATION SECURITY)

### 4.1 Rangka Kerja Keselamatan Pertahanan Mendalam (Defense-in-Depth)

```
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 1: KESELAMATAN PERSEKITARAN (Environmental Security)     │
│  ├─ Pusat Data: Pusat Data BPM (Tier III)                      │
│  ├─ Akses Fizikal: Kawalan biometrik, CCTV 24/7                │
│  ├─ Kelengkapan: UPS, Generator, Sistem Penyejukan N+1         │
│  └─ Rangement: Awan Kita / Sovereign Cloud                     │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 2: KESELAMATAN RANGKAIAN (Network Security)             │
│  ├─ Firewall: Stateful inspection, DPI                         │
│  ├─ WAF: ModSecurity, OWASP CRS                               │
│  ├─ VLAN: Pengasingan segment rangkaian                        │
│  ├─ VPN: Akses pentadbir melalui VPN sahaja                    │
│  └─ DDoS Protection: Cloudflare / Setara                       │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 3: KESELAMATAN APLIKASI (Application Security)          │
│  ├─ Pengesahan: MFA, myDigital ID, RBAC                       │
│  ├─ Pengesahan Input: Validation, Sanitization                 │
│  ├─ Perlindungan: CSRF, XSS, SQL Injection                     │
│  ├─ Sesi: Secure cookies, Session timeout                      │
│  └─ API: Rate limiting, JWT/OAuth 2.0                         │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 4: KESELAMATAN DATA (Data Security)                     │
│  ├─ Penyulitan: AES-256 untuk data rehat                       │
│  ├─ TLS: 1.3 untuk data dalam transit                          │
│  ├─ Backup: Encrypted, off-site, tested                        │
│  ├─ Tokenization: Data sensitif (NRIC, etc.)                   │
│  └─ Masking: Data dalam laporan                                │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 5: KESELAMATAN OPERASI (Operational Security)           │
│  ├─ Monitoring: SIEM, Real-time alerts                         │
│  ├─ Logging: Centralized, immutable logs                       │
│  ├─ Patching: OS dan aplikasi terkini                         │
│  ├─ Hardening: CIS Benchmarks                                 │
│  └─ Incident Response: Playbook, Escalation                    │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 Pengesahan Pengguna (User Authentication)

| Ciri | Pelaksanaan | Standard |
|------|-------------|----------|
| **myDigital ID Integration** | Single Sign-On (SSO) menggunakan protokol SAML 2.0 / OpenID Connect | myDigital ID v2.0 |
| **Multi-Factor Authentication (MFA)** | TOTP (Time-based OTP) melalui aplikasi pengesah | RFC 6238 |
| **Kata Laluan** | Minimum 12 aksara, kompleksiti wajib, penyemakan breach | NIST 800-63B |
| **Session Management** | Timeout 30 minit, pengesahan semula untuk tindakan sensitif | OWASP |
| **Account Lockout** | 5 percubaan gagal = kunci 30 minit | Best Practice |
| **Biometrik** | Sokongan Touch ID / Face ID untuk aplikasi mudah alih | Platform Native |

### 4.3 Kawalan Akses (Access Control)

#### 4.3.1 Peranan Sistem (System Roles)

| Peranan | Capaian | Tindakan Utama |
|---------|---------|----------------|
| **Super Admin** | Keseluruhan sistem | Konfigurasi sistem, pengurusan penyewa |
| **Pentadbir Sistem** | Modul Pentadbir | Tetapan sistem, audit trail, pengurusan pengguna |
| **Urus Setia** | Modul Pengurusan | Proses permohonan, penilaian, tapisan |
| **Penilai** | Paparan permohonan sahaja | Membuat penilaian, kemas kini keputusan |
| **Pemohon** | Portal awam | Hantar permohonan, semak status |
| **Penerima** | Portal awam (terhad) | Pengesahan kehadiran |
| **Pentadbir Integrasi** | Konfigurasi API sahaja | Pengurusan API, webhook |

#### 4.3.2 Matriks Kawalan Akses Berasaskan Peranan (RBAC)

```
Aksi                     │ Super │Pentadbir│Urus  │Penilai│Pemohon│Penerima
                         │ Admin │Sistem   │Setia │       │       │
─────────────────────────┼───────┼─────────┼──────┼───────┼───────┼────────
Tambah Pengguna          │   ✓   │    ✓    │      │       │       │
Ubah Pengguna            │   ✓   │    ✓    │      │       │       │
Padam Pengguna           │   ✓   │         │      │       │       │
Proses Permohonan        │   ✓   │    ✓    │  ✓   │       │       │
Nilai Permohonan         │   ✓   │         │  ✓   │   ✓   │       │
Hantar Permohonan        │       │         │      │       │   ✓   │
Semak Status             │   ✓   │    ✓    │  ✓   │   ✓   │   ✓   │  ✓
Jana Laporan             │   ✓   │    ✓    │  ✓   │       │       │
Konfigurasi Sistem       │   ✓   │    ✓    │      │       │       │
Audit Trail              │   ✓   │    ✓    │      │       │       │
Backup/Restore           │   ✓   │         │      │       │       │
```

### 4.4 Enkripsi Data

| Data | Kaedah | Lokasi | Kunci |
|------|--------|--------|-------|
| **Data Rehat (At Rest)** | AES-256-GCM | Pangkalan data, fail sistem | Dikendalikan BPM |
| **Data Transit (In Transit)** | TLS 1.3 | Rangkaian | Let's Encrypt / BPM CA |
| **Data Sensitif (Field-Level)** | AES-256 | Medan NRIC, telefon | HSM (Hardware Security Module) |
| **Backup** | AES-256 | Storan luar | Terpisah daripada kunci produksi |
| **Kata Laluan** | bcrypt (cost=12) | Pangkalan data | Salt unik setiap pengguna |

### 4.5 Keselamatan Pangkalan Data

| Aspek | Kawalan |
|-------|---------|
| **Pengasingan** | Satu skema per penyewa (multi-tenant) |
| **Akses** | Akaun DB khusus aplikasi sahaja, tiada akses langsung |
| **Kebenaran** | Principle of least privilege |
| **Pengauditan** | Log semua pertanyaan sensitif |
| **Pengemaskinian** | Patch MySQL terkini, kebolehan zero-downtime |
| **Replikasi** | Replicated ke DR site, encrypted |

### 4.6 Pentadbiran Keselamatan

| Ciri | Pelaksanaan |
|------|-------------|
| **Security Operations Center (SOC)** | Pusat kawalan 24/7 untuk pemantauan ancaman |
| **Vulnerability Scanning** | Pengimbasan automatik mingguan (OpenVAS/Nessus) |
| **Penetration Testing (VAPT)** | Pengujian CREST sebelum go-live dan tahunan |
| **Security Audit** | Audit keselamatan suku tahunan |
| **Incident Response** | Playbook tindak balas insiden dengan SLA |
| **Security Awareness** | Latihan keselamatan untuk semua pengguna |

### 4.7 Pematuhan Piawaian Keselamatan

| Piawaian | Status | Penerangan |
|----------|--------|------------|
| **MS ISO/IEC 27001** | Dipatuhi | Sistem pengurusan keselamatan maklumat |
| **OWASP Top 10** | Dilindungi | 10 risiko keselamatan aplikasi web utama |
| **CIS Benchmarks** | Dipatuhi | Konfigurasi selamat untuk OS dan perisian |
| **PCI DSS** | Rujukan | Amalan terbaik untuk data sensitif |
| **Awan Kita** | Dipatuhi | Keperluan awan kerajaan Malaysia |

### 4.8 Code Hardening

| Amalan | Pelaksanaan |
|--------|-------------|
| **Static Analysis** | SAST (SonarQube) untuk mengesan isu kod |
| **Dependency Scanning** | Semak pergantungan yang lapuk atau berisiko |
| **Secret Detection** | Pengesahan automatik kunci API, kata laluan dalam kod |
| **Code Review** | Semakan kod wajib sebelum penggabungan |
| **Secure Defaults** | Konfigurasi selamat secara lalai |
| **Input Validation** | Validasi di sisi pelayan dan klien |
| **Output Encoding** | Pengkodan untuk mencegah XSS |
| **Error Handling** | Mesej ralat generik kepada pengguna, log terperinci untuk pentadbir |

---

## 5.0 SENARAI MODUL YANG AKAN DIBANGUNKAN

### 5.1 Ringkasan Modul

| No. | Modul | Penerangan Ringkas | Status |
|-----|-------|-------------------|--------|
| M1 | Laman Utama | Portal awam dengan maklumat anugerah | Wajib |
| M2 | Dashboard | Papan pemuka analitik dan statistik | Wajib |
| M3 | Permohonan | Aliran pendaftaran dan penghantaran | Wajib |
| M4 | Pengurusan Permohonan | Proses urus setia dan pentadbiran | Wajib |
| M5 | Penilaian & Tapisan | 4 peringkat penilaian, 3 tapisan keselamatan | Wajib |
| M6 | Majlis Pengurniaan | Pengurusan acara dan pengesahan kehadiran | Wajib |
| M7 | Laporan | Pelbagai jenis laporan dan statistik | Wajib |
| M8 | Pentadbir Sistem | Konfigurasi dan pentadbiran keseluruhan | Wajib |
| M9 | Fungsi Integrasi | API untuk sambungan sistem luar | Wajib |
| M10 | Backup & Migrasi | Pengurusan data dan pemulihan | Wajib |

### 5.2 Butiran Modul

#### 5.2.1 MODUL 1: Laman Utama (Public Portal)

| Ciri | Penerangan |
|------|------------|
| **Reka Bentuk** | Responsif, dinamik, interaktif |
| **Pengurusan Kandungan** | CMS untuk pentadbir mengemas kini |
| **Komponen:** |
| - Paparan Darjah/Bintang/Pingat | Senarai dengan keterangan lengkap |
| - Senarai Penerima | Carian dan paparan penerima terdahulu |
| - Warta | Pengurusan dan carian warta |
| - Hebahan | Pengumuman terkini |
| - Menu Bantuan | FAQ, maklumat lazim, garis panduan, hubungi kami |

#### 5.2.2 MODUL 2: Dashboard

| Ciri | Penerangan |
|------|------------|
| **Paparan Statistik** | Jumlah permohonan, status, kategori |
| **Infografik** | Carta dan visualisasi data |
| **Senarai Permohonan** | Ringkasan dengan penapis |
| **Notifikasi** | Kemas kini penting dan tindakan diperlukan |
| **Personalization** | Dashboard disesuaikan mengikut peranan |

#### 5.2.3 MODUL 3: Permohonan (Applicant Portal)

| Ciri | Penerangan |
|------|------------|
| **Pendaftaran Pengguna** | Daftar akaun baharu |
| **Log Masuk** | Kata laluan, myDigital ID |
| **Lupa Kata Laluan** | Proses reset selamat |
| **Borang Permohonan** | Borang atas talian lengkap |
| **Muat Naik Dokumen** | Sokongan pelbagai format, pengesahan fail |
| **Semakan Insolvensi** | Integrasi untuk pengesahan status |
| **Cetakan** | Slip pengesahan dengan QR code |
| **Notifikasi** | Status kemas kini melalui emel/SMS/WhatsApp |
| **Semakan Status** | Jejak permohonan real-time |
| **Semakan Kelayakan** | Penilaian automatik kelayakan |
| **Pengesahan Penerimaan** | Pengesahan dalam talian jika terpilih |

#### 5.2.4 MODUL 4: Pengurusan Permohonan (Secretariat)

| Ciri | Penerangan |
|------|------------|
| **Tetapan Kategori** | Pengurusan kategori permohonan |
| **Tetapan Kelayakan** | Syarat kelayakan boleh dikonfigurasi |
| **Tetapan Sesi** | Buka/tutup sesi permohonan |
| **Pengimbasan QR** | Semakan permohonan fizikal |
| **Proses Permohonan** | Semak, kemas kini, sahkan |
| **Pengisian bagi Pihak** | Urus setia boleh hantar bagi pemohon |
| **Cetakan** | Borang, senarai pencalonan, laporan |

#### 5.2.5 MODUL 5: Pengurusan Proses Penilaian dan Tapisan

| Ciri | Penerangan |
|------|------------|
| **4 Sesi Mesyuarat** | Kemas kini keputusan setiap sesi |
| **4 Sesi Penilaian** | Status permohonan setiap peringkat |
| **Penjanaan Surat** | Surat tawaran dengan QR (tahun lock) |
| **Akuan Sumpah** | Penjanaan borang dengan QR |
| **Borang Pemulangan** | Pengurusan pemulangan darjah/pingat |
| **Notifikasi** | Hantar status dan tarikh pengambilan |
| **Tapisan Keselamatan** | Integrasi 3 agensi (SPRM, Insolvensi, ROS) |
| **Integrasi Laman Web** | Hantar senarai ke portal Darjah Kebesaran |
| **Pengesahan bagi Pihak** | Urus setia boleh sahkan bagi penerima |

#### 5.2.6 MODUL 6: Pengurusan Majlis Pengurniaan

| Ciri | Penerangan |
|------|------------|
| **Pengurusan Acara** | Tetapan tarikh, lokasi, tetamu |
| **Senarai Kehadiran** | Pengesahan dan pengurusan |
| **QR Code Check-in** | Pengesahan digital kehadiran |
| **Cetakan Sijil** | Penjanaan sijil/surat penganugerahan |
| **Galeri** | Muat naik dan pengurusan gambar |

#### 5.2.7 MODUL 7: Laporan

| Jenis Laporan | Penerangan |
|---------------|------------|
| **Laporan Tahunan** | Mengikut sesi, kategori, penilaian |
| **Laporan Penerima** | Mengikut sesi, kategori, statistik |
| **Statistik Keseluruhan** | Data kumulatif sehingga kini |
| **Infografik** | Paparan visual untuk setiap laporan |
| **Carian Warta** | Carian penerima dan warta |
| **Eksport** | PDF, Excel, CSV |

#### 5.2.8 MODUL 8: Pentadbir Sistem

| Ciri | Penerangan |
|------|------------|
| **Ketetapan Sistem** | Penyelenggaraan data lookup |
| **Audit Trail** | Log semua aktiviti sistem |
| **Tetapan Notifikasi** | Konfigurasi emel/SMS/WhatsApp |
| **Integrasi AD** | Sambungan Active Directory |
| **myDigital ID** | Konfigurasi SSO |
| **Pengesahan Emel** | Tetapan verifikasi emel |
| **Masquerade** | Log masuk sebagai pengguna lain |
| **Konfigurasi Lanjutan** | Bergantung kepada keperluan URS |

#### 5.2.9 MODUL 9: Fungsi Integrasi (API)

| Sistem | Jenis Integrasi | Data |
|--------|-----------------|------|
| **SPRM** | API | Tapisan integriti |
| **Jabatan Insolvensi** | API | Status insolvensi |
| **Laman Web Darjah Kebesaran** | API | Senarai penerima |
| **ROS** | API | Tapisan syarikat/persatuan |
| **myIDENTITY** | API | Pengesahan identiti |
| **HRMIS** | API | Data pegawai |
| **myDigital ID** | SSO | Log masuk pengguna |
| **SMS/WhatsApp** | API | Notifikasi |
| **Emel** | SMTP/API | Komunikasi rasmi |

#### 5.2.10 MODUL 10: Backup dan Migrasi

| Ciri | Penerangan |
|------|------------|
| **Backup Data** | Automatik ke storan keras |
| **Backup Harian/Mingguan/Bulanan** | Jadual pengurusan |
| **Migrasi Sistem** | Pindahan daripada Lotus Notes |
| **Migrasi Data** | Pindahan data permohonan dan penerima |
| **Data Cleaning** | Pembersihan dan normalisasi data |
| **Pengujian** | Ujian integriti selepas migrasi |

---

## 6.0 LAKARAN CADANGAN DASHBOARD

### 6.1 Struktur Dashboard Utama

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  HEADER                                                                     │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │ [Logo ePingat Selangor]    Dashboard    [🔍] [🔔 3] [👤 Afeez ▼]   │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────────────────────┤
│  SIDEBAR                              │  MAIN CONTENT                       │
│  ┌─────────────────────────────────┐  │  ┌───────────────────────────────┐ │
│  │ 📊 Dashboard                    │  │  │  KPI CARDS                    │ │
│  │ ─────────────────────────────── │  │  │  ┌─────┐ ┌─────┐ ┌─────┐     │ │
│  │ 📋 Senarai Permohonan           │  │  │  │Total│ │New  │ │Approved│   │ │
│  │ ➕ Proses Permohonan Baru       │  │  │  │1,245│ │ 89  │ │  456   │   │ │
│  │ 📊 Laporan                      │  │  │  └─────┘ └─────┘ └─────┘     │ │
│  │ ─────────────────────────────── │  │  │  ┌─────┐ ┌─────┐ ┌─────┐     │ │
│  │ ⚙️  Tetapan                     │  │  │  │Pending│ │Rejected│ │Review││ │
│  │ 👥 Pengurusan Pengguna          │  │  │  │ 567 │ │  78  │ │ 144  │   │ │
│  │ 📜 Audit Trail                  │  │  │  └─────┘ └─────┘ └─────┘     │ │
│  │ ─────────────────────────────── │  │  └───────────────────────────────┘ │
│  │ 🌐 Portal Awam                  │  │                                     │
│  │ ❓ Bantuan                      │  │  ┌───────────────────────────────┐ │
│  │ 🚪 Log Keluar                   │  │  │  STATISTIK PERMOHONAN         │ │
│  └─────────────────────────────────┘  │  │                                 │ │
│                                       │  │   ▲                             │ │
│                                       │  │   │      ╭────╮                 │ │
│                                       │  │   │     ╱      ╲                │ │
│                                       │  │   │    │   ▓▓   │  ▓ Sesi 1     │ │
│                                       │  │   │    │  ▓▓▓▓  │  ▓ Sesi 2     │ │
│                                       │  │   │     ╲▓▓▓▓▓╱                 │ │
│                                       │  │   │        ╲▓╱                  │ │
│                                       │  │   └───────────────────────────────┘ │
│                                       │  │                                     │ │
│                                       │  │  ┌───────────────────────────────┐ │
│                                       │  │  │  AKTIVITI TERKINI             │ │
│                                       │  │  │  ─────────────────────────    │ │
│                                       │  │  │  📝 Permohonan baharu #1245   │ │
│                                       │  │  │  ✓ Permohonan #1230 diluluskan│ │
│                                       │  │  │  ⚠️ Dokumen tambahan diperlukan│ │
│                                       │  │  │  📋 Sesi penilaian 3 bermula  │ │
│                                       │  │  └───────────────────────────────┘ │
│                                       │  │                                     │ │
│                                       │  │  ┌───────────────────────────────┐ │
│                                       │  │  │  TUGAS MENUNGGU               │ │
│                                       │  │  │  ─────────────────────────    │ │
│                                       │  │  │  ☐ Semak permohonan (5)       │ │
│                                       │  │  │  ☐ Sahkan tapisan SPRM (3)    │ │
│                                       │  │  │  ☐ Kemas kini mesyuarat       │ │
│                                       │  │  └───────────────────────────────┘ │
│                                       │  └───────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Dashboard Urus Setia (Admin View)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  FILTER & SEARCH BAR                                                      │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │ Tahun: [2026 ▼]  Sesi: [Semua ▼]  Status: [Semua ▼]  [Cari...] [🔍] │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────────────────────┤
│  SENARAI PERMOHONAN                                                         │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │ □ │ No. │ Nama Pemohon │ Kategori │ Tarikh │ Status │ Tindakan      │ │
│  ├───┼─────┼──────────────┼──────────┼────────┼────────┼───────────────┤ │
│  │ □ │1245 │ Ahmad Bin Ali│ Dato'    │01/02/26│ ⏳ Baru │ [Semak][Lihat]│ │
│  │ □ │1244 │ Siti Aminah  │ Datin    │31/01/26│ ✅ Lulus │ [Cetak][Hantar]││
│  │ □ │1243 │ Mohd Hassan  │ Pingat   │31/01/26│ 🔄 Proses│ [Semak][Lihat]│ │
│  │ □ │1242 │ Raja Ahmad   │ Dato'    │30/01/26│ ❌ Tolak │ [Lihat][Padam]│ │
│  │ □ │1241 │ Fatimah Zahra│ Datin    │30/01/26│ ✅ Lulus │ [Cetak][Hantar]││
│  └───────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐ │
│  │  ← 1  2  3  4  5 ... 25 →    Papar 10 25 50 100 per halaman         │ │
│  └───────────────────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.3 Dashboard Analitik (Reporting View)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  DASHBOARD ANALITIK PERMOHONAN TAHUNAN                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐ │
│  │   CARTA PAI         │  │   GRAF BAR          │  │   GRAF GARIS        │ │
│  │                     │  │                     │  │                     │ │
│  │    ╭──────╮         │  │   ▲                 │  │   ▲                 │ │
│  │   ╱  35%  ╲        │  │   │    ██            │  │   │      ╭─╮       │ │
│  │  │ Dato'   │        │  │   │    ██  ██       │  │   │     ╭╯ ╰╮      │ │
│  │  │(425)    │        │  │   │ ██ ██  ██  ██   │  │   │    ╭╯   ╰╮     │ │
│  │   ╲        ╱        │  │   │ ██ ██  ██  ██   │  │   │╭───╯     ╰───╮ │ │
│  │    ╰──────╯         │  │   └───────────────▶  │  │   └─────────────▶ │ │
│  │    ╭──────╮         │  │   S1  S2  S3  S4    │  │   Jan Feb Mac Apr │ │
│  │   ╱  28%  ╲        │  │                     │  │                     │ │
│  │  │ Datin   │        │  │   Permohonan mengikut│  │   Trend Bulanan   │ │
│  │  │(340)    │        │  │   sesi penilaian    │  │                     │ │
│  │   ╲        ╱        │  │                     │  │                     │ │
│  │    ╰──────╯         │  │                     │  │                     │ │
│  │                     │  │                     │  │                     │ │
│  │  Kategori Permohonan│  │                     │  │                     │ │
│  └─────────────────────┘  └─────────────────────┘  └─────────────────────┘ │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                         JADUAL RINGKASAN                             │   │
│  ├──────────────┬──────────┬──────────┬──────────┬──────────┬──────────┤   │
│  │ Kategori     │ Sesi 1   │ Sesi 2   │ Sesi 3   │ Sesi 4   │ Jumlah   │   │
│  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤   │
│  │ Dato'        │   105    │   112    │   98     │   110    │   425    │   │
│  │ Datin        │    85    │    88    │   82     │    85    │   340    │   │
│  │ Dato' Paduka │    45    │    52    │   48     │    50    │   195    │   │
│  │ Datin Paduka │    38    │    42    │   35     │    40    │   155    │   │
│  │ Pingat       │   120    │   135    │   125    │   130    │   510    │   │
│  ├──────────────┼──────────┼──────────┼──────────┼──────────┼──────────┤   │
│  │ JUMLAH       │   393    │   429    │   388    │   415    │  1,625   │   │
│  └──────────────┴──────────┴──────────┴──────────┴──────────┴──────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 7.0 PENGURUSAN BACKUP DAN RESTORE

### 7.1 Strategi Backup 3-2-1

| Komponen | Pelaksanaan |
|----------|-------------|
| **3** | 3 salinan data (primary + 2 backup) |
| **2** | 2 media berbeza (disk lokal + cloud/NAS) |
| **1** | 1 salinan di lokasi luar (off-site) |

### 7.2 Jadual Backup

| Jenis Backup | Kekerapan | Masa | Tempoh Simpanan |
|--------------|-----------|------|-----------------|
| **Backup Harian Penuh** | Setiap hari | 02:00 pagi | 7 hari |
| **Backup Harian Inkremental** | Setiap 6 jam | 00:00, 06:00, 12:00, 18:00 | 3 hari |
| **Backup Mingguan** | Setiap Ahad | 01:00 pagi | 4 minggu |
| **Backup Bulanan** | Hari pertama bulan | 00:00 | 12 bulan |
| **Backup Tahunan** | Tahun baru | 00:00 | 7 tahun |

### 7.3 Skop Backup

| Data | Kaedah | Kekerapan |
|------|--------|-----------|
| **Pangkalan Data (MySQL)** | mysqldump + binary log | Harian penuh, inkremental 6 jam |
| **Fail Aplikasi** | rsync/snapshot | Harian |
| **Dokumen Muat Naik** | rsync ke NAS | Harian |
| **Konfigurasi Server** | Git repository + backup | Setiap perubahan |
| **Konfigurasi Aplikasi** | Export + version control | Setiap kemas kini |

### 7.4 Prosedur Restore

| Senario | Masa Pemulihan (RTO) | Data Loss Diterima (RPO) |
|---------|---------------------|--------------------------|
| **Kepadaman Fail Tertentu** | < 1 jam | < 6 jam |
| **Kerosakan Pangkalan Data** | < 4 jam | < 6 jam |
| **Kegagalan Server Penuh** | < 8 jam | < 24 jam |
| **Bencana Pusat Data** | < 24 jam | < 24 jam |

### 7.5 Prosedur Restore Langkah demi Langkah

```
TAHAP 1: PENILAIAN
├── Kenal pasti skop kehilangan data
├── Pilih titik pemulihan yang sesuai
└── Maklumkan kepada pihak berkepentingan

TAHAP 2: PENYEDIAAN
├── Peruntukkan sumber yang diperlukan
├── Pastikan kebolehcapaian backup
└── Sediakan persekitaran pemulihan

TAHAP 3: PEMULIHAN
├── Pulihkan sistem pengendalian (jika perlu)
├── Pulihkan perisian dan konfigurasi
├── Pulihkan pangkalan data
├── Pulihkan fail aplikasi
└── Pulihkan dokumen pengguna

TAHAP 4: PENGESAHAN
├── Jalankan ujian integriti data
├── Uji fungsi aplikasi kritikal
├── Sahkan data dengan pengguna
└── Dokumenkan pemulihan

TAHAP 5: KEMBALI KE PRODUKSI
├── Aktifkan sistem kepada pengguna
├── Pantau prestasi dan kestabilan
└── Kemas kini dokumentasi
```

### 7.6 Ujian Backup (Backup Testing)

| Kekerapan | Aktiviti |
|-----------|----------|
| **Bulanan** | Ujian restore ke persekitaran staging |
| **Suku Tahunan** | Ujian disaster recovery penuh |
| **Tahunan** | Audit prosedur backup dan dokumentasi |

### 7.7 Dokumentasi Backup

| Dokumen | Penerangan |
|---------|------------|
| **Pelan Backup** | Strategi, jadual, dan tanggungjawab |
| **Prosedur Backup** | Langkah operasi harian |
| **Prosedur Restore** | Langkah pemulihan mengikut senario |
| **Log Backup** | Rekod setiap operasi backup |
| **Laporan Ujian** | Keputusan ujian restore |

---

## 8.0 LATIHAN DAN TRANSFER OF TECHNOLOGY (TOT)

### 8.1 Pendekatan Latihan

Kami percaya dalam **"Learn by Doing"** — latihan praktikal yang membolehkan peserta menggunakan sistem dalam persekitaran selamat sebelum go-live.

### 8.2 Jenis-jenis Latihan

#### 8.2.1 Latihan Pengguna (User Training)

| Aspek | Butiran |
|-------|---------|
| **Kumpulan Sasaran** | Urus Setia, Penilai, Pentadbir |
| **Tempoh** | 2 hari (16 jam) |
| **Bilangan Peserta** | Maksimum 20 setiap sesi |
| **Tempat** | Pejabat Setiausaha Kerajaan Negeri Selangor |
| **Bahan** | Manual pengguna, video tutorial, FAQ |

| Modul Latihan | Durasi | Kandungan |
|---------------|--------|-----------|
| **Pengenalan Sistem** | 2 jam | Overview, log masuk, navigasi |
| **Modul Permohonan** | 3 jam | Hantar permohonan, muat naik dokumen |
| **Modul Pengurusan** | 4 jam | Proses permohonan, penilaian |
| **Modul Laporan** | 2 jam | Jana laporan, eksport data |
| **Troubleshooting** | 2 jam | Isu biasa, carian bantuan |
| **Latihan Praktikal** | 3 jam | Hands-on dengan data sampel |

#### 8.2.2 Latihan Pentadbir Sistem (Administrator Training)

| Aspek | Butiran |
|-------|---------|
| **Kumpulan Sasaran** | Pentadbir Sistem PSUK |
| **Tempoh** | 3 hari (24 jam) |
| **Bilangan Peserta** | Maksimum 10 setiap sesi |
| **Tempat** | Pejabat Setiausaha Kerajaan Negeri Selangor |
| **Prasyarat** | Asas sistem pengendalian Linux |

| Modul Latihan | Durasi | Kandungan |
|---------------|--------|-----------|
| **Pentadbiran Sistem** | 4 jam | Konfigurasi, tetapan pengguna |
| **Pengurusan Data** | 3 jam | Backup, restore, migrasi |
| **Keselamatan** | 3 jam | Kawalan akses, audit trail |
| **Integrasi** | 4 jam | Konfigurasi API, SSO |
| **Pemantauan** | 3 jam | Log, alert, prestasi |
| **Troubleshooting** | 4 jam | Isu teknikal, recovery |
| **Latihan Praktikal** | 3 jam | Simulasi isu sebenar |

#### 8.2.3 Transfer of Technology (TOT)

| Aspek | Butiran |
|-------|---------|
| **Kumpulan Sasaran** | Pasukan teknikal PSUK |
| **Tempoh** | 5 hali (40 jam) |
| **Bilangan Peserta** | Maksimum 5 setiap sesi |
| **Tempat** | Pejabat Setiausaha Kerajaan Negeri Selangor + Pusat Data |
| **Prasyarat** | Pengalaman pembangunan web, PHP, MySQL |

### 8.3 Kandungan TOT

| Hari | Topik | Aktiviti |
|------|-------|----------|
| **1** | Arkitektur Sistem | Gambarajah keseluruhan, aliran data |
| **1** | Timbal Teknologi | OS, web server, database, cache |
| **2** | Kod Sumber | Struktur projek, framework, komponen |
| **2** | Pangkalan Data | Skema, hubungan, prosedur tersimpan |
| **3** | API & Integrasi | Endpoints, autentikasi, webhook |
| **3** | Keselamatan | Konfigurasi, kekerapan, audit |
| **4** | Deployment | Proses build, release, rollback |
| **4** | Pemantauan | Tools, metrik, alerting |
| **5** | Troubleshooting | Log analysis, debugging, recovery |
| **5** | Hands-on Project | Pelaksanaan fitur kecil |

### 8.4 Dokumentasi TOT

| Dokumen | Format | Penjelasan |
|---------|--------|------------|
| **Senarai Fail Modul** | Excel/PDF | Semua fail dalam sistem dengan penerangan |
| **Dokumentasi Teknikal** | PDF/Markdown | Spesifikasi API, ERD, gambarajah aliran |
| **Manual Operasi** | PDF | Prosedur harian, troubleshooting |
| **Video Tutorial** | MP4 | Screencast operasi kritikal |
| **Kod Sumber** | Git Repository | Akses penuh kepada repository |

### 8.5 Jaminan Sokongan Pasca-TOT

| Tempoh | Sokongan |
|--------|----------|
| **Bulan 1-3** | Sesi mentoring mingguan, respons dalam 4 jam |
| **Bulan 4-6** | Sesi mentoring bulanan, respons dalam 8 jam |
| **Sepanjang Waranti** | Sokongan teknikal penuh |

### 8.6 Kemudahan Latihan

| Kemudahan | Penyediaan |
|-----------|------------|
| **Bilik Latihan** | Dipasang projek, papan putih, WiFi |
| **Komputer** | 1 unit setiap peserta (minimum i5, 8GB RAM) |
| **Akses Internet** | Lebar jalur tinggi untuk demo atas talian |
| **Peralatan** | Nota, pen, pemegang dokumen |
| **Refreshment** | Kopi, teh, air minuman |
| **Makanan** | Sajian makan tengah hari untuk latihan berlarutan |

---

## 9.0 KESIMPULAN

Sinergi Elit Sdn Bhd (SESB) berkomited untuk menyampaikan Sistem ePingat Negeri Selangor yang:

1. **Memenuhi Semua Keperluan** — 100% pematuhan kepada spesifikasi Jadual 1
2. **Melebihi Jangkaan** — Penambahbaikan nilai tambah bernilai RM 1.8 juta
3. **Dibina dengan Keselamatan** — Arsitektur pertahanan mendalam dengan VAPT CREST
4. **Bersedia untuk Masa Depan** — Arkitektur modular untuk peluasan
5. **Didokumentasi dengan Lengkap** — Dokumentasi KRISA/JDN penuh
6. **Disokong dengan Berkesan** — SLA 99.9% dengan sokongan 24/7

Kami percaya cadangan ini menunjukkan keupayaan teknikal kami, pengalaman dalam projek kerajaan, dan komitmen untuk kecemerlangan. Sistem ePingat yang kami bangunkan akan menjadi model digitalisasi pengurusan anugerah di peringkat negeri dan kebangsaan.

---

**Disediakan oleh:**

_________________________________
Nama: 
Jawatan: 
Tarikh: 

_________________________________
Nama: 
Jawatan: 
Tarikh: 

**Cop Syarikat:**

---

*Kertas Cadangan ini adalah sebahagian daripada Tawaran Tender T/SUKSEL/04-2026*
