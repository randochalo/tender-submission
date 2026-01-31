# ANNEX A: TECHNICAL ARCHITECTURE

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**Document Version:** 1.0  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Architecture Overview](#1-architecture-overview)
2. [Deployment Model](#2-deployment-model)
3. [System Components](#3-system-components)
4. [Integration Architecture](#4-integration-architecture)
5. [Security Architecture](#5-security-architecture)
6. [Data Architecture](#6-data-architecture)
7. [Scalability & Performance](#7-scalability--performance)
8. [Disaster Recovery & Business Continuity](#8-disaster-recovery--business-continuity)

---

## 1. ARCHITECTURE OVERVIEW

### 1.1 System Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           CLIENT LAYER                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │   Web App   │  │ Mobile App  │  │   Tablet    │  │    Customer Portal  │ │
│  │  (React)    │  │(React Native│  │   (PWA)     │  │    (Self-Service)   │ │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────────┬──────────┘ │
└─────────┼────────────────┼────────────────┼────────────────────┼────────────┘
          │                │                │                    │
          └────────────────┴────────────────┴────────────────────┘
                                   │
                          ┌────────▼────────┐
                          │   CDN / WAF     │
                          │  (Cloudflare)   │
                          └────────┬────────┘
                                   │
┌──────────────────────────────────┼──────────────────────────────────────────┐
│                        API GATEWAY LAYER                                    │
├──────────────────────────────────┼──────────────────────────────────────────┤
│                          ┌───────▼────────┐                                 │
│                          │  Kong Gateway  │                                 │
│                          │  - Rate Limit  │                                 │
│                          │  - Auth/JWT    │                                 │
│                          │  - Logging     │                                 │
│                          └───────┬────────┘                                 │
└──────────────────────────────────┼──────────────────────────────────────────┘
                                   │
┌──────────────────────────────────┼──────────────────────────────────────────┐
│                      APPLICATION LAYER (Kubernetes)                         │
├──────────────────────────────────┼──────────────────────────────────────────┤
│  ┌─────────────┐ ┌─────────────┐ │ ┌─────────────┐ ┌─────────────┐          │
│  │     HMS     │ │     FFS     │ │     WMS     │ │     TMS     │          │
│  │  Microsvc   │ │  Microsvc   │ │  Microsvc   │ │  Microsvc   │          │
│  │   (3 pods)  │ │   (3 pods)  │ │   (3 pods)  │ │   (3 pods)  │          │
│  └─────────────┘ └─────────────┘ │ └─────────────┘ └─────────────┘          │
│  ┌─────────────┐ ┌─────────────┐ │ ┌─────────────────────────────┐          │
│  │     FMS     │ │  Integration│ │ │      AI/ML Services         │          │
│  │  Microsvc   │ │   Engine    │ │ │  (Prediction, NLP, OCR)     │          │
│  │   (3 pods)  │ │   (2 pods)  │ │ │      (4 pods)               │          │
│  └─────────────┘ └─────────────┘ │ └─────────────────────────────┘          │
│                                  │                                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │              Shared Services (Authentication, Logging, Config)       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
└────────────────────────────────────────────────────────────────────────────┘
                                   │
┌──────────────────────────────────┼──────────────────────────────────────────┐
│                         DATA LAYER                                          │
├──────────────────────────────────┼──────────────────────────────────────────┤
│  ┌─────────────────┐ ┌───────────▼───────────┐ ┌─────────────────────────┐  │
│  │   PostgreSQL    │ │      Redis Cluster    │ │    Object Storage       │  │
│  │   (Primary-     │ │   (Session/Cache/     │ │   (Documents/Images/    │  │
│  │    Standby)     │ │     Queue)            │ │     Backups)            │  │
│  │   HA Cluster    │ │                       │ │                         │  │
│  └─────────────────┘ └───────────────────────┘ └─────────────────────────┘  │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    Elasticsearch (Search/Analytics)                    │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────────────────┘
                                   │
┌──────────────────────────────────┼──────────────────────────────────────────┐
│                    EXTERNAL INTEGRATIONS                                    │
├──────────────────────────────────┼──────────────────────────────────────────┤
│  ┌──────────┐ ┌──────────┐ ┌─────▼──────┐ ┌──────────┐ ┌────────────────┐  │
│  │   IRBM   │ │  MyGBS   │ │  Port Klang│ │   KTMB   │ │ Shipping Lines │  │
│  │ MyInvois │ │ (Customs)│ │    PCS     │ │  (Rail)  │ │  (API/EDI)     │  │
│  └──────────┘ └──────────┘ └────────────┘ └──────────┘ └────────────────┘  │
│  ┌──────────┐ ┌──────────┐ ┌──────────────┐ ┌──────────────────────────┐   │
│  │  Banks   │ │  JPJ     │ │    GPS/      │ │     Customer ERPs        │   │
│  │  (FPX/  │ │ (Vehicle)│ │ Telematics   │ │  (SAP/Oracle/Dynamics)   │   │
│  │  IBFT)   │ │          │ │              │ │                          │   │
│  └──────────┘ └──────────┘ └──────────────┘ └──────────────────────────┘   │
└────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Architecture Principles

| Principle | Implementation |
|-----------|----------------|
| **Cloud-Native** | Containerized microservices on Kubernetes with auto-scaling |
| **API-First** | All functionality exposed via REST APIs with OpenAPI documentation |
| **Event-Driven** | Asynchronous processing via message queues for high throughput |
| **Multi-Tenant** | Single codebase serving multiple branches with data isolation |
| **Offline-Capable** | Progressive Web Apps with local storage and background sync |
| **Security-First** | Zero-trust architecture with defense-in-depth approach |

---

## 2. DEPLOYMENT MODEL

### 2.1 Awan Kita Sovereign Cloud

Our solution is deployed on **Awan Kita** compliant infrastructure ensuring:

- ✅ **Data Residency:** All data stored within Malaysia
- ✅ **Local Encryption:** Encryption keys managed within Malaysian jurisdiction
- ✅ **Compliance:** Meets Malaysian government cloud security requirements
- ✅ **Low Latency:** Sub-50ms response times for Malaysian users

### 2.2 Infrastructure Components

| Component | Technology | Specification | HA Strategy |
|-----------|------------|---------------|-------------|
| **Compute** | Kubernetes (EKS/AKS/GKE) | 3+ worker nodes per cluster | Multi-zone deployment |
| **Database** | PostgreSQL 15 | Primary + 2 Standby replicas | Automatic failover |
| **Cache** | Redis 7 | 3-node cluster | Sharded with replication |
| **Queue** | RabbitMQ | 3-node cluster | Mirrored queues |
| **Storage** | S3-compatible Object Store | 99.999999999% durability | Cross-region replication |
| **Search** | Elasticsearch 8 | 3-node cluster | Replicated indices |
| **CDN** | Cloudflare | 275+ PoPs globally | Always-on DDoS protection |

### 2.3 Network Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                         INTERNET                                │
└───────────────────────┬─────────────────────────────────────────┘
                        │
              ┌─────────▼─────────┐
              │   Cloudflare WAF  │
              │   + DDoS Protection│
              └─────────┬─────────┘
                        │
┌───────────────────────▼─────────────────────────────────────────┐
│                     VPC (Virtual Private Cloud)                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  Public Subnet (Load Balancers, Bastion Hosts)         │   │
│  └──────────────────────┬──────────────────────────────────┘   │
│                         │                                      │
│  ┌──────────────────────▼──────────────────────────────────┐   │
│  │  Private Subnet (Application Services)                  │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │   │
│  │  │   HMS Pods  │  │   FFS Pods  │  │   WMS Pods  │     │   │
│  │  │   (3)       │  │   (3)       │  │   (3)       │     │   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘     │   │
│  └──────────────────────┬──────────────────────────────────┘   │
│                         │                                      │
│  ┌──────────────────────▼──────────────────────────────────┐   │
│  │  Database Subnet (Isolated, No Internet)               │   │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │   │
│  │  │ PostgreSQL  │  │    Redis    │  │Elasticsearch│     │   │
│  │  │   Primary   │  │   Cluster   │  │   Cluster   │     │   │
│  │  └─────────────┘  └─────────────┘  └─────────────┘     │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. SYSTEM COMPONENTS

### 3.1 HMS (Haulage Management System)

| Aspect | Specification |
|--------|---------------|
| **Microservices** | 12 independently deployable services |
| **Core Modules** | Job Planning, GPS Tracking, Driver Management, Billing |
| **Mobile App** | React Native with offline-first architecture |
| **GPS Integration** | Geotab, Wialon, and custom telematics support |
| **AI Components** | Route optimization, predictive maintenance, driver scoring |

**Service Breakdown:**
- `hms-job-service`: Job creation, assignment, tracking
- `hms-fleet-service`: Vehicle registry, maintenance, compliance
- `hms-driver-service`: Driver profiles, incentives, performance
- `hms-billing-service`: Rating, invoicing, e-invoice generation
- `hms-gps-service`: Real-time tracking, geofencing, alerts
- `hms-mobile-api`: Mobile app backend with offline sync

### 3.2 FFS (Forwarding Management System)

| Aspect | Specification |
|--------|---------------|
| **Microservices** | 10 independently deployable services |
| **Core Modules** | Shipment Management, Documentation, Customs, Quotation |
| **EDI Support** | ANSI X12, UN/EDIFACT, XML, JSON |
| **AI Components** | Exception prediction, document extraction, revenue intelligence |

**Service Breakdown:**
- `ffs-shipment-service`: Booking, tracking, status management
- `ffs-documentation-service`: BL, AWB, CO generation
- `ffs-customs-service`: MyGBS integration, declaration management
- `ffs-quotation-service`: Rate cards, automated quoting
- `ffs-edi-service`: EDI message processing and transformation

### 3.3 WMS (Warehouse Management System)

| Aspect | Specification |
|--------|---------------|
| **Microservices** | 14 independently deployable services |
| **Core Modules** | Inventory, Receiving, Picking, Packing, Shipping |
| **Hardware Support** | Barcode scanners, RFID, IoT sensors, voice picking |
| **AI Components** | Slotting optimization, demand forecasting, drone integration |

**Service Breakdown:**
- `wms-inventory-service`: Stock levels, movements, adjustments
- `wms-receiving-service`: ASN processing, put-away, quality control
- `wms-picking-service`: Wave planning, pick path optimization
- `wms-shipping-service`: Packing, carrier integration, manifests
- `wms-location-service`: Bin management, warehouse mapping
- `wms-labor-service`: Task assignment, productivity tracking

### 3.4 TMS (Terminal Management System)

| Aspect | Specification |
|--------|---------------|
| **Microservices** | 11 independently deployable services |
| **Core Modules** | Yard Management, Gate Operations, Rail, Billing |
| **Hardware Integration** | Weighbridges, gate scanners, RFID readers |
| **AI Components** | Yard optimization, congestion prediction, equipment telemetry |

**Service Breakdown:**
- `tms-yard-service`: Container stacking, slotting, tracking
- `tms-gate-service`: Gate-in/gate-out, validation, weighing
- `tms-rail-service`: KTMB integration, rail manifest management
- `tms-billing-service`: Storage, handling, repair billing
- `tms-apad-service`: APAD compliance, TAT tracking

### 3.5 FMS (Finance Management System)

| Aspect | Specification |
|--------|---------------|
| **Microservices** | 16 independently deployable services |
| **Core Modules** | GL, AP, AR, Fixed Assets, Tax, Reporting |
| **Compliance** | MFRS, IRBM e-Invoicing, SST/GST |
| **AI Components** | Cash flow forecasting, fraud detection, credit scoring |

**Service Breakdown:**
- `fms-gl-service`: General ledger, journal entries, period close
- `fms-ap-service`: Vendor management, invoice processing, payments
- `fms-ar-service`: Customer billing, collections, receipts
- `fms-asset-service`: Fixed asset register, depreciation, disposal
- `fms-tax-service`: SST/GST calculation, e-invoice submission
- `fms-reporting-service`: Financial reports, consolidation, analytics

---

## 4. INTEGRATION ARCHITECTURE

### 4.1 Enterprise Service Bus (ESB)

```
┌─────────────────────────────────────────────────────────────────┐
│                    INTEGRATION LAYER                            │
├─────────────────────────────────────────────────────────────────┤
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              API Gateway (Kong)                         │   │
│  │  - Authentication/Authorization                         │   │
│  │  - Rate Limiting & Throttling                           │   │
│  │  - Request/Response Transformation                      │   │
│  │  - Caching & Load Balancing                             │   │
│  └────────────────────┬────────────────────────────────────┘   │
│                       │                                         │
│  ┌────────────────────▼────────────────────────────────────┐   │
│  │              Message Queue (RabbitMQ)                   │   │
│  │  - Async Processing                                     │   │
│  │  - Event-Driven Architecture                            │   │
│  │  - Guaranteed Delivery                                  │   │
│  └────────────────────┬────────────────────────────────────┘   │
│                       │                                         │
│  ┌────────────────────▼────────────────────────────────────┐   │
│  │              Integration Adapters                       │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  │   │
│  │  │  REST    │ │  SOAP    │ │   EDI    │ │  SFTP    │  │   │
│  │  │ Adapters │ │ Adapters │ │ Adapters │ │ Adapters │  │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘  │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 Internal System Integration

| Source | Target | Integration Type | Frequency |
|--------|--------|------------------|-----------|
| HMS | FMS | Real-time events | Immediate |
| FFS | HMS | API calls | On-demand |
| WMS | FFS | Message queue | Near real-time |
| TMS | HMS | API calls | On-demand |
| All | FMS | Event streaming | Real-time |

### 4.3 External System Integration

| External System | Protocol | Data Exchange | Status |
|-----------------|----------|---------------|--------|
| **IRBM MyInvois** | REST API | e-Invoice submission | ✅ Production Ready |
| **MyGBS (Customs)** | SOAP/REST | Customs declarations | ✅ Production Ready |
| **Port Klang PCS** | EDI/API | Container movements | ✅ Production Ready |
| **KTMB** | EDI | Rail manifests | ✅ Production Ready |
| **Shipping Lines** | EDI/API | Booking, tracking | ✅ 15+ carriers |
| **GPS/Telematics** | REST/WebSocket | Vehicle tracking | ✅ Geotab/Wialon |
| **Banks (FPX)** | REST API | Payment processing | ✅ Major banks |

---

## 5. SECURITY ARCHITECTURE

### 5.1 Defense in Depth

```
┌─────────────────────────────────────────────────────────────────┐
│  LAYER 1: PERIMETER SECURITY                                    │
│  • Cloudflare WAF with OWASP Top 10 protection                  │
│  • DDoS mitigation (Layer 3/4/7)                                │
│  • Bot management and threat intelligence                       │
│  • SSL/TLS 1.3 encryption                                       │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 2: NETWORK SECURITY                                      │
│  • VPC isolation with private subnets                           │
│  • Network ACLs and security groups                             │
│  • Bastion hosts for secure access                              │
│  • VPN for administrative access                                │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 3: APPLICATION SECURITY                                  │
│  • OAuth 2.0 / OpenID Connect authentication                    │
│  • JWT tokens with short expiry                                 │
│  • RBAC with 50+ granular permissions                           │
│  • Input validation and sanitization                            │
│  • API rate limiting and throttling                             │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 4: DATA SECURITY                                         │
│  • AES-256 encryption at rest                                   │
│  • TLS 1.3 encryption in transit                                │
│  • Database encryption (TDE)                                    │
│  • Field-level encryption for PII                               │
│  • Encryption keys in HSM (Hardware Security Module)            │
├─────────────────────────────────────────────────────────────────┤
│  LAYER 5: MONITORING & AUDIT                                    │
│  • SIEM integration (Security Information & Event Management)   │
│  • Real-time threat detection                                   │
│  • Immutable audit logs                                         │
│  • Automated security scanning                                  │
└─────────────────────────────────────────────────────────────────┘
```

### 5.2 Authentication & Authorization

| Feature | Implementation |
|---------|----------------|
| **Multi-Factor Authentication** | TOTP (Google Authenticator), SMS, Email |
| **Single Sign-On** | SAML 2.0, Microsoft Entra ID integration |
| **Password Policy** | NIST 800-63B compliant (min 12 chars, complexity) |
| **Session Management** | 30-minute idle timeout, concurrent session limits |
| **API Security** | OAuth 2.0 with PKCE, mTLS for service-to-service |

### 5.3 Security Certifications

- ✅ **VAPT:** CREST-accredited penetration testing
- ✅ **ISO 27001:** Information Security Management
- ✅ **SOC 2 Type II:** Security and availability controls
- ✅ **Awan Kita:** Malaysian government cloud compliance
- ✅ **PDPA:** Personal Data Protection Act compliance

---

## 6. DATA ARCHITECTURE

### 6.1 Data Flow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                        DATA SOURCES                             │
├─────────────────────────────────────────────────────────────────┤
│  ┌────────────┐  ┌────────────┐  ┌────────────┐                │
│  │ User Input │  │ Mobile App │  │   APIs     │                │
│  │  (Forms)   │  │   (GPS)    │  │  (EDI)     │                │
│  └─────┬──────┘  └─────┬──────┘  └─────┬──────┘                │
│        │               │               │                        │
│        └───────────────┼───────────────┘                        │
│                        ▼                                        │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │              VALIDATION & TRANSFORMATION                 │  │
│  │         (Schema validation, Data cleansing)              │  │
│  └──────────────────────────┬───────────────────────────────┘  │
│                             ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │                   APPLICATION LAYER                      │  │
│  │         (Business logic, Rules engine)                   │  │
│  └──────────────────────────┬───────────────────────────────┘  │
│                             ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │                   DATA STORAGE                           │  │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────────┐     │  │
│  │  │PostgreSQL  │  │   Redis    │  │ Elasticsearch  │     │  │
│  │  │(Transactional│  │  (Cache)   │  │  (Search/Analytics)│  │
│  │  └────────────┘  └────────────┘  └────────────────┘     │  │
│  └──────────────────────────────────────────────────────────┘  │
│                             ▼                                   │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │              REPORTING & ANALYTICS                       │  │
│  │       (BI Dashboards, Data exports, APIs)                │  │
│  └──────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

### 6.2 Database Schema Overview

| System | Primary Tables | Estimated Records | Data Retention |
|--------|---------------|-------------------|----------------|
| **HMS** | 120+ tables | 10M+ transactions | 7 years |
| **FFS** | 95+ tables | 5M+ shipments | 7 years |
| **WMS** | 85+ tables | 50M+ inventory movements | 7 years |
| **TMS** | 75+ tables | 2M+ container movements | 7 years |
| **FMS** | 110+ tables | 20M+ financial transactions | 10 years |

### 6.3 Data Backup Strategy

| Backup Type | Frequency | Retention | Storage Location |
|-------------|-----------|-----------|------------------|
| **Automated Full Backup** | Daily | 30 days | Malaysia (Primary) |
| **Incremental Backup** | Every 4 hours | 7 days | Malaysia (Primary) |
| **Transaction Log Backup** | Every 15 minutes | 24 hours | Malaysia (Primary) |
| **Cross-Region Backup** | Daily | 90 days | Malaysia (Secondary) |
| **Archive Backup** | Monthly | 7 years | Cold storage |

---

## 7. SCALABILITY & PERFORMANCE

### 7.1 Performance Metrics

| Metric | Target | Peak Capacity |
|--------|--------|---------------|
| **API Response Time** | < 200ms (p95) | < 500ms (p99) |
| **Page Load Time** | < 2 seconds | < 3 seconds |
| **Mobile App Sync** | < 5 seconds | < 10 seconds |
| **Report Generation** | < 30 seconds | < 60 seconds |
| **Concurrent Users** | 500 | 2,000 |
| **Transactions/Second** | 1,000 TPS | 5,000 TPS |

### 7.2 Auto-Scaling Configuration

```yaml
# Kubernetes HPA (Horizontal Pod Autoscaler) Configuration
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: logisticspro-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: logisticspro-services
  minReplicas: 3
  maxReplicas: 20
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 70
  - type: Resource
    resource:
      name: memory
      target:
        type: Utilization
        averageUtilization: 80
  behavior:
    scaleUp:
      stabilizationWindowSeconds: 60
      policies:
      - type: Percent
        value: 100
        periodSeconds: 15
    scaleDown:
      stabilizationWindowSeconds: 300
      policies:
      - type: Percent
        value: 10
        periodSeconds: 60
```

### 7.3 Caching Strategy

| Cache Layer | Technology | TTL | Use Case |
|-------------|------------|-----|----------|
| **CDN Cache** | Cloudflare | 1 hour | Static assets, images |
| **Application Cache** | Redis | 5 minutes | Session data, user preferences |
| **Database Cache** | PostgreSQL | Query-based | Frequently accessed queries |
| **API Cache** | Kong | Configurable | External API responses |

---

## 8. DISASTER RECOVERY & BUSINESS CONTINUITY

### 8.1 RTO/RPO Targets

| Metric | Target | Maximum Acceptable |
|--------|--------|-------------------|
| **RTO (Recovery Time Objective)** | < 2 hours | 4 hours |
| **RPO (Recovery Point Objective)** | < 15 minutes | 1 hour |

### 8.2 Disaster Recovery Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    PRIMARY SITE (Active)                        │
│  Location: Malaysia Data Center (Awan Kita Zone A)             │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  • Full application stack (HMS, FFS, WMS, TMS, FMS)    │   │
│  │  • Primary database cluster                             │   │
│  │  • Real-time replication to DR site                     │   │
│  └─────────────────────────────────────────────────────────┘   │
└───────────────────────────────┬─────────────────────────────────┘
                                │ Synchronous Replication
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│              DISASTER RECOVERY SITE (Standby)                   │
│  Location: Malaysia Data Center (Awan Kita Zone B)             │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  • Standby application stack (warm standby)            │   │
│  │  • Replica database cluster (read-only)                │   │
│  │  • Automatic failover capability                        │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

### 8.3 Business Continuity Procedures

| Scenario | Response | Recovery Action |
|----------|----------|-----------------|
| **Database Failure** | Automatic | Failover to standby replica (< 60 seconds) |
| **Application Failure** | Automatic | Restart containers, traffic rerouting (< 5 minutes) |
| **Data Center Failure** | Semi-Automatic | DNS failover to DR site (< 2 hours) |
| **Region Failure** | Manual | Restore from cross-region backups (< 4 hours) |
| **Data Corruption** | Manual | Point-in-time recovery to last known good state |

### 8.4 DR Testing Schedule

| Test Type | Frequency | Scope |
|-----------|-----------|-------|
| **Tabletop Exercise** | Quarterly | Process validation |
| **Failover Test** | Bi-annually | DR site activation |
| **Full Recovery Test** | Annually | End-to-end restoration |
| **Backup Restoration** | Monthly | Data integrity verification |

---

## APPENDIX A.1: TECHNOLOGY STACK

| Category | Technology | Version | Purpose |
|----------|------------|---------|---------|
| **Frontend** | React | 18.x | Web application |
| **Mobile** | React Native | 0.72+ | iOS/Android apps |
| **Backend** | Node.js / Python | 18.x / 3.11 | Microservices |
| **Database** | PostgreSQL | 15.x | Primary database |
| **Cache** | Redis | 7.x | Session & cache |
| **Queue** | RabbitMQ | 3.12+ | Message broker |
| **Search** | Elasticsearch | 8.x | Full-text search |
| **Container** | Docker | 24.x | Containerization |
| **Orchestration** | Kubernetes | 1.28+ | Container orchestration |
| **Monitoring** | Prometheus/Grafana | Latest | Metrics & monitoring |
| **Logging** | ELK Stack | 8.x | Centralized logging |
| **CI/CD** | GitHub Actions | N/A | Deployment automation |

---

**Document Control**

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
