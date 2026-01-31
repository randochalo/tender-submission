# ANNEX E: PROPOSED IT ARCHITECTURE & SECURITY FRAMEWORK

**Tender Reference:** T/SUKSEL/04-2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Project:** Sistem ePINGAT Negeri Selangor  
**Date:** 31 January 2026

---

## 1. SYSTEM ARCHITECTURE OVERVIEW

### 1.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ePINGAT SYSTEM ARCHITECTURE                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         CLIENT LAYER                                  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Web App   │  │  Mobile     │  │  Admin      │  │  Urus Setia │  │  │
│  │  │  (Public)   │  │  Responsive │  │   Panel     │  │   Panel     │  │  │
│  │  │   React     │  │   (PWA)     │  │  (React)    │  │  (React)    │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼ WAF/SSL                                │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      APPLICATION LAYER (Laravel)                      │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    LARAVEL APPLICATION CORE                     │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │ Nomination│ │Evaluation│ │ Ceremony │ │ Reporting│ │  Admin   │  │  │  │
│  │  │  │ Service │ │ Service │ │ Service  │ │ Service  │ │ Service │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │  User   │ │  Auth   │ │  Workflow│ │ Notification│ │  Audit  │  │  │  │
│  │  │  │ Service │ │ Service │ │  Engine  │ │  Service   │ │ Service │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         DATA LAYER                                    │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │  MySQL      │  │    Redis    │  │  File       │  │  Audit      │  │  │
│  │  │ (Primary)   │  │   (Cache)   │  │  Storage    │  │  Log DB     │  │  │
│  │  │  v8.0       │  │             │  │             │  │             │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Technology Stack

| Layer | Technology | Justification |
|-------|------------|---------------|
| **Frontend** | React 18 + Tailwind CSS | Modern UI, responsive design |
| **Backend** | Laravel 10 (PHP 8.2) | Robust framework, security features |
| **Database** | MySQL 8.0 | ACID compliance, full-text search |
| **Cache** | Redis | Session management, query caching |
| **Queue** | Redis Queue | Background job processing |
| **Search** | Elasticsearch | Fast search for recipients/awards |
| **Storage** | Local + AWS S3 | Document storage with backup |
| **Server** | Ubuntu 22.04 LTS | Stable, secure, long-term support |
| **Web Server** | Nginx | High performance, load balancing |

---

## 2. DETAILED ARCHITECTURE

### 2.1 Application Modules

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    ePINGAT MODULE STRUCTURE                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  1. LAMAN UTAMA (Public Portal)                                       │  │
│  │     • Information pages                                               │  │
│  │     • Search awards/recipients                                        │  │
│  │     • Statistics display                                              │  │
│  │     • Contact information                                             │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  2. MODUL PERMOHONAN (Nomination Module)                              │  │
│  │     • Online nomination forms                                         │  │
│  │     • Document upload (IC, certificates)                              │  │
│  │     • Auto-save draft functionality                                   │  │
│  │     • Application tracking                                            │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  3. MODUL PENGURUSAN PERMOHONAN (Application Management)              │  │
│  │     • Dashboard Urus Setia                                            │  │
│  │     • Application listing & filtering                                 │  │
│  │     • Status management (New → Review → Approved/Rejected)            │  │
│  │     • Document verification                                           │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  4. MODUL PENILAIAN DAN TAPISAN (Evaluation & Screening)              │  │
│  │     • Scoring rubrics                                                 │  │
│  │     • Committee assignment                                            │  │
│  │     • Evaluation forms                                                │  │
│  │     • Automated screening checks                                      │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  5. MODUL PENGURUSAN MAJLIS (Ceremony Management)                     │  │
│  │     • Ceremony scheduling                                             │  │
│  │     • Attendance management                                           │  │
│  │     • Seating arrangement                                             │  │
│  │     • Digital certificate generation                                  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  6. MODUL LAPORAN (Reporting Module)                                  │  │
│  │     • Statistical reports                                             │  │
│  │     • Audit trail reports                                             │  │
│  │     • Custom report builder                                           │  │
│  │     • Export to Excel/PDF                                             │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  7. MODUL PENTADBIR SISTEM (System Administration)                    │  │
│  │     • User management                                                 │  │
│  │     • Role & permission configuration                                 │  │
│  │     • System settings                                                 │  │
│  │     • Master data management                                          │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Database Schema (Simplified)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DATABASE ENTITY RELATIONSHIP                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────┐       ┌─────────────┐       ┌─────────────┐               │
│  │   users     │◄─────►│ applications│◄─────►│  documents  │               │
│  │             │       │             │       │             │               │
│  │ - id        │       │ - id        │       │ - id        │               │
│  │ - name      │       │ - user_id   │       │ - app_id    │               │
│  │ - email     │       │ - category  │       │ - file_path │               │
│  │ - role      │       │ - status    │       │ - doc_type  │               │
│  │ - dept      │       │ - submit_date│      │ - uploaded_at│              │
│  └─────────────┘       │ - score     │       └─────────────┘               │
│                        └──────┬──────┘                                     │
│                               │                                            │
│                               ▼                                            │
│                        ┌─────────────┐       ┌─────────────┐               │
│                        │evaluations  │◄─────►│  ceremonies │               │
│                        │             │       │             │               │
│                        │ - id        │       │ - id        │               │
│                        │ - app_id    │       │ - name      │               │
│                        │ - evaluator │       │ - date      │               │
│                        │ - score     │       │ - venue     │               │
│                        │ - comments  │       │ - status    │               │
│                        └─────────────┘       └─────────────┘               │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. SECURITY ARCHITECTURE

### 3.1 Defense in Depth

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       SECURITY LAYERS                                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  LAYER 1: PERIMETER                                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • SSL/TLS 1.3 encryption                                            │   │
│  │  • Web Application Firewall (WAF)                                    │   │
│  │  • DDoS protection                                                   │   │
│  │  • Rate limiting per IP/user                                         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 2: NETWORK                                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Firewall configuration                                            │   │
│  │  • VPN access for admin                                              │   │
│  │  • Network segmentation                                              │   │
│  │  • Intrusion detection                                               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 3: APPLICATION                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • OWASP Top 10 protection                                           │   │
│  │  • Input validation & sanitization                                   │   │
│  │  • CSRF protection (Laravel default)                                 │   │
│  │  • XSS prevention                                                    │   │
│  │  • SQL injection prevention (Parameter binding)                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 4: DATA                                                            │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • AES-256 encryption for sensitive data                             │   │
│  │  • Hashed passwords (bcrypt)                                         │   │
│  │  • Database activity logging                                         │   │
│  │  • Encrypted backups                                                 │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 5: IDENTITY                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Multi-factor authentication (MFA)                                 │   │
│  │  • Role-based access control (RBAC)                                  │   │
│  │  • Session management                                                │   │
│  │  • Password policies                                                 │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Security Controls Matrix

| Control Category | Implementation | Verification |
|------------------|----------------|--------------|
| **Authentication** | MFA, strong passwords | Quarterly review |
| **Authorization** | RBAC, least privilege | Monthly audit |
| **Encryption** | AES-256, TLS 1.3 | Continuous monitoring |
| **Logging** | Comprehensive audit trail | Real-time alerting |
| **Backup** | Encrypted, tested | Monthly restore test |

---

## 4. INFRASTRUCTURE & DEPLOYMENT

### 4.1 Server Specifications

| Component | Specification |
|-----------|---------------|
| **Operating System** | Ubuntu 22.04 LTS (64-bit) |
| **CPU** | 8 cores minimum, 16 cores recommended |
| **RAM** | 32GB minimum, 64GB recommended |
| **Storage** | 500GB SSD (System) + 1TB (Data) |
| **Network** | 1Gbps dedicated connection |
| **Backup Storage** | Separate backup server/cloud |

### 4.2 Deployment Architecture

| Environment | Purpose | Configuration |
|-------------|---------|---------------|
| **Production** | Live system | High availability, load balanced |
| **Staging** | Pre-production testing | Mirror of production |
| **Development** | Development work | Standard configuration |

### 4.3 Disaster Recovery

| Metric | Target |
|--------|--------|
| **RPO (Recovery Point Objective)** | < 1 hour |
| **RTO (Recovery Time Objective)** | < 4 hours |
| **Backup Frequency** | Daily full, hourly incremental |
| **Retention Period** | 30 days local, 90 days offsite |

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
