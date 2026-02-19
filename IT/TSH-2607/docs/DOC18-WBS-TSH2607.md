# DOC18: Work Breakdown Structure (WBS)
## TSH-2607 MCMC UCMS Tender

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Date:** February 2026

---

## 1. WBS OVERVIEW

### 1.1 Project Structure

```
UCMS PROJECT (TSH-2607)
│
├── 1.0 PROJECT MANAGEMENT (Level 1)
│   ├── 1.1 Project Initiation
│   ├── 1.2 Project Planning
│   ├── 1.3 Project Monitoring
│   └── 1.4 Project Closure
│
├── 2.0 REQUIREMENTS & ANALYSIS (Level 1)
│   ├── 2.1 Requirements Gathering
│   ├── 2.2 Business Process Analysis
│   ├── 2.3 Requirements Documentation
│   └── 2.4 Requirements Approval
│
├── 3.0 DESIGN & ARCHITECTURE (Level 1)
│   ├── 3.1 System Architecture Design
│   ├── 3.2 Database Design
│   ├── 3.3 Interface Design
│   ├── 3.4 Security Design
│   └── 3.5 Design Review
│
├── 4.0 DEVELOPMENT (Level 1)
│   ├── 4.1 Master Data Module
│   ├── 4.2 User Management Module
│   ├── 4.3 Budget Module
│   ├── 4.4 Claims Module
│   ├── 4.5 Payment Module
│   ├── 4.6 Reports Module
│   ├── 4.7 Dashboard Module
│   ├── 4.8 Audit Trail Module
│   ├── 4.9 Self-Service Module
│   └── 4.10 Value-Added Module
│
├── 5.0 INTEGRATION (Level 1)
│   ├── 5.1 USPFS Integration
│   ├── 5.2 Azure AD Integration
│   ├── 5.3 Banking Integration
│   └── 5.4 Digital Signature Integration
│
├── 6.0 TESTING (Level 1)
│   ├── 6.1 Unit Testing
│   ├── 6.2 Integration Testing
│   ├── 6.3 System Testing
│   ├── 6.4 UAT
│   ├── 6.5 Performance Testing
│   └── 6.6 VAPT
│
├── 7.0 DEPLOYMENT (Level 1)
│   ├── 7.1 Environment Setup
│   ├── 7.2 Data Migration
│   ├── 7.3 System Deployment
│   └── 7.4 Go-Live Support
│
├── 8.0 TRAINING (Level 1)
│   ├── 8.1 Training Material Development
│   ├── 8.2 End-User Training
│   ├── 8.3 Admin Training
│   └── 8.4 Knowledge Transfer
│
├── 9.0 DOCUMENTATION (Level 1)
│   ├── 9.1 Technical Documentation
│   ├── 9.2 User Manuals
│   └── 9.3 Training Guides
│
└── 10.0 SUPPORT (Level 1)
    ├── 10.1 Warranty Support
    └── 10.2 Extended Support
```

---

## 2. DETAILED WBS

### 2.1 Level 2 Breakdown: Development (4.0)

```
4.0 DEVELOPMENT
│
├── 4.1 MASTER DATA MODULE
│   ├── 4.1.1 Project ID Management
│   ├── 4.1.2 DUSP Profile Management
│   ├── 4.1.3 Bond Management
│   ├── 4.1.4 NOA/Contract Management
│   ├── 4.1.5 VO Tracking
│   └── 4.1.6 ID Structure (4-tier)
│
├── 4.2 USER MANAGEMENT MODULE
│   ├── 4.2.1 User Registration
│   ├── 4.2.2 RBAC Implementation
│   ├── 4.2.3 MFA Integration
│   ├── 4.2.4 Delegation Feature
│   └── 4.2.5 User Audit Trail
│
├── 4.3 BUDGET MODULE
│   ├── 4.3.1 Capped Cost Tracking
│   ├── 4.3.2 BOQ Management
│   ├── 4.3.3 Cost Component Allocation
│   └── 4.3.4 Variance Reporting
│
├── 4.4 CLAIMS MODULE
│   ├── 4.4.1 Advance Claims
│   ├── 4.4.2 Quarterly Claims
│   ├── 4.4.3 Yearly Claims
│   ├── 4.4.4 Claim Validation
│   └── 4.4.5 Claim Workflow
│
├── 4.5 PAYMENT MODULE
│   ├── 4.5.1 Payment Memo
│   ├── 4.5.2 Approval Workflow
│   ├── 4.5.3 Digital Signature
│   └── 4.5.4 Voucher Generation
│
└── [Other modules follow same pattern...]
```

---

## 3. WBS DICTIONARY

### 3.1 Work Package Definitions

| WBS Code | Work Package | Description | Deliverable | Owner |
|----------|--------------|-------------|-------------|-------|
| 1.1 | Project Initiation | Setup project governance | PID | PM |
| 2.1 | Requirements Gathering | Conduct workshops | SRS | BA |
| 3.1 | Architecture Design | Design system architecture | SDS | Architect |
| 4.1.1 | Project ID Management | Develop project ID features | Code | Dev Lead |
| 5.1 | USPFS Integration | Build USPFS connectors | APIs | Integration Lead |
| 6.1 | Unit Testing | Execute unit tests | Test Report | QA |
| 7.3 | System Deployment | Deploy to production | Live System | Tech Lead |
| 8.2 | End-User Training | Train MCMC users | Training Completion | Trainer |

---

## 4. EFFORT ESTIMATES

| Phase | Work Packages | Effort (Man-Months) |
|-------|---------------|---------------------|
| 1.0 Project Management | 4 | 19 |
| 2.0 Requirements | 4 | 4 |
| 3.0 Design | 5 | 4 |
| 4.0 Development | 10 modules | 48 |
| 5.0 Integration | 4 | 8 |
| 6.0 Testing | 6 | 12 |
| 7.0 Deployment | 4 | 4 |
| 8.0 Training | 4 | 2 |
| 9.0 Documentation | 3 | 4 |
| 10.0 Support | 2 | 48 |
| **TOTAL** | **44** | **153** |

---

## 5. WBS & SCHEDULE ALIGNMENT

| Phase | Start | End | Duration |
|-------|-------|-----|----------|
| 1.0 PM | M1 | M67 | 67 months |
| 2.0 Req | M1 | M2 | 2 months |
| 3.0 Design | M3 | M4 | 2 months |
| 4.0 Dev | M5 | M16 | 12 months |
| 5.0 Int | M13 | M17 | 5 months |
| 6.0 Test | M15 | M18 | 4 months |
| 7.0 Deploy | M18 | M19 | 2 months |
| 8.0 Train | M18 | M19 | 2 months |
| 9.0 Doc | M1 | M19 | 19 months |
| 10.0 Support | M19 | M67 | 48 months |

---

*This Work Breakdown Structure is part of TSH-2607 tender submission.*
