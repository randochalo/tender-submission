# ANNEX-T02-SYSTEM-ARCHITECTURE-TSH2607.md

# ANNEX T2: DETAILED SYSTEM ARCHITECTURE
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T2  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [System Architecture Overview](#1-system-architecture-overview)
2. [Microservices Architecture](#2-microservices-architecture)
3. [Data Flow Architecture](#3-data-flow-architecture)
4. [Oracle Integration Architecture](#4-oracle-integration-architecture)
5. [Cloud Infrastructure Architecture](#5-cloud-infrastructure-architecture)
6. [Container Architecture](#6-container-architecture)

---

## 1. SYSTEM ARCHITECTURE OVERVIEW

### 1.1 Architectural Style

The UCMS implements a **Microservices Architecture** built on **Cloud-Native Principles** with the following characteristics:

| Characteristic | Implementation |
|----------------|----------------|
| Service Decomposition | Domain-driven design with 15+ microservices |
| Communication | Synchronous (REST/gRPC) and Asynchronous (Message Queue) |
| Data Management | Database per service pattern |
| Deployment | Containerized with Kubernetes orchestration |
| Scalability | Horizontal pod autoscaling |
| Resilience | Circuit breakers, retries, and graceful degradation |

### 1.2 Architecture Layers

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                              UCMS SYSTEM ARCHITECTURE                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                           CLIENT LAYER                                           │   │
│  │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐           │   │
│  │  │  Web Portal  │ │  Mobile App  │ │   MCMC Site  │ │  Third Party │           │   │
│  │  │  (Angular)   │ │ (React Native)│ │  Integration │ │    APIs      │           │   │
│  │  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘           │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          ▼                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                         API GATEWAY LAYER                                        │   │
│  │                                                                                  │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │                     ORACLE API GATEWAY / AZURE APIM                      │   │   │
│  │  │  • Authentication (OAuth 2.0, JWT)                                       │   │   │
│  │  │  • Rate Limiting                                                         │   │   │
│  │  │  • Request/Response Transformation                                       │   │   │
│  │  │  • Caching                                                               │   │   │
│  │  │  • Logging & Monitoring                                                  │   │   │
│  │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          ▼                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                      MICROSERVICES LAYER                                         │   │
│  │                                                                                  │   │
│  │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐           │   │
│  │  │ User Service │ │Claim Service │ │Budget Service│ │Payment Svc   │           │   │
│  │  │              │ │              │ │              │ │              │           │   │
│  │  │ • Auth       │ │ • Submission │ │ • Allocation │ │ • Processing │           │   │
│  │  │ • Profile    │ │ • Validation │ │ • Tracking   │ │ • Approval   │           │   │
│  │  │ • Roles      │ │ • Workflow   │ │ • Reporting  │ │ • Voucher    │           │   │
│  │  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘           │   │
│  │                                                                                  │   │
│  │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐           │   │
│  │  │ Master Data  │ │ Document Svc │ │Workflow Svc  │ │Analytics Svc │           │   │
│  │  │              │ │              │ │              │ │              │           │   │
│  │  │ • Projects   │ │ • Upload     │ │ • Engine     │ │ • Reports    │           │   │
│  │  │ • DUSP       │ │ • Storage    │ │ • Tasks      │ │ • Dashboard  │           │   │
│  │  │ • Items      │ │ • OCR        │ │ • Alerts     │ │ • ML Models  │           │   │
│  │  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘           │   │
│  │                                                                                  │   │
│  │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐           │   │
│  │  │ Audit Svc    │ │Notif. Svc    │ │Integrate Svc │ │Config Svc    │           │   │
│  │  │              │ │              │ │              │ │              │           │   │
│  │  │ • Logging    │ │ • Email      │ │ • USPFS      │ │ • Settings   │           │   │
│  │  │ • Tracking   │ │ • SMS        │ │ • External   │ │ • Parameters │           │   │
│  │  │ • Compliance │ │ • Push       │ │ • APIs       │ │ • Rules      │           │   │
│  │  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘           │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          ▼                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                        DATA LAYER                                                │   │
│  │                                                                                  │   │
│  │  ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐           │   │
│  │  │ Oracle DB    │ │ Redis Cache  │ │Object Store  │ │Search Engine │           │   │
│  │  │ (Primary)    │ │ (Session)    │ │(Documents)   │ │(Elastic)     │           │   │
│  │  └──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘           │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. MICROSERVICES ARCHITECTURE

### 2.1 Service Catalog

| Service ID | Service Name | Responsibility | Technology | Database |
|------------|--------------|----------------|------------|----------|
| SVC-001 | User Management Service | Authentication, authorization, user profiles | Java Spring Boot | Oracle DB |
| SVC-002 | Claims Management Service | Claim submission, validation, processing | Java Spring Boot | Oracle DB |
| SVC-003 | Budget Management Service | Budget allocation, tracking, reporting | Java Spring Boot | Oracle DB |
| SVC-004 | Payment Processing Service | Payment workflows, vouchers, reconciliation | Java Spring Boot | Oracle DB |
| SVC-005 | Master Data Service | DUSP, Project, Item master data | Java Spring Boot | Oracle DB |
| SVC-006 | Document Management Service | File upload, storage, OCR processing | Node.js | Object Storage |
| SVC-007 | Workflow Engine Service | Approval workflows, task management | Java Spring Boot | Oracle DB |
| SVC-008 | Analytics Service | Reporting, dashboards, ML models | Python/Spark | Data Warehouse |
| SVC-009 | Audit Service | Audit logging, compliance tracking | Java Spring Boot | Oracle DB |
| SVC-010 | Notification Service | Email, SMS, push notifications | Node.js | Redis |
| SVC-011 | Integration Service | External system integration | Java Spring Boot | Oracle DB |
| SVC-012 | Configuration Service | System settings, parameters | Java Spring Boot | Oracle DB |
| SVC-013 | Dashboard Service | Real-time dashboard data | Node.js | Redis/Oracle |
| SVC-014 | RPA Orchestrator | RPA bot management | UiPath | Oracle DB |
| SVC-015 | AI/ML Service | Document analysis, fraud detection | Python/TensorFlow | Oracle DB |

### 2.2 Service Communication Patterns

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         SERVICE COMMUNICATION PATTERNS                                   │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  SYNCHRONOUS COMMUNICATION (REST/gRPC)                                                   │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │   Client          API Gateway           Microservice                             │   │
│  │     │                  │                    │                                    │   │
│  │     │ ── Request ─────►│                    │                                    │   │
│  │     │                  │ ── Route ─────────►│                                    │   │
│  │     │                  │                    │ ── Process ────┐                   │   │
│  │     │                  │                    │                │                   │   │
│  │     │                  │                    │ ◄── Result ────┘                   │   │
│  │     │                  │ ◄─ Response ───────│                                    │   │
│  │     │ ◄─ Response ─────│                    │                                    │   │
│  │     │                  │                    │                                    │   │
│  │                                                                                  │   │
│  │  Use Cases: User authentication, claim submission, data queries                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  ASYNCHRONOUS COMMUNICATION (Message Queue)                                              │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │   Service A              Message Queue               Service B                   │   │
│  │      │                         │                        │                        │   │
│  │      │ ── Publish Event ──────►│                        │                        │   │
│  │      │                         │ ── Route Event ───────►│                        │   │
│  │      │                         │                        │ ── Process Event ────┐ │   │
│  │      │                         │                        │                      │ │   │
│  │      │                         │ ◄── Ack ───────────────│ ◄── Complete ────────┘ │   │
│  │      │                         │                        │                        │   │
│  │                                                                                  │   │
│  │  Use Cases: Payment processing, notifications, audit logging, report generation  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  EVENT SOURCING PATTERN                                                                  │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │   Command ──► Command Handler ──► Event Store ──► Event Bus ──► Projections      │   │
│  │                                                                                  │   │
│  │   Use Cases: Audit trails, state reconstruction, compliance logging              │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 2.3 Service Dependencies

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                            SERVICE DEPENDENCY GRAPH                                      │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│                                     API Gateway                                          │
│                                          │                                               │
│                    ┌─────────────────────┼─────────────────────┐                        │
│                    │                     │                     │                        │
│                    ▼                     ▼                     ▼                        │
│            ┌───────────┐          ┌───────────┐          ┌───────────┐                  │
│            │   User    │          │   Claims  │          │  Budget   │                  │
│            │  Service  │◄────────►│  Service  │◄────────►│  Service  │                  │
│            └─────┬─────┘          └─────┬─────┘          └─────┬─────┘                  │
│                  │                      │                      │                        │
│                  │              ┌───────┴───────┐              │                        │
│                  │              │               │              │                        │
│                  ▼              ▼               ▼              ▼                        │
│            ┌───────────┐  ┌───────────┐  ┌───────────┐  ┌───────────┐                  │
│            │   Auth    │  │  Document │  │  Workflow │  │  Payment  │                  │
│            │  Service  │  │  Service  │  │  Service  │  │  Service  │                  │
│            └─────┬─────┘  └─────┬─────┘  └─────┬─────┘  └─────┬─────┘                  │
│                  │              │              │              │                        │
│                  └──────────────┼──────────────┼──────────────┘                        │
│                                 │              │                                       │
│                                 ▼              ▼                                       │
│                          ┌───────────┐  ┌───────────┐                                  │
│                          │  Master   │  │   Audit   │                                  │
│                          │  Service  │  │  Service  │                                  │
│                          └───────────┘  └───────────┘                                  │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. DATA FLOW ARCHITECTURE

### 3.1 Claim Submission Data Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         CLAIM SUBMISSION DATA FLOW                                       │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   Step 1: DUSP initiates claim                                                          │
│   ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌──────────┐                   │
│   │   DUSP   │─────►│   Web    │─────►│   API    │─────►│  Claims  │                   │
│   │   User   │      │  Portal  │      │  Gateway │      │  Service │                   │
│   └──────────┘      └──────────┘      └──────────┘      └─────┬────┘                   │
│                                                               │                          │
│   Step 2: System validates and processes                                                   │
│                                                               ▼                          │
│                        ┌──────────┐      ┌──────────┐      ┌──────────┐                 │
│                        │  Budget  │◄────►│  Master  │◄────►│ Validate │                 │
│                        │  Service │      │  Service │      │  Claim   │                 │
│                        └────┬─────┘      └──────────┘      └────┬─────┘                 │
│                             │                                    │                       │
│                             │                                    ▼                       │
│                             │                             ┌──────────┐                  │
│                             │                             │  Workflow│                  │
│                             │                             │  Service │                  │
│                             │                             └────┬─────┘                  │
│                             │                                  │                         │
│   Step 3: Document processing and storage                                                │
│                             │                                  ▼                         │
│                        ┌────┴─────┐      ┌──────────┐      ┌──────────┐                 │
│                        │  Store   │◄────►│ Document │◄────►│   OCR    │                 │
│                        │  Budget  │      │  Service │      │  Engine  │                 │
│                        │  Check   │      └────┬─────┘      └──────────┘                 │
│                        └──────────┘           │                                        │
│                                               │                                        │
│   Step 4: Notification and audit                                                         │
│                                               ▼                                        │
│                                        ┌──────────┐      ┌──────────┐                   │
│                                        │ Object   │      │  Audit   │                   │
│                                        │ Storage  │      │  Service │                   │
│                                        └──────────┘      └────┬─────┘                   │
│                                                               │                          │
│                                                               ▼                          │
│                                                        ┌──────────┐                     │
│                                                        │  Notify  │                     │
│                                                        │  Service │                     │
│                                                        └──────────┘                     │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Payment Processing Data Flow

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                        PAYMENT PROCESSING DATA FLOW                                      │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐         │
│   │  Claims  │───►│ Workflow │───►│ Digital  │───►│ Payment  │───►│  USPFS   │         │
│   │ Approved │    │  Engine  │    │ Signature│    │ Service  │    │ Voucher  │         │
│   └──────────┘    └────┬─────┘    └────┬─────┘    └────┬─────┘    └────┬─────┘         │
│                        │               │               │               │               │
│                        │               │               │               │               │
│                        ▼               │               │               │               │
│                  ┌──────────┐          │               │               │               │
│                  │ Generate │          │               │               │               │
│                  │ Memo PDF │          │               │               │               │
│                  └────┬─────┘          │               │               │               │
│                       │                │               │               │               │
│                       ▼                ▼               ▼               ▼               │
│                 ┌──────────────────────────────────────────────────────────┐            │
│                 │              APPROVAL WORKFLOW (3 Layers)                │            │
│                 │  ┌──────────┐    ┌──────────┐    ┌──────────┐           │            │
│                 │  │ Level 1  │───►│ Level 2  │───►│ Level 3  │           │            │
│                 │  │ Reviewer │    │ Manager  │    │ Director │           │            │
│                 │  └──────────┘    └──────────┘    └──────────┘           │            │
│                 └──────────────────────────────────────────────────────────┘            │
│                                         │                                               │
│                                         ▼                                               │
│                                 ┌──────────────┐                                        │
│                                 │  POST TO     │                                        │
│                                 │  USPFS/      │                                        │
│                                 │  ORACLE EBS  │                                        │
│                                 └──────────────┘                                        │
│                                         │                                               │
│                    ┌────────────────────┼────────────────────┐                          │
│                    │                    │                    │                          │
│                    ▼                    ▼                    ▼                          │
│              ┌──────────┐       ┌──────────┐       ┌──────────┐                        │
│              │ Generate │       │   Send   │       │  Update  │                        │
│              │ Letter to│       │   SMS/   │       │  Claim   │                        │
│              │   DUSP   │       │  Email   │       │  Status  │                        │
│              └──────────┘       └──────────┘       └──────────┘                        │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. ORACLE INTEGRATION ARCHITECTURE

### 4.1 Oracle Technology Stack

| Component | Oracle Product | Version | Purpose |
|-----------|---------------|---------|---------|
| Database | Oracle Database Enterprise Edition | 19c | Primary data store |
| Application Server | Oracle WebLogic Server | 14c | Application hosting |
| Integration | Oracle Integration Cloud (OIC) | Latest | System integration |
| API Management | Oracle API Gateway | Latest | API security and management |
| Analytics | Oracle Analytics Cloud | Latest | Reporting and dashboards |
| Development | Oracle APEX | 22.x | Rapid application development |
| Security | Oracle Advanced Security | - | Encryption and security |

### 4.2 Oracle Database Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         ORACLE DATABASE ARCHITECTURE                                     │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                         ORACLE RAC CLUSTER (Primary)                             │   │
│   │                                                                                  │   │
│   │   ┌─────────────────┐         ┌─────────────────┐                               │   │
│   │   │   NODE 1        │◄───────►│   NODE 2        │                               │   │
│   │   │  (Active)       │  Heartbeat│  (Active)       │                               │   │
│   │   │                 │         │                 │                               │   │
│   │   │ • Instance 1    │         │ • Instance 2    │                               │   │
│   │   │ • Services A-D  │         │ • Services E-H  │                               │   │
│   │   └────────┬────────┘         └────────┬────────┘                               │   │
│   │            │                            │                                       │   │
│   │            └────────────┬───────────────┘                                       │   │
│   │                         │                                                       │   │
│   │            ┌────────────┴───────────────┐                                       │   │
│   │            │    SHARED STORAGE          │                                       │   │
│   │            │  (ASM Disk Groups)         │                                       │   │
│   │            │                            │                                       │   │
│   │            │  ┌─────────────────────┐   │                                       │   │
│   │            │  │   DATA DISKGROUP    │   │                                       │   │
│   │            │  │  • DATA Tablespace  │   │                                       │   │
│   │            │  │  • INDEX Tablespace │   │                                       │   │
│   │            │  │  • LOB Tablespace   │   │                                       │   │
│   │            │  └─────────────────────┘   │                                       │   │
│   │            │                            │                                       │   │
│   │            │  ┌─────────────────────┐   │                                       │   │
│   │            │  │   FRA DISKGROUP     │   │                                       │   │
│   │            │  │  • Archive Logs     │   │                                       │   │
│   │            │  │  • Backups          │   │                                       │   │
│   │            │  │  • Flashback        │   │                                       │   │
│   │            │  └─────────────────────┘   │                                       │   │
│   │            └────────────────────────────┘                                       │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                          │                                               │
│                                          │ Data Guard                                     │
│                                          ▼                                               │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                         STANDBY DATABASE (DR Site)                               │   │
│   │                                                                                  │   │
│   │   ┌─────────────────────────────────────────────────────────┐                   │   │
│   │   │  Physical Standby (Real-Time Apply)                    │                   │   │
│   │   │  • Async Replication                                   │                   │   │
│   │   │  • Automatic Failover (FSFO)                           │                   │   │
│   │   │  • Read-only queries (Active Data Guard)               │                   │   │
│   │   └─────────────────────────────────────────────────────────┘                   │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│   Security Features:                                                                     │
│   • Transparent Data Encryption (TDE)                                                   │
│   • Database Vault                                                                      │
│   • Data Redaction                                                                      │
│   • Label Security                                                                      │
│   • Audit Vault                                                                         │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 4.3 Oracle EBS Integration

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         UCMS - USPFS (ORACLE EBS) INTEGRATION                            │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌──────────────────────┐                          ┌──────────────────────┐            │
│   │         UCMS         │                          │      USPFS/Oracle EBS │            │
│   │                      │                          │                       │            │
│   │  ┌────────────────┐  │                          │  ┌────────────────┐   │            │
│   │  │  OIC Integration│  │◄────────────────────────►│  │  Oracle EBS    │   │            │
│   │  │  (Orchestration)│  │   REST/SOAP APIs         │  │  Integration   │   │            │
│   │  │                │  │   or Database Link       │  │  Repository    │   │            │
│   │  │ • API Adapter  │  │                          │  │                │   │            │
│   │  │ • DB Adapter   │  │                          │  │ • PL/SQL APIs  │   │            │
│   │  │ • File Adapter │  │                          │  │ • Java APIs    │   │            │
│   │  │ • ERP Adapter  │  │                          │  │ • Web Services │   │            │
│   │  └────────────────┘  │                          │  └────────────────┘   │            │
│   │           │          │                          │           │           │            │
│   │           ▼          │                          │           ▼           │            │
│   │  ┌────────────────┐  │                          │  ┌────────────────┐   │            │
│   │  │   Oracle DB    │  │                          │  │  Oracle EBS DB │   │            │
│   │  │   (UCMS Data)  │  │◄─── GoldenGate/CDC ───►│  │  (Financial)   │   │            │
│   │  └────────────────┘  │                          │  └────────────────┘   │            │
│   │                      │                          │                       │            │
│   └──────────────────────┘                          └──────────────────────┘            │
│                                                                                          │
│   Integration Flows:                                                                     │
│                                                                                          │
│   1. BUDGET DATA SYNC                                                                    │
│      UCMS ──► OIC ──► Oracle EBS (Query Budget Balance) ──► UCMS Cache                 │
│                                                                                          │
│   2. CLAIM VALIDATION                                                                    │
│      UCMS ──► OIC ──► Oracle EBS (Validate Capped Cost) ──► UCMS Response              │
│                                                                                          │
│   3. VOUCHER CREATION                                                                    │
│      UCMS ──► OIC ──► Oracle EBS (Create Voucher) ──► Voucher Number Return            │
│                                                                                          │
│   4. PAYMENT STATUS                                                                      │
│      Oracle EBS ──► OIC ──► UCMS (Payment Status Update)                                │
│                                                                                          │
│   5. MASTER DATA SYNC                                                                    │
│      Oracle EBS ──► OIC ──► UCMS (Daily COA, Supplier, Project Data)                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. CLOUD INFRASTRUCTURE ARCHITECTURE

### 5.1 OCI/Azure Hybrid Deployment

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                      CLOUD INFRASTRUCTURE ARCHITECTURE                                   │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   PRIMARY REGION: Oracle Cloud Infrastructure (OCI)                                      │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                                                                                  │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │                      VIRTUAL CLOUD NETWORK (VCN)                         │   │   │
│   │  │  CIDR: 10.0.0.0/16                                                        │   │   │
│   │  │                                                                           │   │   │
│   │  │  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐          │   │   │
│   │  │  │  PUBLIC SUBNET  │  │ PRIVATE SUBNET  │  │  DB SUBNET      │          │   │   │
│   │  │  │  10.0.1.0/24    │  │ 10.0.2.0/24     │  │ 10.0.3.0/24     │          │   │   │
│   │  │  │                 │  │                 │  │                 │          │   │   │
│   │  │  │ • Load Balancer │  │ • App Servers   │  │ • Oracle RAC    │          │   │   │
│   │  │  │ • Bastion Host  │  │ • OIC Runtime   │  │ • Exadata       │          │   │   │
│   │  │  │ • NAT Gateway   │  │ • RPA Servers   │  │ • Backup        │          │   │   │
│   │  │  └─────────────────┘  └─────────────────┘  └─────────────────┘          │   │   │
│   │  │                                                                           │   │   │
│   │  │  ┌─────────────────────────────────────────────────────────────────┐   │   │   │
│   │  │  │  SERVICES: OKE (Kubernetes), OAC (Analytics), Object Storage    │   │   │   │
│   │  │  └─────────────────────────────────────────────────────────────────┘   │   │   │
│   │  │                                                                           │   │   │
│   │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│   │                                                                                  │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│   SECONDARY REGION: Microsoft Azure (Optional)                                           │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                                                                                  │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │                      VIRTUAL NETWORK                                     │   │   │
│   │  │                                                                           │   │   │
│   │  │  ┌─────────────────────────────────────────────────────────────────┐   │   │   │
│   │  │  │  SERVICES: Azure AD, API Management, Backup Storage             │   │   │   │
│   │  │  └─────────────────────────────────────────────────────────────────┘   │   │   │
│   │  │                                                                           │   │   │
│   │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│   │                                                                                  │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│   CONNECTIVITY:                                                                          │
│   • VPN: Site-to-Site VPN between MCMC HQ and OCI                                       │
│   • FastConnect: Dedicated connection for production traffic                            │
│   • Inter-Cloud: ExpressRoute for Azure integration                                     │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Infrastructure Services

| Service Category | OCI Service | Azure Equivalent | Purpose |
|------------------|-------------|------------------|---------|
| Compute | Compute Instances / OKE | VMs / AKS | Application hosting |
| Database | Oracle Base Database / Exadata | Azure SQL / Oracle on Azure | Data storage |
| Storage | Object Storage / Block Volumes | Blob Storage / Managed Disks | File and data storage |
| Networking | VCN, Load Balancer, DNS | VNet, ALB, Azure DNS | Network infrastructure |
| Security | IAM, Vault, WAF | Azure AD, Key Vault, WAF | Security services |
| Monitoring | Monitoring, Logging | Monitor, Log Analytics | Observability |
| Integration | Integration Cloud | Logic Apps | System integration |

---

## 6. CONTAINER ARCHITECTURE

### 6.1 Kubernetes Deployment

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         KUBERNETES DEPLOYMENT ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                         OKE CLUSTER (Oracle Kubernetes Engine)                   │   │
│  │                                                                                  │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │                    NODE POOL: APPLICATION (3 nodes)                      │   │   │
│  │  │  Shape: VM.Standard2.4 (4 OCPU, 60GB RAM)                                │   │   │
│  │  │                                                                           │   │   │
│  │  │  ┌─────────────────────────────────────────────────────────────────┐   │   │   │
│  │  │  │  PODS:                                                          │   │   │   │
│  │  │  │  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌───────────┐│   │   │   │
│  │  │  │  │   API       │ │   Web       │ │  Worker     │ │  RPA      ││   │   │   │
│  │  │  │  │   Pods      │ │   Pods      │ │   Pods      │ │   Bots    ││   │   │   │
│  │  │  │  │  (3 replicas)│ │  (3 replicas)│ │  (2 replicas)│ │ (5 bots)  ││   │   │   │
│  │  │  │  └─────────────┘ └─────────────┘ └─────────────┘ └───────────┘│   │   │   │
│  │  │  └─────────────────────────────────────────────────────────────────┘   │   │   │
│  │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│  │                                                                                  │   │
│  │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│  │  │                    NODE POOL: SERVICES (2 nodes)                         │   │   │
│  │  │  Shape: VM.Standard2.2 (2 OCPU, 30GB RAM)                                │   │   │
│  │  │                                                                           │   │   │
│  │  │  ┌─────────────────────────────────────────────────────────────────┐   │   │   │
│  │  │  │  PODS:                                                          │   │   │   │
│  │  │  │  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐               │   │   │   │
│  │  │  │  │   Redis     │ │   Kafka     │ │ Monitoring  │               │   │   │   │
│  │  │  │  │   Cluster   │ │   Brokers   │ │   Stack     │               │   │   │   │
│  │  │  │  └─────────────┘ └─────────────┘ └─────────────┘               │   │   │   │
│  │  │  └─────────────────────────────────────────────────────────────────┘   │   │   │
│  │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│  │                                                                                  │   │
│  │  KUBERNETES RESOURCES:                                                           │   │
│  │  • Deployments: 15                                                               │   │
│  │  • Services: 15 (ClusterIP, LoadBalancer)                                        │   │
│  │  • Ingress: 2 (Public, Internal)                                                 │   │
│  │  • ConfigMaps: 20                                                                │   │
│  │  • Secrets: 15 (Azure Key Vault integration)                                     │   │
│  │  • HPA: 10 (Horizontal Pod Autoscaling)                                          │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Container Registry & CI/CD

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         CONTAINER REGISTRY & CI/CD PIPELINE                              │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  DEVELOPER WORKFLOW                                                                      │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐         │
│  │   Code   │───►│   Push   │───►│  Build   │───►│   Test   │───►│  Deploy  │         │
│  │  Commit  │    │  to Git  │    │ Trigger  │    │   & QA   │    │ to OKE   │         │
│  └──────────┘    └──────────┘    └──────────┘    └──────────┘    └──────────┘         │
│                                                                                          │
│  CI/CD PIPELINE (Azure DevOps / OCI DevOps)                                              │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐         │   │
│  │  │    Build    │──►│    Test     │──►│   Security  │──►│   Deploy    │         │   │
│  │  │    Stage    │   │    Stage    │   │    Scan     │   │    Stage    │         │   │
│  │  │             │   │             │   │             │   │             │         │   │
│  │  │ • Compile   │   │ • Unit Test │   │ • SAST      │   │ • Dev Env   │         │   │
│  │  │ • Package   │   │ • Integration│   │ • DAST      │   │ • Staging   │         │   │
│  │  │ • Container │   │ • Coverage  │   │ • Container │   │ • Production│         │   │
│  │  │   Build     │   │             │   │   Scan      │   │             │         │   │
│  │  └─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘         │   │
│  │         │                 │                 │                 │                  │   │
│  │         └─────────────────┴─────────────────┴─────────────────┘                  │   │
│  │                               │                                                  │   │
│  │                               ▼                                                  │   │
│  │                    ┌─────────────────────┐                                       │   │
│  │                    │   OCI CONTAINER     │                                       │   │
│  │                    │   REGISTRY (OCIR)   │                                       │   │
│  │                    │                     │                                       │   │
│  │                    │ • ucms/api:latest   │                                       │   │
│  │                    │ • ucms/web:v1.2.3   │                                       │   │
│  │                    │ • ucms/worker:prod  │                                       │   │
│  │                    │ • ucms/rpa:stable   │                                       │   │
│  │                    └─────────────────────┘                                       │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  IMAGE PROMOTION STRATEGY                                                                │
│  Dev Registry ──► Staging Registry ──► Production Registry                              │
│  (latest tag)     (semantic version)     (immutable tags)                               │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Technical Team | Initial version |

---

**END OF ANNEX T2**
