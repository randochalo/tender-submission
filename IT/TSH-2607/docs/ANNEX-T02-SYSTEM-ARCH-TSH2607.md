# ANNEX T2: DETAILED SYSTEM ARCHITECTURE
## TSH-2607: Universal Service Provision (USP) Claims Management System (UCMS)
**Document Reference:** ANNEX-T02-SYSTEM-ARCH-TSH2607.md  
**Version:** 1.0  
**Date:** January 2025  
**Classification:** Technical Annexure

---

## 1. INTRODUCTION

This annexure provides detailed system architecture specifications for the USP Claims Management System (UCMS). It elaborates on the technical components, integration patterns, and deployment strategies that underpin the solution.

**Cross-References:**
- URS Section 4: Technical Requirements
- BRS Section 3: Business Process Architecture
- SRS Section 5-7: System Design Specifications
- SDS Section 2: Solution Architecture

---

## 2. TECHNICAL ARCHITECTURE FRAMEWORK

### 2.1 Architecture Principles

| Principle | Description | Implementation |
|-----------|-------------|----------------|
| **Modularity** | Independent, interchangeable modules | 10 discrete modules with API interfaces |
| **Scalability** | Horizontal and vertical scaling capability | OCI auto-scaling, load balancing |
| **Security** | Defense in depth strategy | Multi-layer security controls |
| **Interoperability** | Seamless integration with external systems | Standard APIs, message queues |
| **Resilience** | Fault tolerance and disaster recovery | HA configuration, automated failover |
| **Maintainability** | Easy updates and maintenance | Microservices pattern, containerization |

### 2.2 Technology Stack Matrix

| Layer | Primary Technology | Alternative/Supporting | Version |
|-------|-------------------|------------------------|---------|
| Database | Oracle Database | Oracle NoSQL | 19c/21c |
| Application Server | Oracle WebLogic | Oracle Helidon | 14c |
| Development | Oracle APEX | Java/Spring Boot | 23.2+ |
| RPA | UiPath Enterprise | - | 2023.10+ |
| OCR | Tesseract + Custom ML | OCR.space API | 5.3+ |
| Digital Signature | Adobe Sign API | Docusign API | REST API v6 |
| Reporting | Oracle Analytics Cloud | Oracle BI Publisher | 2024 |
| Integration | Oracle Integration Cloud | Apache Camel | 3.x |
| Caching | Redis Enterprise | Oracle Coherence | 7.x |
| Message Queue | Oracle AQ | Apache Kafka | 21c |

---

## 3. COMPONENT ARCHITECTURE

### 3.1 Database Architecture

```mermaid
graph TB
    subgraph "Oracle Database Cluster"
        subgraph "Primary Instance"
            PDB1[(Pluggable DB:<br/>UCMS_PROD)]
            PDB2[(Pluggable DB:<br/>UCMS_AUDIT)]
            PDB3[(Pluggable DB:<br/>UCMS_REPORT)]
        end

        subgraph "Standby Instance"
            SPDB1[(Standby:<br/>UCMS_PROD_DR)]
            SPDB2[(Standby:<br/>UCMS_AUDIT_DR)]
        end

        subgraph "Database Services"
            SVC1[Connection Pool<br/>UCMS_APP_SVC]
            SVC2[Read Replica<br/>UCMS_REPORT_SVC]
            SVC3[Audit Stream<br/>UCMS_AUDIT_SVC]
        end
    end

    subgraph "Data Guard"
        DG[Oracle Data Guard<br/>Maximum Availability]
    end

    PDB1 -->|Sync Replication| SPDB1
    PDB2 -->|Async Replication| SPDB2
    PDB1 --> SVC1
    PDB3 --> SVC2
    PDB2 --> SVC3
```

### 3.2 Database Schema Design

| Schema | Purpose | Key Tables | Estimated Volume |
|--------|---------|------------|------------------|
| **UCMS_CORE** | Core application data | CLAIMS, CLAIMANTS, PAYMENTS | 10M+ records |
| **UCMS_DOC** | Document metadata | DOCUMENTS, ATTACHMENTS, VERSIONS | 5M+ records |
| **UCMS_WF** | Workflow data | WORKFLOWS, TASKS, APPROVALS | 50M+ records |
| **UCMS_AUDIT** | Audit trails | AUDIT_LOG, ACCESS_LOG, CHANGES | 100M+ records |
| **UCMS_MDM** | Master data | LOOKUPS, CONFIGURATIONS, TAXONOMY | 100K+ records |
| **UCMS_INT** | Integration data | API_LOGS, MESSAGE_QUEUE, ERRORS | 25M+ records |

### 3.3 Application Server Architecture

```mermaid
graph LR
    subgraph "WebLogic Cluster"
        ADM[Admin Server]
        
        subgraph "Managed Servers"
            MS1[MS-1<br/>UCMS-Core]
            MS2[MS-2<br/>UCMS-Core]
            MS3[MS-3<br/>UCMS-API]
            MS4[MS-4<br/>UCMS-Batch]
        end

        subgraph "Clusters"
            C1[UCMS_Cluster_1<br/>Port: 8001-8002]
            C2[UCMS_Cluster_2<br/>Port: 8003-8004]
        end
    end

    subgraph "Node Managers"
        NM1[Node Manager 1]
        NM2[Node Manager 2]
    end

    ADM --> MS1
    ADM --> MS2
    ADM --> MS3
    ADM --> MS4
    MS1 --> C1
    MS2 --> C1
    MS3 --> C2
    MS4 --> C2
    NM1 --> MS1
    NM1 --> MS3
    NM2 --> MS2
    NM2 --> MS4
```

---

## 4. INTEGRATION ARCHITECTURE

### 4.1 Integration Patterns

```mermaid
graph TB
    subgraph "Synchronous Integration"
        REST[REST APIs<br/>Real-time queries]
        SOAP[SOAP Services<br/>Legacy systems]
        GRAPH[GraphQL<br/>Flexible queries]
    end

    subgraph "Asynchronous Integration"
        AQ[Oracle AQ<br/>Message Queuing]
        EVENT[Event Streaming<br/>Change Data Capture]
        FILE[File Transfer<br/>Batch processing]
    end

    subgraph "External Systems"
        CIMS[CIMS<br/>SOAP/XML]
        MYUSP[MyUSP<br/>REST/JSON]
        BANK[Bank APIs<br/>REST/SOAP]
        EMAIL[Email/SMS<br/>SMTP/API]
    end

    UCMS[UCMS Application] --> REST
    UCMS --> SOAP
    UCMS --> GRAPH
    UCMS --> AQ
    UCMS --> EVENT
    UCMS --> FILE

    REST --> MYUSP
    SOAP --> CIMS
    AQ --> BANK
    FILE --> EMAIL
```

### 4.2 API Gateway Architecture

| API Category | Protocol | Authentication | Rate Limit |
|--------------|----------|----------------|------------|
| Public APIs | REST/HTTPS | OAuth 2.0 + API Key | 1000/hour |
| Partner APIs | REST/HTTPS | mTLS + OAuth 2.0 | 10000/hour |
| Internal APIs | REST/HTTPS | JWT + IP Whitelist | Unlimited |
| Legacy APIs | SOAP/HTTPS | Basic Auth + IP | 5000/hour |

### 4.3 CIMS Integration Details

```mermaid
sequenceDiagram
    participant UCMS as UCMS Application
    participant API as API Gateway
    participant CIMS as CIMS System
    participant Cache as Redis Cache

    UCMS->>API: Request Company Info (Reg No)
    API->>Cache: Check cache first
    alt Cache Hit
        Cache-->>API: Return cached data
        API-->>UCMS: Company details
    else Cache Miss
        API->>CIMS: SOAP: GetCompanyDetails
        CIMS-->>API: XML Response
        API->>Cache: Store in cache (TTL: 1 hour)
        API-->>UCMS: Company details (JSON)
    end
```

---

## 5. SECURITY ARCHITECTURE

### 5.1 Authentication & Authorization Flow

```mermaid
graph LR
    subgraph "Identity Management"
        IDP[Identity Provider<br/>Oracle IAM/AD]
        MFA[MFA Service<br/>SMS/Email/App]
        LDAP[LDAP Directory]
    end

    subgraph "Authorization"
        RBAC[RBAC Engine]
        ABAC[ABAC Engine]
        POLICY[Policy Manager]
    end

    subgraph "Access Control"
        GATE[API Gateway]
        APP[Application]
        RES[Resources]
    end

    User -->|1. Login| IDP
    IDP -->|2. Challenge| MFA
    MFA -->|3. Verify| IDP
    IDP -->|4. Token| GATE
    GATE -->|5. Validate| RBAC
    RBAC -->|6. Check| ABAC
    ABAC -->|7. Decision| GATE
    GATE -->|8. Access| APP
    APP -->|9. Authorize| RES
```

### 5.2 Data Security Controls

| Data State | Control Mechanism | Implementation |
|------------|-------------------|----------------|
| **At Rest** | Transparent Data Encryption (TDE) | Oracle TDE with AES-256 |
| **At Rest** | Column-Level Encryption | Sensitive PII fields |
| **In Transit** | TLS Encryption | TLS 1.3 mandatory |
| **In Transit** | Certificate Pinning | Mobile applications |
| **In Use** | Memory Encryption | Secure enclaves where available |
| **Backup** | Backup Encryption | RMAN encryption |

---

## 6. PERFORMANCE ARCHITECTURE

### 6.1 Caching Strategy

```mermaid
graph TB
    subgraph "Multi-Layer Caching"
        L1[Browser Cache<br/>Static Assets]
        L2[CDN Cache<br/>Global Distribution]
        L3[Application Cache<br/>Redis Cluster]
        L4[Database Cache<br/>Result Cache/Buffer]
    end

    subgraph "Cache Types"
        SESSION[Session Cache<br/>User sessions]
        QUERY[Query Cache<br/>Frequent queries]
        OBJECT[Object Cache<br/>Reference data]
        PAGE[Page Cache<br/>Static content]
    end

    Client --> L1
    L1 --> L2
    L2 --> L3
    L3 --> L4
    L4 --> DB[(Oracle DB)]

    L3 --> SESSION
    L3 --> QUERY
    L3 --> OBJECT
    L2 --> PAGE
```

### 6.2 Performance Targets

| Metric | Target | Measurement |
|--------|--------|-------------|
| Page Load Time | < 3 seconds | 95th percentile |
| API Response Time | < 500ms | Average |
| Database Query | < 100ms | Simple queries |
| Report Generation | < 30 seconds | Complex reports |
| Concurrent Users | 10,000+ | Simultaneous |
| Throughput | 1000 TPS | Peak load |

---

## 7. DISASTER RECOVERY ARCHITECTURE

### 7.1 DR Topology

```mermaid
graph TB
    subgraph "Production Site"
        PROD_LB[Load Balancer]
        PROD_APP[Application Servers]
        PROD_DB[(Primary DB<br/>RAC)]
    end

    subgraph "DR Site"
        DR_LB[DR Load Balancer]
        DR_APP[DR App Servers<br/>Standby]
        DR_DB[(Standby DB<br/>Active Data Guard)]
    end

    subgraph "Data Replication"
        SYNC[Sync Replication<br/>0 RPO]
        ASYNC[Async Replication<br/>< 5 min RPO]
    end

    PROD_DB -->|Redo Transport| SYNC
    SYNC -->|Apply| DR_DB
    PROD_APP -.->|Config Sync| ASYNC
    ASYNC -.->|Apply| DR_APP

    PROD_LB -.->|Health Check| DR_LB
```

### 7.2 Recovery Objectives

| Component | RTO | RPO | Strategy |
|-----------|-----|-----|----------|
| Database | 1 hour | 0 (Sync) | Active Data Guard |
| Application | 2 hours | 5 minutes | Warm standby |
| Documents | 4 hours | 15 minutes | Cross-region replication |
| Configuration | 30 minutes | 0 | GitOps, automated deployment |

---

## 8. MONITORING & OBSERVABILITY

### 8.1 Monitoring Stack

```mermaid
graph TB
    subgraph "Data Collection"
        METRICS[Metrics<br/>Prometheus/OCI]
        LOGS[Logs<br/>ELK/OCI Logging]
        TRACES[Traces<br/>Jaeger/Zipkin]
        APM[APM<br/>Oracle APM]
    end

    subgraph "Analysis"
        DASH[Dashboards<br/>Grafana/OCI]
        ALERT[Alerting<br/>PagerDuty/OCI]
        ANOMALY[Anomaly Detection<br/>ML-based]
    end

    subgraph "Response"
        AUTO[Auto-Remediation<br/>Runbooks]
        INCIDENT[Incident Management<br/>ServiceNow]
        REPORT[Reporting<br/>Scheduled Reports]
    end

    METRICS --> DASH
    LOGS --> DASH
    TRACES --> DASH
    APM --> DASH
    DASH --> ALERT
    ALERT --> ANOMALY
    ANOMALY --> AUTO
    AUTO --> INCIDENT
    INCIDENT --> REPORT
```

---

## 9. COMPLIANCE & GOVERNANCE

| Standard | Requirement | Implementation |
|----------|-------------|----------------|
| **PDPA** | Personal data protection | Encryption, access controls, audit |
| **ISO 27001** | Information security | ISMS implementation |
| **OWASP** | Application security | Top 10 mitigation |
| **MS ISO** | Malaysian standards | Compliance certification |
| **Audit** | Audit trail | Immutable logs, 7-year retention |

---

## 10. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | January 2025 | Technical Team | Initial version |

---

**END OF ANNEX T2**
