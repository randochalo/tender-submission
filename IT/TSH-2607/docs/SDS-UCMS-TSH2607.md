# SOFTWARE DESIGN SPECIFICATION (SDS) / SYSTEM DESIGN DOCUMENT (SDD)

## UNIVERSAL SERVICE PROVISION (USP) CLAIMS MANAGEMENT SYSTEM (UCMS)

**Tender Reference:** TSH-2607 / MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

**Version:** 1.0

**Date:** February 2026

**Classification:** CONFIDENTIAL

---

## DOCUMENT CONTROL

### Version History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 0.1 | 15 Feb 2026 | Solution Architect | Initial Draft | - |
| 0.2 | 17 Feb 2026 | Technical Lead | Design Review | - |
| 0.3 | 18 Feb 2026 | Solution Architect | Final Updates | - |
| 1.0 | 18 Feb 2026 | Project Manager | Release | MCMC Representative |

---

## TABLE OF CONTENTS

1. [Introduction](#1-introduction)
2. [System Architecture](#2-system-architecture)
3. [Database Design](#3-database-design)
4. [Module Design](#4-module-design)
5. [Interface Design](#5-interface-design)
6. [Security Architecture](#6-security-architecture)
7. [Integration Architecture](#7-integration-architecture)
8. [AI/ML Component Design](#8-aiml-component-design)
9. [RPA Design](#9-rpa-design)
10. [Deployment Architecture](#10-deployment-architecture)
11. [Performance and Scalability Design](#11-performance-and-scalability-design)
12. [Disaster Recovery Design](#12-disaster-recovery-design)
13. [Appendices](#13-appendices)

---

## 1. INTRODUCTION

### 1.1 Purpose

This System Design Document (SDD) provides the comprehensive technical design for the Universal Service Provision (USP) Claims Management System (UCMS). It describes the system architecture, component design, data structures, interfaces, and deployment approach.

### 1.2 Scope

This document covers:
- System architecture and component design
- Database schema and data flow
- Module-level design specifications
- Security architecture
- Integration architecture
- AI/ML and RPA component design
- Deployment and infrastructure design

### 1.3 Reference Documents

- System Requirements Specification (SRS) - UCMS TSH-2607
- User Requirements Specification (URS) - UCMS TSH-2607
- Business Requirements Specification (BRS) - UCMS TSH-2607
- Tender Document: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

---

## 2. SYSTEM ARCHITECTURE

### 2.1 Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           UCMS SYSTEM ARCHITECTURE                           │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                              PRESENTATION LAYER                              │
├─────────────────────────────────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   Web App    │  │  Mobile Web  │  │    APIs      │  │   Admin      │    │
│  │   (React)    │  │  (Responsive)│  │  (REST)      │  │   Console    │    │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                             APPLICATION LAYER                                │
├─────────────────────────────────────────────────────────────────────────────┤
│  ┌────────────────────────────────────────────────────────────────────┐    │
│  │                        API Gateway (Kong/AWS)                       │    │
│  │                    Rate Limiting, Auth, Routing                     │    │
│  └────────────────────────────────────────────────────────────────────┘    │
│                                      │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐      │
│  │  Master  │  Claims  │  Budget  │ Payment  │  Report  │   User   │      │
│  │  Data    │  Mgmt    │  Mgmt    │  Mgmt    │  Engine  │  Mgmt    │      │
│  │Service   │Service   │Service   │Service   │Service   │Service   │      │
│  └──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘      │
│                                      │
│  ┌────────────────────────────────────────────────────────────────────┐    │
│  │                    Workflow Engine (Camunda)                        │    │
│  │              BPMN-based Approval and Business Processes             │    │
│  └────────────────────────────────────────────────────────────────────┘    │
│                                      │
│  ┌────────────────────────────────────────────────────────────────────┐    │
│  │                     AI/ML Service Layer                             │    │
│  │     Document Classification, OCR, Fraud Detection, Analytics        │    │
│  └────────────────────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                               DATA LAYER                                     │
├─────────────────────────────────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   Oracle     │  │    Redis     │  │Elasticsearch │  │    MinIO     │    │
│  │   Database   │  │    Cache     │  │    Search    │  │   Storage    │    │
│  │   (19c)      │  │              │  │              │  │  (S3-API)    │    │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           INTEGRATION LAYER                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐      │
│  │  USPFS   │  Azure   │  Digital │  Banking │   OCR    │   RPA    │      │
│  │ (Oracle  │    AD    │   Sig    │   API    │ Service  │  Engine  │      │
│  │  EBS)    │   SSO    │ Provider │          │          │          │      │
│  └──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘      │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Component Architecture

#### 2.2.1 Frontend Components

```
Frontend Architecture (React + TypeScript)
│
├── src/
│   ├── components/           # Reusable UI components
│   │   ├── common/          # Buttons, Inputs, Tables
│   │   ├── layout/          # Header, Sidebar, Footer
│   │   ├── forms/           # Form components
│   │   └── charts/          # Data visualization
│   │
│   ├── modules/             # Feature modules
│   │   ├── master-data/     # Master Data module
│   │   ├── claims/          # Claims module
│   │   ├── budget/          # Budget module
│   │   ├── payment/         # Payment module
│   │   ├── reports/         # Reports module
│   │   └── admin/           # Admin module
│   │
│   ├── services/            # API services
│   ├── store/               # Redux state management
│   ├── utils/               # Utility functions
│   └── i18n/                # Internationalization (BM/EN)
│
├── public/                  # Static assets
└── tests/                   # Test suites
```

#### 2.2.2 Backend Components

```
Backend Architecture (Microservices)
│
├── api-gateway/             # Kong API Gateway
│   ├── config/
│   ├── plugins/
│   └── routes/
│
├── services/                # Business microservices
│   ├── master-data-service/     # Master Data Management
│   ├── claims-service/          # Claims Processing
│   ├── budget-service/          # Budget Management
│   ├── payment-service/         # Payment Processing
│   ├── report-service/          # Reporting Engine
│   ├── user-service/            # User Management
│   ├── notification-service/    # Notifications
│   └── workflow-service/        # Workflow Engine
│
├── ai-ml-services/          # AI/ML microservices
│   ├── document-classifier/     # Document classification
│   ├── ocr-service/             # OCR processing
│   ├── fraud-detector/          # Fraud detection
│   └── analytics-engine/        # Predictive analytics
│
├── shared/                  # Shared libraries
│   ├── common/              # Common utilities
│   ├── models/              # Data models
│   ├── security/            # Security utilities
│   └── integrations/        # Integration clients
│
└── infrastructure/          # Infrastructure code
    ├── docker/
    ├── k8s/
    └── terraform/
```

### 2.3 Technology Stack Details

| Layer | Technology | Version | Purpose |
|-------|------------|---------|---------|
| Frontend | React | 18.x | UI framework |
| Frontend | TypeScript | 5.x | Type safety |
| Frontend | Redux Toolkit | 2.x | State management |
| Frontend | Material-UI | 5.x | Component library |
| Frontend | Recharts | 2.x | Data visualization |
| Backend | Node.js | 20.x | Runtime |
| Backend | Express | 4.x | Web framework |
| Backend | TypeORM | 0.3.x | ORM |
| Database | Oracle | 19c | Primary database |
| Cache | Redis | 7.x | Caching/Sessions |
| Search | Elasticsearch | 8.x | Search engine |
| Storage | MinIO | Latest | Object storage |
| Message Queue | RabbitMQ | 3.12.x | Async messaging |
| Workflow | Camunda | 8.x | BPMN engine |
| AI/ML | Python | 3.11 | ML services |
| AI/ML | TensorFlow | 2.x | Deep learning |
| OCR | Tesseract | 5.x | Text extraction |
| Container | Docker | 24.x | Containerization |
| Orchestration | Kubernetes | 1.28.x | Container orchestration |
| API Gateway | Kong | 3.x | API management |
| Monitoring | Prometheus/Grafana | Latest | Observability |

---

## 3. DATABASE DESIGN

### 3.1 Entity Relationship Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      DATABASE ENTITY RELATIONSHIP DIAGRAM                    │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────┐         ┌─────────────────┐         ┌─────────────────┐
│   mcmc_users    │         │  organizations  │         │   projects      │
├─────────────────┤         ├─────────────────┤         ├─────────────────┤
│ PK user_id      │────┐    │ PK org_id       │◀────┐   │ PK project_id   │
│    username     │    │    │    org_type     │     │   │    project_name │
│    email        │    │    │    reg_number   │     │   │    description  │
│    org_id (FK)  │────┘    │    org_name     │     └──▶│    org_id (FK)  │
│    role_id (FK) │         │    status       │         │    status       │
└─────────────────┘         └─────────────────┘         └─────────────────┘
         │                                                        │
         │                                                        │
         ▼                                                        ▼
┌─────────────────┐         ┌─────────────────┐         ┌─────────────────┐
│     roles       │         │      noas       │         │    clusters     │
├─────────────────┤         ├─────────────────┤         ├─────────────────┤
│ PK role_id      │         │ PK noa_id       │         │ PK cluster_id   │
│    role_name    │         │ FK project_id   │────────▶│ FK project_id   │
│    permissions  │         │    noa_ref      │         │    cluster_name │
└─────────────────┘         │    contract_val │         └─────────────────┘
                            │    start_date   │                  │
                            │    end_date     │                  │
                            └─────────────────┘                  │
                                                                  │
┌─────────────────┐         ┌─────────────────┐                   │
│  claims         │         │   sites         │◀──────────────────┘
├─────────────────┤         ├─────────────────┤
│ PK claim_id     │         │ PK site_id      │
│ FK project_id   │◀────────│ FK cluster_id   │
│ FK site_id      │────────▶│    site_name    │
│ FK submitted_by │         │    location     │
│    claim_type   │         │    coordinates  │
│    amount       │         └─────────────────┘
│    status       │
│    submission_dt│         ┌─────────────────┐
└─────────────────┘         │  claim_documents│
         │                  ├─────────────────┤
         │                  │ PK doc_id       │
         └─────────────────▶│ FK claim_id     │
                            │    doc_type     │
                            │    file_path    │
                            │    ocr_text     │
                            └─────────────────┘

┌─────────────────┐         ┌─────────────────┐         ┌─────────────────┐
│   budgets       │         │    payments     │         │  audit_logs     │
├─────────────────┤         ├─────────────────┤         ├─────────────────┤
│ PK budget_id    │         │ PK payment_id   │         │ PK log_id       │
│ FK project_id   │         │ FK claim_id     │         │    user_id      │
│    total_budget │         │    amount       │         │    action       │
│    utilized     │         │    payment_date │         │    timestamp    │
│    available    │         │    voucher_ref  │         │    ip_address   │
└─────────────────┘         │    status       │         │    details      │
                            └─────────────────┘         └─────────────────┘
```

### 3.2 Table Specifications

#### 3.2.1 Projects Table

```sql
CREATE TABLE projects (
    project_id VARCHAR2(15) PRIMARY KEY,
    project_name VARCHAR2(255) NOT NULL,
    description CLOB,
    org_id VARCHAR2(20) NOT NULL REFERENCES organizations(org_id),
    status VARCHAR2(20) DEFAULT 'ACTIVE' 
        CHECK (status IN ('ACTIVE', 'COMPLETED', 'CANCELLED', 'ON_HOLD')),
    start_date DATE,
    planned_end_date DATE,
    actual_end_date DATE,
    total_budget NUMBER(15,2),
    created_by VARCHAR2(100) NOT NULL,
    created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP NOT NULL,
    modified_by VARCHAR2(100),
    modified_date TIMESTAMP,
    version NUMBER DEFAULT 1,
    CONSTRAINT chk_project_dates CHECK (planned_end_date >= start_date)
) TABLESPACE ucms_data
PARTITION BY RANGE (created_date) (
    PARTITION p2026 VALUES LESS THAN (TO_DATE('2027-01-01', 'YYYY-MM-DD')),
    PARTITION p2027 VALUES LESS THAN (TO_DATE('2028-01-01', 'YYYY-MM-DD')),
    PARTITION p2028 VALUES LESS THAN (TO_DATE('2029-01-01', 'YYYY-MM-DD')),
    PARTITION pmax VALUES LESS THAN (MAXVALUE)
);

-- Indexes
CREATE INDEX idx_projects_org ON projects(org_id);
CREATE INDEX idx_projects_status ON projects(status);
CREATE INDEX idx_projects_dates ON projects(start_date, planned_end_date);
```

#### 3.2.2 Claims Table

```sql
CREATE TABLE claims (
    claim_id VARCHAR2(20) PRIMARY KEY,
    project_id VARCHAR2(15) NOT NULL REFERENCES projects(project_id),
    site_id VARCHAR2(20) REFERENCES sites(site_id),
    claim_type VARCHAR2(30) NOT NULL 
        CHECK (claim_type IN ('ADVANCE', 'QUARTERLY', 'MAJOR_CONTRIBUTOR', 'YEARLY')),
    claim_period_start DATE,
    claim_period_end DATE,
    claim_amount NUMBER(15,2) NOT NULL,
    claim_status VARCHAR2(30) DEFAULT 'DRAFT'
        CHECK (claim_status IN ('DRAFT', 'SUBMITTED', 'UNDER_REVIEW', 
                                'ADDITIONAL_INFO_REQUIRED', 'VERIFIED', 
                                'APPROVED', 'REJECTED', 'PAYMENT_PROCESSING', 
                                'PAID', 'CLOSED')),
    submitted_by VARCHAR2(100) REFERENCES mcmc_users(user_id),
    submission_date TIMESTAMP,
    verified_by VARCHAR2(100) REFERENCES mcmc_users(user_id),
    verification_date TIMESTAMP,
    approved_by VARCHAR2(100) REFERENCES mcmc_users(user_id),
    approval_date TIMESTAMP,
    rejection_reason CLOB,
    payment_id VARCHAR2(20) REFERENCES payments(payment_id),
    created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP NOT NULL,
    modified_date TIMESTAMP,
    CONSTRAINT chk_claim_amount CHECK (claim_amount > 0),
    CONSTRAINT chk_claim_period CHECK (claim_period_end >= claim_period_start)
) TABLESPACE ucms_data
PARTITION BY RANGE (submission_date) INTERVAL (NUMTOYMINTERVAL(1, 'MONTH')) (
    PARTITION p202601 VALUES LESS THAN (TO_DATE('2026-02-01', 'YYYY-MM-DD'))
);

-- Indexes
CREATE INDEX idx_claims_project ON claims(project_id);
CREATE INDEX idx_claims_status ON claims(claim_status);
CREATE INDEX idx_claims_dates ON claims(submission_date);
CREATE INDEX idx_claims_type ON claims(claim_type);
CREATE INDEX idx_claims_submitter ON claims(submitted_by);
```

#### 3.2.3 Audit Logs Table

```sql
CREATE TABLE audit_logs (
    log_id NUMBER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    user_id VARCHAR2(100),
    user_type VARCHAR2(20) CHECK (user_type IN ('INTERNAL', 'EXTERNAL', 'SYSTEM')),
    action VARCHAR2(50) NOT NULL,
    resource_type VARCHAR2(50) NOT NULL,
    resource_id VARCHAR2(50),
    action_details CLOB,
    before_value CLOB,
    after_value CLOB,
    ip_address VARCHAR2(45),
    user_agent VARCHAR2(500),
    session_id VARCHAR2(100),
    result VARCHAR2(20) CHECK (result IN ('SUCCESS', 'FAILURE', 'WARNING')),
    error_message VARCHAR2(4000),
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP NOT NULL,
    hash_value VARCHAR2(64)  -- For tamper detection
) TABLESPACE ucms_audit
PARTITION BY RANGE (timestamp) INTERVAL (NUMTOYMINTERVAL(1, 'MONTH')) (
    PARTITION p202601 VALUES LESS THAN (TO_DATE('2026-02-01', 'YYYY-MM-DD'))
);

-- Indexes
CREATE INDEX idx_audit_user ON audit_logs(user_id);
CREATE INDEX idx_audit_action ON audit_logs(action);
CREATE INDEX idx_audit_resource ON audit_logs(resource_type, resource_id);
CREATE INDEX idx_audit_timestamp ON audit_logs(timestamp);
```

### 3.3 Data Flow Diagrams

#### 3.3.1 Claim Submission Data Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     CLAIM SUBMISSION DATA FLOW                               │
└─────────────────────────────────────────────────────────────────────────────┘

DUSP User
    │
    │ 1. Submit Claim
    ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   Web Frontend  │────▶│  Claims Service │────▶│  API Gateway    │
│   (React)       │     │  (Validation)   │     │  (Auth/Rate)    │
└─────────────────┘     └─────────────────┘     └────────┬────────┘
                                                         │
                                    ┌────────────────────┼────────────────────┐
                                    │                    │                    │
                                    ▼                    ▼                    ▼
                              ┌──────────┐       ┌──────────┐       ┌──────────┐
                              │  Oracle  │       │  Redis   │       │RabbitMQ  │
                              │ Database │       │  Cache   │       │  Queue   │
                              └──────────┘       └──────────┘       └────┬─────┘
                                                                          │
                                                                          ▼
                                                                   ┌──────────┐
                                                                   │OCR/AI-ML │
                                                                   │ Service  │
                                                                   └──────────┘
```

---

## 4. MODULE DESIGN

### 4.1 Master Data Module Design

#### 4.1.1 Component Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        MASTER DATA MODULE                                    │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         MasterDataController                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐       │
│  │  create()   │  │   get()     │  │  update()   │  │  delete()   │       │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘       │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                    ┌─────────────────┼─────────────────┐
                    │                 │                 │
                    ▼                 ▼                 ▼
         ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
         │  ProjectService │ │   NOAService    │ │   BondService   │
         ├─────────────────┤ ├─────────────────┤ ├─────────────────┤
         │ +createProject()│ │ +createNOA()    │ │ +createBond()   │
         │ +getProject()   │ │ +getNOA()       │ │ +getBond()      │
         │ +updateProject()│ │ +updateNOA()    │ │ +updateBond()   │
         │ +deleteProject()│ │ +amendNOA()     │ │ +extendBond()   │
         │ +search()       │ │ +terminateNOA() │ │ +releaseBond()  │
         └────────┬────────┘ └────────┬────────┘ └────────┬────────┘
                  │                   │                   │
                  └───────────────────┼───────────────────┘
                                      │
                                      ▼
                           ┌─────────────────────┐
                           │ MasterDataRepository│
                           │  (TypeORM/Oracle)   │
                           └─────────────────────┘
```

#### 4.1.2 Class Design

```typescript
// Project Entity
@Entity('projects')
class Project {
  @PrimaryColumn({ length: 15 })
  projectId: string;

  @Column({ length: 255, nullable: false })
  projectName: string;

  @Column('text')
  description: string;

  @ManyToOne(() => Organization)
  @JoinColumn({ name: 'org_id' })
  organization: Organization;

  @Column({
    type: 'enum',
    enum: ProjectStatus,
    default: ProjectStatus.ACTIVE
  })
  status: ProjectStatus;

  @Column('date')
  startDate: Date;

  @Column('date')
  plannedEndDate: Date;

  @Column('timestamp')
  createdDate: Date;

  @OneToMany(() => NOA, noa => noa.project)
  noas: NOA[];

  @OneToMany(() => Cluster, cluster => cluster.project)
  clusters: Cluster[];

  // Methods
  async createProject(dto: CreateProjectDTO): Promise<Project> {}
  async updateProject(id: string, dto: UpdateProjectDTO): Promise<Project> {}
  async getProjectHierarchy(id: string): Promise<ProjectHierarchy> {}
  async searchProjects(criteria: SearchCriteria): Promise<Project[]> {}
}

// Project Service
@Service()
class ProjectService {
  constructor(
    @InjectRepository(Project)
    private projectRepo: Repository<Project>,
    private idGenerator: IDGeneratorService,
    private auditService: AuditService,
    private uspfsClient: USPFSClient
  ) {}

  async createProject(dto: CreateProjectDTO, userId: string): Promise<Project> {
    // Generate unique project ID
    const projectId = await this.idGenerator.generateProjectId();
    
    // Create project entity
    const project = this.projectRepo.create({
      projectId,
      ...dto,
      createdBy: userId,
      createdDate: new Date()
    });

    // Save to database
    const savedProject = await this.projectRepo.save(project);

    // Sync with USPFS
    await this.uspfsClient.syncProject(savedProject);

    // Audit log
    await this.auditService.log({
      action: 'PROJECT_CREATE',
      resourceId: projectId,
      userId,
      afterValue: savedProject
    });

    return savedProject;
  }
}
```

### 4.2 Claims Module Design

#### 4.2.1 State Machine Design

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     CLAIM STATE MACHINE                                      │
└─────────────────────────────────────────────────────────────────────────────┘

                              ┌─────────┐
                              │  DRAFT  │
                              └────┬────┘
                                   │ submit()
                                   ▼
                           ┌───────────────┐
                           │   SUBMITTED   │◀─────────────────────────┐
                           └───────┬───────┘                          │
                                   │ validate()                        │
                    ┌──────────────┼──────────────┐                   │
                    │              │              │                   │
                    ▼              ▼              ▼                   │
            ┌─────────────┐ ┌─────────────┐ ┌─────────────┐          │
            │UNDER_REVIEW │ │  REJECTED   │ │   CLOSED    │          │
            └──────┬──────┘ └─────────────┘ └─────────────┘          │
                   │ requestInfo()                                      │
                   ▼                                                    │
           ┌───────────────┐                                           │
           │ADDITIONAL_INFO│───────────────────────────────────────────┘
           │   REQUIRED    │        resubmit()
           └───────────────┘
                    │
                    │ verify()
                    ▼
            ┌─────────────┐
            │   VERIFIED  │
            └──────┬──────┘
                   │ approve()
                   ▼
            ┌─────────────┐
            │   APPROVED  │
            └──────┬──────┘
                   │ processPayment()
                   ▼
            ┌─────────────┐
            │   PAYMENT   │
            │  PROCESSING │
            └──────┬──────┘
                   │ confirmPayment()
                   ▼
            ┌─────────────┐
            │    PAID     │
            └──────┬──────┘
                   │ close()
                   ▼
            ┌─────────────┐
            │    CLOSED   │
            └─────────────┘
```

#### 4.2.2 Workflow Design (BPMN)

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     CLAIM APPROVAL WORKFLOW (BPMN)                           │
└─────────────────────────────────────────────────────────────────────────────┘

[Start] ──▶ [Submit Claim] ──▶ [Validate Documents] ──▶ {Valid?}
                                                      │
                                       No ────────────┴────────────▶ [Request
                                                                      Correction]
                                                                       │
                                                                       ▼
[Finance      ◀────── [Final      ◀────── [Level 3    ◀────── [Level 2
 Approval]           Approval]            Approval?]            Approval?]
   │                     │                  │                      │
   │                     │                  │ Yes                  │ Yes
   │                     │                  ▼                      ▼
   │                     │            [Director                [Finance
   │                     │             Approval]                 Approval]
   │                     │                  │                      │
   │                     │                  └──────────────────────┘
   │                     │                            │
   │                     │                            │ No
   │                     │                            ▼
   │                     │                      [Level 1
   │                     │                       Approval]
   │                     │                            │
   │                     │                            ▼
   │                     │                      [Department
   │                     │                       Approval]
   │                     │                            │
   │                     │                            ▼
   │                     └──────────────────── [Verified]
   │                                              │
   ▼                                              ▼
[Generate                                 [Reject Claim]
 Voucher]                                        │
   │                                             ▼
   │                                        [Notify DUSP]
   ▼                                              │
[Process                                           ▼
 Payment]                                     [End]
   │
   ▼
[Confirm
 Payment]
   │
   ▼
[Notify
 DUSP]
   │
   ▼
[End]
```

### 4.3 Payment Module Design

#### 4.3.1 Integration Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     PAYMENT INTEGRATION FLOW                                 │
└─────────────────────────────────────────────────────────────────────────────┘

Claim Approved
      │
      ▼
┌─────────────────┐
│ Payment Service │
│  - Generate     │
│    Memo         │
│  - Route for    │
│    Approval     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐     ┌─────────────────┐
│ Digital Sig     │────▶│  Approval       │
│ Service         │     │  Complete       │
│  - Sign Memo    │     │                 │
│  - Verify       │     │                 │
└─────────────────┘     └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │ USPFS Adapter   │
                        │  - Create       │
                        │    Voucher      │
                        │  - Submit to    │
                        │    Oracle EBS   │
                        └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │  Bank Adapter   │
                        │  - Generate     │
                        │    Payment File │
                        │  - Transmit     │
                        └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │  Confirmation   │
                        │  Received       │
                        └────────┬────────┘
                                 │
                                 ▼
                        ┌─────────────────┐
                        │  Notification   │
                        │  Service        │
                        │  - Email DUSP   │
                        │  - Update Status│
                        └─────────────────┘
```

---

## 5. INTERFACE DESIGN

### 5.1 API Design

#### 5.1.1 REST API Specification

```yaml
openapi: 3.0.0
info:
  title: UCMS API
  version: 1.0.0
  description: Universal Service Provision Claims Management System API

paths:
  /api/v1/claims:
    post:
      summary: Create new claim
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/CreateClaimRequest'
      responses:
        201:
          description: Claim created successfully
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Claim'
        400:
          description: Invalid request
        401:
          description: Unauthorized

    get:
      summary: List claims
      parameters:
        - name: status
          in: query
          schema:
            type: string
            enum: [DRAFT, SUBMITTED, APPROVED, PAID]
        - name: projectId
          in: query
          schema:
            type: string
        - name: page
          in: query
          schema:
            type: integer
            default: 1
        - name: limit
          in: query
          schema:
            type: integer
            default: 20
      responses:
        200:
          description: List of claims
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ClaimList'

  /api/v1/claims/{claimId}:
    get:
      summary: Get claim details
      parameters:
        - name: claimId
          in: path
          required: true
          schema:
            type: string
      responses:
        200:
          description: Claim details
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/ClaimDetail'

    put:
      summary: Update claim
      parameters:
        - name: claimId
          in: path
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/UpdateClaimRequest'
      responses:
        200:
          description: Claim updated

  /api/v1/claims/{claimId}/submit:
    post:
      summary: Submit claim for processing
      parameters:
        - name: claimId
          in: path
          required: true
          schema:
            type: string
      responses:
        200:
          description: Claim submitted successfully

  /api/v1/claims/{claimId}/approve:
    post:
      summary: Approve claim
      parameters:
        - name: claimId
          in: path
          required: true
          schema:
            type: string
      requestBody:
        content:
          application/json:
            schema:
              type: object
              properties:
                comments:
                  type: string
                conditions:
                  type: array
                  items:
                    type: string
      responses:
        200:
          description: Claim approved

components:
  schemas:
    CreateClaimRequest:
      type: object
      required:
        - projectId
        - claimType
        - claimAmount
      properties:
        projectId:
          type: string
          description: Project identifier
        claimType:
          type: string
          enum: [ADVANCE, QUARTERLY, MAJOR_CONTRIBUTOR, YEARLY]
        claimAmount:
          type: number
          minimum: 0
        claimPeriodStart:
          type: string
          format: date
        claimPeriodEnd:
          type: string
          format: date
        description:
          type: string
        documents:
          type: array
          items:
            $ref: '#/components/schemas/DocumentReference'

    Claim:
      type: object
      properties:
        claimId:
          type: string
        projectId:
          type: string
        claimType:
          type: string
        claimAmount:
          type: number
        claimStatus:
          type: string
        submissionDate:
          type: string
          format: date-time
        submittedBy:
          type: string

    ClaimList:
      type: object
      properties:
        data:
          type: array
          items:
            $ref: '#/components/schemas/Claim'
        pagination:
          $ref: '#/components/schemas/Pagination'

    Pagination:
      type: object
      properties:
        page:
          type: integer
        limit:
          type: integer
        total:
          type: integer
        totalPages:
          type: integer
```

### 5.2 User Interface Design

#### 5.2.1 Screen Layout

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  MCMC Logo        Universal Service Provision Claims Management    [User] ▼ │
├──────────────────┬──────────────────────────────────────────────────────────┤
│                  │                                                          │
│  NAVIGATION      │                    MAIN CONTENT AREA                     │
│                  │                                                          │
│  ┌────────────┐  │  ┌─────────────────────────────────────────────────────┐ │
│  │ Dashboard  │  │  │  PAGE TITLE                              [Actions] │ │
│  └────────────┘  │  └─────────────────────────────────────────────────────┘ │
│  ┌────────────┐  │                                                          │
│  │ Projects   │  │  ┌─────────────────────────────────────────────────────┐ │
│  └────────────┘  │  │                                                     │ │
│  ┌────────────┐  │  │  Content Area                                       │ │
│  │ Claims     │  │  │                                                     │ │
│  └────────────┘  │  │  - Forms                                            │ │
│  ┌────────────┐  │  │  - Tables                                           │ │
│  │ Budget     │  │  │  - Charts                                           │ │
│  └────────────┘  │  │  - Widgets                                          │ │
│  ┌────────────┐  │  │                                                     │ │
│  │ Payments   │  │  └─────────────────────────────────────────────────────┘ │
│  └────────────┘  │                                                          │
│  ┌────────────┐  │  ┌─────────────────────────────────────────────────────┐ │
│  │ Reports    │  │  │  Tab Navigation (if applicable)                     │ │
│  └────────────┘  │  └─────────────────────────────────────────────────────┘ │
│                  │                                                          │
│  ADMINISTRATION  │                                                          │
│  ┌────────────┐  │                                                          │
│  │ Users      │  │                                                          │
│  └────────────┘  │                                                          │
│  ┌────────────┐  │                                                          │
│  │ Settings   │  │                                                          │
│  └────────────┘  │                                                          │
│                  │                                                          │
├──────────────────┴──────────────────────────────────────────────────────────┤
│  © 2026 MCMC                                    Help | Support | Logout    │
└─────────────────────────────────────────────────────────────────────────────┘
```

#### 5.2.2 Form Design

```
Claim Submission Form

┌─────────────────────────────────────────────────────────────────┐
│  Step 1 of 4: Claim Details                              [Save] │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Project *                  Claim Type *                        │
│  ┌────────────────────┐    ┌────────────────────┐              │
│  │ Select Project...  │    │ Select Type...     │              │
│  └────────────────────┘    └────────────────────┘              │
│                                                                 │
│  Claim Period                                                      │
│  From *                    To *                                 │
│  ┌────────────┐           ┌────────────┐                       │
│  │ 01/01/2026 │           │ 31/03/2026 │                       │
│  └────────────┘           └────────────┘                       │
│                                                                 │
│  Claim Amount *                                                 │
│  ┌────────────────────────────────────────┐                    │
│  │ RM                                     │                    │
│  └────────────────────────────────────────┘                    │
│  [?] Enter amount excluding GST                               │
│                                                                 │
│  Description                                                    │
│  ┌────────────────────────────────────────────────────────┐    │
│  │                                                        │    │
│  │                                                        │    │
│  └────────────────────────────────────────────────────────┘    │
│                                                                 │
│  ┌────────────────────────────────────────────────────────┐    │
│  │  ⚠ Validation Message                                  │    │
│  └────────────────────────────────────────────────────────┘    │
│                                                                 │
│                    [Back]        [Next: Documents >]            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 6. SECURITY ARCHITECTURE

### 6.1 Security Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        SECURITY ARCHITECTURE                                 │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                              PERIMETER SECURITY                              │
├─────────────────────────────────────────────────────────────────────────────┤
│  WAF (ModSecurity)  ──▶  DDoS Protection  ──▶  SSL/TLS Termination         │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           ACCESS CONTROL LAYER                               │
├─────────────────────────────────────────────────────────────────────────────┤
│  Azure AD SSO  ──▶  OAuth 2.0/OIDC  ──▶  JWT Tokens  ──▶  Session Mgmt     │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         AUTHORIZATION LAYER                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│  RBAC Engine  ──▶  Policy Enforcement  ──▶  Data-Level Security             │
│                                                                              │
│  • Role Definitions      • API Gateway Rules      • Row-Level Security      │
│  • Permission Matrix     • Function Access        • Column Masking          │
│  • Segregation of Duties • Resource Access        • Encryption              │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           DATA SECURITY LAYER                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │  Encryption     │  │   Tokenization  │  │   Masking       │              │
│  │  (AES-256)      │  │   (Sensitive)   │  │   (Display)     │              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      Database Security                               │    │
│  │  • Transparent Data Encryption (TDE)   • Column-level encryption     │    │
│  │  • Database Vault                      • Audit policies              │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Authentication Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                     AZURE AD AUTHENTICATION FLOW                             │
└─────────────────────────────────────────────────────────────────────────────┘

User                    UCMS Frontend         API Gateway         Azure AD
  │                           │                   │                   │
  │  1. Access Application    │                   │                   │
  │ ─────────────────────────▶│                   │                   │
  │                           │                   │                   │
  │                           │  2. Check Auth    │                   │
  │                           │ ─────────────────▶│                   │
  │                           │                   │                   │
  │                           │  3. No Token      │                   │
  │                           │ ◀─────────────────│                   │
  │                           │                   │                   │
  │  4. Redirect to Azure AD  │                   │                   │
  │ ◀─────────────────────────│                   │                   │
  │                           │                   │                   │
  │  5. Login to Azure AD     │                   │                   │
  │ ────────────────────────────────────────────────────────────────▶│
  │                           │                   │                   │
  │  6. Return Auth Code      │                   │                   │
  │ ◀────────────────────────────────────────────────────────────────│
  │                           │                   │                   │
  │  7. Send Code to Backend  │                   │                   │
  │ ─────────────────────────▶│                   │                   │
  │                           │                   │                   │
  │                           │  8. Exchange Code │                   │
  │                           │ ────────────────────────────────────▶│
  │                           │                   │                   │
  │                           │  9. Return Tokens │                   │
  │                           │ ◀────────────────────────────────────│
  │                           │                   │                   │
  │                           │  10. Create Session                  │
  │                           │ ─────────────────▶│                   │
  │                           │                   │                   │
  │  11. Return JWT + Session │                   │                   │
  │ ◀─────────────────────────│                   │                   │
  │                           │                   │                   │
  │  12. API Request with JWT │                   │                   │
  │ ─────────────────────────▶│                   │                   │
  │                           │                   │                   │
  │                           │  13. Validate JWT │                   │
  │                           │ ─────────────────▶│                   │
  │                           │                   │                   │
  │                           │  14. Check Permissions                  │
  │                           │                   │                   │
  │                           │  15. Route to Service                   │
  │                           │                   │                   │
```

---

## 7. INTEGRATION ARCHITECTURE

### 7.1 Integration Patterns

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        INTEGRATION ARCHITECTURE                              │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                           API GATEWAY (Kong)                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│  Authentication │ Rate Limiting │ Request Routing │ Response Transform     │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                        SERVICE MESH (Istio/Linkerd)                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌───────────────┐    ┌───────────────┐    ┌───────────────┐              │
│   │   Service A   │◀──▶│   Service B   │◀──▶│   Service C   │              │
│   └───────────────┘    └───────────────┘    └───────────────┘              │
│          │                    │                    │                         │
│          └────────────────────┼────────────────────┘                         │
│                               │                                              │
│                               ▼                                              │
│                    ┌─────────────────────┐                                   │
│                    │  Message Queue      │                                   │
│                    │  (RabbitMQ/Kafka)   │                                   │
│                    └─────────────────────┘                                   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         INTEGRATION ADAPTERS                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────┐  ┌───────────────┐  ┌───────────────┐  ┌──────────────┐ │
│  │  USPFS        │  │  Azure AD     │  │  Digital Sig  │  │  Banking     │ │
│  │  Adapter      │  │  Adapter      │  │  Adapter      │  │  Adapter     │ │
│  │               │  │               │  │               │  │              │ │
│  │ • SOAP/REST   │  │ • SAML/OIDC   │  │ • API/Webhook │  │ • SFTP/API   │ │
│  │ • Oracle API  │  │ • Graph API   │  │ • Doc Signing │  │ • File Exch  │ │
│  └───────────────┘  └───────────────┘  └───────────────┘  └──────────────┘ │
│                                                                              │
│  ┌───────────────┐  ┌───────────────┐  ┌───────────────┐                   │
│  │  OCR Service  │  │  AI/ML        │  │  Email/SMS    │                   │
│  │  Adapter      │  │  Adapter      │  │  Adapter      │                   │
│  │               │  │               │  │               │                   │
│  │ • REST API    │  │ • gRPC/REST   │  │ • SMTP        │                   │
│  │ • Async Proc  │  │ • Model Serving│  │ • SMS Gateway │                   │
│  └───────────────┘  └───────────────┘  └───────────────┘                   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 8. AI/ML COMPONENT DESIGN

### 8.1 AI/ML Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         AI/ML SERVICE ARCHITECTURE                           │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         API LAYER (FastAPI)                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│  /classify    /extract    /detect-fraud    /analyze    /predict             │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      MODEL SERVING LAYER (TensorFlow Serving)                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐       │
│  │ Document          │  │ Fraud Detection   │  │ Anomaly Detection │       │
│  │ Classification    │  │ Model             │  │ Model             │       │
│  │ Model (v1.2)      │  │ (v2.0)            │  │ (v1.5)            │       │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘       │
│                                                                              │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐       │
│  │ OCR Correction    │  │ Amount Prediction │  │ Risk Scoring      │       │
│  │ Model (v1.0)      │  │ Model (v1.3)      │  │ Model (v1.8)      │       │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘       │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      DATA PROCESSING LAYER                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐       │
│  │ Image             │  │ Text              │  │ Feature           │       │
│  │ Preprocessing     │  │ Processing        │  │ Engineering       │       │
│  │ • Resize          │  │ • Tokenization    │  │ • Normalization   │       │
│  │ • Denoise         │  │ • NER             │  │ • Encoding        │       │
│  │ • Enhancement     │  │ • Classification  │  │ • Selection       │       │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘       │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         DATA STORAGE                                         │
├─────────────────────────────────────────────────────────────────────────────┤
│  Model Registry (MLflow)  │  Feature Store (Feast)  │  Training Data (S3)  │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 8.2 Document Processing Pipeline

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DOCUMENT PROCESSING PIPELINE                              │
└─────────────────────────────────────────────────────────────────────────────┘

Input Document
      │
      ▼
┌─────────────────┐
│ 1. Ingestion    │  ──▶ File validation, Virus scan, Format check
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 2. Preprocessing│  ──▶ Image enhancement, Deskew, Binarization
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 3. OCR          │  ──▶ Text extraction (Tesseract/AWS Textract)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 4. Classification│ ──▶ Document type identification (Invoice, Receipt, etc.)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 5. Extraction   │  ──▶ Field extraction (Amount, Date, Vendor, etc.)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 6. Validation   │  ──▶ Data validation, Cross-check with claim
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 7. Fraud Check  │  ──▶ Anomaly detection, Pattern analysis
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ 8. Results      │  ──▶ Structured output with confidence scores
└─────────────────┘
```

### 8.3 Fraud Detection Model

```python
# Fraud Detection Service Architecture

class FraudDetectionService:
    """
    Multi-layer fraud detection system
    """
    
    def __init__(self):
        self.rule_engine = RuleEngine()
        self.ml_model = FraudMLModel()
        self.anomaly_detector = AnomalyDetector()
        self.network_analyzer = NetworkAnalyzer()
    
    async def detect_fraud(self, claim_data: ClaimData) -> FraudAssessment:
        """
        Run comprehensive fraud detection
        """
        assessment = FraudAssessment()
        
        # Layer 1: Rule-based checks
        rule_results = await self.rule_engine.evaluate(claim_data)
        assessment.add_results(rule_results)
        
        # Layer 2: ML model prediction
        ml_score = await self.ml_model.predict(claim_data)
        assessment.ml_score = ml_score
        
        # Layer 3: Anomaly detection
        anomaly_score = await self.anomaly_detector.detect(claim_data)
        assessment.anomaly_score = anomaly_score
        
        # Layer 4: Network analysis
        network_risk = await self.network_analyzer.analyze(claim_data)
        assessment.network_risk = network_risk
        
        # Calculate overall risk score
        assessment.overall_risk = self.calculate_risk(assessment)
        
        return assessment
    
    def calculate_risk(self, assessment: FraudAssessment) -> RiskScore:
        """
        Weighted calculation of risk factors
        """
        weights = {
            'rules': 0.25,
            'ml_model': 0.30,
            'anomaly': 0.25,
            'network': 0.20
        }
        
        overall_score = (
            assessment.rule_score * weights['rules'] +
            assessment.ml_score * weights['ml_model'] +
            assessment.anomaly_score * weights['anomaly'] +
            assessment.network_risk * weights['network']
        )
        
        return RiskScore(
            score=overall_score,
            level=self.get_risk_level(overall_score),
            factors=assessment.get_triggered_factors()
        )
```

---

## 9. RPA DESIGN

### 9.1 RPA Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         RPA ARCHITECTURE                                     │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         ORCHESTRATOR (UiPath/Blue Prism)                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      QUEUE MANAGEMENT                                │    │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐           │    │
│  │  │  Data    │  │  Report  │  │  Recon   │  │  Notify  │           │    │
│  │  │  Entry   │  │  Gen     │  │  Tasks   │  │  Tasks   │           │    │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘           │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         ROBOT POOL                                           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐       │
│  │  Robot 1          │  │  Robot 2          │  │  Robot 3          │       │
│  │  (Data Entry)     │  │  (Report Dist)    │  │  (Reconciliation) │       │
│  │                   │  │                   │  │                   │       │
│  │ • Form filling    │  │ • Email reports   │  │ • USPFS recon     │       │
│  │ • Data validation │  │ • File transfer   │  │ • Exception hdlg  │       │
│  │ • System updates  │  │ • Notification    │  │ • Reporting       │       │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘       │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      SYSTEM INTEGRATIONS                                     │
├─────────────────────────────────────────────────────────────────────────────┤
│  UCMS API  │  USPFS  │  Email  │  File System  │  Excel/Office  │  Web    │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 9.2 RPA Use Cases

| Use Case ID | Description | Frequency | Robot Type |
|-------------|-------------|-----------|------------|
| RPA-001 | Automated data entry from documents | Real-time | Attended |
| RPA-002 | Report distribution to stakeholders | Daily | Unattended |
| RPA-003 | USPFS reconciliation | Hourly | Unattended |
| RPA-004 | Exception notification processing | Event-driven | Attended |
| RPA-005 | Backup verification | Daily | Unattended |
| RPA-006 | Data quality checks | Weekly | Unattended |

---

## 10. DEPLOYMENT ARCHITECTURE

### 10.1 Infrastructure Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      DEPLOYMENT ARCHITECTURE                                 │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         LOAD BALANCER (HAProxy/Nginx)                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                      SSL Termination, Traffic Distribution                   │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                    KUBERNETES CLUSTER (OpenShift/EKS)                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                         INGRESS CONTROLLER                           │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                     SERVICE MESH (Istio)                             │    │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐  │    │
│  │  │ Frontend │ │  API     │ │  AI/ML   │ │  Worker  │ │  Report  │  │    │
│  │  │   Pods   │ │  Pods    │ │  Pods    │ │  Pods    │ │  Pods    │  │    │
│  │  │ (3 replicas)│(5 replicas)│(2 replicas)│(3 replicas)│(2 replicas)│  │    │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────┘  │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
│  ┌─────────────────────────────────────────────────────────────────────┐    │
│  │                      STATEFUL SERVICES                               │    │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐              │    │
│  │  │  Oracle  │ │  Redis   │ │RabbitMQ  │ │   S3     │              │    │
│  │  │   RAC    │ │ Cluster  │ │ Cluster  │ │  (MinIO) │              │    │
│  │  │(3 nodes) │ │(3 nodes) │ │(3 nodes) │ │(4 nodes) │              │    │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘              │    │
│  └─────────────────────────────────────────────────────────────────────┘    │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                      STORAGE LAYER                                           │
├─────────────────────────────────────────────────────────────────────────────┤
│  Database Storage (SSD)  │  File Storage (Object)  │  Backup Storage        │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 10.2 Environment Strategy

| Environment | Purpose | Configuration | Data |
|-------------|---------|---------------|------|
| Development | Feature development | Single instance | Synthetic |
| Testing | QA and UAT | Production-like | Anonymized production |
| Staging | Pre-production validation | Mirror production | Subset of production |
| Production | Live system | Full HA cluster | Production data |
| DR | Disaster recovery | Hot standby | Replicated |

---

## 11. PERFORMANCE AND SCALABILITY DESIGN

### 11.1 Caching Strategy

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         CACHING ARCHITECTURE                                 │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                              CDN LAYER                                       │
├─────────────────────────────────────────────────────────────────────────────┤
│  Static Assets (JS, CSS, Images) - Global edge caching                       │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         APPLICATION CACHE (Redis)                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────────┐  ┌───────────────────┐  ┌───────────────────┐       │
│  │   Session Cache   │  │   Data Cache      │  │   Query Cache     │       │
│  │                   │  │                   │  │                   │       │
│  │ • User sessions   │  │ • Master data     │  │ • Search results  │       │
│  │ • Auth tokens     │  │ • Configurations  │  │ • Report data     │       │
│  │ TTL: 30 min       │  │ TTL: 1 hour       │  │ TTL: 15 min       │       │
│  └───────────────────┘  └───────────────────┘  └───────────────────┘       │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
           │
           ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         DATABASE LAYER                                       │
├─────────────────────────────────────────────────────────────────────────────┤
│  Oracle RAC with Read Replicas, Query Result Cache, Connection Pooling       │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 11.2 Scalability Design

| Component | Scaling Strategy | Max Scale |
|-----------|------------------|-----------|
| Web Frontend | Horizontal (Pods) | 20 pods |
| API Services | Horizontal (Pods) | 50 pods |
| AI/ML Services | Horizontal (GPU nodes) | 10 pods |
| Database | Vertical + Read replicas | 3 nodes + 5 replicas |
| Cache | Cluster mode | 6 nodes |
| Message Queue | Cluster mode | 5 nodes |

---

## 12. DISASTER RECOVERY DESIGN

### 12.1 DR Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      DISASTER RECOVERY ARCHITECTURE                          │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                              PRIMARY SITE                                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────┐  ┌───────────────┐  ┌───────────────┐  ┌──────────────┐ │
│  │   Web Tier    │  │   App Tier    │  │   Data Tier   │  │    Storage   │ │
│  │   (Active)    │  │   (Active)    │  │   (Primary)   │  │   (Primary)  │ │
│  └───────┬───────┘  └───────┬───────┘  └───────┬───────┘  └──────┬───────┘ │
│          │                  │                  │                 │         │
└──────────┼──────────────────┼──────────────────┼─────────────────┼─────────┘
           │                  │                  │                 │
           │  Replicate       │  Sync            │  Sync           │  Replicate
           │                  │                  │                 │
┌──────────┼──────────────────┼──────────────────┼─────────────────┼─────────┐
│          │                  │                  │                 │         │
│  ┌───────▼───────┐  ┌───────▼───────┐  ┌───────▼───────┐  ┌──────▼────────┐ │
│  │   Web Tier    │  │   App Tier    │  │   Data Tier   │  │    Storage    │ │
│  │  (Standby)    │  │  (Standby)    │  │  (Standby)    │  │   (Replica)   │ │
│  └───────────────┘  └───────────────┘  └───────────────┘  └───────────────┘ │
│                                                                              │
│                         DISASTER RECOVERY SITE                               │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 12.2 Recovery Objectives

| Metric | Objective | Implementation |
|--------|-----------|----------------|
| RTO | 4 hours | Hot standby with automated failover |
| RPO | 1 hour | Continuous replication |
| Data Loss | Zero (synchronous) | For critical transactions |
| Failover | Automatic | Kubernetes + Database clustering |

---

## 13. APPENDICES

### Appendix A: Technology Stack Summary

| Layer | Technology | Version |
|-------|------------|---------|
| Frontend | React | 18.x |
| Backend | Node.js | 20.x |
| Database | Oracle | 19c |
| Cache | Redis | 7.x |
| Search | Elasticsearch | 8.x |
| Message Queue | RabbitMQ | 3.12.x |
| Container | Docker | 24.x |
| Orchestration | Kubernetes | 1.28.x |
| API Gateway | Kong | 3.x |
| Workflow | Camunda | 8.x |
| AI/ML | TensorFlow | 2.x |

### Appendix B: Network Architecture

```
Internet ──▶ Firewall ──▶ WAF ──▶ Load Balancer ──▶ Kubernetes Cluster
                                              │
                                              ▶ Database (Private Network)
                                              │
                                              ▶ External Services (API Gateway)
```

### Appendix C: Security Checklist

- [ ] TLS 1.3 for all communications
- [ ] AES-256 encryption at rest
- [ ] OAuth 2.0 / OIDC for authentication
- [ ] RBAC for authorization
- [ ] Input validation on all APIs
- [ ] SQL injection prevention
- [ ] XSS prevention
- [ ] CSRF protection
- [ ] Rate limiting
- [ ] Audit logging
- [ ] Penetration testing
- [ ] Vulnerability scanning

---

**END OF DOCUMENT**
