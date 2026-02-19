# ANNEX T1: SYSTEM ARCHITECTURE DIAGRAM
## TSH-2607: Universal Service Provision (USP) Claims Management System (UCMS)
**Document Reference:** ANNEX-T01-ARCHITECTURE-TSH2607.md  
**Version:** 1.0  
**Date:** January 2025  
**Classification:** Technical Annexure

---

## 1. EXECUTIVE SUMMARY

This annexure presents the comprehensive system architecture diagram for the USP Claims Management System (UCMS) developed for the Malaysian Communications and Multimedia Commission (MCMC). The architecture follows industry best practices for enterprise-grade Oracle-based solutions with integrated digital signature, RPA, and OCR capabilities.

**Cross-References:**
- URS Section 4.1: System Architecture Requirements
- BRS Section 3.2: Business Architecture
- SRS Section 5.1: Technical Architecture Specifications
- SDS Section 2.3: Solution Design Architecture

---

## 2. ARCHITECTURAL OVERVIEW

The UCMS architecture is designed as a multi-tier, service-oriented architecture (SOA) that ensures scalability, security, and maintainability. The system comprises 10 integrated modules supporting the complete lifecycle of USP claims management.

### 2.1 Architecture Layers

| Layer | Components | Technology Stack |
|-------|------------|------------------|
| **Presentation Layer** | Web Portal, Mobile Interface, Admin Dashboard | Oracle APEX, React.js, HTML5/CSS3 |
| **Application Layer** | Business Logic, API Gateway, Workflow Engine | Oracle Fusion Middleware, REST APIs |
| **Integration Layer** | RPA Bots, OCR Engine, Digital Signature Service | UiPath, Tesseract/OCR.space, Docusign/Adobe Sign |
| **Data Layer** | Database, Document Store, Cache | Oracle Database 19c/21c, Oracle NoSQL |
| **Infrastructure Layer** | Servers, Network, Security | Oracle Cloud Infrastructure (OCI) |

---

## 3. SYSTEM ARCHITECTURE DIAGRAM

```mermaid
graph TB
    subgraph "External Systems"
        CIMS[CIMS System]
        MyUSP[MyUSP Portal]
        Finance[Finance System]
        Email[Email/SMS Gateway]
        Bank[Banking APIs]
    end

    subgraph "Presentation Tier"
        WebPortal[Web Portal<br/>Claimants/Administrators]
        MobileApp[Mobile Responsive]
        AdminDash[Admin Dashboard]
    end

    subgraph "Application Tier"
        APIGateway[API Gateway<br/>OAuth 2.0 / JWT]
        AppServer[Oracle WebLogic Server]
        Workflow[Workflow Engine<br/>BPMN 2.0]
        RuleEngine[Business Rule Engine]
    end

    subgraph "Integration Tier"
        RPA[RPA Services<br/>UiPath]
        OCR[OCR Engine<br/>Document Processing]
        DigiSign[Digital Signature<br/>Service]
        Report[Reporting Engine<br/>Oracle BI]
    end

    subgraph "Data Tier"
        OracleDB[(Oracle Database 19c<br/>Primary Data Store)]
        DocStore[(Document Store<br/>Oracle NoSQL)]
        Cache[(Redis Cache<br/>Session/Performance)]
        Backup[(Backup & DR<br/>Oracle Data Guard)]
    end

    subgraph "Security Layer"
        Firewall[WAF / Firewall]
        IAM[Identity & Access<br/>Management]
        Audit[Audit Logging]
        Encrypt[Encryption<br/>AES-256/TLS 1.3]
    end

    CIMS <-->|SOAP/REST| APIGateway
    MyUSP <-->|REST API| APIGateway
    Finance <-->|Secure FTP/API| AppServer
    Email <-->|SMTP/API| AppServer
    Bank <-->|REST API| DigiSign

    WebPortal --> APIGateway
    MobileApp --> APIGateway
    AdminDash --> APIGateway

    APIGateway --> AppServer
    AppServer --> Workflow
    AppServer --> RuleEngine

    Workflow --> RPA
    Workflow --> OCR
    Workflow --> DigiSign
    AppServer --> Report

    AppServer --> OracleDB
    AppServer --> DocStore
    AppServer --> Cache
    OracleDB --> Backup

    APIGateway --> IAM
    AppServer --> Audit
    OracleDB --> Encrypt
```

---

## 4. MODULE ARCHITECTURE

The UCMS comprises 10 core modules as defined in the tender requirements:

### 4.1 Module Interaction Diagram

```mermaid
graph LR
    subgraph "UCMS Core Modules"
        M1[Module 1:<br/>User Management]
        M2[Module 2:<br/>Claims Registration]
        M3[Module 3:<br/>Document Management]
        M4[Module 4:<br/>Workflow Engine]
        M5[Module 5:<br/>Assessment & Approval]
        M6[Module 6:<br/>Payment Processing]
        M7[Module 7:<br/>Reporting & Analytics]
        M8[Module 8:<br/>Audit & Compliance]
        M9[Module 9:<br/>Master Data Management]
        M10[Module 10:<br/>System Administration]
    end

    M1 --> M2
    M2 --> M3
    M2 --> M4
    M3 --> M4
    M4 --> M5
    M5 --> M6
    M5 --> M7
    M6 --> M7
    M8 -.-> M1
    M8 -.-> M2
    M8 -.-> M3
    M8 -.-> M4
    M8 -.-> M5
    M8 -.-> M6
    M9 -.-> M2
    M9 -.-> M5
    M9 -.-> M6
    M10 -.-> M1
    M10 -.-> M9
```

### 4.2 Module Descriptions

| Module | Name | Primary Function | Integration Points |
|--------|------|------------------|-------------------|
| M1 | User Management | Role-based access control, user provisioning | IAM, Active Directory |
| M2 | Claims Registration | Claim submission, validation, categorization | CIMS, MyUSP |
| M3 | Document Management | Document upload, OCR processing, storage | OCR Engine, DocStore |
| M4 | Workflow Engine | Process orchestration, routing, notifications | BPMN, Email Gateway |
| M5 | Assessment & Approval | Evaluation workflows, approval hierarchies | Rule Engine, Finance |
| M6 | Payment Processing | Payment calculation, disbursement tracking | Banking APIs, Finance |
| M7 | Reporting & Analytics | Dashboards, KPIs, statutory reports | Oracle BI, Data Warehouse |
| M8 | Audit & Compliance | Logging, trail maintenance, compliance checks | Audit DB, SIEM |
| M9 | Master Data Management | Reference data, lookup tables, configurations | Golden Record |
| M10 | System Administration | Configuration, monitoring, maintenance | OCI Console |

---

## 5. TECHNICAL SPECIFICATIONS

### 5.1 Infrastructure Requirements

| Component | Specification | Quantity |
|-----------|---------------|----------|
| Application Servers | Oracle WebLogic 14c, 16 CPU, 64GB RAM | 2 (HA Pair) |
| Database Servers | Oracle DB 19c Enterprise, 32 CPU, 128GB RAM | 2 (Primary/Standby) |
| RPA Servers | UiPath Server, 8 CPU, 32GB RAM | 2 |
| Load Balancer | Oracle Cloud Load Balancer | 2 (Active/Active) |
| Storage | Oracle Cloud Block Storage, 10TB SSD | As required |

### 5.2 Security Architecture

```mermaid
graph TD
    subgraph "Perimeter Security"
        WAF[Web Application Firewall]
        DDoS[DDoS Protection]
        CDN[Content Delivery Network]
    end

    subgraph "Network Security"
        VLAN[VLAN Segmentation]
        ACL[Access Control Lists]
        VPN[VPN Gateway]
    end

    subgraph "Application Security"
        Auth[Multi-Factor Authentication]
        RBAC[Role-Based Access Control]
        InputVal[Input Validation]
    end

    subgraph "Data Security"
        TDE[Transparent Data Encryption]
        ColEncrypt[Column-Level Encryption]
        BackupEncrypt[Backup Encryption]
    end

    Internet --> WAF
    WAF --> DDoS
    DDoS --> CDN
    CDN --> VLAN
    VLAN --> ACL
    ACL --> VPN
    VPN --> Auth
    Auth --> RBAC
    RBAC --> InputVal
    InputVal --> TDE
    TDE --> ColEncrypt
    ColEncrypt --> BackupEncrypt
```

---

## 6. DEPLOYMENT ARCHITECTURE

### 6.1 High Availability Design

```mermaid
graph TB
    subgraph "Primary Data Center"
        LB1[Load Balancer]
        APP1[App Server 1]
        APP2[App Server 2]
        DB1[(Primary DB)]
    end

    subgraph "DR Data Center"
        LB2[DR Load Balancer]
        APP3[DR App Server]
        DB2[(Standby DB)]
    end

    Users -->|Active| LB1
    Users -.->|Failover| LB2
    LB1 --> APP1
    LB1 --> APP2
    APP1 --> DB1
    APP2 --> DB1
    DB1 -.->|Data Guard| DB2
    LB2 --> APP3
    APP3 --> DB2
```

---

## 7. COMPLIANCE MAPPING

| Requirement ID | Description | Architecture Component | SDS Reference |
|----------------|-------------|------------------------|---------------|
| URS-ARCH-001 | Multi-tier architecture | All layers | SDS-2.1 |
| URS-ARCH-002 | High availability | DR configuration | SDS-2.4 |
| URS-ARCH-003 | Scalability | OCI Auto-scaling | SDS-2.5 |
| URS-SEC-001 | Encryption at rest | TDE, Column encryption | SDS-3.1 |
| URS-SEC-002 | Encryption in transit | TLS 1.3 | SDS-3.2 |
| URS-INT-001 | CIMS integration | API Gateway | SDS-4.1 |
| URS-INT-002 | MyUSP integration | REST API | SDS-4.2 |

---

## 8. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | January 2025 | Technical Team | Initial version |

---

**END OF ANNEX T1**
