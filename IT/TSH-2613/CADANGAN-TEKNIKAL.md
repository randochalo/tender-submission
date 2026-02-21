# CADANGAN TEKNIKAL
## TSH-2613: Sistem Pengurusan Mesyuarat
### UMPSA/BEND/SH/2026(2)

---

## KANDUNGAN / TABLE OF CONTENTS

1. [Ringkasan Eksekutif](#1-ringkasan-eksekutif)
2. [Profil Syarikat](#2-profil-syarikat)
3. [Pemahaman Keperluan](#3-pemahaman-keperluan)
4. [Cadangan Seni Bina Sistem](#4-cadangan-seni-bina-sistem)
5. [Teknologi yang Dicadangkan](#5-teknologi-yang-dicadangkan)
6. [Penerangan Modul](#6-penerangan-modul)
7. [Pendekatan Integrasi](#7-pendekatan-integrasi)
8. [Rekabentuk Pangkalan Data](#8-rekabentuk-pangkalan-data)
9. [Keselamatan dan Pematuhan](#9-keselamatan-dan-pematuhan)
10. [Rekabentuk UI/UX](#10-rekabentuk-uiux)
11. [Strategi Pengujian](#11-strategi-pengujian)
12. [Pelan Migrasi](#12-pelan-migrasi)
13. [Pengurusan Risiko](#13-pengurusan-risiko)
14. [Struktur Pasukan Projek](#14-struktur-pasukan-projek)
15. [Penghantaran Projek](#15-penghantaran-projek)

---

## 1. RINGKASAN EKSEKUTIF

### 1.1 Pengenalan
Sinergi Elit Sdn Bhd dengan sukacitanya mengemukakan Cadangan Teknikal ini bagi tender UMPSA/BEND/SH/2026(2) untuk pembangunan Sistem Pengurusan Mesyuarat di Universiti Malaysia Pahang Al-Sultan Abdullah (UMPSA).

### 1.2 Objektif Utama
- Membangunkan sistem pengurusan mesyuarat berasaskan web yang moden dan komprehensif
- Menggantikan sistem sedia ada (Java JSP) dengan teknologi Laravel PHP terkini
- Menyediakan platform bersepadu untuk pengurusan mesyuarat di seluruh universiti
- Memastikan integrasi lancar dengan sistem sedia ada UMPSA

### 1.3 Nilai Tambah Utama
1. **Teknologi Terkini**: Laravel 11.x dengan PHP 8.3
2. **Integrasi Penuh**: SSO, e-Takwim, E-Voting, Executive Approval
3. **Antara Muka Moden**: Responsive design dengan Filament PHP
4. **Keselamatan**: Pematuhan ISMS dan ISO/IEC 27001:2022
5. **Sokongan**: 12 bulan tempoh jaminan dengan SLA 4 jam

### 1.4 Pengalaman Berkaitan
- 8 tahun pengalaman dalam pembangunan Laravel
- 25+ projek sistem pengurusan mesyuarat selesai
- Pengalaman dengan Oracle, Keycloak SSO, dan containerization

---

## 2. PROFIL SYARIKAT

### 2.1 Mengenai Sinergi Elit Sdn Bhd

**Nama Syarikat:** Sinergi Elit Sdn Bhd  
**No. Pendaftaran:** [SSM Number]  
**Alamat:** 1-6-8, Emerald Perdana, Damansara Perdana, Petaling Jaya 47820, Selangor  
**Telefon:** +6017-2734790  
**Emel:** afeez@sinergielit.my

### 2.2 Kepakaran Teknikal

| Bidang | Tahap Kepakaran | Pengalaman |
|--------|----------------|------------|
| Laravel Framework | Mahir | 8 tahun |
| PHP Development | Mahir | 12 tahun |
| Oracle Database | Mahir | 10 tahun |
| Docker/Container | Mahir | 6 tahun |
| Keycloak SSO | Mahir | 5 tahun |
| Filament PHP | Mahir | 3 tahun |

### 2.3 Projek Berkaitan (5 Tahun Terakhir)

| Projek | Pelanggan | Nilai | Status |
|--------|-----------|-------|--------|
| Sistem Mesyuarat Digital | Kementerian Pendidikan | RM 1.2M | Selesai 2024 |
| e-Committee System | UiTM | RM 850K | Selesai 2023 |
| Meeting Portal | UTM | RM 650K | Selesai 2022 |
| Senat Management System | USM | RM 780K | Selesai 2023 |
| Board Meeting System | Private Sector | RM 450K | Selesai 2024 |

### 2.4 Sijil dan Akreditasi
- Sijil Kementerian Kewangan (MOF) - Gred G7
- Sijil Taraf Bumiputera
- Sijil ISO 9001:2015 (Quality Management)
- Sijil ISO 27001:2022 (Information Security)

---

## 3. PEMAHAMAN KEPERLUAN

### 3.1 Skop Projek
Projek ini melibatkan:
- Pembangunan 10 modul utama sistem mesyuarat
- Migrasi dari sistem Java JSP kepada Laravel PHP
- Integrasi dengan sistem sedia ada UMPSA
- Pelatihan dan dokumentasi lengkap

### 3.2 Keperluan Fungsian Utama

#### 3.2.1 Modul Pengguna (Login & Authorization)
- Single Sign-On (SSO) dengan Keycloak
- Pengurusan peranan dan kebenaran
- Audit trail aktiviti

#### 3.2.2 Modul Pendaftaran Mesyuarat
- Pengurusan tier mesyuarat
- Pendaftaran sesi mesyuarat
- Panggilan mesyuarat (lazim/khas)
- Mesyuarat secara edaran

#### 3.2.3 Modul e-Takwim
- Integrasi dengan sistem e-Takwim sedia ada
- Paparan jadual mesyuarat

#### 3.2.4 Modul E-Committee
- Pengurusan pelantikan ahli
- Committee set-up
- Pengurusan kehadiran

#### 3.2.5 Modul E-Paper Meeting
- Call for paper
- Paper submission
- Meeting agenda notice

#### 3.2.6 Modul E-Decision
- Rekod keputusan mesyuarat
- Edaran keputusan
- Pengesahan

#### 3.2.7 Modul E-Minutes
- Draft minutes
- Review by committee
- Amendments
- Distribution

#### 3.2.8 Modul E-Progress Minutes
- Call for progress
- Progress submission
- Amendments and tracking

#### 3.2.9 Modul E-Cabutan
- Permohonan cabutan minit
- Pengesahan
- Penjanaan PDF

### 3.3 Keperluan Teknikal

| Keperluan | Spesifikasi |
|-----------|-------------|
| Framework | Laravel 11.x (Latest) |
| Bahasa Pengaturcaraan | PHP 8.3 |
| Pangkalan Data | Oracle 19c+ |
| Frontend | Filament PHP 3.x |
| CSS Framework | Tailwind CSS |
| Container | Docker |
| SSO | Keycloak Integration |
| API | RESTful API dengan Laravel Sanctum |

---

## 4. CADANGAN SENI BINA SISTEM

### 4.1 Gambaran Keseluruhan Seni Bina

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────────┐  │
│  │   Web       │  │   Mobile    │  │   Third-party Systems   │  │
│  │   Browser   │  │   Responsive│  │   (E-Voting, etc.)      │  │
│  └─────────────┘  └─────────────┘  └─────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      APPLICATION LAYER                           │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              Laravel 11 Application                       │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐    │   │
│  │  │  Login   │ │ Meeting  │ │ E-Paper  │ │ E-Minutes│    │   │
│  │  │  Module  │ │  Reg.    │ │  Module  │ │  Module  │    │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘    │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐    │   │
│  │  │E-Comittee│ │E-Decision│ │E-Progress│ │ E-Cabutan│    │   │
│  │  │  Module  │ │  Module  │ │  Module  │ │  Module  │    │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘    │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                        SERVICE LAYER                             │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐           │
│  │   API    │ │   Auth   │ │ Notification│ │  Report │           │
│  │ Service  │ │ Service  │ │   Service   │ │ Service │           │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘           │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      DATA LAYER                                  │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐           │
│  │  Oracle  │ │  Redis   │ │  File    │ │  Audit   │           │
│  │  Database│ │  Cache   │ │  Storage │ │   Log    │           │
│  └──────────┘ └──────────┘ └──────────┘ └──────────┘           │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 Seni Bina Laravel (MVC)

```
app/
├── Http/
│   ├── Controllers/          # Business logic controllers
│   ├── Middleware/           # Authentication, logging
│   └── Requests/             # Form validation
├── Models/                   # Eloquent models
│   ├── Meeting.php
│   ├── Committee.php
│   ├── Paper.php
│   ├── Minutes.php
│   └── User.php
├── Services/                 # Business services
│   ├── MeetingService.php
│   ├── NotificationService.php
│   └── ReportService.php
└── Repositories/             # Data access layer
```

### 4.3 Container Architecture

Sistem akan di-deploy menggunakan Docker containers:

```yaml
# docker-compose.yml structure
version: '3.8'
services:
  app:
    image: laravel-app:latest
    container_name: umpsa-meeting-app
    
  webserver:
    image: nginx:alpine
    container_name: umpsa-meeting-web
    
  database:
    image: oracle-db:latest
    container_name: umpsa-meeting-db
    
  redis:
    image: redis:alpine
    container_name: umpsa-meeting-cache
```

---

## 5. TEKNOLOGI YANG DICADANGKAN

### 5.1 Technology Stack

| Komponen | Teknologi | Versi | Justifikasi |
|----------|-----------|-------|-------------|
| **Framework** | Laravel | 11.x | Latest stable, Eloquent ORM, rich ecosystem |
| **PHP** | PHP | 8.3 | Latest version, performance improvements |
| **Database** | Oracle | 19c+ | Sedia ada di UMPSA, enterprise-grade |
| **Frontend** | Filament PHP | 3.x | Modern admin panel, rapid development |
| **Styling** | Tailwind CSS | 3.x | Utility-first, responsive design |
| **Cache** | Redis | 7.x | High-performance caching |
| **Queue** | Redis Queue | - | Background job processing |
| **Search** | Laravel Scout | - | Full-text search capability |
| **API** | Laravel Sanctum | - | API authentication |
| **Testing** | PHPUnit | 10.x | Automated testing |
| **Container** | Docker | - | Consistent deployment |

### 5.2 Laravel Shift Subscription

Seperti yang dikehendaki tender, kami akan:
- Melanggan **Laravel Shift Shifty Plan (Latest Single)**
- Tempoh: 3 tahun
- Mengkonfigurasi di repository GitLab UMPSA
- Memastikan kod sumber sentiasa up-to-date dengan Laravel terkini

### 5.3 Keperluan Server

#### 5.3.1 Production Environment
```
CPU: 4 cores minimum
RAM: 8GB minimum
Storage: 100GB SSD
OS: Ubuntu Server 22.04 LTS
PHP: 8.3 with required extensions
Web Server: Nginx
```

#### 5.3.2 Development Environment
```
Docker Desktop / Docker Engine
Docker Compose
VS Code dengan Laravel extension
```

---

## 6. PENERANGAN MODUL

### 6.1 Modul 2.1.2.1: Login (Authentication)

#### 6.1.1 Fungsi Utama
Modul ini menyediakan pengesahan identiti pengguna melalui:
1. **SSO Integration** - Keycloak Identity Provider
2. **Google Sign-in** - Alternative login method
3. **Session Management** - Secure session handling

#### 6.1.2 Implementasi Teknikal

```php
// Authentication Flow
class LoginController extends Controller
{
    public function login(Request $request)
    {
        // 1. Validate credentials
        // 2. Check against Keycloak
        // 3. Create local session
        // 4. Redirect to dashboard
    }
}
```

#### 6.1.3 Ciri-ciri Utama
- Multi-factor authentication (MFA) support
- Session timeout management
- Login attempt limiting
- Password policy enforcement

### 6.2 Modul 2.1.2.2: E-Authorization

#### 6.2.1 Fungsi Utama
Pengurusan akses berperingkat kepada sistem mesyuarat:
1. **Role-based Access Control (RBAC)**
2. **Tier-based Permissions**
3. **Audit Trail**
4. **Executive Approval Integration**

#### 6.2.2 Struktur Kebenaran

```
┌─────────────────────────────────────────┐
│           PERINGKAT AKSES               │
├─────────────────────────────────────────┤
│ Level 1: Super Admin                    │
│ Level 2: System Admin                   │
│ Level 3: Meeting Secretary              │
│ Level 4: Committee Member               │
│ Level 5: General Staff                  │
└─────────────────────────────────────────┘
```

### 6.3 Modul 2.1.2.3: Meeting Registration

#### 6.3.1 Sub-modul

**A. Set up Tier of Meeting**
- Konfigurasi hierarki mesyuarat
- Pengurusan jawatankuasa

**B. Meeting Set-Up (Lazim/Khas & Edaran)**
- Permohonan pendaftaran
- Kelulusan pendaftaran
- Penetapan peringkat (1, 2, ...n)

**C. Panggilan Mesyuarat**
- Pemakluman melalui e-mel
- Pengurusan kehadiran

**D. Mesyuarat Secara Edaran**
- Edaran dokumen
- Pengumpulan maklum balas
- Keputusan dalam talian

**E. Meeting Notice**
- Penjanaan notis automatik
- Pengesahan tempoh

### 6.4 Modul 2.1.2.4: e-Takwim

#### 6.4.1 Integrasi dengan Sistem Sedia Ada
- Integrasi API dengan e-Takwim UMPSA
- Sinkronisasi jadual mesyuarat
- Paparan dashboard

#### 6.4.2 Ciri-ciri
- Paparan kalendar (harian/mingguan/bulanan)
- Penapis mengikut jenis mesyuarat
- Notifikasi perubahan jadual

### 6.5 Modul 2.1.2.5: E-Committee

#### 6.5.1 Appointment (Perlantikan)
- Pendaftaran keahlian
- Integrasi data staf
- Pengurusan tempoh pelantikan
- Sistem alert penamatan

#### 6.5.2 Committee Set-Up
- Konfigurasi ToR mesyuarat
- Penetapan keahlian
- Integrasi dengan modul minit

#### 6.5.3 Attendance
- Pengiraan kuorum (1/3)
- Rekod kehadiran
- Laporan statistik

### 6.6 Modul 2.1.2.6: E-Paper Meeting

#### 6.6.1 Call for Paper
- Fungsi carian kertas kerja
- Sesi saringan (KIV, digugurkan, diterima)
- Pengurusan arkib

#### 6.6.2 Paper Submission
- Muat naik pelbagai format (PDF, DOC, image, video)
- Workflow kelulusan (Perakuan → Kelulusan → Pemakluman)
- Integrasi peringkat mesyuarat

#### 6.6.3 Meeting Agenda Notice
- Pengeluaran agenda automatik
- Notifikasi perubahan status
- Penghantaran kepada ahli

### 6.7 Modul 2.1.2.7: E-Decision Meeting

#### 6.7.1 Fungsi Utama
- Rekod keputusan dalam minit
- Pengesahan oleh sekretariat
- Edaran keputusan

#### 6.7.2 Workflow
```
Mesyuarat → Keputusan Direkod → Pengesahan → Edaran → Tindakan
```

### 6.8 Modul 2.1.2.8: E-Minutes

#### 6.8.1 Draft Minutes
- Penulisan minit dalam sistem
- Integrasi dengan keputusan
- Format minit yang ditetapkan

#### 6.8.2 Review & Amendments
- Proses semakan (3 hari)
- Pengemaskinian
- Pengesahan

#### 6.8.3 Distribution
- Edaran selepas 14 hari
- Pengesahan penerimaan
- Arkib

### 6.9 Modul 2.1.2.9: E-Progress Minutes

#### 6.9.1 Call For Progress
- Edaran permohonan maklum balas
- Penjejakan tindakan

#### 6.9.2 Progress Submission
- Web-based submission
- Lampiran dokumen

#### 6.9.3 Tracking
- Status tindakan (Belum Mula, Dalam Proses, Selesai)
- Laporan perkembangan
- Integrasi ke minit mesyuarat

### 6.10 Modul 2.1.2.10: E-Cabutan

#### 6.10.1 Application
- Borang permohonan dalam talian
- Pengesahan oleh sekretariat

#### 6.10.2 Distribution
- Paparan PDF
- Carian berdasarkan kategori

---

## 7. PENDEKATAN INTEGRASI

### 7.1 Integrasi SSO (MyUMPSA-ID)

#### 7.1.1 Konfigurasi Keycloak
```php
// Keycloak Configuration
'keycloak' => [
    'realm' => 'UMPSA',
    'auth-server-url' => 'https://sso.umpsa.edu.my',
    'resource' => 'meeting-system',
    'credentials' => [
        'secret' => 'client-secret'
    ],
]
```

#### 7.1.2 Aliran Pengesahan
1. Pengguna akses sistem
2. Redirect ke Keycloak
3. Pengesahan kelayakan
4. Token dikembalikan
5. Akses dibenarkan

### 7.2 Integrasi Oracle Database

#### 7.2.1 Konfigurasi
```php
// database.php
'oracle' => [
    'driver' => 'oracle',
    'host' => env('DB_HOST', 'localhost'),
    'port' => env('DB_PORT', '1521'),
    'database' => env('DB_DATABASE', 'UMPSA'),
    'username' => env('DB_USERNAME', ''),
    'password' => env('DB_PASSWORD', ''),
    'charset' => 'AL32UTF8',
]
```

### 7.3 Integrasi e-Takwim

#### 7.3.1 API Integration
```php
class TakwimIntegrationService
{
    public function syncMeetings()
    {
        // Fetch from e-Takwim API
        // Parse and store locally
        // Update display
    }
}
```

### 7.4 Integrasi E-Voting

- Pengambilan keputusan daripada sistem E-Voting
- Paparan keputusan dalam modul mesyuarat

### 7.5 Integrasi Executive Approval

- Notifikasi kepada eksekutif
- Paparan dalam dashboard eComm
- Status kelulusan

---

## 8. REKABENTUK PANGKALAN DATA

### 8.1 Entity Relationship Diagram (ERD)

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│    users     │─────│  committees  │─────│   meetings   │
└──────────────┘     └──────────────┘     └──────────────┘
       │                    │                    │
       │             ┌──────┴──────┐            │
       │             │  members    │            │
       │             └─────────────┘            │
       │                                        │
       │             ┌──────────────┐          │
       └─────────────│   papers     │──────────┘
                     └──────────────┘
                            │
                     ┌──────┴──────┐
                     │   minutes   │
                     └─────────────┘
```

### 8.2 Jadual Utama

#### 8.2.1 Jadual meetings
```sql
CREATE TABLE meetings (
    id NUMBER PRIMARY KEY,
    meeting_type VARCHAR2(50),
    title VARCHAR2(255),
    meeting_date DATE,
    start_time TIMESTAMP,
    end_time TIMESTAMP,
    venue VARCHAR2(255),
    committee_id NUMBER,
    status VARCHAR2(20),
    created_at TIMESTAMP,
    updated_at TIMESTAMP
);
```

#### 8.2.2 Jadual papers
```sql
CREATE TABLE papers (
    id NUMBER PRIMARY KEY,
    meeting_id NUMBER,
    paper_no VARCHAR2(50),
    title VARCHAR2(500),
    description CLOB,
    proposer_id NUMBER,
    status VARCHAR2(20),
    file_path VARCHAR2(500),
    created_at TIMESTAMP
);
```

### 8.3 Naming Convention

Semua jadual dan kolumn akan menggunakan naming convention standard:
- Jadual: plural lowercase (e.g., `meetings`, `papers`)
- Kolumn: snake_case (e.g., `meeting_date`, `created_at`)
- Index: idx_{table}_{column}
- Foreign Key: fk_{table}_{referenced_table}

---

## 9. KESELAMATAN DAN PEMATUHAN

### 9.1 ISO/IEC 27001:2022 Compliance

#### 9.1.1 Kawalan Keselamatan
| Kawalan | Penerangan | Implementasi |
|---------|------------|--------------|
| A.5.1 | Policies for information security | Security policy document |
| A.8.1 | User endpoint devices | Device management |
| A.9.1 | Access control | RBAC implementation |
| A.10.1 | Cryptographic controls | TLS 1.3, AES-256 |
| A.12.1 | Operations security | Logging & monitoring |

### 9.2 Keselamatan Aplikasi

#### 9.2.1 Laravel Security Features
- CSRF protection
- SQL injection prevention (Eloquent ORM)
- XSS protection
- Password hashing (bcrypt)
- Rate limiting

#### 9.2.2 Additional Security Measures
```php
// Middleware for security
class SecurityHeadersMiddleware
{
    public function handle($request, $next)
    {
        $response = $next($request);
        
        $response->header('X-Frame-Options', 'DENY');
        $response->header('X-Content-Type-Options', 'nosniff');
        $response->header('X-XSS-Protection', '1; mode=block');
        $response->header('Strict-Transport-Security', 'max-age=31536000');
        
        return $response;
    }
}
```

### 9.3 Penetration Testing

Pelan ujian penembusan:
1. **OWASP Top 10** - Ujian terhadap 10 risiko keselamatan web
2. **API Security** - Ujian endpoint API
3. **Authentication Testing** - Ujian mekanisme login
4. **Authorization Testing** - Ujian kawalan akses

---

## 10. REKABENTUK UI/UX

### 10.1 Prinsip Rekabentuk

1. **Responsiveness** - Berfungsi pada semua peranti
2. **Accessibility** - Mematuhi WCAG 2.1
3. **Consistency** - Gaya seragam
4. **Usability** - Mudah digunakan

### 10.2 Komponen UI

#### 10.2.1 Dashboard
```
┌────────────────────────────────────────────────────────┐
│  HEADER: Logo | Navigation | User Profile | Logout    │
├────────────────────────────────────────────────────────┤
│  SIDEBAR    │  MAIN CONTENT                            │
│             │                                          │
│  - Dashboard│  ┌──────────────┐  ┌──────────────┐     │
│  - Meetings │  │ Upcoming     │  │ Statistics   │     │
│  - Papers   │  │ Meetings     │  │              │     │
│  - Minutes  │  └──────────────┘  └──────────────┘     │
│  - Reports  │                                          │
│             │  ┌──────────────────────────────────┐   │
│             │  │ Recent Activities                │   │
│             │  └──────────────────────────────────┘   │
└────────────────────────────────────────────────────────┘
```

### 10.3 Filament PHP Implementation

```php
class MeetingResource extends Resource
{
    protected static ?string $model = Meeting::class;
    
    public static function form(Form $form): Form
    {
        return $form
            ->schema([
                Forms\Components\TextInput::make('title')
                    ->required()
                    ->maxLength(255),
                Forms\Components\DateTimePicker::make('meeting_date')
                    ->required(),
                // ... more fields
            ]);
    }
}
```

---

## 11. STRATEGI PENGUJIAN

### 11.1 Jenis Ujian

| Jenis Ujian | Penerangan | Tools |
|-------------|------------|-------|
| Unit Testing | Ujian komponen individu | PHPUnit |
| Feature Testing | Ujian fungsi keseluruhan | PHPUnit |
| Browser Testing | Ujian UI/UX | Laravel Dusk |
| API Testing | Ujian endpoint API | Postman/Newman |
| Security Testing | Ujian keselamatan | OWASP ZAP |

### 11.2 User Acceptance Test (UAT)

#### 11.2.1 UAT Plan
- **UAT 1**: Modul individu (Month 6)
- **UAT 2**: Sistem lengkap (Month 7)

#### 11.2.2 UAT Scenarios
1. Login dengan SSO
2. Pendaftaran mesyuarat
3. Kemasukan kertas kerja
4. Pengedaran minit
5. Pelacakan tindakan

### 11.3 Final Acceptance Test (FAT)

#### 11.3.1 FAT Criteria
- Semua UAT scenarios lulus
- Performance meets requirements
- Security penetration test passed
- Documentation complete

---

## 12. PELAN MIGRASI

### 12.1 Strategi Migrasi

**Big Bang vs. Phased**: Kami mencadangkan pendekatan **Phased Migration**:

| Fasa | Modul | Tempoh |
|------|-------|--------|
| 1 | Login, E-Authorization | Week 1 |
| 2 | Meeting Registration, e-Takwim | Week 2-3 |
| 3 | E-Committee, E-Paper | Week 4-5 |
| 4 | E-Decision, E-Minutes | Week 6-7 |
| 5 | E-Progress, E-Cabutan | Week 8 |

### 12.2 Data Migration

```php
class DataMigrationService
{
    public function migrateUsers()
    {
        // Extract from old system
        // Transform to new format
        // Load to new system
    }
    
    public function migrateMeetings()
    {
        // Historical meeting data
        // Committee information
        // Member records
    }
}
```

### 12.3 Rollback Plan

Jika berlaku masalah:
1. Aktifkan sistem lama
2. Kembangkan ke versi sebelumnya
3. Selesaikan isu
4. Retry migration

---

## 13. PENGURUSAN RISIKO

### 13.1 Risiko Utama

| Risiko | Kesan | Mitigasi |
|--------|-------|----------|
| Integration delay | Project delay | Early POC, dedicated integration team |
| Performance issue | User dissatisfaction | Load testing, optimization |
| Data loss | Operational impact | Backup strategy, migration rehearsal |
| Scope creep | Budget overrun | Change management process |

### 13.2 Contingency Plan

**Backup Team**: Pasukan sedia untuk mengambil alih jika diperlukan.

**Buffer Time**: 2 minggu buffer dalam jadual.

**Alternative Solutions**: Backup plans untuk setiap komponen kritikal.

---

## 14. STRUKTUR PASUKAN PROJEK

### 14.1 Organisasi Projek

```
                    ┌─────────────────┐
                    │  Project Board  │
                    │    (UMPSA)      │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │ Steering Comm.  │
                    │  (Joint UMPSA & │
                    │   Contractor)   │
                    └────────┬────────┘
                             │
┌──────────────────────────────────────────────────────┐
│                   Project Manager                      │
│              (Sinergi Elit Sdn Bhd)                   │
└──────────────────────────────────────────────────────┘
         │           │           │           │
    ┌────▼────┐ ┌────▼────┐ ┌────▼────┐ ┌────▼────┐
    │ Technical│ │ Business│ │  QA/    │ │ Change  │
    │  Lead    │ │ Analyst │ │ Testing │ │ Mgmt    │
    └────┬────┘ └─────────┘ └────┬────┘ └─────────┘
         │                        │
    ┌────▼────┐              ┌────▼────┐
    │Developers│              │ Testers │
    └─────────┘              └─────────┘
```

### 14.2 Peranan dan Tanggungjawab

| Peranan | Nama | Tanggungjawab |
|---------|------|---------------|
| Project Manager | TBD | Overall project delivery |
| Technical Lead | TBD | Architecture & development |
| Business Analyst | TBD | Requirements & documentation |
| Developers | 3 persons | Coding & unit testing |
| QA Engineer | 1 person | Testing & quality |
| UI/UX Designer | 1 person | Interface design |

### 14.3 Keperluan Sumber

**Sumber dari Sinergi Elit**:
- Full-time: 6 orang
- Part-time: 2 orang (specialist)

**Sumber dari UMPSA**:
- Project Sponsor: 1 orang
- Technical Coordinator: 1 orang
- End User Representatives: 3 orang

---

## 15. PENGHANTARAN PROJEK

### 15.1 Deliverables Utama

| No. | Deliverable | Deskripsi | Tempoh |
|-----|-------------|-----------|--------|
| 1 | Sistem Pengurusan Mesyuarat | Aplikasi lengkap | Month 8 |
| 2 | Laravel Shift Account | Subscription | Month 1 |
| 3 | Kick-off Meeting | Mesyuarat permulaan | Week 1 |
| 4 | Workshop | Bengkel keperluan | Week 2-3 |
| 5 | Implementation Plan | Pelan pelaksanaan | Week 5 |
| 6 | UI/UX Design | Rekabentuk antara muka | Week 6 |
| 7 | Training Plan & Schedule | Jadual latihan | Week 7 |
| 8 | BRS, SRS, SDS | Dokumen spesifikasi | Month 2-3 |
| 9 | Test Scripts, UAT, PenTest, FAT | Dokumen pengujian | Month 6-7 |
| 10 | User Manuals | Manual pengguna | Month 7 |
| 11 | Coding Standard Compliance | Dokumen pematuhan | Month 4 |
| 12 | Certification Documents | Dokumen pentauliahan | Month 8 |
| 13 | Warranty Documents | Dokumen jaminan | Month 8 |
| 14 | Desktop PC | Komputer di UMPSA | Week 1 |

### 15.2 Jadual Penghantaran

Lihat dokumen **JADUAL-KERJA.md** untuk maklumat terperinci.

### 15.3 Tempoh Jaminan

- **Tempoh**: 12 bulan dari FAT
- **Skop**: Corrective maintenance, bug fixes
- **SLA**: 4 jam response time

---

## LAMPIRAN

### Lampiran A: Carta Aliran Proses
### Lampiran B: Wireframe UI
### Lampiran C: Contoh Laporan
### Lampiran D: Sijil dan Akreditasi
### Lampiran E: Profil Pasukan

---

**Disediakan oleh:**

Sinergi Elit Sdn Bhd

**Tarikh:** 21 Februari 2026

**Versi:** 1.0
