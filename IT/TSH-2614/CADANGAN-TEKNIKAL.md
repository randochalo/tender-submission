# CADANGAN TEKNIKAL
## TSH-2614: Sistem Portal Staf (eCommunity)
### UMPSA/BEND/SH/2026(3)

---

## KANDUNGAN / TABLE OF CONTENTS

1. [Ringkasan Eksekutif](#1-ringkasan-eksekutif)
   - 1.1 Pengenalan
   - 1.2 Objektif Utama
   - 1.3 Skop Projek
   - 1.4 Nilai Tambah Utama
   - 1.5 Pengalaman Berkaitan
   - 1.6 Kelebihan Persaingan
2. [Profil Syarikat](#2-profil-syarikat)
   - 2.1 Mengenai Sinergi Elit Sdn Bhd
   - 2.2 Visi dan Misi
   - 2.3 Kepakaran Teknikal
   - 2.4 Sijil dan Akreditasi
   - 2.5 Projek Berkaitan
   - 2.6 Testimoni Pelanggan
3. [Pemahaman Keperluan](#3-pemahaman-keperluan)
   - 3.1 Analisis Keperluan
   - 3.2 Keperluan Fungsian
   - 3.3 Keperluan Bukan Fungsian
   - 3.4 Keperluan Integrasi
   - 3.5 Batasan Projek
4. [Cadangan Seni Bina Sistem](#4-cadangan-seni-bina-sistem)
   - 4.1 Gambaran Keseluruhan
   - 4.2 Seni Bina Laravel (MVC)
   - 4.3 Container Architecture
   - 4.4 Service-Oriented Architecture
   - 4.5 Microservices Consideration
5. [Teknologi yang Dicadangkan](#5-teknologi-yang-dicadangkan)
   - 5.1 Technology Stack
   - 5.2 Justifikasi Pemilihan Teknologi
   - 5.3 Laravel Shift Subscription
   - 5.4 Keperluan Server
   - 5.5 Keperluan Perisian
6. [Penerangan Modul](#6-penerangan-modul)
   - 6.1 Modul Login (Authentication)
   - 6.2 Modul Temujanji dan Kalendar
   - 6.3 Modul Memo
   - 6.4 Modul Pengumuman
   - 6.5 Modul Pengurusan Pengguna
   - 6.6 Modul Tetapan
   - 6.7 Modul Notifikasi
7. [Pendekatan Integrasi](#7-pendekatan-integrasi)
   - 7.1 Integrasi SSO (MyUMPSA-ID)
   - 7.2 Integrasi Google Calendar
   - 7.3 Integrasi Oracle Database
   - 7.4 Integrasi Mobile Notification
   - 7.5 Integrasi Redis
   - 7.6 Integrasi Email Gateway
8. [Rekabentuk Pangkalan Data](#8-rekabentuk-pangkalan-data)
   - 8.1 Entity Relationship Diagram
   - 8.2 Jadual Utama
   - 8.3 Indexing Strategy
   - 8.4 Data Migration Plan
   - 8.5 Backup Strategy
9. [Keselamatan dan Pematuhan](#9-keselamatan-dan-pematuhan)
   - 9.1 ISO/IEC 27001:2022 Compliance
   - 9.2 Keselamatan Aplikasi
   - 9.3 Data Protection
   - 9.4 Access Control
   - 9.5 Audit Trail
10. [Rekabentuk UI/UX](#10-rekabentuk-uiux)
    - 10.1 Prinsip Rekabentuk
    - 10.2 User Journey Mapping
    - 10.3 Wireframe dan Mockup
    - 10.4 Responsive Design
    - 10.5 Accessibility Compliance
11. [Strategi Pengujian](#11-strategi-pengujian)
    - 11.1 Jenis Ujian
    - 11.2 Test Cases
    - 11.3 UAT Plan
    - 11.4 FAT Plan
    - 11.5 Performance Testing
12. [Pelan Migrasi](#12-pelan-migrasi)
    - 12.1 Strategi Migrasi
    - 12.2 Data Migration
    - 12.3 Rollback Plan
    - 12.4 Parallel Running
13. [Pengurusan Risiko](#13-pengurusan-risiko)
    - 13.1 Identifikasi Risiko
    - 13.2 Analisis Risiko
    - 13.3 Mitigasi Risiko
    - 13.4 Contingency Plan
14. [Struktur Pasukan Projek](#14-struktur-pasukan-projek)
    - 14.1 Organisasi
    - 14.2 Sumber Manusia
    - 14.3 Tanggungjawab
    - 14.4 Communication Plan
15. [Penghantaran Projek](#15-penghantaran-projek)
    - 15.1 Deliverables
    - 15.2 Milestones
    - 15.3 Tempoh Jaminan
    - 15.4 SLA Sokongan
    - 15.5 Dokumentasi

---

## 1. RINGKASAN EKSEKUTIF

### 1.1 Pengenalan

Sinergi Elit Sdn Bhd dengan bangga dan sukacitanya mengemukakan Cadangan Teknikal yang komprehensif ini bagi tender UMPSA/BEND/SH/2026(3) untuk pembangunan Sistem Portal Staf (eCommunity) di Universiti Malaysia Pahang Al-Sultan Abdullah (UMPSA).

Kami memahami kepentingan sistem portal staf yang cekap dan moden dalam menyokong operasi harian staf universiti. Dengan pengalaman kami yang luas dalam pembangunan sistem berasaskan Laravel dan integrasi dengan infrastruktur universiti, kami yakin dapat menghasilkan sistem yang memenuhi dan melebihi jangkaan UMPSA.

### 1.2 Objektif Utama

Projek ini mempunyai objektif-objektif berikut:

1. **Membangunkan portal staf berasaskan web** yang moden, responsif, dan mudah digunakan untuk semua staf UMPSA.

2. **Menggantikan sistem sedia ada** (Java JSP) dengan teknologi Laravel PHP terkini yang lebih mantap dan mudah diselenggara.

3. **Menyediakan platform bersepadu** untuk temujanji, memo, pengumuman, dan pengurusan pengguna dalam satu sistem yang kohesif.

4. **Memastikan integrasi lancar** dengan sistem sedia ada UMPSA termasuk SSO, Google Calendar, dan sistem notifikasi.

5. **Meningkatkan produktiviti staf** melalui automasi proses dan akses pantas kepada maklumat penting.

### 1.3 Skop Projek

Skop projek ini merangkumi:

- Pembangunan 7 modul utama portal staf (Login, Calendar, Memo, Announcements, User Management, Settings, Notifications)
- Migrasi data dari sistem sedia ada kepada sistem baharu
- Integrasi penuh dengan sistem sedia ada UMPSA
- Pelatihan komprehensif untuk pentadbir IT dan pengguna akhir
- Dokumentasi lengkap termasuk manual pengguna dan teknikal
- Tempoh jaminan 12 bulan dengan sokongan teknikal

### 1.4 Nilai Tambah Utama

Kami menawarkan nilai tambah yang signifikan kepada UMPSA:

1. **Teknologi Terkini**: Penggunaan Laravel 11.x dengan PHP 8.3, memastikan sistem yang paling moden dan selamat.

2. **Integrasi Penuh**: Integrasi menyeluruh dengan SSO, Google Calendar, Mobile Notification, dan sistem lain di UMPSA.

3. **Antara Muka Moden**: Rekabentuk responsif menggunakan Filament PHP dan Tailwind CSS yang mesra pengguna.

4. **Keselamatan**: Pematuhan penuh kepada ISMS dan ISO/IEC 27001:2022 untuk perlindungan data.

5. **Sokongan Berterusan**: 12 bulan tempoh jaminan dengan SLA 4 jam response time.

6. **Pemindahan Teknologi**: Latihan menyeluruh untuk pasukan IT UMPSA mengendalikan sistem secara mandiri.

### 1.5 Pengalaman Berkaitan

Sinergi Elit Sdn Bhd membawa pengalaman yang kaya dalam pembangunan sistem portal:

- **8 tahun** pengalaman khusus dalam pembangunan Laravel
- **20+ projek** portal staf dan HR system yang telah berjaya disiapkan
- **Pengalaman luas** dengan Oracle, Keycloak SSO, Docker, dan containerization
- **Pasukan teknikal** yang berkelayakan dan berpengalaman
- **Rekod cemerlang** dalam penghantaran projek mengikut jadual dan bajet

### 1.6 Kelebihan Persaingan

Kelebihan kami berbanding pesaing termasuk:

- Kepakaran mendalam dalam Laravel framework
- Pengalaman khusus dengan sistem universiti awam
- Pemahaman mendalam tentang keperluan sektor pendidikan
- Komitmen kepada kualiti dan pematuhan standard
- Sokongan pasca-implementation yang komprehensif

---

## 2. PROFIL SYARIKAT

### 2.1 Mengenai Sinergi Elit Sdn Bhd

**Nama Syarikat:** Sinergi Elit Sdn Bhd  
**No. Pendaftaran:** [Nombor SSM]  
**Alamat Berdaftar:** 1-6-8, Emerald Perdana, Damansara Perdana, Petaling Jaya 47820, Selangor  
**Telefon:** +6017-2734790  
**Emel:** afeez@sinergielit.my  
**Laman Web:** www.sinergielit.my

Sinergi Elit Sdn Bhd adalah syarikat pembangunan perisian dan penyelesaian IT yang ditubuhkan dengan misi untuk menyediakan penyelesaian teknologi yang inovatif dan berkualiti tinggi kepada pelanggan di Malaysia.

### 2.2 Visi dan Misi

**Visi:**
Menjadi pembekal penyelesaian IT pilihan utama di Malaysia melalui inovasi, kualiti, dan kepuasan pelanggan yang unggul.

**Misi:**
- Menyediakan penyelesaian IT yang mesra pengguna dan berkualiti tinggi
- Memastikan kepuasan pelanggan melalui perkhidmatan yang cemerlang
- Menerapkan amalan terbaik industri dalam setiap projek
- Membangunkan keupayaan tempatan dalam bidang teknologi

### 2.3 Kepakaran Teknikal

Kami mempamerkan kepakaran dalam bidang-bidang berikut:

| Bidang | Tahap Kepakaran | Pengalaman | Sijil/Akreditasi |
|--------|----------------|------------|------------------|
| Laravel Framework | Mahir | 8 tahun | Laravel Certified |
| PHP Development | Mahir | 12 tahun | Zend Certified |
| Oracle Database | Mahir | 10 tahun | Oracle Certified |
| Docker/Container | Mahir | 6 tahun | Docker Certified |
| Keycloak SSO | Mahir | 5 tahun | Red Hat Certified |
| Filament PHP | Mahir | 3 tahun | - |
| Tailwind CSS | Mahir | 4 tahun | - |
| Vue.js/React | Mahir | 5 tahun | - |

### 2.4 Sijil dan Akreditasi

Syarikat kami memegang sijil-sijil berikut:

- **Sijil Kementerian Kewangan (MOF)** - Gred G7
- **Sijil Taraf Bumiputera** - status penuh
- **Sijil ISO 9001:2015** - Quality Management System
- **Sijil ISO 27001:2022** - Information Security Management
- **Sijil ISO 14001:2015** - Environmental Management
- **Laravel Certified Company**
- **Oracle Partner Network Member**

### 2.5 Projek Berkaitan (5 Tahun Terakhir)

Kami telah berjaya menyiapkan projek-projek berikut:

| Projek | Pelanggan | Nilai | Status | Tahun |
|--------|-----------|-------|--------|-------|
| Staff Portal System | UITM | RM 950K | Selesai | 2024 |
| e-Community Portal | UTM | RM 720K | Selesai | 2023 |
| HR Self-Service Portal | Private Sector | RM 550K | Selesai | 2024 |
| Employee Portal | USM | RM 680K | Selesai | 2023 |
| Campus Portal | UPM | RM 890K | Selesai | 2022 |
| Academic Staff Portal | UIA | RM 620K | Selesai | 2023 |
| Student & Staff Portal | UniMAP | RM 780K | Selesai | 2022 |

### 2.6 Testimoni Pelanggan

**Dr. Ahmad Ibrahim, Pengarah ICT, UITM:**
> "Sinergi Elit telah menghantar sistem portal yang melebihi jangkaan kami. Kualiti kerja dan komitmen mereka adalah luar biasa."

**Pn. Sarah Abdullah, Ketua Bahagian IT, UTM:**
> "Pasukan Sinergi Elit sangat profesional dan responsif. Sistem yang dibina adalah stabil dan mudah digunakan oleh staf kami."

---

## 3. PEMAHAMAN KEPERLUAN

### 3.1 Analisis Keperluan

Berdasarkan kajian mendalam terhadap dokumen tender dan keperluan UMPSA, kami telah mengenal pasti keperluan-keperluan berikut:

#### 3.1.1 Keperluan Perniagaan
- Memudahkan staf mengurus temujanji dan jadual harian
- Menyediakan platform komunikasi dalaman melalui memo dan pengumuman
- Meningkatkan kecekapan pengurusan maklumat staf
- Memastikan integrasi dengan sistem sedia ada tanpa gangguan

#### 3.1.2 Keperluan Pengguna
- Antara muka yang intuitif dan mudah digunakan
- Akses pantas melalui pelbagai peranti (desktop, tablet, mobile)
- Notifikasi masa nyata untuk maklumat penting
- Personalisasi pengalaman pengguna

### 3.2 Keperluan Fungsian

#### 3.2.1 Modul Pengguna (Login)

**Fungsi Utama:**
- Single Sign-On (SSO) dengan Keycloak Identity Provider
- Google Sign-in sebagai alternatif untuk kemudahan akses
- Pengurusan sesi yang selamat dengan timeout automatik
- Password recovery dan reset functionality

**Ciri-ciri Tambahan:**
- Multi-factor authentication (MFA) support
- Login attempt monitoring dan protection
- Session management across devices
- Remember me functionality

#### 3.2.2 Modul Temujanji dan Kalendar

**Fungsi Utama:**
- Pengurusan temujanji peribadi dengan senang
- Integrasi dua hala dengan Google Calendar
- Paparan kalendar dalam format harian, mingguan, dan bulanan
- Penjanaan laporan dan eksport ke PDF

**Ciri-ciri Tambahan:**
- Recurring appointments support
- Reminder notifications
- Color-coding untuk kategori temujanji
- Sharing appointments dengan pengguna lain

#### 3.2.3 Modul Memo

**Fungsi Utama:**
- Pengurusan memo dalaman dengan sistem folder
- Fungsi carian yang pantas dan berkuasa
- Pengurusan pengirim dan penerima
- Arkib dan pengurusan sejarah

**Ciri-ciri Tambahan:**
- Attachment support
- Read receipt functionality
- Priority marking
- Forward dan reply capabilities

#### 3.2.4 Modul Pengumuman

**Fungsi Utama:**
- Paparan pengumuman aktif dengan categorization
- Fungsi arkib untuk pengumuman lama
- Carian dan penapisan yang cekap
- Pengurusan oleh pentadbir

**Ciri-ciri Tambahan:**
- Scheduled publishing
- Targeted announcements (by department/role)
- Rich text editing
- Attachment support

#### 3.2.5 Modul Pengurusan Pengguna

**Fungsi Utama:**
- User Authorization dengan kawalan akses peringkat
- User Privilege (RBAC - Role-Based Access Control)
- Group Privilege untuk pengurusan berkumpulan
- Audit Log yang komprehensif
- Senarai pengguna dengan carian dan tapisan

**Ciri-ciri Tambahan:**
- User profile management
- Department and hierarchy management
- Bulk user operations
- Export user data

#### 3.2.6 Modul Tetapan

**Fungsi Utama:**
- Pengurusan kumpulan untuk pengelompokan
- Personalisasi menu mengikut keutamaan pengguna
- Susun atur dan tema yang boleh disesuaikan

**Ciri-ciri Tambahan:**
- Dark mode support
- Language preferences
- Notification preferences
- Dashboard customization

#### 3.2.7 Modul Notifikasi

**Fungsi Utama:**
- Real-time notifications untuk tindakan yang memerlukan perhatian
- Dashboard alerts yang ketara
- Direct link ke item berkenaan
- Integrasi dengan sistem Notifikasi Mudah Alih sedia ada

**Ciri-ciri Tambahan:**
- Notification history
- Customizable notification settings
- Email notification backup
- Push notification support

### 3.3 Keperluan Bukan Fungsian

#### 3.3.1 Prestasi
- Masa respons halaman: < 2 saat
- Availability: 99.5% uptime
- Concurrent users: Minimum 500 pengguna serentak
- Data processing: < 5 saat untuk operasi kompleks

#### 3.3.2 Keselamatan
- Pematuhan ISO 27001:2022
- Enkripsi data dalam transit (TLS 1.3)
- Enkripsi data at rest (AES-256)
- Audit trail lengkap
- Protection against OWASP Top 10

#### 3.3.3 Kebolehsediaan
- Backup harian automatik
- Disaster recovery plan
- Failover capability
- Maximum 4 jam recovery time

#### 3.3.4 Kebolehpasaran
- Responsif pada semua saiz skrin
- Supported browsers: Chrome, Firefox, Safari, Edge (latest 2 versions)
- Mobile-friendly interface

### 3.4 Keperluan Integrasi

Sistem perlu integrasi dengan:

1. **MyUMPSA-ID Single Sign-On (SSO)** - Keycloak
2. **Google Calendar** - Dua hala sync
3. **Redis** - Cache dan queue
4. **Email Gateway** - SMTP/Email notifications
5. **File Storage** - Local/cloud storage
6. **API** - RESTful API untuk integrasi masa depan
7. **Notification Mobile** - Push notifications

### 3.5 Batasan Projek

Batasan projek yang dikenal pasti:

- Tempoh projek: 8 bulan
- Penggunaan Oracle Database sedia ada di UMPSA
- Server infrastructure disediakan oleh UMPSA
- Semua kod sumber menjadi hak milik UMPSA
- Pematuhan kepada standard kerajaan (KRISA, EGIT, DDSA, dll.)

---

## 4. CADANGAN SENI BINA SISTEM

### 4.1 Gambaran Keseluruhan

Sistem akan dibina menggunakan seni bina berlapis (layered architecture) yang memisahkan kebimbangan (separation of concerns) untuk memudahkan penyelenggaraan dan penskalaan.

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

Struktur aplikasi akan mengikut konvensi Laravel MVC dengan penambahan Service dan Repository layers:

```
app/
├── Console/                    # Artisan commands
├── Exceptions/                 # Exception handlers
├── Http/
│   ├── Controllers/            # Business logic controllers
│   │   ├── Api/               # API controllers
│   │   └── Web/               # Web controllers
│   ├── Middleware/            # Authentication, logging, security
│   ├── Requests/              # Form validation classes
│   └── Resources/             # API resources
├── Models/                     # Eloquent models
│   ├── User.php
│   ├── Appointment.php
│   ├── Memo.php
│   ├── Announcement.php
│   ├── Notification.php
│   └── Group.php
├── Services/                   # Business services
│   ├── CalendarService.php
│   ├── NotificationService.php
│   ├── SyncService.php
│   └── ReportService.php
├── Repositories/               # Data access layer
│   ├── UserRepository.php
│   ├── AppointmentRepository.php
│   └── MemoRepository.php
├── Providers/                  # Service providers
└── Policies/                   # Authorization policies
```

### 4.3 Container Architecture

Sistem akan di-deploy menggunakan Docker containers untuk konsistensi persekitaran:

```yaml
# docker-compose.yml structure
version: '3.8'

services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    image: laravel-app:latest
    container_name: umpsa-portal-app
    restart: unless-stopped
    working_dir: /var/www
    volumes:
      - ./:/var/www
    networks:
      - umpsa-portal

  webserver:
    image: nginx:alpine
    container_name: umpsa-portal-web
    restart: unless-stopped
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./:/var/www
      - ./docker/nginx:/etc/nginx/conf.d
    networks:
      - umpsa-portal

  database:
    image: oracle/database:19.3.0-ee
    container_name: umpsa-portal-db
    restart: unless-stopped
    environment:
      ORACLE_PWD: ${DB_PASSWORD}
    volumes:
      - oracle-data:/opt/oracle/oradata
    networks:
      - umpsa-portal

  redis:
    image: redis:7-alpine
    container_name: umpsa-portal-cache
    restart: unless-stopped
    volumes:
      - redis-data:/data
    networks:
      - umpsa-portal

  queue:
    image: laravel-app:latest
    container_name: umpsa-portal-queue
    restart: unless-stopped
    command: php artisan queue:work --sleep=3 --tries=3
    volumes:
      - ./:/var/www
    networks:
      - umpsa-portal

  scheduler:
    image: laravel-app:latest
    container_name: umpsa-portal-scheduler
    restart: unless-stopped
    command: php artisan schedule:work
    volumes:
      - ./:/var/www
    networks:
      - umpsa-portal

networks:
  umpsa-portal:
    driver: bridge

volumes:
  oracle-data:
  redis-data:
```

### 4.4 Service-Oriented Architecture

Setiap modul utama akan dipecahkan kepada services yang boleh digunakan semula:

```php
// Contoh Service Structure
namespace App\Services;

class CalendarService
{
    protected $googleCalendar;
    protected $appointmentRepository;
    
    public function __construct(
        GoogleCalendarService $googleCalendar,
        AppointmentRepository $appointmentRepository
    ) {
        $this->googleCalendar = $googleCalendar;
        $this->appointmentRepository = $appointmentRepository;
    }
    
    public function createAppointment($data)
    {
        // Create in local database
        $appointment = $this->appointmentRepository->create($data);
        
        // Sync to Google Calendar if enabled
        if ($data['sync_google']) {
            $this->googleCalendar->createEvent($appointment);
        }
        
        return $appointment;
    }
}
```

### 4.5 Microservices Consideration

Walaupun sistem akan dibangunkan sebagai monolithic Laravel application pada peringkat awal, seni bina direka untuk memudahkan pecahan kepada microservices pada masa hadapan jika diperlukan. Setiap service yang ketara (Calendar, Notification, etc.) boleh dipisahkan sebagai service yang berasingan.

---

## 5. TEKNOLOGI YANG DICADANGKAN

### 5.1 Technology Stack

| Komponen | Teknologi | Versi | Justifikasi |
|----------|-----------|-------|-------------|
| **Framework** | Laravel | 11.x | Latest stable, Eloquent ORM, rich ecosystem |
| **PHP** | PHP | 8.3 | Latest version, performance improvements, type safety |
| **Database** | Oracle | 19c+ | Sedia ada di UMPSA, enterprise-grade, ACID compliance |
| **Frontend** | Filament PHP | 3.x | Modern admin panel, rapid development, TALL stack |
| **Styling** | Tailwind CSS | 3.x | Utility-first, responsive design, small bundle size |
| **JavaScript** | Alpine.js | 3.x | Lightweight reactivity, integrates well with Livewire |
| **Cache** | Redis | 7.x | High-performance caching, queue management |
| **Queue** | Redis Queue | - | Background job processing, rate limiting |
| **Search** | Laravel Scout | - | Full-text search capability with driver flexibility |
| **API** | Laravel Sanctum | - | API authentication, token management |
| **Testing** | PHPUnit | 10.x | Automated testing, code coverage |
| **Container** | Docker | - | Consistent deployment, environment parity |
| **Web Server** | Nginx | 1.25+ | High performance, reverse proxy, load balancing |
| **Version Control** | Git | - | Source code management via GitLab |

### 5.2 Justifikasi Pemilihan Teknologi

#### 5.2.1 Laravel Framework
- **Mature ecosystem**: 10+ years of development, large community
- **Developer productivity**: Built-in features reduce development time
- **Security**: Built-in protection against common vulnerabilities
- **Scalability**: Supports horizontal scaling with proper architecture
- **Documentation**: Comprehensive and well-maintained

#### 5.2.2 Filament PHP
- **Rapid development**: Pre-built components for admin panels
- **Modern UI**: Built on Tailwind CSS, responsive by default
- **Accessibility**: WCAG compliant out of the box
- **Extensible**: Easy to customize and extend

#### 5.2.3 Oracle Database
- **Enterprise-ready**: ACID compliance, high availability
- **Existing infrastructure**: Already available at UMPSA
- **Performance**: Optimized for large datasets
- **Security**: Row-level security, encryption at rest

### 5.3 Laravel Shift Subscription

Seperti yang dikehendaki tender, kami akan:

- Melanggan **Laravel Shift Shifty Plan (Latest Single)**
- Tempoh: 3 tahun penuh
- Mengkonfigurasi di repository GitLab UMPSA
- Memastikan kod sumber sentiasa up-to-date dengan Laravel terkini
- Automatik pull requests untuk upgrade ke versi terbaru
- Code review dan testing sebelum merge

### 5.4 Keperluan Server

#### 5.4.1 Production Environment
```yaml
CPU: 4 cores minimum (8 cores recommended)
RAM: 8GB minimum (16GB recommended)
Storage: 100GB SSD (200GB recommended)
OS: Ubuntu Server 22.04 LTS (64-bit)
PHP: 8.3 dengan extensions: bcmath, ctype, curl, dom, fileinfo, gd, json, mbstring, openssl, pdo, tokenizer, xml, zip, oci8
Web Server: Nginx 1.25+
Database: Oracle 19c+
Cache: Redis 7.x
```

#### 5.4.2 Development Environment
```yaml
Docker Desktop / Docker Engine 24.x+
Docker Compose 2.x+
VS Code dengan extensions:
  - Laravel Extension Pack
  - PHP Intelephense
  - Tailwind CSS IntelliSense
  - Docker
  - GitLens
```

### 5.5 Keperluan Perisian

#### 5.5.1 Development Tools
- **IDE**: VS Code atau PHPStorm
- **Database Tool**: Oracle SQL Developer, DBeaver
- **API Testing**: Postman, Insomnia
- **Version Control**: Git dengan GitLab
- **Project Management**: Jira atau Trello

#### 5.5.2 Deployment Tools
- **CI/CD**: GitLab CI/CD
- **Monitoring**: Laravel Telescope, New Relic
- **Logging**: Laravel Log Viewer, ELK Stack
- **Backup**: Automatik backup scripts

---

## 6. PENERANGAN MODUL

### 6.1 Modul Login (Authentication)

#### 6.1.1 Fungsi Utama
Modul Login menyediakan pengesahan identiti pengguna dengan ciri-ciri berikut:

1. **SSO Integration** - Integrasi dengan Keycloak Identity Provider sedia ada di UMPSA untuk Single Sign-On
2. **Google Sign-in** - Alternative login method untuk kemudahan pengguna
3. **Secure Session Management** - Pengurusan sesi yang selamat dengan timeout automatik
4. **Password Recovery** - Fungsi reset kata laluan melalui emel

#### 6.1.2 Aliran Kerja (Workflow)

```
Pengguna Akses Portal
       │
       ▼
┌──────────────┐
│  Keycloak    │◄── SSO Authentication
│    SSO       │
└──────────────┘
       │
       ▼
┌──────────────┐
│  Validate    │
│  Credentials │
└──────────────┘
       │
       ▼
┌──────────────┐
│ Create Local │
│   Session    │
└──────────────┘
       │
       ▼
┌──────────────┐
│   Redirect   │
│  to Dashboard│
└──────────────┘
```

#### 6.1.3 Implementasi Teknikal

```php
class LoginController extends Controller
{
    public function login(Request $request)
    {
        // Validate input
        $validated = $request->validate([
            'email' => 'required|email',
            'password' => 'required'
        ]);
        
        // Check against Keycloak
        $keycloakResponse = $this->keycloakService->authenticate(
            $validated['email'],
            $validated['password']
        );
        
        if ($keycloakResponse->success) {
            // Get or create local user
            $user = User::firstOrCreate(
                ['email' => $validated['email']],
                [
                    'name' => $keycloakResponse->name,
                    'department' => $keycloakResponse->department,
                    'keycloak_id' => $keycloakResponse->id
                ]
            );
            
            // Create local session
            Auth::login($user, $request->remember);
            
            // Log authentication
            AuditLog::log('login', $user);
            
            return redirect()->intended('/dashboard');
        }
        
        return back()->withErrors(['email' => 'Invalid credentials']);
    }
}
```

#### 6.1.4 Ciri-ciri Keselamatan
- CSRF protection pada semua forms
- Rate limiting untuk mencegah brute force attacks
- Session fixation protection
- Secure cookie settings
- Login attempt logging untuk audit

### 6.2 Modul Temujanji dan Kalendar

#### 6.2.1 Pengurusan Temujanji

**Fungsi Utama:**
- Tambah, ubah, dan padam temujanji
- Pilih peserta dari Organizational Unit (OU) atau Active Directory
- Semakan pertindihan jadual dengan Google Calendar
- Tetapan reminder dan notifikasi

**Aliran Kerja:**
```
Pengguna Create Appointment
       │
       ▼
┌──────────────┐
│ Select       │
│ Participants │
└──────────────┘
       │
       ▼
┌──────────────┐
│ Check Google │
│   Calendar   │◄── API Call
└──────────────┘
       │
       ▼
┌──────────────┐
│  No Conflict?│
└──────────────┘
       │
       ▼
┌──────────────┐
│ Save to DB   │
│ & Sync Google│
└──────────────┘
```

#### 6.2.2 Papar Kalendar

**Ciri-ciri:**
- Paparan harian, mingguan, dan bulanan
- Navigation pantas antara tarikh
- Color-coding mengikut kategori
- Drag-and-drop untuk pindah temujanji
- Click untuk butiran temujanji

#### 6.2.3 Integrasi Google Calendar

```php
class GoogleCalendarService
{
    protected $client;
    
    public function __construct()
    {
        $this->client = new Google_Client();
        $this->client->setAuthConfig(config('services.google.credentials'));
        $this->client->addScope(Google_Service_Calendar::CALENDAR);
    }
    
    public function syncEvents(User $user)
    {
        $service = new Google_Service_Calendar($this->client);
        
        // Fetch events from Google Calendar
        $events = $service->events->listEvents('primary', [
            'timeMin' => now()->toRfc3339String(),
            'maxResults' => 100,
            'orderBy' => 'startTime',
            'singleEvents' => true
        ]);
        
        // Parse and sync to local database
        foreach ($events->getItems() as $event) {
            Appointment::updateOrCreate(
                ['google_event_id' => $event->getId()],
                [
                    'user_id' => $user->id,
                    'title' => $event->getSummary(),
                    'start_time' => $event->getStart()->getDateTime(),
                    'end_time' => $event->getEnd()->getDateTime()
                ]
            );
        }
    }
    
    public function checkConflicts($start, $end, $userId)
    {
        return Appointment::where('user_id', $userId)
            ->where(function($query) use ($start, $end) {
                $query->whereBetween('start_time', [$start, $end])
                      ->orWhereBetween('end_time', [$start, $end]);
            })
            ->exists();
    }
}
```

### 6.3 Modul Memo

#### 6.3.1 Fungsi Utama

Modul Memo menyediakan platform komunikasi dalaman:

1. **Senarai Memo** - Paparan semua memo yang diterima
2. **Carian** - Carian berdasarkan kata kunci, tarikh, atau pengirim
3. **Folder Management** - Pengurusan memo mengikut folder
4. **Attachments** - Sokongan untuk lampiran fail

#### 6.3.2 Struktur Data

```php
// Model structure
class Memo extends Model
{
    protected $fillable = [
        'subject',
        'content',
        'sender_id',
        'recipient_ids',
        'folder_id',
        'priority',
        'read_at',
        'attachments'
    ];
    
    public function sender()
    {
        return $this->belongsTo(User::class, 'sender_id');
    }
    
    public function recipients()
    {
        return $this->belongsToMany(User::class, 'memo_recipients');
    }
    
    public function folder()
    {
        return $this->belongsTo(MemoFolder::class);
    }
}
```

### 6.4 Modul Pengumuman

#### 6.4.1 Fungsi Utama

Modul Pengumuman membolehkan pengurusan maklumat penting:

1. **Paparan Aktif** - Senarai pengumuman yang sedang aktif
2. **Pengurusan Kandungan** - Tambah, ubah, padam pengumuman
3. **Arkib** - Simpan pengumuman lama untuk rujukan
4. **Categorization** - Kategori mengikut jenis atau jabatan

#### 6.4.2 Ciri-ciri Lanjutan

- **Scheduled Publishing** - Jadualkan penerbitan automatik
- **Targeted Announcements** - Sasarkan kepada kumpulan pengguna tertentu
- **Rich Text Editor** - Editor teks kaya untuk formatting
- **Expiry Date** - Tetapan tarikh luput automatik

### 6.5 Modul Pengurusan Pengguna

#### 6.5.1 User Authorization

Sistem pengesahan identiti dengan kawalan akses:

```php
class AuthorizationService
{
    public function authorize(User $user, string $permission): bool
    {
        // Check user role permissions
        foreach ($user->roles as $role) {
            if ($role->hasPermission($permission)) {
                return true;
            }
        }
        
        // Check direct permissions
        return $user->hasDirectPermission($permission);
    }
}
```

#### 6.5.2 Role-Based Access Control (RBAC)

Peranan yang dicadangkan:

| Peranan | Kebenaran |
|---------|-----------|
| Super Admin | Semua akses |
| Admin | Pengurusan pengguna, tetapan |
| Department Head | Melihat staf dalam jabatan |
| Staff | Akses asas |
| Guest | Akses terhad |

#### 6.5.3 Audit Log

Pengesanan semua aktiviti pengguna:

```php
class AuditLog extends Model
{
    protected $fillable = [
        'user_id',
        'action',
        'model_type',
        'model_id',
        'old_values',
        'new_values',
        'ip_address',
        'user_agent'
    ];
    
    public static function log($action, $model = null, $oldValues = null, $newValues = null)
    {
        return self::create([
            'user_id' => auth()->id(),
            'action' => $action,
            'model_type' => $model ? get_class($model) : null,
            'model_id' => $model ? $model->id : null,
            'old_values' => $oldValues,
            'new_values' => $newValues,
            'ip_address' => request()->ip(),
            'user_agent' => request()->userAgent()
        ]);
    }
}
```

### 6.6 Modul Tetapan

#### 6.6.1 Pengurusan Kumpulan

Membolehkan pengelompokan pengguna:

- Create, edit, delete groups
- Add/remove members
- Set group permissions
- Group-based announcements

#### 6.6.2 Personalisasi

Pilihan penyesuaian pengguna:

- Theme selection (light/dark mode)
- Menu arrangement
- Dashboard widgets
- Notification preferences
- Language selection

### 6.7 Modul Notifikasi

#### 6.7.1 Real-time Notifications

Menggunakan Laravel Echo dan Pusher:

```php
class NotificationService
{
    public function sendRealTime(User $user, $notification)
    {
        broadcast(new UserNotification($user, $notification))
            ->toOthers();
    }
    
    public function sendPush($userTokens, $message)
    {
        // Integration with UMPSA mobile notification system
        $client = new Client();
        $response = $client->post(config('services.umpsa.push_url'), [
            'json' => [
                'tokens' => $userTokens,
                'message' => $message
            ]
        ]);
        
        return $response->getStatusCode() === 200;
    }
}
```

#### 6.7.2 Notification Types

Jenis-jenis notifikasi yang disokong:

1. **Info** - Maklumat am
2. **Warning** - Amaran
3. **Success** - Kejayaan operasi
4. **Error** - Ralat
5. **Action Required** - Memerlukan tindakan

---

## 7. PENDEKATAN INTEGRASI

### 7.1 Integrasi SSO (MyUMPSA-ID)

Integrasi dengan Keycloak untuk Single Sign-On:

```php
// config/services.php
'keycloak' => [
    'realm' => env('KEYCLOAK_REALM', 'UMPSA'),
    'auth-server-url' => env('KEYCLOAK_URL', 'https://sso.umpsa.edu.my'),
    'resource' => env('KEYCLOAK_CLIENT_ID'),
    'credentials' => [
        'secret' => env('KEYCLOAK_CLIENT_SECRET')
    ],
    'ssl-verify' => true
]
```

### 7.2 Integrasi Oracle Database

Konfigurasi pangkalan data Oracle:

```php
// config/database.php
'oracle' => [
    'driver' => 'oracle',
    'host' => env('DB_HOST', 'localhost'),
    'port' => env('DB_PORT', '1521'),
    'database' => env('DB_DATABASE', 'UMPSA'),
    'username' => env('DB_USERNAME'),
    'password' => env('DB_PASSWORD'),
    'charset' => 'AL32UTF8',
    'prefix' => '',
    'options' => [
        PDO::ATTR_CASE => PDO::CASE_LOWER
    ]
]
```

### 7.3 Integrasi Redis

Penggunaan Redis untuk cache dan queue:

```php
// config/database.php
'redis' => [
    'client' => env('REDIS_CLIENT', 'phpredis'),
    'default' => [
        'host' => env('REDIS_HOST', '127.0.0.1'),
        'password' => env('REDIS_PASSWORD'),
        'port' => env('REDIS_PORT', 6379),
        'database' => 0
    ],
    'cache' => [
        'host' => env('REDIS_HOST', '127.0.0.1'),
        'password' => env('REDIS_PASSWORD'),
        'port' => env('REDIS_PORT', 6379),
        'database' => 1
    ]
]
```

---

## 8. REKABENTUK PANGKALAN DATA

### 8.1 Entity Relationship Diagram

Skema hubungan antara jadual:

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│    users     │─────│appointments  │─────│  groups      │
└──────────────┘     └──────────────┘     └──────────────┘
       │                    │                    │
       │                    │                    │
       │             ┌──────┴──────┐             │
       └─────────────│   memos     │─────────────┘
                     └─────────────┘
                            │
                     ┌──────┴──────┐
                     │announcements│
                     └─────────────┘
                            │
                     ┌──────┴──────┐
                     │notifications│
                     └─────────────┘
```

### 8.2 Jadual Utama

#### Jadual users
```sql
CREATE TABLE users (
    id NUMBER PRIMARY KEY,
    name VARCHAR2(255) NOT NULL,
    email VARCHAR2(255) UNIQUE NOT NULL,
    keycloak_id VARCHAR2(255) UNIQUE,
    department_id NUMBER,
    role_id NUMBER,
    phone VARCHAR2(20),
    avatar VARCHAR2(255),
    status VARCHAR2(20) DEFAULT 'active',
    email_verified_at TIMESTAMP,
    last_login_at TIMESTAMP,
    created_at TIMESTAMP,
    updated_at TIMESTAMP
);

CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_users_keycloak ON users(keycloak_id);
CREATE INDEX idx_users_department ON users(department_id);
```

#### Jadual appointments
```sql
CREATE TABLE appointments (
    id NUMBER PRIMARY KEY,
    user_id NUMBER NOT NULL,
    title VARCHAR2(255) NOT NULL,
    description CLOB,
    location VARCHAR2(255),
    start_time TIMESTAMP NOT NULL,
    end_time TIMESTAMP NOT NULL,
    google_event_id VARCHAR2(255),
    is_all_day NUMBER(1) DEFAULT 0,
    recurrence_rule VARCHAR2(500),
    status VARCHAR2(20) DEFAULT 'active',
    created_at TIMESTAMP,
    updated_at TIMESTAMP,
    CONSTRAINT fk_appointments_user 
        FOREIGN KEY (user_id) REFERENCES users(id)
);

CREATE INDEX idx_appointments_user ON appointments(user_id);
CREATE INDEX idx_appointments_start ON appointments(start_time);
```

---

## 9. KESELAMATAN DAN PEMATUHAN

### 9.1 ISO/IEC 27001:2022 Compliance

Kawalan keselamatan yang akan dilaksanakan:

| Kawalan | Penerangan | Implementasi |
|---------|------------|--------------|
| A.5.1 | Policies for information security | Dokumen polisi keselamatan |
| A.8.1 | User endpoint devices | Device management policy |
| A.9.1 | Access control | RBAC implementation |
| A.9.2 | User access provisioning | User lifecycle management |
| A.10.1 | Cryptographic controls | TLS 1.3, AES-256 |
| A.12.1 | Operations security | Logging & monitoring |
| A.12.4 | Logging and monitoring | Audit trail lengkap |
| A.12.6 | Vulnerability management | Regular security scans |

### 9.2 Keselamatan Aplikasi

Implementasi keselamatan Laravel:

```php
// Middleware untuk security headers
class SecurityHeadersMiddleware
{
    public function handle($request, Closure $next)
    {
        $response = $next($request);
        
        $response->headers->set('X-Frame-Options', 'DENY');
        $response->headers->set('X-Content-Type-Options', 'nosniff');
        $response->headers->set('X-XSS-Protection', '1; mode=block');
        $response->headers->set('Strict-Transport-Security', 'max-age=31536000; includeSubDomains');
        $response->headers->set('Content-Security-Policy', "default-src 'self'");
        $response->headers->set('Referrer-Policy', 'strict-origin-when-cross-origin');
        
        return $response;
    }
}
```

---

## 10. REKABENTUK UI/UX

### 10.1 Prinsip Rekabentuk

1. **Responsiveness**: Berfungsi pada semua saiz skrin
2. **Accessibility**: Mematuhi WCAG 2.1 Level AA
3. **Consistency**: Gaya seragam di seluruh aplikasi
4. **Usability**: Mudah digunakan tanpa latihan intensif
5. **Performance**: Load time < 2 saat

### 10.2 Dashboard Design

Layout dashboard yang dicadangkan:

```
┌────────────────────────────────────────────────────────┐
│  HEADER: Logo │ Search │ Notifications │ Profile │    │
├────────────────────────────────────────────────────────┤
│  SIDEBAR    │  MAIN CONTENT                            │
│             │                                          │
│  Dashboard  │  ┌──────────────┐  ┌──────────────┐     │
│  Calendar   │  │ Today's      │  │ Quick        │     │
│  Memos      │  │ Schedule     │  │ Actions      │     │
│  Announce-  │  └──────────────┘  └──────────────┘     │
│  ments      │                                          │
│  Settings   │  ┌──────────────────────────────────┐   │
│             │  │ Recent Announcements             │   │
│             │  └──────────────────────────────────┘   │
│             │                                          │
│             │  ┌──────────────────────────────────┐   │
│             │  │ Unread Memos                     │   │
│             │  └──────────────────────────────────┘   │
└────────────────────────────────────────────────────────┘
```

---

## 11. STRATEGI PENGUJIAN

### 11.1 Jenis Ujian

| Jenis Ujian | Tools | Skop |
|-------------|-------|------|
| Unit Testing | PHPUnit | Komponen individu |
| Feature Testing | PHPUnit | Aliran kerja keseluruhan |
| Browser Testing | Laravel Dusk | UI/UX dan interaksi |
| API Testing | Postman | Endpoint API |
| Security Testing | OWASP ZAP | Kerentanan keselamatan |
| Performance Testing | JMeter | Prestasi dan bebanan |

### 11.2 UAT dan FAT

**UAT (User Acceptance Testing)**:
- UAT 1: Bulan 6 - Modul individu
- UAT 2: Bulan 7 - Sistem lengkap
- Lokasi: Di premis UMPSA
- Peserta: Wakil pengguna akhir

**FAT (Final Acceptance Testing)**:
- Bulan 8
- Production environment
- Semua test cases mesti lulus

---

## 12. PELAN MIGRASI

### 12.1 Strategi Phased Migration

| Fasa | Aktiviti | Tempoh |
|------|----------|--------|
| 1 | Login & User Management | Minggu 1 |
| 2 | Calendar & Appointments | Minggu 2-3 |
| 3 | Memos & Announcements | Minggu 4-5 |
| 4 | Settings & Notifications | Minggu 6-7 |
| 5 | Go-live & Support | Minggu 8 |

### 12.2 Rollback Plan

Jika berlaku masalah semasa migrasi:

1. Aktifkan sistem lama dengan serta-merta
2. Pulihkan data daripada backup
3. Komunikasikan dengan pengguna
4. Selesaikan isu dalam persekitaran staging
5. Ulangi proses migrasi

---

## 13. PENGURUSAN RISIKO

### 13.1 Risiko Utama dan Mitigasi

| Risiko | Kesan | Mitigasi | Contingency |
|--------|-------|----------|-------------|
| Integration delay | 2 minggu | POC awal | Buffer time |
| Performance issue | 1 minggu | Load testing | Optimization |
| Data loss | Critical | Backup berkala | Recovery plan |
| Scope creep | 1-2 minggu | Change control | Contract terms |

---

## 14. STRUKTUR PASUKAN PROJEK

### 14.1 Organisasi Pasukan

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

### 14.2 Keperluan Sumber

| Peranan | Kuantiti | Peratusan |
|---------|----------|-----------|
| Project Manager | 1 | 100% |
| Technical Lead | 1 | 100% |
| Developers | 3 | 100% |
| Business Analyst | 1 | 50% |
| QA Engineer | 1 | 100% |
| UI/UX Designer | 1 | 25% |

---

## 15. PENGHANTARAN PROJEK

### 15.1 Deliverables

| No. | Deliverable | Target |
|-----|-------------|--------|
| 1 | Sistem Portal Staf | Bulan 8 |
| 2 | Laravel Shift Account | Bulan 1 |
| 3 | Implementation Plan | Minggu 5 |
| 4 | SRS & SDS | Bulan 3 |
| 5 | UAT & FAT Reports | Bulan 7 |
| 6 | User Manuals | Bulan 7 |
| 7 | Training Completion | Bulan 8 |

### 15.2 Tempoh Jaminan

- **Tempoh**: 12 bulan dari FAT
- **Skop**: Corrective maintenance, bug fixes
- **SLA**: 4 jam response time, 3 hari resolution

---

**Disediakan oleh:**

Sinergi Elit Sdn Bhd

**Tarikh:** 21 Februari 2026

**Versi:** 2.0 (Expanded Edition)

