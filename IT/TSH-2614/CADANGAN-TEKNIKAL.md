# CADANGAN TEKNIKAL
## TSH-2614: Sistem Portal Staf (eCommunity)
### UMPSA/BEND/SH/2026(3)

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
Sinergi Elit Sdn Bhd dengan sukacitanya mengemukakan Cadangan Teknikal ini bagi tender UMPSA/BEND/SH/2026(3) untuk pembangunan Sistem Portal Staf (eCommunity) di Universiti Malaysia Pahang Al-Sultan Abdullah (UMPSA).

### 1.2 Objektif Utama
- Membangunkan portal staf berasaskan web yang moden dan komprehensif
- Menggantikan sistem sedia ada (Java JSP) dengan teknologi Laravel PHP terkini
- Menyediakan platform bersepadu untuk temujanji, memo, pengumuman dan pengurusan pengguna
- Memastikan integrasi lancar dengan sistem sedia ada UMPSA

### 1.3 Nilai Tambah Utama
1. **Teknologi Terkini**: Laravel 11.x dengan PHP 8.3
2. **Integrasi Penuh**: SSO, Google Calendar, Mobile Notification
3. **Antara Muka Moden**: Responsive design dengan Filament PHP
4. **Keselamatan**: Pematuhan ISMS dan ISO/IEC 27001:2022
5. **Sokongan**: 12 bulan tempoh jaminan dengan SLA 4 jam

### 1.4 Pengalaman Berkaitan
- 8 tahun pengalaman dalam pembangunan Laravel
- 20+ projek portal staf/HR system selesai
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
| Staff Portal System | UITM | RM 950K | Selesai 2024 |
| e-Community Portal | UTM | RM 720K | Selesai 2023 |
| HR Self-Service Portal | Private Sector | RM 550K | Selesai 2024 |
| Employee Portal | USM | RM 680K | Selesai 2023 |
| Campus Portal | UPM | RM 890K | Selesai 2022 |

### 2.4 Sijil dan Akreditasi
- Sijil Kementerian Kewangan (MOF) - Gred G7
- Sijil Taraf Bumiputera
- Sijil ISO 9001:2015 (Quality Management)
- Sijil ISO 27001:2022 (Information Security)

---

## 3. PEMAHAMAN KEPERLUAN

### 3.1 Skop Projek
Projek ini melibatkan:
- Pembangunan 7 modul utama portal staf
- Migrasi dari sistem Java JSP kepada Laravel PHP
- Integrasi dengan sistem sedia ada UMPSA
- Pelatihan dan dokumentasi lengkap

### 3.2 Keperluan Fungsian Utama

#### 3.2.1 Modul Pengguna (Login)
- Single Sign-On (SSO) dengan Keycloak
- Google Sign-in sebagai alternatif
- Pengurusan sesi yang selamat

#### 3.2.2 Modul Temujanji dan Kalendar
- Pengurusan temujanji peribadi
- Integrasi Google Calendar
- Paparan kalendar harian/mingguan/bulanan

#### 3.2.3 Modul Memo
- Pengurusan memo dalaman
- Fungsi carian dan folder
- Pengurusan pengirim/penerima

#### 3.2.4 Modul Pengumuman
- Pengurusan pengumuman aktif
- Fungsi arkib
- Carian dan penapisan

#### 3.2.5 Modul Pengurusan Pengguna
- User Authorization
- User Privilege (RBAC)
- Group Privilege
- Audit Log
- Senarai pengguna

#### 3.2.6 Modul Tetapan
- Pengurusan kumpulan
- Personalisasi menu
- Susun atur dan tema

#### 3.2.7 Modul Notifikasi
- Real-time notifications
- Dashboard alerts
- Mobile notification integration

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
│  │   Browser   │  │   Responsive│  │   (Google Calendar)     │  │
│  └─────────────┘  └─────────────┘  └─────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      APPLICATION LAYER                           │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              Laravel 11 Application                       │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐    │   │
│  │  │  Login   │ │ Calendar │ │   Memo   │ │Announce- │    │   │
│  │  │  Module  │ │  Module  │ │  Module  │ │  ments   │    │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘    │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐                 │   │
│  │  │  User    │ │ Settings │ │Notification              │   │
│  │  │  Mgmt    │ │  Module  │ │  Module  │                 │   │
│  │  └──────────┘ └──────────┘ └──────────┘                 │   │
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
│   ├── User.php
│   ├── Appointment.php
│   ├── Memo.php
│   ├── Announcement.php
│   └── Notification.php
├── Services/                 # Business services
│   ├── CalendarService.php
│   ├── NotificationService.php
│   └── SyncService.php
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
    container_name: umpsa-portal-app
    
  webserver:
    image: nginx:alpine
    container_name: umpsa-portal-web
    
  database:
    image: oracle-db:latest
    container_name: umpsa-portal-db
    
  redis:
    image: redis:alpine
    container_name: umpsa-portal-cache
```

---

## 5. TEKNOLOGI YANG DICADANGKAN

### 5.1 Technology Stack

| Komponen | Teknologi | Versi | Justifikasi |
|----------|-----------|-------|-------------|
| **Framework** | Laravel | 11.x | Latest stable, Eloquent ORM |
| **PHP** | PHP | 8.3 | Latest version, performance |
| **Database** | Oracle | 19c+ | Sedia ada di UMPSA |
| **Frontend** | Filament PHP | 3.x | Modern admin panel |
| **Styling** | Tailwind CSS | 3.x | Utility-first, responsive |
| **Cache** | Redis | 7.x | High-performance caching |
| **Queue** | Redis Queue | - | Background jobs |
| **Search** | Laravel Scout | - | Full-text search |
| **API** | Laravel Sanctum | - | API authentication |
| **Testing** | PHPUnit | 10.x | Automated testing |
| **Container** | Docker | - | Consistent deployment |

### 5.2 Laravel Shift Subscription

- Melanggan **Laravel Shift Shifty Plan (Latest Single)**
- Tempoh: 3 tahun
- Mengkonfigurasi di repository GitLab UMPSA

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

---

## 6. PENERANGAN MODUL

### 6.1 Modul Login (Authentication)

#### 6.1.1 Fungsi Utama
- SSO dengan Keycloak Identity Provider
- Google Sign-in alternative
- Secure session management

#### 6.1.2 Implementasi
```php
class LoginController extends Controller
{
    public function login(Request $request)
    {
        // Validate credentials
        // Check against Keycloak
        // Create local session
        // Redirect to dashboard
    }
}
```

### 6.2 Modul Temujanji dan Kalendar

#### 6.2.1 Pengurusan Temujanji
- Tambah/ubah/padam temujanji
- Pilih peserta dari OU/AD
- Semakan Google Calendar
- Elak pertindihan jadual

#### 6.2.2 Papar Kalendar
- Format harian/mingguan/bulanan
- Sinkronisasi Google Calendar
- Penjanaan laporan PDF

### 6.3 Modul Memo

#### 6.3.1 Fungsi Utama
- Senarai memo diterima
- Carian kata kunci/tarikh/pengirim
- Pengurusan folder

### 6.4 Modul Pengumuman

#### 6.4.1 Fungsi Utama
- Senarai pengumuman aktif
- Tambah/ubah/padam pengumuman
- Fungsi arkib
- Carian dan penapisan

### 6.5 Modul Pengurusan Pengguna

#### 6.5.1 User Authorization
- Pengesahan identiti
- Kawalan akses

#### 6.5.2 User Privilege
- Role-based access
- Tahap akses peranan

#### 6.5.3 Group Privilege
- Pengurusan kumpulan
- Akses berkumpulan

#### 6.5.4 Audit Log
- Rekod aktiviti pengguna
- Laporan dan statistik

#### 6.5.5 Senarai Pengguna
- Paparan maklumat asas
- Fungsi carian

### 6.6 Modul Tetapan

#### 6.6.1 Pengurusan Kumpulan
- Pengelompokan pengguna
- Pemberian akses

#### 6.6.2 Personalisasi Menu
- Ubah susunan menu
- Konfigurasi paparan

#### 6.6.3 Susun Atur & Tema
- Pilihan tema warna
- Susun atur antaramuka

### 6.7 Modul Notifikasi

#### 6.7.1 Fungsi Utama
- Real-time notifications
- Dashboard alerts
- Direct link ke item
- Mobile notification integration

---

## 7. PENDEKATAN INTEGRASI

### 7.1 Integrasi SSO (MyUMPSA-ID)

```php
// Keycloak Configuration
'keycloak' => [
    'realm' => 'UMPSA',
    'auth-server-url' => 'https://sso.umpsa.edu.my',
    'resource' => 'portal-system',
    'credentials' => [
        'secret' => 'client-secret'
    ],
]
```

### 7.2 Integrasi Google Calendar

```php
class GoogleCalendarService
{
    public function syncEvents()
    {
        // Fetch from Google Calendar API
        // Parse and store locally
        // Update display
    }
    
    public function checkConflicts($start, $end)
    {
        // Check for overlapping events
        // Return availability status
    }
}
```

### 7.3 Integrasi Oracle Database

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

### 7.4 Integrasi Mobile Notification

- Integrasi dengan sistem Notifikasi Mudah Alih sedia ada
- Push notification support
- Real-time updates

---

## 8. REKABENTUK PANGKALAN DATA

### 8.1 Entity Relationship Diagram

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│    users     │─────│appointments  │─────│  groups      │
└──────────────┘     └──────────────┘     └──────────────┘
       │                                            │
       │             ┌──────────────┐              │
       └─────────────│   memos      │──────────────┘
                     └──────────────┘
                            │
                     ┌──────┴──────┐
                     │announcements│
                     └─────────────┘
```

### 8.2 Jadual Utama

#### 8.2.1 Jadual users
```sql
CREATE TABLE users (
    id NUMBER PRIMARY KEY,
    name VARCHAR2(255),
    email VARCHAR2(255) UNIQUE,
    keycloak_id VARCHAR2(255),
    department VARCHAR2(100),
    role VARCHAR2(50),
    status VARCHAR2(20),
    created_at TIMESTAMP,
    updated_at TIMESTAMP
);
```

#### 8.2.2 Jadual appointments
```sql
CREATE TABLE appointments (
    id NUMBER PRIMARY KEY,
    user_id NUMBER,
    title VARCHAR2(255),
    description CLOB,
    start_time TIMESTAMP,
    end_time TIMESTAMP,
    google_event_id VARCHAR2(255),
    status VARCHAR2(20),
    created_at TIMESTAMP
);
```

---

## 9. KESELAMATAN DAN PEMATUHAN

### 9.1 ISO/IEC 27001:2022 Compliance

| Kawalan | Penerangan | Implementasi |
|---------|------------|--------------|
| A.5.1 | Information security policies | Security policy document |
| A.9.1 | Access control | RBAC implementation |
| A.10.1 | Cryptographic controls | TLS 1.3, AES-256 |
| A.12.1 | Operations security | Logging & monitoring |

### 9.2 Keselamatan Aplikasi

```php
// Security Middleware
class SecurityHeadersMiddleware
{
    public function handle($request, $next)
    {
        $response = $next($request);
        
        $response->header('X-Frame-Options', 'DENY');
        $response->header('X-Content-Type-Options', 'nosniff');
        $response->header('Strict-Transport-Security', 'max-age=31536000');
        
        return $response;
    }
}
```

---

## 10. REKABENTUK UI/UX

### 10.1 Prinsip Rekabentuk

1. **Responsiveness** - Semua peranti
2. **Accessibility** - WCAG 2.1 compliance
3. **Consistency** - Gaya seragam
4. **Usability** - Mudah digunakan

### 10.2 Dashboard Design

```
┌────────────────────────────────────────────────────────┐
│  HEADER: Logo | Navigation | Notifications | Profile  │
├────────────────────────────────────────────────────────┤
│  SIDEBAR    │  MAIN CONTENT                            │
│             │                                          │
│  - Dashboard│  ┌──────────────┐  ┌──────────────┐     │
│  - Calendar │  │ Upcoming     │  │ Quick        │     │
│  - Memos    │  │ Appointments │  │ Actions      │     │
│  - Announce-│  └──────────────┘  └──────────────┘     │
│    ments    │                                          │
│  - Settings │  ┌──────────────────────────────────┐   │
│             │  │ Recent Announcements             │   │
│             │  └──────────────────────────────────┘   │
└────────────────────────────────────────────────────────┘
```

---

## 11. STRATEGI PENGUJIAN

### 11.1 Jenis Ujian

| Jenis Ujian | Tools |
|-------------|-------|
| Unit Testing | PHPUnit |
| Feature Testing | PHPUnit |
| Browser Testing | Laravel Dusk |
| API Testing | Postman |
| Security Testing | OWASP ZAP |

### 11.2 User Acceptance Test (UAT)

- **UAT 1**: Modul individu (Month 6)
- **UAT 2**: Sistem lengkap (Month 7)

### 11.3 Final Acceptance Test (FAT)

- Pada production server
- Semua scenarios lulus
- Dokumentasi lengkap

---

## 12. PELAN MIGRASI

### 12.1 Strategi Migrasi

| Fasa | Aktiviti | Tempoh |
|------|----------|--------|
| 1 | Login & User Management | Week 1 |
| 2 | Calendar & Appointments | Week 2-3 |
| 3 | Memos & Announcements | Week 4-5 |
| 4 | Settings & Notifications | Week 6-7 |
| 5 | Go-live & Support | Week 8 |

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
}
```

---

## 13. PENGURUSAN RISIKO

### 13.1 Risiko Utama

| Risiko | Mitigasi |
|--------|----------|
| Integration delay | Early POC |
| Performance issue | Load testing |
| Data loss | Backup strategy |
| Scope creep | Change management |

---

## 14. STRUKTUR PASUKAN PROJEK

### 14.1 Organisasi

```
Project Manager
├── Technical Lead
│   ├── Developer 1 (Backend)
│   ├── Developer 2 (Frontend)
│   └── Developer 3 (Integration)
├── Business Analyst
├── QA Engineer
└── UI/UX Designer
```

### 14.2 Sumber

| Peranan | Kuantiti |
|---------|----------|
| Project Manager | 1 |
| Technical Lead | 1 |
| Developers | 3 |
| Business Analyst | 1 |
| QA Engineer | 1 |
| UI/UX Designer | 1 |

---

## 15. PENGHANTARAN PROJEK

### 15.1 Deliverables

| No. | Deliverable | Tempoh |
|-----|-------------|--------|
| 1 | Sistem Portal Staf | Month 8 |
| 2 | Laravel Shift Account | Month 1 |
| 3 | Implementation Plan | Week 5 |
| 4 | UI/UX Design | Week 6 |
| 5 | SRS, SDS | Month 2-3 |
| 6 | UAT, FAT | Month 6-7 |
| 7 | User Manuals | Month 7 |

### 15.2 Tempoh Jaminan

- **Tempoh**: 12 bulan dari FAT
- **SLA**: 4 jam response time

---

**Disediakan oleh:**

Sinergi Elit Sdn Bhd

**Tarikh:** 21 Februari 2026

**Versi:** 1.0
