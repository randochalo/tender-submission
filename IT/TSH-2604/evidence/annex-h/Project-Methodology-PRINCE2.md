# ANNEX H: PROJECT METHODOLOGY (PRINCE2)

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**Project:** Business Operating & Finance IT System Implementation  
**Methodology:** PRINCE2 (Projects IN Controlled Environments)  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [PRINCE2 Overview](#1-prince2-overview)
2. [Project Organization](#2-project-organization)
3. [Management Stages](#3-management-stages)
4. [Product-Based Planning](#4-product-based-planning)
5. [Quality Management](#5-quality-management)
6. [Risk Management](#6-risk-management)
7. [Change Control](#7-change-control)
8. [Project Controls](#8-project-controls)
9. [Stage Gates & Tolerance](#9-stage-gates--tolerance)
10. [Project Closure](#10-project-closure)

---

## 1. PRINCE2 OVERVIEW

### 1.1 PRINCE2 Principles

Our project delivery follows the 7 PRINCE2 principles:

| Principle | Application in MMF Project |
|-----------|---------------------------|
| **Continued Business Justification** | Business case reviewed at every Stage Gate; project continues only if value exceeds cost |
| **Learn from Experience** | Lessons learned captured and applied throughout; previous logistics implementations inform approach |
| **Defined Roles & Responsibilities** | Clear RACI matrix; Project Board, PM, Team Managers defined |
| **Manage by Stages** | 5 Management Stages with Stage Gates; go/no-go decisions at each gate |
| **Manage by Exception** | Tolerance-based management; escalate only when tolerance exceeded |
| **Focus on Products** | Product-Based Planning; deliverables defined before activities |
| **Tailor to Suit Environment** | PRINCE2 adapted for IT implementation; not bureaucracy-heavy |

### 1.2 PRINCE2 Themes

| Theme | Implementation |
|-------|---------------|
| **Business Case** | ROI tracked; benefits realization monitored |
| **Organization** | Three-tier structure (Direction, Management, Delivery) |
| **Quality** | Quality Register; acceptance criteria for all products |
| **Plans** | 4 levels (Project, Stage, Team, Exception) |
| **Risk** | Risk Register; proactive risk management |
| **Change** | Change Control Board; impact assessment mandatory |
| **Progress** | Highlight Reports; Stage Plans; tolerance monitoring |

### 1.3 PRINCE2 Processes

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         PRINCE2 PROCESS FLOW                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│   ┌─────────────────┐                                                        │
│   │  Pre-Project    │  ← Prepare outline business case                       │
│   └────────┬────────┘                                                        │
│            │                                                                 │
│            ▼                                                                 │
│   ┌─────────────────┐                                                        │
│   │   Starting Up   │  ← Appoint team; prepare PID                           │
│   │    a Project    │                                                        │
│   └────────┬────────┘                                                        │
│            │                                                                 │
│            ▼                                                                 │
│   ┌─────────────────┐                                                        │
│   │   Initiating    │  ← Confirm approach; establish controls                │
│   │    a Project    │                                                        │
│   └────────┬────────┘                                                        │
│            │                                                                 │
│   ┌────────▼────────┐     ┌─────────────────┐                               │
│   │  Directing      │◄────│ Authorize Stage │                               │
│   │   a Project     │     └─────────────────┘                               │
│   └────────┬────────┘                                                        │
│            │                                                                 │
│            ▼                                                                 │
│   ┌─────────────────┐     ┌─────────────────┐                               │
│   │ Controlling     │────►│ Managing Product│                               │
│   │     a Stage     │     │   Delivery      │                               │
│   └────────┬────────┘     └─────────────────┘                               │
│            │                                                                 │
│            ▼                                                                 │
│   ┌─────────────────┐     ┌─────────────────┐                               │
│   │ Managing Stage  │────►│   Stage         │                               │
│   │   Boundaries    │     │   Complete?     │                               │
│   └─────────────────┘     └────────┬────────┘                               │
│                                    │                                        │
│                           YES ─────┘                                        │
│                                    │                                        │
│                           NO ──────┼─────► [Next Stage]                     │
│                                    │                                        │
│                                    ▼                                        │
│                           ┌─────────────────┐                               │
│                           │  Closing        │                               │
│                           │   a Project     │                               │
│                           └─────────────────┘                               │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 2. PROJECT ORGANIZATION

### 2.1 Project Management Structure

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      PROJECT BOARD (Direction Level)                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │                          EXECUTIVE                                   │   │
│  │                    MMF Managing Director                             │   │
│  │                         (or delegate)                                │   │
│  │                                                                      │   │
│  │  Responsibilities:                                                   │   │
│  │  • Accountable for project success                                   │   │
│  │  • Authorize project/stage funding                                   │   │
│  │  • Approve/close project                                             │   │
│  │  • Chair Stage Gate reviews                                          │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                      │                                       │
│           ┌──────────────────────────┴──────────────────────────┐            │
│           │                                                     │            │
│  ┌────────▼─────────┐                              ┌────────────▼─────────┐  │
│  │ SENIOR USER      │                              │ SENIOR SUPPLIER      │  │
│  │ MMF Operations   │                              │ SESB Project Director│  │
│  │ Director         │                              │                      │  │
│  │                  │                              │                      │  │
│  │ Responsibilities:│                              │ Responsibilities:    │  │
│  │ • User needs     │                              │ • Solution quality   │  │
│  │ • User resources │                              │ • Resource provision │  │
│  │ • Benefit accrual│                              │ • Technical viability│  │
│  └──────────────────┘                              └──────────────────────┘  │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                   PROJECT MANAGEMENT (Management Level)                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │                     PROJECT MANAGER (PM)                             │   │
│  │               SESB Lead Project Manager                              │   │
│  │                                                                      │   │
│  │  Responsibilities:                                                   │   │
│  │  • Day-to-day management                                             │   │
│  │  • Stage planning & execution                                        │   │
│  │  • Team coordination                                                 │   │
│  │  • Risk & issue management                                           │   │
│  │  • Reporting to Project Board                                        │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                    DELIVERY LEVEL (Team Managers)                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │  HMS Team    │  │  FFS Team    │  │  WMS Team    │  │  TMS Team    │    │
│  │   Manager    │  │   Manager    │  │   Manager    │  │   Manager    │    │
│  │   (SESB)     │  │   (SESB)     │  │   (SESB)     │  │   (SESB)     │    │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘    │
│                                                                              │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                      │
│  │  FMS Team    │  │ Integration  │  │    Data      │                      │
│  │   Manager    │  │    Team      │  │  Migration   │                      │
│  │   (SESB)     │  │   Manager    │  │   Manager    │                      │
│  └──────────────┘  │   (SESB)     │  │   (SESB)     │                      │
│                    └──────────────┘  └──────────────┘                      │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 RACI Matrix

| Activity | Executive | S. User | S. Supplier | PM | Team Mgr | MMF Users |
|----------|-----------|---------|-------------|-----|----------|-----------|
| **Project Initiation** | A | R | R | R | C | I |
| **Stage Authorization** | A | C | C | R | I | I |
| **Business Case Updates** | A | R | C | R | I | I |
| **Requirements Sign-off** | I | A | C | R | C | R |
| **System Configuration** | I | C | A | R | R | C |
| **UAT Execution** | I | A | C | R | C | R |
| **Go-Live Decision** | A | R | R | R | C | C |
| **Benefits Realization** | A | R | C | R | I | R |

**Legend:** A = Accountable, R = Responsible, C = Consulted, I = Informed

### 2.3 Project Assurance

| Assurance Type | Provider | Scope |
|----------------|----------|-------|
| **User Assurance** | MMF Operations Team | Requirements met; user acceptance achieved |
| **Technical Assurance** | SESB Solution Architect | Technical standards; integration integrity |
| **Business Assurance** | MMF Finance | Budget control; ROI tracking |
| **Quality Assurance** | Independent QA Lead | Testing coverage; defect management |

---

## 3. MANAGEMENT STAGES

### 3.1 Stage Overview

| Stage | Duration | Key Deliverables | Stage Gate |
|-------|----------|------------------|------------|
| **Stage 0: Initiation** | 2 weeks | PID, Project Plan, Stage 1 Plan | SG-0 |
| **Stage 1: Foundation** | 4 weeks | BRS/URS, Architecture, FSD | SG-1 |
| **Stage 2: Configuration** | 6 weeks | Configured Systems, Data Migration | SG-2 |
| **Stage 3: Deployment** | 4 weeks | UAT Complete, Training, Go-Live | SG-3 |
| **Stage 4: Closure** | 2 weeks | Handover, Warranty Start, Lessons Learned | SG-4 |

### 3.2 Stage 0: Project Initiation

**Duration:** 2 weeks  
**Objective:** Establish project foundations and governance

| Product | Owner | Acceptance Criteria |
|---------|-------|---------------------|
| Project Initiation Document (PID) | PM | Approved by Project Board |
| Project Plan (High-level) | PM | Baseline established |
| Stage 1 Plan (Detailed) | PM | Resources allocated |
| Risk Register (Initial) | PM | Top 10 risks identified |
| Communication Plan | PM | Stakeholder map complete |
| Quality Register | QA Lead | Standards defined |

**Activities:**
- Project kick-off meeting
- Stakeholder identification
- Communication channels setup
- Team mobilization
- Initial risk workshop

**Stage Gate 0 (SG-0) Checklist:**
- [ ] PID approved by Executive
- [ ] Funding authorized for Stage 1
- [ ] Project Board members appointed
- [ ] Project Manager appointed
- [ ] Stage 1 plan baselined

---

### 3.3 Stage 1: Foundation

**Duration:** 4 weeks  
**Objective:** Complete requirements and design; freeze scope

| Product | Owner | Acceptance Criteria |
|---------|-------|---------------------|
| Business Requirements Spec (BRS) | Business Analyst | Signed off by MMF Users |
| User Requirements Spec (URS) | Business Analyst | Traceability to SOW 100% |
| System Architecture Design | Solution Architect | Approved by Technical Lead |
| Functional Spec (FSD) | System Analyst | Approved by MMF IT |
| Integration Design | Integration Lead | API specifications complete |
| Data Migration Plan | Data Lead | Migration approach approved |
| Security Design | Security Lead | VAPT plan approved |

**Activities:**
- Requirements workshops (all branches)
- AS-IS process documentation
- TO-BE process design
- System configuration workbook
- Interface mapping
- Data profiling and cleansing plan

**Stage Gate 1 (SG-1) Checklist:**
- [ ] BRS/URS signed by MMF
- [ ] FSD approved by MMF IT
- [ ] Architecture design approved
- [ ] Change freeze on requirements
- [ ] Stage 2 funding authorized
- [ ] Resources confirmed for Stage 2

---

### 3.4 Stage 2: Configuration

**Duration:** 6 weeks  
**Objective:** Build and configure the solution

| Product | Owner | Acceptance Criteria |
|---------|-------|---------------------|
| Configured HMS Module | HMS Team Lead | Unit tests passed |
| Configured FFS Module | FFS Team Lead | Unit tests passed |
| Configured WMS Module | WMS Team Lead | Unit tests passed |
| Configured TMS Module | TMS Team Lead | Unit tests passed |
| Configured FMS Module | FMS Team Lead | Unit tests passed |
| Integration Connections | Integration Lead | All integrations tested |
| Migrated Data (Test) | Data Lead | Data quality >99% |
| UAT Scripts | QA Lead | Reviewed and approved |
| Training Materials | Training Lead | Approved by MMF |

**Activities:**
- System configuration based on FSD
- Custom development (if any)
- Integration development
- Data migration scripts
- Unit testing
- System integration testing
- Test data preparation

**Stage Gate 2 (SG-2) Checklist:**
- [ ] All modules configured
- [ ] Unit tests passed
- [ ] Integration tests passed
- [ ] Data migration validated
- [ ] UAT environment ready
- [ ] Training materials ready
- [ ] Stage 3 funding authorized

---

### 3.5 Stage 3: Deployment

**Duration:** 4 weeks  
**Objective:** Complete UAT, training, and go-live

| Product | Owner | Acceptance Criteria |
|---------|-------|---------------------|
| UAT Completion Report | QA Lead | 95%+ test cases passed |
| Defect Resolution | Dev Team | Critical/High defects resolved |
| User Training Completion | Training Lead | 100% users trained |
| Go-Live Checklist | PM | All items checked |
| Production Deployment | PM | All systems live |
| Post-Go-Live Support | Support Lead | Helpdesk operational |
| Data Migration (Prod) | Data Lead | Cutover completed |

**Activities:**
- UAT execution by MMF users
- Defect fixing and regression testing
- End-user training (all branches)
- Go-Live preparation
- Production deployment
- Hypercare support

**Stage Gate 3 (SG-3) Checklist:**
- [ ] UAT sign-off by MMF
- [ ] All Critical/High defects resolved
- [ ] Training completed for all users
- [ ] Go-Live checklist complete
- [ ] Rollback plan tested
- [ ] Business continuity plan activated
- [ ] Stage 4 funding authorized

---

### 3.6 Stage 4: Closure

**Duration:** 2 weeks  
**Objective:** Complete project handover and warranty transition

| Product | Owner | Acceptance Criteria |
|---------|-------|---------------------|
| Project Closure Report | PM | Approved by Project Board |
| Handover Documentation | PM | Accepted by MMF IT |
| Lessons Learned Report | PM | Captured and shared |
| Benefits Realization Plan | PM | Baseline metrics recorded |
| Warranty Agreement | PM | Signed by both parties |
| Final Account | PM | All invoices reconciled |
| Archive | PM | Project files archived |

**Activities:**
- Outstanding issues resolution
- Knowledge transfer to MMF IT
- Documentation handover
- Warranty period commencement
- Project review and lessons learned
- Team demobilization

**Stage Gate 4 (SG-4) Checklist:**
- [ ] All project objectives achieved
- [ ] Documentation handed over
- [ ] Warranty period started
- [ ] Final payment authorized
- [ ] Project closed in PMO
- [ ] Lessons learned documented

---

## 4. PRODUCT-BASED PLANNING

### 4.1 Product Breakdown Structure (PBS)

```
MMF IT System Implementation
│
├── Management Products
│   ├── Project Initiation Document
│   ├── Business Case
│   ├── Project Plan
│   ├── Risk Register
│   ├── Quality Register
│   ├── Issue Register
│   ├── Stage Plans (5)
│   ├── Highlight Reports
│   └── End Stage Reports
│
├── Specialist Products
│   ├── Requirements
│   │   ├── BRS (Business Requirements)
│   │   ├── URS (User Requirements)
│   │   └── Traceability Matrix
│   │
│   ├── Design
│   │   ├── System Architecture
│   │   ├── FSD (Functional Spec)
│   │   ├── Technical Design
│   │   ├── Interface Design
│   │   └── Security Design
│   │
│   ├── Development
│   │   ├── HMS Configuration
│   │   ├── FFS Configuration
│   │   ├── WMS Configuration
│   │   ├── TMS Configuration
│   │   ├── FMS Configuration
│   │   ├── Integration Code
│   │   └── Custom Reports
│   │
│   ├── Data
│   │   ├── Data Migration Scripts
│   │   ├── Migrated Data (Test)
│   │   ├── Migrated Data (Prod)
│   │   └── Data Quality Reports
│   │
│   ├── Testing
│   │   ├── Unit Test Results
│   │   ├── Integration Test Results
│   │   ├── UAT Scripts
│   │   ├── UAT Results
│   │   └── VAPT Report
│   │
│   ├── Training
│   │   ├── Training Materials
│   │   ├── User Manuals
│   │   ├── Admin Manuals
│   │   └── Training Completion Records
│   │
│   └── Deployment
│       ├── Go-Live Plan
│       ├── Cutover Plan
│       ├── Support Plan
│       └── Handover Documentation
│
└── Quality Products
    ├── Quality Management Strategy
    ├── Configuration Item Records
    ├── Product Descriptions
    └── Approval Records
```

### 4.2 Product Descriptions (Sample)

#### Product: Business Requirements Specification (BRS)

| Attribute | Description |
|-----------|-------------|
| **Purpose** | Document business needs and objectives for the IT system |
| **Composition** | Executive Summary, Business Context, AS-IS Processes, TO-BE Processes, Business Rules, Requirements List |
| **Derivation** | Tender SOW, MMF Business Strategy, Stakeholder Interviews |
| **Format** | MS Word document with diagrams (Visio) |
| **Quality Criteria** | 100% SOW coverage; approved by MMF Operations Director |

#### Product: User Requirements Specification (URS)

| Attribute | Description |
|-----------|-------------|
| **Purpose** | Detailed functional and non-functional requirements |
| **Composition** | User Stories, Use Cases, Functional Requirements, NFRs, UI Mockups |
| **Derivation** | BRS, User Workshops, Process Analysis |
| **Format** | MS Word + Figma mockups |
| **Quality Criteria** | Traceable to BRS; testable; approved by MMF Users |

### 4.3 Work Packages

| Work Package | Manager | Products | Duration | Dependencies |
|--------------|---------|----------|----------|--------------|
| WP-01: Requirements | BA Lead | BRS, URS, Traceability | 3 weeks | None |
| WP-02: Architecture | Solution Architect | Architecture, FSD | 2 weeks | WP-01 |
| WP-03: HMS Build | HMS Team Lead | Configured HMS | 4 weeks | WP-02 |
| WP-04: FFS Build | FFS Team Lead | Configured FFS | 4 weeks | WP-02 |
| WP-05: WMS Build | WMS Team Lead | Configured WMS | 4 weeks | WP-02 |
| WP-06: TMS Build | TMS Team Lead | Configured TMS | 4 weeks | WP-02 |
| WP-07: FMS Build | FMS Team Lead | Configured FMS | 4 weeks | WP-02 |
| WP-08: Integration | Integration Lead | All integrations | 3 weeks | WP-03 to WP-07 |
| WP-09: Data Migration | Data Lead | Migrated data | 3 weeks | WP-08 |
| WP-10: Testing | QA Lead | Test results | 4 weeks | WP-09 |
| WP-11: Training | Training Lead | Training materials | 2 weeks | WP-10 |
| WP-12: Deployment | PM | Live system | 2 weeks | WP-11 |

---

## 5. QUALITY MANAGEMENT

### 5.1 Quality Strategy

**Quality Philosophy:** "Right First Time" - Build quality into the product through prevention, not inspection.

| Quality Level | Activities | Responsibility |
|--------------|------------|----------------|
| **Prevention** | Standards, training, reviews | All team members |
| **Build** | Unit testing, peer review | Developers |
| **Check** | System testing, UAT | QA Team |
| **Assurance** | Audits, VAPT, sign-offs | QA Lead |

### 5.2 Quality Register

| Product | Quality Method | Reviewer | Review Date | Status |
|---------|---------------|----------|-------------|--------|
| BRS | Peer Review + Client Review | MMF Users | TBD | Pending |
| URS | Inspection | System Analyst + MMF IT | TBD | Pending |
| FSD | Technical Review | Solution Architect | TBD | Pending |
| HMS Config | Unit Testing + Demo | HMS Team Lead | TBD | Pending |
| FFS Config | Unit Testing + Demo | FFS Team Lead | TBD | Pending |
| WMS Config | Unit Testing + Demo | WMS Team Lead | TBD | Pending |
| TMS Config | Unit Testing + Demo | TMS Team Lead | TBD | Pending |
| FMS Config | Unit Testing + Demo | FMS Team Lead | TBD | Pending |
| Integration | Integration Testing | Integration Lead | TBD | Pending |
| UAT Scripts | Walkthrough | QA Lead + MMF | TBD | Pending |
| Training Materials | Walkthrough | Training Lead + MMF | TBD | Pending |

### 5.3 Quality Criteria by Product

**BRS/URS Acceptance Criteria:**
- All SOW items traced to requirements
- Requirements are SMART (Specific, Measurable, Achievable, Relevant, Time-bound)
- Business rules clearly defined
- Approved by MMF stakeholders

**System Configuration Acceptance Criteria:**
- Configuration matches FSD
- Unit tests pass (100%)
- No Critical or High defects
- Performance meets targets

**UAT Acceptance Criteria:**
- 100% Critical test cases passed
- 95% High priority test cases passed
- All Critical/High defects resolved
- MMF Business Sign-off obtained

---

## 6. RISK MANAGEMENT

### 6.1 Risk Management Strategy

**Approach:** Proactive risk identification and mitigation; escalate when response exceeds tolerance.

**Risk Tolerance:**
- Schedule: +/- 1 week per stage
- Cost: +/- 10% of stage budget
- Scope: Minor changes only (change control for major)
- Quality: Zero tolerance for Critical defects in production

### 6.2 Risk Register (Top 10)

| ID | Risk Description | Probability | Impact | Score | Owner | Response Strategy |
|----|-----------------|-------------|--------|-------|-------|-------------------|
| R001 | Legacy data quality issues affecting migration | Medium | High | 12 | Data Lead | Mitigate: Data profiling in Week 1; migration dry-runs |
| R002 | Integration complexity with 3rd party systems | Medium | High | 12 | Integration Lead | Mitigate: Early proof-of-concept; sandbox testing |
| R003 | User adoption resistance across 6 branches | Medium | Medium | 9 | Change Mgr | Mitigate: Change management kit; super-user program |
| R004 | Branch-specific requirements creep | High | Medium | 8 | PM | Mitigate: Strict change control; steering committee |
| R005 | MMF resource availability for UAT | Medium | Medium | 6 | MMF PM | Mitigate: Clear commitment letter; dedicated coordinator |
| R006 | Performance issues under peak load | Low | High | 6 | Tech Lead | Mitigate: Performance testing; auto-scaling configured |
| R007 | Security vulnerabilities discovered | Low | High | 6 | Security Lead | Mitigate: VAPT early; continuous monitoring |
| R008 | Training completion delays | Medium | Low | 4 | Training Lead | Mitigate: Online modules; just-in-time training |
| R009 | Go-Live weekend issues | Low | Medium | 3 | PM | Mitigate: Rollback plan; hypercare support |
| R010 | Vendor dependency (critical component) | Low | Medium | 3 | PM | Mitigate: Alternative solutions identified |

**Risk Score:** Probability (1-5) × Impact (1-5)  
**Threshold for escalation:** Score ≥ 12 to Project Board

### 6.3 Risk Response Types

| Type | When Used | Example |
|------|-----------|---------|
| **Avoid** | Threat can be eliminated | Use proven technology instead of experimental |
| **Reduce** | Decrease probability or impact | Additional testing to reduce defect risk |
| **Transfer** | Third party better positioned | Insurance; warranty from vendor |
| **Accept** | Cost of response exceeds impact | Low-impact risks with contingency plan |
| **Exploit** | Enhance opportunity | Deploy early to capture market benefit |

---

## 7. CHANGE CONTROL

### 7.1 Change Control Process

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      CHANGE CONTROL PROCESS                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Step 1: Change Request                                                      │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │ • Originator completes Change Request Form                           │   │
│  │ • Describe change, reason, requestor                                 │   │
│  │ • Submit to Project Manager                                          │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│                                 ▼                                            │
│  Step 2: Initial Assessment                                                  │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │ • PM assesses impact (Time, Cost, Quality, Scope)                    │   │
│  │ • Determine Change Authority level                                   │   │
│  │ • Minor → PM decides; Major → CCB required                           │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│                    ┌────────────┴────────────┐                              │
│           Minor ───┘                         └─── Major                     │
│                    │                                            │            │
│                    ▼                                            ▼            │
│  Step 3A: PM Decision                              Step 3B: CCB Review       │
│  ┌──────────────────────────────┐              ┌────────────────────────┐   │
│  │ PM approves/rejects          │              │ CCB meeting convened   │   │
│  │ Update records               │              │ Full impact assessment │   │
│  │                              │              │ CCB decides            │   │
│  └──────────────┬───────────────┘              └───────────┬────────────┘   │
│                 │                                          │                │
│                 └──────────────────┬───────────────────────┘                │
│                                    │                                         │
│                                    ▼                                         │
│  Step 4: Implementation                                                      │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │ • Update Project Plan                                                │   │
│  │ • Implement approved change                                          │   │
│  │ • Update configuration baseline                                      │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│                                 ▼                                            │
│  Step 5: Review & Close                                                      │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │ • Verify change implemented correctly                                │   │
│  │ • Update Lessons Learned                                             │   │
│  │ • Close change request                                               │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 7.2 Change Authority Levels

| Level | Change Impact | Authority | Decision Time |
|-------|--------------|-----------|---------------|
| **Level 1** | <1 day, <RM 5,000, no scope change | Project Manager | 24 hours |
| **Level 2** | 1-3 days, RM 5,000-20,000, minor scope | Change Control Board | 3 days |
| **Level 3** | >3 days, >RM 20,000, major scope | Project Board | 7 days |

### 7.3 Change Control Board (CCB)

**Members:**
- Chair: MMF Project Sponsor
- Members: MMF IT Lead, MMF Operations Lead, SESB PM, SESB Solution Architect
- Secretary: Project Administrator

**Meeting Frequency:** Ad-hoc for Level 2/3 changes; weekly during peak change periods

---

## 8. PROJECT CONTROLS

### 8.1 Reporting Structure

| Report | Frequency | Audience | Produced By | Content |
|--------|-----------|----------|-------------|---------|
| **Highlight Report** | Weekly | Project Board | PM | Status, progress, risks, issues, next steps |
| **Stage Plan Update** | Bi-weekly | Project Board | PM | Stage progress vs. plan |
| **Risk Register Update** | Weekly | Project Board | PM | New risks, risk status changes |
| **Issue Register Update** | Weekly | Project Board | PM | New issues, resolution progress |
| **Team Status Report** | Daily | PM | Team Managers | Task completion, blockers |
| **Minutes** | Per meeting | All attendees | PM | Decisions, actions, owners |

### 8.2 Highlight Report Template

```
┌─────────────────────────────────────────────────────────────────────┐
│           HIGHLIGHT REPORT - Week Ending [Date]                      │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  Project: MMF IT System Implementation (MMFSB/TD 01/2026)           │
│  Stage: [Current Stage]                                              │
│  Report Date: [Date]                                                 │
│  Reported By: [PM Name]                                              │
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 1. PROJECT STATUS SUMMARY                                        ││
│  │                                                                  ││
│  │ Overall Status: [🟢 On Track / 🟡 At Risk / 🔴 Off Track]       ││
│  │                                                                  ││
│  │ Schedule: [On Plan / +/- X days]                                ││
│  │ Budget: [On Plan / +/- RM X]                                    ││
│  │ Scope: [Stable / Changes under control]                         ││
│  │ Quality: [Meeting standards / Issues noted]                     ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 2. PROGRESS THIS PERIOD                                          ││
│  │                                                                  ││
│  │ Completed:                                                       ││
│  │ • [Deliverable 1]                                                ││
│  │ • [Deliverable 2]                                                ││
│  │                                                                  ││
│  │ In Progress:                                                     ││
│  │ • [Work Package 1] - XX% complete                               ││
│  │ • [Work Package 2] - XX% complete                               ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 3. TOP 3 RISKS                                                   ││
│  │                                                                  ││
│  │ 1. [Risk 1] - Probability/Impact - Status - Action              ││
│  │ 2. [Risk 2] - Probability/Impact - Status - Action              ││
│  │ 3. [Risk 3] - Probability/Impact - Status - Action              ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 4. TOP 3 ISSUES                                                  ││
│  │                                                                  ││
│  │ 1. [Issue 1] - Owner - Target Date - Status                     ││
│  │ 2. [Issue 2] - Owner - Target Date - Status                     ││
│  │ 3. [Issue 3] - Owner - Target Date - Status                     ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 5. NEXT PERIOD PRIORITIES                                        ││
│  │                                                                  ││
│  │ • [Priority 1]                                                   ││
│  │ • [Priority 2]                                                   ││
│  │ • [Priority 3]                                                   ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ 6. DECISIONS REQUIRED                                            ││
│  │                                                                  ││
│  │ • [Decision 1] - By when - From whom                            ││
│  │                                                                  ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  Prepared by: _________________  Date: _________________              │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 9. STAGE GATES & TOLERANCE

### 9.1 Stage Gate Process

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                      STAGE GATE PROCESS                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  STAGE COMPLETION                                                    │   │
│  │  • All stage products completed                                      │   │
│  │  • Quality criteria met                                              │   │
│  │  • Acceptance signed off                                             │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│                                 ▼                                            │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  END STAGE REPORT                                                    │   │
│  │  • Stage performance vs. plan                                        │   │
│  │  • Actual costs vs. budget                                           │   │
│  │  • Quality status                                                    │   │
│  │  • Risk and issue status                                             │   │
│  │  • Lessons learned                                                   │   │
│  │  • Next Stage Plan                                                   │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│                                 ▼                                            │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  STAGE GATE REVIEW MEETING                                           │   │
│  │                                                                      │   │
│  │  Attendees: Project Board (Executive, S. User, S. Supplier)         │   │
│  │  Inputs: End Stage Report, Next Stage Plan, Updated Business Case   │   │
│  │                                                                      │   │
│  │  Agenda:                                                             │   │
│  │  1. Review stage achievements                                        │   │
│  │  2. Confirm quality of deliverables                                  │   │
│  │  3. Review business case viability                                   │   │
│  │  4. Assess risks for next stage                                      │   │
│  │  5. Approve/reject next stage plan                                   │   │
│  │  6. Authorize funding for next stage                                 │   │
│  └──────────────────────────────┬───────────────────────────────────────┘   │
│                                 │                                            │
│              ┌──────────────────┼──────────────────┐                        │
│              │                  │                  │                        │
│              ▼                  ▼                  ▼                        │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐             │
│  │   APPROVE       │  │  CONDITIONAL    │  │    REJECT       │             │
│  │                 │  │                 │  │                 │             │
│  │ Proceed to next │  │ Proceed with    │  │ Return to PM    │             │
│  │ stage with      │  │ conditions met  │  │ for remedial    │             │
│  │ tolerance       │  │ or contingency  │  │ action          │             │
│  │ boundaries      │  │ plan activated  │  │                 │             │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘             │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 9.2 Tolerance Definition

| Tolerance Type | Stage 1 | Stage 2 | Stage 3 | Stage 4 |
|----------------|---------|---------|---------|---------|
| **Time** | +/- 3 days | +/- 1 week | +/- 1 week | +/- 3 days |
| **Cost** | +/- 10% | +/- 10% | +/- 10% | +/- 5% |
| **Scope** | Minor only | Minor only | Bug fixes only | None |
| **Quality** | Zero defects | Zero Critical/High | Zero Critical | Zero Critical |

**Tolerance Breach Response:**
- Within tolerance: Project Manager decides
- Exceeds tolerance: Escalate to Project Board with Exception Report

### 9.3 Exception Report

When tolerance is forecast to be exceeded, the PM submits an Exception Report:

```
┌─────────────────────────────────────────────────────────────────────┐
│                    EXCEPTION REPORT                                  │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  Project: MMF IT System Implementation                               │
│  Exception Type: [Time / Cost / Scope / Quality]                    │
│  Date: [Date]                                                        │
│                                                                      │
│  1. EXCEPTION DESCRIPTION                                            │
│  [Describe the situation causing the exception]                      │
│                                                                      │
│  2. CAUSE                                                            │
│  [Root cause analysis]                                               │
│                                                                      │
│  3. IMPACT                                                           │
│  • Schedule impact: [X days delay]                                   │
│  • Cost impact: [RM X additional]                                    │
│  • Scope impact: [Description]                                       │
│  • Quality impact: [Description]                                     │
│                                                                      │
│  4. OPTIONS CONSIDERED                                               │
│  Option A: [Description] - Pros: [] Cons: []                         │
│  Option B: [Description] - Pros: [] Cons: []                         │
│                                                                      │
│  5. RECOMMENDATION                                                   │
│  [Recommended option with justification]                             │
│                                                                      │
│  6. REVISED PLAN (if applicable)                                     │
│  [Updated Stage Plan or Project Plan]                                │
│                                                                      │
│  PM Signature: _________________  Date: _________________             │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 10. PROJECT CLOSURE

### 10.1 Pre-Closure Checklist

| Item | Responsibility | Status |
|------|---------------|--------|
| All project objectives achieved | PM | ⬜ |
| All products accepted | MMF Users | ⬜ |
| All defects resolved or documented | QA Lead | ⬜ |
| Handover documentation complete | PM | ⬜ |
| Knowledge transfer completed | Team Leads | ⬜ |
| Warranty terms agreed and signed | PM + MMF | ⬜ |
| Final account prepared | PM | ⬜ |
| Lessons learned documented | PM | ⬜ |
| Project files archived | PM | ⬜ |
| Post-project review scheduled | PM | ⬜ |

### 10.2 Project Closure Report

```
┌─────────────────────────────────────────────────────────────────────┐
│                    PROJECT CLOSURE REPORT                            │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  Project: MMF IT System Implementation (MMFSB/TD 01/2026)           │
│  Closure Date: [Date]                                                │
│  Prepared By: [Project Manager]                                      │
│                                                                      │
│  1. PROJECT OBJECTIVES ACHIEVEMENT                                   │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ Objective                    │ Target    │ Actual    │ Status   ││
│  ├─────────────────────────────────────────────────────────────────┤│
│  │ Deploy HMS, FFS, WMS, TMS    │ ✓         │ ✓         │ Achieved ││
│  │ Deploy FMS                   │ ✓         │ ✓         │ Achieved ││
│  │ Complete data migration      │ ✓         │ ✓         │ Achieved ││
│  │ Train all users              │ 100%      │ 100%      │ Achieved ││
│  │ Go-Live on schedule          │ 10 weeks  │ 10 weeks  │ Achieved ││
│  │ Pass UAT                     │ 95%       │ 98%       │ Exceeded ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  2. FINAL ACCOUNT                                                    │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ Category                     │ Budget    │ Actual    │ Variance ││
│  ├─────────────────────────────────────────────────────────────────┤│
│  │ Software Licenses            │ RM X      │ RM X      │ RM X     ││
│  │ Implementation Services      │ RM X      │ RM X      │ RM X     ││
│  │ Training                     │ RM X      │ RM X      │ RM X     ││
│  │ Data Migration               │ RM X      │ RM X      │ RM X     ││
│  │ Contingency                  │ RM X      │ RM X      │ RM X     ││
│  ├─────────────────────────────────────────────────────────────────┤│
│  │ TOTAL                        │ RM X      │ RM X      │ RM X     ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  3. BENEFITS REALIZATION                                             │
│  ┌─────────────────────────────────────────────────────────────────┐│
│  │ Benefit                      │ Expected  │ Actual    │ Date Met ││
│  ├─────────────────────────────────────────────────────────────────┤│
│  │ Reduced manual processing    │ 40%       │ TBD       │ 6 months ││
│  │ Improved billing accuracy    │ 99%       │ TBD       │ 3 months ││
│  │ Faster month-end close       │ 3 days    │ TBD       │ 3 months ││
│  │ Reduced paperwork            │ 70%       │ TBD       │ 1 month  ││
│  └─────────────────────────────────────────────────────────────────┘│
│                                                                      │
│  4. LESSONS LEARNED                                                  │
│  What Went Well:                                                     │
│  • [Lesson 1]                                                        │
│  • [Lesson 2]                                                        │
│                                                                      │
│  What Could Be Improved:                                             │
│  • [Lesson 3]                                                        │
│  • [Lesson 4]                                                        │
│                                                                      │
│  5. OUTSTANDING ITEMS                                                │
│  • [Item 1] - Owner - Target Date                                    │
│  • [Item 2] - Owner - Target Date                                    │
│                                                                      │
│  6. WARRANTY PERIOD                                                  │
│  • Start Date: [Date]                                                │
│  • End Date: [Date + 12 months]                                      │
│  • Support Level: 24/7 Critical, Business Hours Standard             │
│                                                                      │
│  APPROVALS:                                                          │
│                                                                      │
│  Executive: _________________  Date: _________________                │
│                                                                      │
│  Senior User: _________________  Date: _________________              │
│                                                                      │
│  Senior Supplier: _________________  Date: _________________          │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
```

### 10.3 Benefits Realization Review

Post-project review at 3, 6, and 12 months to measure actual benefits:

| Review | Date | Focus | Attendees |
|--------|------|-------|-----------|
| **3-Month** | +3 months | Initial adoption, early wins | PM, MMF Operations |
| **6-Month** | +6 months | Process improvements, efficiency gains | PM, MMF Operations, Finance |
| **12-Month** | +12 months | Full benefits realization, ROI | Project Board |

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |
| Methodology | PRINCE2 (Tailored) |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
