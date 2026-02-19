# DOCUMENT 11: TECHNICAL CATALOGUES AND BROCHURES

## TSH-2607: USP Claims Management System (UCMS)
### Tender Reference: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

---

## TABLE OF CONTENTS

1. [Product Overview](#1-product-overview)
2. [Oracle Database Enterprise Edition](#2-oracle-database-enterprise-edition)
3. [Oracle WebLogic Server](#3-oracle-weblogic-server)
4. [Oracle Business Intelligence](#4-oracle-business-intelligence)
5. [Digital Signature Solutions](#5-digital-signature-solutions)
6. [RPA Platform](#6-rpa-platform)
7. [OCR & Document Processing](#7-ocr--document-processing)
8. [AI/ML Framework](#8-ai--ml-framework)
9. [Security & Authentication](#9-security--authentication)
10. [Integration Capabilities](#10-integration-capabilities)

---

## 1. PRODUCT OVERVIEW

### 1.1 UCMS Technology Stack

Our proposed UCMS solution leverages industry-leading technologies that are proven, scalable, and enterprise-ready:

```
┌─────────────────────────────────────────────────────────────┐
│  UCMS TECHNOLOGY STACK                                       │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  PRESENTATION TIER                                           │
│  ├── React.js 18+ (Frontend Framework)                      │
│  ├── Material-UI (Component Library)                        │
│  ├── PWA Capabilities (Mobile Access)                       │
│  └── Responsive Design (All Devices)                        │
│                                                              │
│  APPLICATION TIER                                            │
│  ├── Oracle WebLogic 14c (Application Server)               │
│  ├── Oracle SOA Suite (Integration)                         │
│  ├── REST APIs (OpenAPI 3.0)                                │
│  └── Microservices Architecture                             │
│                                                              │
│  DATA TIER                                                   │
│  ├── Oracle Database 19c (Primary Database)                 │
│  ├── Oracle Partitioning (Performance)                      │
│  └── Advanced Security (Encryption)                         │
│                                                              │
│  INTELLIGENCE TIER                                         │
│  ├── Oracle Analytics Cloud (Reporting)                     │
│  ├── TensorFlow (AI/ML Models)                              │
│  └── RPA Engine (Automation)                                │
│                                                              │
│  SECURITY & INTEGRATION                                      │
│  ├── Azure AD (Authentication)                              │
│  ├── MSC TrustSign (Digital Signatures)                     │
│  └── USPFS APIs (Integration)                               │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

### 1.2 Key Features Summary

| Category | Features |
|----------|----------|
| **Scalability** | Horizontal scaling, load balancing, high availability |
| **Security** | End-to-end encryption, MFA, RBAC, audit logging |
| **Integration** | REST APIs, SOAP, message queues, file-based |
| **Intelligence** | AI/ML models, predictive analytics, RPA automation |
| **Accessibility** | Web, mobile PWA, 24/7 availability |
| **Compliance** | KRISA, PDPA, audit-ready architecture |

---

## 2. ORACLE DATABASE ENTERPRISE EDITION

### 2.1 Product Description

Oracle Database 19c Enterprise Edition provides a secure, scalable, and reliable database platform for mission-critical applications. It forms the foundation of our UCMS data layer.

### 2.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Real Application Clusters (RAC)** | Database clustering for high availability | 99.9% uptime guarantee |
| **Partitioning** | Table partitioning for large datasets | Performance optimization for claims data |
| **Advanced Compression** | Data compression for storage efficiency | Cost reduction for document storage |
| **Advanced Security** | Transparent Data Encryption, Data Redaction | Protection of sensitive financial data |
| **Database Vault** | Separation of duties for DBAs | Enhanced security governance |
| **Audit Vault** | Centralized audit management | Comprehensive audit compliance |
| **Active Data Guard** | Disaster recovery and read scaling | Business continuity |

### 2.3 Technical Specifications

```yaml
Database Specifications:
  Version: Oracle Database 19c (19.3.0+)
  Edition: Enterprise Edition
  Platforms: Linux x86-64, Windows Server
  Maximum Database Size: 8 Exabytes
  Maximum Table Size: 128 Terabytes
  Concurrent Users: Unlimited (licensed)
  
Performance Features:
  - Automatic Memory Management
  - SQL Plan Management
  - Real-Time SQL Monitoring
  - In-Memory Column Store
  - Automatic Indexing
  
High Availability:
  - Real Application Clusters (RAC)
  - Automatic Storage Management (ASM)
  - Flashback Technology
  - Online Reorganization
  - Rolling Upgrades
```

### 2.4 UCMS Database Architecture

```
┌─────────────────────────────────────────┐
│         ORACLE RAC CLUSTER              │
│  ┌─────────────┐    ┌─────────────┐    │
│  │  NODE 1     │◄──►│  NODE 2     │    │
│  │ (Primary)   │    │ (Secondary) │    │
│  └──────┬──────┘    └──────┬──────┘    │
│         └────────┬─────────┘            │
│                  ▼                      │
│         ┌─────────────┐                 │
│         │  SHARED     │                 │
│         │  STORAGE    │                 │
│         │  (ASM)      │                 │
│         └─────────────┘                 │
└─────────────────────────────────────────┘
                   │
         ┌────────┴────────┐
         ▼                 ▼
┌─────────────────┐ ┌─────────────────┐
│  ACTIVE DATA    │ │  STANDBY SITE   │
│  GUARD (Local)  │ │  (DR Location)  │
└─────────────────┘ └─────────────────┘
```

---

## 3. ORACLE WEBLOGIC SERVER

### 3.1 Product Description

Oracle WebLogic Server 14c is a leading Java EE application server providing a robust, mature, and scalable platform for enterprise applications.

### 3.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Java EE 8 Support** | Full Java Enterprise Edition support | Modern application development |
| **Clustering** | Dynamic clustering and load balancing | Scalability for 250 users |
| **High Availability** | Automatic failover and session replication | Continuous service availability |
| **Security** | Integrated security framework | Authentication and authorization |
| **Diagnostics** | Comprehensive monitoring and diagnostics | Proactive issue resolution |

### 3.3 Technical Specifications

```yaml
WebLogic Specifications:
  Version: 14.1.1.0+
  Java Version: Java SE 11/17
  Deployment: On-premises or Cloud
  
Clustering Features:
  - Dynamic Clusters
  - Whole Server Migration
  - Service Migration
  - In-Memory Session Replication
  - JMS Clustering
  
Security Features:
  - SAML 2.0 Support
  - OAuth 2.0 Integration
  - SSL/TLS Encryption
  - Role-Based Access Control
```

---

## 4. ORACLE BUSINESS INTELLIGENCE

### 4.1 Product Description

Oracle Analytics Cloud (OAC) and Oracle Business Intelligence Enterprise Edition (OBIEE) provide comprehensive analytics and reporting capabilities.

### 4.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Interactive Dashboards** | Real-time visual analytics | Management dashboards |
| **Ad-hoc Querying** | Self-service reporting | User-generated reports |
| **Mobile Analytics** | Native mobile apps | Executive mobile access |
| **Advanced Analytics** | Embedded ML algorithms | Predictive analytics |
| **Data Visualization** | Rich chart types and maps | Financial performance views |

### 4.3 Report Types Supported

```yaml
Report Categories:
  Operational Reports:
    - Daily Claims Summary
    - Payment Status Reports
    - Exception Reports
    - User Activity Reports
    
  Financial Reports:
    - Budget Utilization
    - Payment Analysis
    - Variance Reports
    - Forecast Reports
    
  Management Reports:
    - Executive Dashboards
    - KPI Scorecards
    - Trend Analysis
    - Compliance Reports
```

---

## 5. DIGITAL SIGNATURE SOLUTIONS

### 5.1 MSC TrustSign

#### 5.1.1 Product Description

MSC TrustSign is a Malaysian-certified digital signature solution compliant with the Digital Signature Act 1997 and recognized by Malaysian law.

#### 5.1.2 Key Capabilities

| Feature | Description |
|---------|-------------|
| **Legal Compliance** | Fully compliant with Malaysian Digital Signature Act 1997 |
| **Non-Repudiation** | Cryptographic proof of signing |
| **Timestamping** | Trusted timestamp for audit purposes |
| **Multi-Level Signing** | Supports complex approval workflows |
| **Integration** | REST API for seamless integration |

#### 5.1.3 Technical Specifications

```yaml
MSC TrustSign Specifications:
  Standard: PKCS#11, PKCS#12
  Algorithms: RSA 2048/4096, SHA-256/384/512
  Certificates: X.509 v3
  Validation: OCSP, CRL
  Integration: REST API, SOAP, SDK
  
Security Features:
  - Hardware Security Module (HSM) backed
  - Multi-factor authentication
  - Biometric signature capture
  - Audit trail of all signing activities
```

### 5.2 DocuSign (Alternative/Supplementary)

#### 5.2.1 Product Description

DocuSign provides cloud-based electronic signature technology for facilitating electronic exchanges of signed documents.

#### 5.2.2 Key Capabilities

| Feature | Description |
|---------|-------------|
| **Global Recognition** | Accepted in 180+ countries |
| **Workflow Automation** | Automated routing and reminders |
| **Templates** | Pre-built document templates |
| **Mobile Signing** | Sign from any device |
| **Integration** | 350+ pre-built integrations |

---

## 6. RPA PLATFORM

### 6.1 UiPath Enterprise Platform

#### 6.1.1 Product Description

UiPath is a leading Robotic Process Automation platform enabling automation of repetitive business processes through software robots.

#### 6.1.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Attended Robots** | Human-triggered automation | User-assisted data entry |
| **Unattended Robots** | Fully automated processes | Background reconciliation |
| **AI Center** | ML model integration | Document classification |
| **Orchestrator** | Centralized robot management | Bot deployment and monitoring |
| **Process Mining** | Process discovery and optimization | Workflow optimization |

#### 6.1.3 UCMS Automation Use Cases

```yaml
RPA Use Cases in UCMS:
  Document Processing:
    - Invoice data extraction
    - Document classification
    - Duplicate detection
    - Validation checking
    
  Data Reconciliation:
    - USPFS data sync
    - Bank reconciliation
    - Inter-system validation
    
  Report Generation:
    - Automated report scheduling
    - Distribution to stakeholders
    - Exception alerting
    
  Workflow Support:
    - Approval reminders
    - Escalation handling
    - Status updates
```

---

## 7. OCR & DOCUMENT PROCESSING

### 7.1 AWS Textract

#### 7.1.1 Product Description

Amazon Textract is a machine learning service that automatically extracts text and data from scanned documents.

#### 7.1.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Text Extraction** | Printed and handwritten text | Invoice processing |
| **Form Extraction** | Key-value pair extraction | Form data capture |
| **Table Extraction** | Structured table data | Financial statement parsing |
| **Custom Queries** | Natural language queries | Flexible data extraction |

#### 7.1.3 Technical Specifications

```yaml
Textract Capabilities:
  Document Types:
    - PDF, TIFF, PNG, JPEG
    - Multi-page documents
    - Mixed content documents
    
  Extraction Features:
    - Optical Character Recognition (OCR)
    - Form data (key-value pairs)
    - Table structure preservation
    - Confidence scores
    
  Integration:
    - AWS SDK
    - REST API
    - Batch processing support
    - Real-time processing
```

### 7.2 Tesseract OCR (Supplementary)

Open-source OCR engine for on-premises document processing requirements.

---

## 8. AI/ML FRAMEWORK

### 8.1 TensorFlow Enterprise

#### 8.1.1 Product Description

TensorFlow is an end-to-end open-source platform for machine learning, providing comprehensive tools for building and deploying ML models.

#### 8.1.2 UCMS ML Applications

| Application | Description | Business Value |
|-------------|-------------|----------------|
| **Fraud Detection** | Anomaly detection for claims | Risk mitigation |
| **Document Classification** | Auto-categorization of uploads | Processing efficiency |
| **Predictive Analytics** | Budget forecasting | Better planning |
| **Pattern Recognition** | Duplicate claim detection | Fraud prevention |
| **Sentiment Analysis** | User feedback analysis | Service improvement |

#### 8.1.3 ML Model Architecture

```
┌─────────────────────────────────────────┐
│         ML PIPELINE                      │
├─────────────────────────────────────────┤
│                                          │
│  DATA INGESTION                          │
│  ├── Document Uploads                    │
│  ├── Historical Claims                   │
│  └── External Data Sources               │
│                                          │
│  PREPROCESSING                           │
│  ├── Text Extraction (OCR)               │
│  ├── Feature Engineering                 │
│  └── Normalization                       │
│                                          │
│  MODEL INFERENCE                         │
│  ├── Fraud Detection Model               │
│  ├── Classification Model                │
│  └── Prediction Model                    │
│                                          │
│  OUTPUT                                  │
│  ├── Risk Scores                         │
│  ├── Recommendations                     │
│  └── Alerts                              │
│                                          │
│  FEEDBACK LOOP                           │
│  └── Continuous Model Improvement        │
│                                          │
└─────────────────────────────────────────┘
```

---

## 9. SECURITY & AUTHENTICATION

### 9.1 Azure Active Directory

#### 9.1.1 Product Description

Microsoft Azure AD provides cloud-based identity and access management services for secure authentication and authorization.

#### 9.1.2 Key Capabilities

| Feature | Description | UCMS Application |
|---------|-------------|------------------|
| **Single Sign-On (SSO)** | One login for all applications | Seamless user experience |
| **Multi-Factor Authentication** | Additional security layer | Enhanced access security |
| **Conditional Access** | Risk-based access policies | Adaptive security |
| **Identity Protection** | Risk detection and remediation | Proactive threat mitigation |

#### 9.1.3 Security Architecture

```
┌─────────────────────────────────────────┐
│      AZURE AD INTEGRATION               │
├─────────────────────────────────────────┤
│                                          │
│  AUTHENTICATION FLOW                     │
│  ┌─────────┐    ┌─────────┐   ┌──────┐ │
│  │  User   │───►│ Azure AD│──►│ UCMS │ │
│  │ Request │    │  Auth   │   │ App  │ │
│  └─────────┘    └─────────┘   └──────┘ │
│                      │                   │
│                      ▼                   │
│              ┌─────────────┐             │
│              │  SAML/OAuth │             │
│              │   Token     │             │
│              └─────────────┘             │
│                                          │
│  AUTHORIZATION                           │
│  ├── Role-Based Access Control (RBAC)   │
│  ├── Group Membership Sync              │
│  └── Permission Inheritance             │
│                                          │
└─────────────────────────────────────────┘
```

---

## 10. INTEGRATION CAPABILITIES

### 10.1 Integration Architecture

| Integration Type | Technology | Use Case |
|------------------|------------|----------|
| **Real-time APIs** | REST/JSON | USPFS data sync |
| **Message Queue** | Oracle AQ | Asynchronous processing |
| **File Transfer** | SFTP | Batch document exchange |
| **Database Link** | Oracle DB Link | Direct data access |
| **Web Services** | SOAP | Legacy system integration |

### 10.2 API Specifications

```yaml
API Standards:
  Protocol: HTTPS
  Authentication: OAuth 2.0 / API Keys
  Format: JSON
  Documentation: OpenAPI 3.0 (Swagger)
  
API Categories:
  Master Data APIs:
    - Project Management
    - User Management
    - Budget Operations
    
  Claims APIs:
    - Claim Submission
    - Status Inquiry
    - Document Upload
    
  Payment APIs:
    - Payment Request
    - Status Update
    - Reconciliation
    
  Reporting APIs:
    - Report Generation
    - Dashboard Data
    - Analytics Queries
```

---

## APPENDIX: PRODUCT DATASHEETS

### A. Oracle Product Datasheets
- Oracle Database 19c Enterprise Edition
- Oracle WebLogic Server 14c
- Oracle Business Intelligence Enterprise Edition
- Oracle SOA Suite

### B. Digital Signature Datasheets
- MSC TrustSign Technical Specification
- DocuSign eSignature Platform

### C. RPA Platform Datasheets
- UiPath Enterprise Platform
- UiPath AI Center

### D. OCR/AI Datasheets
- AWS Textract Developer Guide
- TensorFlow Enterprise Documentation

### E. Security Datasheets
- Azure Active Directory Technical Documentation
- Oracle Advanced Security Options

---

**Note:** Detailed product datasheets and technical specifications are available upon request or can be downloaded from respective manufacturer websites.

---

*Document Version: 1.0*  
*Date: February 2026*
