# ANNEX E: PROPOSED IT INFRASTRUCTURE & SYSTEM ARCHITECTURE

**Tender Reference:** MMFSB/TD 02/2026  
**System:** Support IT System (EMS, PS, HRMS)  
**Proposed Solution:** LogisticsPro Enterprise Suite v4.2  
**Deployment Model:** Hybrid Cloud (Awan Kita Sovereign Cloud)  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Executive Summary](#1-executive-summary)
2. [System Architecture Overview](#2-system-architecture-overview)
3. [Infrastructure Design](#3-infrastructure-design)
4. [Network Architecture](#4-network-architecture)
5. [Security Architecture](#5-security-architecture)
6. [Integration Architecture](#6-integration-architecture)
7. [Data Architecture](#7-data-architecture)
8. [Disaster Recovery & Business Continuity](#8-disaster-recovery--business-continuity)
9. [Scalability & Performance](#9-scalability--performance)
10. [Compliance & Governance](#10-compliance--governance)

---

## 1. EXECUTIVE SUMMARY

### 1.1 Solution Overview

Sinergi Elit Sdn Bhd (SESB) proposes the **LogisticsPro Enterprise Suite v4.2** deployed on **Awan Kita Sovereign Cloud** infrastructure to deliver the Support IT System requirements for Multimodal Freight Sdn Bhd (MMF).

### 1.2 Key Architectural Principles

| Principle | Implementation |
|-----------|----------------|
| **Sovereignty** | All data hosted within Malaysia (Awan Kita) |
| **Security** | Defense-in-depth with zero-trust architecture |
| **Scalability** | Auto-scaling to support 300% growth |
| **Resilience** | 99.95% uptime SLA with multi-AZ deployment |
| **Integration** | Open APIs for seamless FMS/HMS connectivity |
| **Compliance** | KRISA/JDN, PDPA, and industry standards |

### 1.3 Infrastructure Highlights

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           MMF SUPPORT SYSTEM INFRASTRUCTURE                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         AWAN KITA SOVEREIGN CLOUD                     │  │
│  │                              (Malaysia)                               │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    PRIMARY DATA CENTER (Cyberjaya)              │  │  │
│  │  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │  │  │
│  │  │  │  EMS Module │  │  PS Module  │  │ HRMS Module │             │  │  │
│  │  │  │   (App)     │  │   (App)     │  │   (App)     │             │  │  │
│  │  │  └─────────────┘  └─────────────┘  └─────────────┘             │  │  │
│  │  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │  │  │
│  │  │  │  EMS DB     │  │   PS DB     │  │  HRMS DB    │             │  │  │
│  │  │  │  (Primary)  │  │  (Primary)  │  │  (Primary)  │             │  │  │
│  │  │  └─────────────┘  └─────────────┘  └─────────────┘             │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  │                              │                                        │  │
│  │                              ▼ Replication                           │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                 DISASTER RECOVERY (Kuala Lumpur)               │  │  │
│  │  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │  │  │
│  │  │  │  EMS DB     │  │   PS DB     │  │  HRMS DB    │             │  │  │
│  │  │  │  (Replica)  │  │  (Replica)  │  │  (Replica)  │             │  │  │
│  │  │  └─────────────┘  └─────────────┘  └─────────────┘             │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                              │                                              │
│                              ▼ WAF + VPN                                    │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         MMF CORPORATE NETWORK                         │  │
│  │  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐     │  │
│  │  │   HQ    │  │Port Klng│  │Butterwth│  │Pasir Gdg│  │Padang Bsr│    │  │
│  │  │ Users   │  │  Users  │  │  Users  │  │  Users  │  │  Users   │    │  │
│  │  └─────────┘  └─────────┘  └─────────┘  └─────────┘  └─────────┘     │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. SYSTEM ARCHITECTURE OVERVIEW

### 2.1 Modular Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    LOGISTICSPRO ENTERPRISE SUITE v4.2                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         PRESENTATION LAYER                            │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │ Web Portal  │  │ Mobile App  │  │   API GW    │  │  Reports    │  │  │
│  │  │  (React)    │  │(React Native│  │  (Kong)     │  │ (Power BI)  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         APPLICATION LAYER                             │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    MICROSERVICES ARCHITECTURE                   │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │  Auth   │ │  EMS    │ │   PS    │ │  HRMS   │ │  AI/ML  │  │  │  │
│  │  │  │ Service │ │ Service │ │ Service │ │ Service │ │ Engine  │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │ Workflow│ │Notificat│ │Document│ │  OCR    │ │ Integra │  │  │  │
│  │  │  │ Engine  │ │ Service │ │Service │ │ Service │ │ Service │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                           DATA LAYER                                  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │ PostgreSQL  │  │ PostgreSQL  │  │ PostgreSQL  │  │  Redis      │  │  │
│  │  │ (EMS DB)    │  │   (PS DB)   │  │  (HRMS DB)  │  │  (Cache)    │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │  MinIO      │  │ Elasticsearch│  │  RabbitMQ   │  │ClickHouse   │  │  │
│  │  │(Documents)  │  │  (Search)   │  │  (Message)  │  │ (Analytics) │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Technology Stack

| Layer | Technology | Purpose |
|-------|------------|---------|
| **Frontend** | React 18, TypeScript | Responsive web interface |
| **Mobile** | React Native | iOS/Android apps |
| **Backend** | Node.js, Python (FastAPI) | Microservices |
| **Database** | PostgreSQL 15 | Primary transactional DB |
| **Cache** | Redis Cluster | Session & query caching |
| **Search** | Elasticsearch 8 | Full-text search |
| **Message Queue** | RabbitMQ | Async processing |
| **Analytics** | ClickHouse | OLAP analytics |
| **Storage** | MinIO (S3-compatible) | Document storage |
| **AI/ML** | TensorFlow, PyTorch | Predictive models |

---

## 3. INFRASTRUCTURE DESIGN

### 3.1 Compute Resources

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         COMPUTE INFRASTRUCTURE                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PRODUCTION ENVIRONMENT (Primary - Cyberjaya)                               │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │  Kubernetes Cluster (EKS on Awan Kita)                               │  │
│  │                                                                       │  │
│  │  ┌───────────────────────────────────────────────────────────────┐   │  │
│  │  │                    APPLICATION NODES                          │   │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ │   │  │
│  │  │  │EMS App  │ │ PS App  │ │HRMS App │ │API GW   │ │Worker   │ │   │  │
│  │  │  │Pod x3   │ │Pod x3   │ │Pod x3   │ │Pod x2   │ │Pod x4   │ │   │  │
│  │  │  │4vCPU/8GB│ │4vCPU/8GB│ │4vCPU/8GB│ │2vCPU/4GB│ │2vCPU/4GB│ │   │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘ │   │  │
│  │  └───────────────────────────────────────────────────────────────┘   │  │
│  │                                                                       │  │
│  │  ┌───────────────────────────────────────────────────────────────┐   │  │
│  │  │                    DATABASE NODES                             │   │  │
│  │  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐           │   │  │
│  │  │  │ EMS Primary │  │  PS Primary │  │ HRMS Primary│           │   │  │
│  │  │  │  8vCPU/32GB │  │  8vCPU/32GB │  │  8vCPU/32GB │           │   │  │
│  │  │  │  500GB SSD  │  │  500GB SSD  │  │  500GB SSD  │           │   │  │
│  │  │  └─────────────┘  └─────────────┘  └─────────────┘           │   │  │
│  │  └───────────────────────────────────────────────────────────────┘   │  │
│  │                                                                       │  │
│  │  Auto-scaling: 2-10 pods per service based on CPU/memory metrics     │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  RESOURCE SUMMARY                                                           │
│  ┌─────────────────┬───────────┬───────────┬───────────┬─────────────────┐ │
│  │ Component       │ Min Pods  │ Max Pods  │ Per Pod   │ Total Capacity  │ │
│  ├─────────────────┼───────────┼───────────┼───────────┼─────────────────┤ │
│  │ EMS Application │     3     │    10     │ 4vCPU/8GB │  40vCPU/80GB    │ │
│  │ PS Application  │     3     │    10     │ 4vCPU/8GB │  40vCPU/80GB    │ │
│  │ HRMS Application│     3     │    10     │ 4vCPU/8GB │  40vCPU/80GB    │ │
│  │ Databases       │     3     │     3     │ 8vCPU/32GB│  24vCPU/96GB    │ │
│  │ Supporting Svcs │     6     │    12     │ 2vCPU/4GB │  24vCPU/48GB    │ │
│  ├─────────────────┼───────────┼───────────┼───────────┼─────────────────┤ │
│  │ TOTAL           │    18     │    48     │    -      │ 168vCPU/404GB   │ │
│  └─────────────────┴───────────┴───────────┴───────────┴─────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Storage Architecture

| Storage Type | Technology | Capacity | Usage |
|--------------|------------|----------|-------|
| **Database Storage** | SSD Block Storage | 2 TB | Transactional data |
| **Document Storage** | MinIO Object Store | 5 TB | Receipts, invoices, documents |
| **Backup Storage** | S3-Compatible | 10 TB | Daily backups, archives |
| **Log Storage** | Elasticsearch | 500 GB | Application logs |
| **Cache Storage** | Redis | 50 GB | Session & query cache |

---

## 4. NETWORK ARCHITECTURE

### 4.1 Network Topology

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          NETWORK ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  INTERNET                                                                   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      AWS WAF (Web Application Firewall)             │   │
│  │  • DDoS Protection          • SQL Injection Prevention              │   │
│  │  • Rate Limiting            • Bot Detection                         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      AWS CLOUDFRONT (CDN)                           │   │
│  │  • Global Edge Locations    • Static Asset Caching                  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      APPLICATION LOAD BALANCER                      │   │
│  │  • SSL Termination          • Health Checks                         │   │
│  │  • Sticky Sessions          • Auto-scaling Integration              │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      KUBERNETES CLUSTER (Private Subnets)           │   │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐       │   │
│  │  │  App    │ │  App    │ │  App    │ │  App    │ │  App    │       │   │
│  │  │ Tier-1  │ │ Tier-2  │ │ Tier-3  │ │ Tier-4  │ │ Tier-5  │       │   │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      DATABASE TIER (Isolated Subnet)                │   │
│  │  • No direct internet access    • Security group restricted         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  MMF CORPORATE NETWORK (VPN CONNECTION)                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      AWS SITE-TO-SITE VPN                           │   │
│  │  • IPsec Tunnel               • Encrypted Traffic                   │   │
│  │  • HQ + 4 Branches            • <10ms Latency                       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│     │                                                                       │
│     ▼                                                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      MMF INTERNAL NETWORK                           │   │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐       │   │
│  │  │   HQ    │ │ Port    │ │Butter-  │ │ Pasir   │ │ Padang  │       │   │
│  │  │         │ │ Klang   │ │ worth   │ │ Gudang  │ │ Besar   │       │   │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Network Security Groups

| Source | Destination | Port | Protocol | Purpose |
|--------|-------------|------|----------|---------|
| WAF | ALB | 443 | HTTPS | Secure web traffic |
| ALB | App Tier | 8080 | HTTP | Internal routing |
| App Tier | Database | 5432 | PostgreSQL | DB access |
| VPN | App Tier | 443 | HTTPS | Branch access |
| App Tier | External APIs | 443 | HTTPS | Third-party integration |

---

## 5. SECURITY ARCHITECTURE

### 5.1 Defense in Depth

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        SECURITY ARCHITECTURE                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  LAYER 1: PERIMETER SECURITY                                                │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • AWS WAF with custom rules                                        │   │
│  │  • DDoS Protection (AWS Shield Advanced)                            │   │
│  │  • IP Whitelisting for admin access                                 │   │
│  │  • Geo-blocking (allow Malaysia only)                               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 2: NETWORK SECURITY                                                  │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • VPC Isolation                                                    │   │
│  │  • Private subnets for databases                                    │   │
│  │  • Security Groups (least privilege)                                │   │
│  │  • Network ACLs                                                     │   │
│  │  • VPC Flow Logs                                                    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 3: APPLICATION SECURITY                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • OWASP Top 10 Protection                                          │   │
│  │  • Input validation & sanitization                                  │   │
│  │  • CSRF protection                                                  │   │
│  │  • Rate limiting per user/IP                                        │   │
│  │  • API authentication (JWT/OAuth 2.0)                               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 4: DATA SECURITY                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Encryption at rest (AES-256)                                     │   │
│  │  • Encryption in transit (TLS 1.3)                                  │   │
│  │  • Field-level encryption for PII                                   │   │
│  │  • Database activity monitoring                                     │   │
│  │  • Data masking for non-prod environments                           │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 5: IDENTITY & ACCESS                                                 │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Single Sign-On (SSO)                                             │   │
│  │  • Multi-Factor Authentication (MFA)                                │   │
│  │  • Role-Based Access Control (RBAC)                                 │   │
│  │  • Privileged Access Management                                     │   │
│  │  • Session management & timeout                                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 6: MONITORING & AUDITING                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Centralized logging (SIEM)                                       │   │
│  │  • Real-time threat detection                                       │   │
│  │  • User activity monitoring                                         │   │
│  │  • Audit trail for all transactions                                 │   │
│  │  • Automated security alerts                                        │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Authentication Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AUTHENTICATION ARCHITECTURE                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────┐          ┌──────────────┐          ┌──────────────────────┐  │
│  │  User    │ ───────> │   AWS WAF    │ ───────> │  Application Load    │  │
│  │  Browser │          │   (Rate      │          │  Balancer            │  │
│  └──────────┘          │    Limit)    │          └──────────────────────┘  │
│                        └──────────────┘                    │                │
│                                                            ▼                │
│                                               ┌──────────────────────┐     │
│                                               │   Kong API Gateway   │     │
│                                               │   (Auth Check)       │     │
│                                               └──────────────────────┘     │
│                                                            │                │
│                        ┌───────────────────────────────────┘                │
│                        ▼                                                    │
│         ┌──────────────────────────┐         ┌──────────────────────┐       │
│         │    Valid Session?        │         │   Identity Provider  │       │
│         │    (Redis Cache)         │────────▶│   (Keycloak/ADFS)    │       │
│         │                          │         │                      │       │
│         │  YES ───▶ Forward to App │         │  • LDAP/AD Sync       │       │
│         │  NO  ───▶ Redirect to    │         │  • SAML 2.0 Support   │       │
│         │           Login          │         │  • MFA (TOTP/SMS)     │       │
│         └──────────────────────────┘         └──────────────────────┘       │
│                                                                             │
│  TOKEN VALIDATION:                                                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • JWT signed with RSA-256                                          │   │
│  │  • Short-lived access tokens (15 min)                               │   │
│  │  • Refresh tokens (7 days)                                          │   │
│  │  • Token binding to device/session                                  │   │
│  │  • Automatic revocation on logout                                   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 6. INTEGRATION ARCHITECTURE

### 6.1 System Integration Map

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      INTEGRATION ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    LOGISTICSPRO SUPPORT SYSTEM                        │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                   │  │
│  │  │     EMS     │  │     PS      │  │    HRMS     │                   │  │
│  │  │  (Assets)   │  │  (Procure)  │  │    (HR)     │                   │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘                   │  │
│  │         │                │                │                          │  │
│  │         └────────────────┼────────────────┘                          │  │
│  │                          ▼                                           │  │
│  │              ┌─────────────────────┐                                 │  │
│  │              │   INTEGRATION BUS   │                                 │  │
│  │              │   (RabbitMQ + API)  │                                 │  │
│  │              └─────────────────────┘                                 │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                          │                                                  │
│           ┌──────────────┼──────────────┬──────────────┐                    │
│           │              │              │              │                    │
│           ▼              ▼              ▼              ▼                    │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │     FMS     │  │     HMS     │  │   External  │  │   Banking   │        │
│  │ (Finance)   │  │ (Haulage)   │  │    APIs     │  │   APIs      │        │
│  │             │  │             │  │             │  │             │        │
│  │ • GL Posting│  │ • Vehicle   │  │ • Customs   │  │ • FPX       │        │
│  │ • AP/AR     │  │   Status    │  │ • MyGST     │  │ • Bank Recon│        │
│  │ • Budget    │  │ • Mileage   │  │ • LHDN      │  │ • Statements│        │
│  │   Control   │  │   Sync      │  │ • JPJ       │  │             │        │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘        │
│                                                                             │
│  INTEGRATION PATTERNS:                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  SYNC (Real-time):  Auth, Vehicle Status, Notifications             │   │
│  │  ASYNC (Queue):     Payroll, Financial Posting, Reports             │   │
│  │  BATCH (Nightly):   Analytics, Master Data Sync, Backups            │   │
│  │  EVENT-DRIVEN:      Alerts, Workflows, Audit Logs                   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 API Specifications

| API Category | Protocol | Authentication | Rate Limit |
|--------------|----------|----------------|------------|
| **Internal APIs** | REST/gRPC | mTLS + JWT | 10,000/min |
| **External APIs** | REST/JSON | OAuth 2.0 | 1,000/min |
| **FMS Integration** | REST/SOAP | API Key + JWT | 5,000/min |
| **Banking APIs** | REST/ISO20022 | OAuth 2.0 + Cert | 500/min |
| **Government APIs** | REST/SOAP | Digital Cert | 100/min |

---

## 7. DATA ARCHITECTURE

### 7.1 Data Model Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         DATA ARCHITECTURE                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    MASTER DATA MANAGEMENT (MDM)                       │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │  Vendors    │  │  Employees  │  │   Assets    │  │  Branches   │  │  │
│  │  │  (Golden)   │  │  (Golden)   │  │  (Golden)   │  │  (Golden)   │  │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  │  │
│  │         └─────────────────┴─────────────────┴─────────────────┘       │  │
│  │                                     │                                 │  │
│  │                                     ▼                                 │  │
│  │                    ┌─────────────────────────────┐                    │  │
│  │                    │   MASTER DATA HUB           │                    │  │
│  │                    │   (Sync to all systems)     │                    │  │
│  │                    └─────────────────────────────┘                    │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    TRANSACTIONAL DATA                                 │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   EMS DB    │  │    PS DB    │  │   HRMS DB   │  │   Shared    │  │  │
│  │  │             │  │             │  │             │  │   Tables    │  │  │
│  │  │• Assets     │  │• Purchase   │  │• Employees  │  │             │  │  │
│  │  │• Maintenance│  │  Orders     │  │• Payroll    │  │• Audit Logs │  │  │
│  │  │• Parts      │  │• Vendors    │  │• Leave      │  │• Workflow   │  │  │
│  │  │• Warranty    │  │• Invoices   │  │• Claims     │  │• Documents  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    ANALYTICS DATA (ClickHouse)                        │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │  Equipment  │  │  Spend      │  │  Workforce  │  │  Integrated │  │  │
│  │  │  Analytics  │  │  Analytics  │  │  Analytics  │  │  Analytics  │  │  │
│  │  │             │  │             │  │             │  │             │  │  │
│  │  │• Utilization│  │• Category   │  │• Headcount  │  │• Cross-sys  │  │  │
│  │  │• TCO Trends │  │  Spend      │  │• Attrition  │  │  Insights   │  │  │
│  │  │• Downtime   │  │• Vendor     │  │• Training   │  │• Cost/Ship  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 7.2 Data Retention Policy

| Data Type | Retention Period | Archive Strategy |
|-----------|------------------|------------------|
| **Transactional** | 7 years | Move to cold storage after 2 years |
| **Audit Logs** | 10 years | Immutable storage |
| **Documents** | Per legal requirement | Compressed archive |
| **Analytics** | Unlimited | Aggregated summaries |
| **Backups** | 30 days | Incremental with point-in-time |

---

## 8. DISASTER RECOVERY & BUSINESS CONTINUITY

### 8.1 DR Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DISASTER RECOVERY ARCHITECTURE                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PRIMARY SITE (Cyberjaya)                    DR SITE (Kuala Lumpur)         │
│  ┌──────────────────────────────────┐       ┌─────────────────────────────┐ │
│  │   ACTIVE-ACTIVE APPLICATIONS     │       │   STANDBY APPLICATIONS      │ │
│  │                                  │       │                             │ │
│  │  ┌─────────┐  ┌─────────┐       │       │  ┌─────────┐  ┌─────────┐   │ │
│  │  │  EMS    │  │   PS    │       │       │  │  EMS    │  │   PS    │   │ │
│  │  │  App    │  │  App    │       │       │  │  App    │  │  App    │   │ │
│  │  └─────────┘  └─────────┘       │       │  └─────────┘  └─────────┘   │ │
│  │                                  │       │                             │ │
│  └──────────────────────────────────┘       └─────────────────────────────┘ │
│                                                                             │
│  ┌──────────────────────────────────┐       ┌─────────────────────────────┐ │
│  │   PRIMARY DATABASES              │◀─────▶│   REPLICA DATABASES         │ │
│  │                                  │ Sync  │                             │ │
│  │  ┌─────────┐  ┌─────────┐       │(RPO    │  ┌─────────┐  ┌─────────┐   │ │
│  │  │  EMS    │  │   PS    │       │ <5min) │  │  EMS    │  │   PS    │   │ │
│  │  │  Primary│  │ Primary │       │       │  │ Replica │  │ Replica │   │ │
│  │  └─────────┘  └─────────┘       │       │  └─────────┘  └─────────┘   │ │
│  │                                  │       │                             │ │
│  └──────────────────────────────────┘       └─────────────────────────────┘ │
│                                                                             │
│  FAILOVER PROCESS:                                                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Detection:    Automated health checks every 30 seconds            │   │
│  │  Decision:     Automatic failover after 3 consecutive failures     │   │
│  │  Execution:    DNS switch + database promotion (< 5 minutes)       │   │
│  │  Recovery:     RPO < 5 minutes, RTO < 15 minutes                   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  BACKUP STRATEGY:                                                           │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Continuous WAL archiving (point-in-time recovery)               │   │
│  │  • Hourly incremental backups                                      │   │
│  │  • Daily full backups                                              │   │
│  │  • Weekly offsite backup to separate region                        │   │
│  │  • Monthly air-gapped backup                                       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 8.2 Business Continuity Metrics

| Metric | Target | Actual Capability |
|--------|--------|-------------------|
| **RPO (Recovery Point Objective)** | < 1 hour | < 5 minutes |
| **RTO (Recovery Time Objective)** | < 4 hours | < 15 minutes |
| **Data Durability** | 99.9999999% | 99.999999999% |
| **Uptime SLA** | 99.9% | 99.95% |

---

## 9. SCALABILITY & PERFORMANCE

### 9.1 Scaling Strategy

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       SCALABILITY ARCHITECTURE                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  HORIZONTAL SCALING (Auto-scaling triggers)                                 │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                                                                     │   │
│  │   CPU > 70% ───────┐                                                │   │
│  │   Memory > 80% ────┼──▶  ADD POD ───▶ MAX 10 PODS PER SERVICE       │   │
│  │   Requests > 1000 ─┘                                                │   │
│  │                                                                     │   │
│  │   CPU < 30% ───────┐                                                │   │
│  │   Memory < 40% ────┼──▶  REMOVE POD ──▶ MIN 3 PODS PER SERVICE      │   │
│  │                                                                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  DATABASE SCALING                                                           │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Read replicas for reporting queries (up to 5 replicas)          │   │
│  │  • Connection pooling (PgBouncer)                                  │   │
│  │  • Partitioning for large tables (>10M rows)                       │   │
│  │  • Automatic index optimization                                    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  PERFORMANCE TARGETS                                                        │
│  ┌────────────────────┬─────────────────┬────────────────────────────────┐ │
│  │ Metric             │ Target          │ Current Capacity               │ │
│  ├────────────────────┼─────────────────┼────────────────────────────────┤ │
│  │ Page Load Time     │ < 2 seconds     │ 0.8s (p95)                     │ │
│  │ API Response Time  │ < 500ms         │ 180ms (p95)                    │ │
│  │ Report Generation  │ < 30 seconds    │ 15s (complex reports)          │ │
│  │ Concurrent Users   │ 500             │ 1,200 (tested)                 │ │
│  │ Concurrent Jobs    │ 100             │ 300 (tested)                   │ │
│  └────────────────────┴─────────────────┴────────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 10. COMPLIANCE & GOVERNANCE

### 10.1 Compliance Matrix

| Standard | Requirement | Implementation |
|----------|-------------|----------------|
| **KRISA/JDN** | Data sovereignty | Awan Kita Malaysia-only |
| **PDPA 2010** | Personal data protection | Encryption, consent, access controls |
| **LHDN** | Tax reporting | Direct API integration |
| **EPF/KWSP** | Contribution compliance | Automated calculation & submission |
| **SOCSO** | Social security | Real-time contribution processing |
| **ISO 27001** | Information security | Certified processes |
| **ISO 22301** | Business continuity | DR plans tested quarterly |

### 10.2 Governance Framework

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      GOVERNANCE FRAMEWORK                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    DATA GOVERNANCE                                   │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐│   │
│  │  │  Data       │  │  Data       │  │  Data       │  │  Data       ││   │
│  │  │  Quality    │  │  Lineage    │  │  Catalog    │  │  Retention  ││   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘│   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    OPERATIONAL GOVERNANCE                            │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐│   │
│  │  │  Change     │  │  Incident   │  │  Problem    │  │  Capacity   ││   │
│  │  │  Management │  │  Management │  │  Management │  │  Management ││   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘│   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    SECURITY GOVERNANCE                               │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐│   │
│  │  │  Access     │  │  Vulnerability│  │  Threat     │  │  Compliance ││   │
│  │  │  Reviews    │  │  Management │  │  Intel      │  │  Audits     ││   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘│   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
