# ANNEX F: IMPLEMENTATION PLAN & METHODOLOGY

**Tender Reference:** T/SUKSEL/04-2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Project:** Sistem ePINGAT Negeri Selangor  
**Date:** 31 January 2026

---

## 1. IMPLEMENTATION METHODOLOGY

### 1.1 Agile-Waterfall Hybrid Approach

SESB employs an **Agile-Waterfall Hybrid methodology** for this project, combining the structure of Waterfall phases with the flexibility of Agile sprints within each phase.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AGILE-WATERFALL HYBRID METHODOLOGY                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐     │
│  │   PHASE 1   │──▶│   PHASE 2   │──▶│   PHASE 3   │──▶│   PHASE 4   │     │
│  │ Requirements│   │   Design    │   │ Development │   │  Deployment │     │
│  │  (M1-2)     │   │  (M3-4)     │   │  (M5-14)    │   │  (M15-18)   │     │
│  └─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘     │
│        │                 │                 │                 │              │
│        ▼                 ▼                 ▼                 ▼              │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Within Development Phase: 2-week sprints with planning, review,    │   │
│  │  retrospective                                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Project Phases Overview

| Phase | Timeline | Duration | Key Deliverables |
|-------|----------|----------|------------------|
| **Phase 1** | Month 1-2 | 2 months | URS, SRS, Project Plan |
| **Phase 2** | Month 3-4 | 2 months | Design documents, Prototype |
| **Phase 3** | Month 5-14 | 10 months | Developed system, Testing |
| **Phase 4** | Month 15-18 | 4 months | Deployment, UAT, Training |
| **Phase 5** | Month 19-27 | 9 months | Warranty, Support |

---

## 2. DETAILED PROJECT TIMELINE (18 Months Development + 9 Months Warranty)

### 2.1 Phase 1: Requirements Analysis (Month 1-2)

| Week | Activity | Deliverable |
|------|----------|-------------|
| 1-2 | Project kick-off, team mobilization | Kick-off meeting minutes |
| 3-4 | Stakeholder interviews, requirement gathering | Interview reports |
| 5-6 | URS document preparation | User Requirement Specification |
| 7-8 | SRS document preparation, review | System Requirement Specification |

**Phase 1 Deliverables:**
- User Requirement Specification (URS)
- System Requirement Specification (SRS)
- Project Plan with detailed timeline
- Risk Management Plan

### 2.2 Phase 2: System Design (Month 3-4)

| Week | Activity | Deliverable |
|------|----------|-------------|
| 9-10 | System architecture design | Architecture Document |
| 11-12 | Database design (ERD, Data Dictionary) | Database Design Document |
| 13-14 | UI/UX design, wireframes | UI Mockups, Prototype |
| 15-16 | Technical design review, approval | Approved Design Documents |

**Phase 2 Deliverables:**
- System Architecture Document
- Database Design (ERD, Data Dictionary, DFD)
- UI/UX Design and Prototype
- Technical Specifications

### 2.3 Phase 3: Development (Month 5-14)

Development will follow **2-week Agile Sprints**:

| Sprint | Timeline | Focus Area |
|--------|----------|------------|
| Sprint 1-2 | Month 5 | Core framework, Authentication |
| Sprint 3-4 | Month 6 | User Management, RBAC |
| Sprint 5-6 | Month 7 | Modul Laman Utama, Dashboard |
| Sprint 7-8 | Month 8 | Modul Permohonan (Nomination) |
| Sprint 9-10 | Month 9 | Modul Pengurusan Permohonan |
| Sprint 11-12 | Month 10 | Modul Penilaian dan Tapisan |
| Sprint 13-14 | Month 11 | Modul Pengurusan Majlis |
| Sprint 15-16 | Month 12 | Modul Laporan, Admin |
| Sprint 17-18 | Month 13 | Integration, Fungsi Backup |
| Sprint 19-20 | Month 14 | System Integration Testing |

**Phase 3 Deliverables:**
- Fully developed system
- Unit Test Reports
- Integration Test Reports
- Source Code with documentation

### 2.4 Phase 4: Deployment & UAT (Month 15-18)

| Week | Activity | Deliverable |
|------|----------|-------------|
| 57-58 | Production environment setup | Live environment ready |
| 59-60 | System deployment | Deployed system |
| 61-66 | User Acceptance Testing | UAT Sign-off |
| 67-68 | Bug fixes, refinements | Stabilized system |
| 69-70 | User training | Training completion certificates |
| 71-72 | Go-live preparation | Go-live checklist complete |

**Phase 4 Deliverables:**
- Deployed system in production
- UAT Sign-off Document
- Training Completion Reports
- User Manuals (Bahasa Malaysia)
- Technical Documentation
- Go-Live Approval

### 2.5 Phase 5: Warranty & Support (Month 19-27)

| Period | Activity |
|--------|----------|
| Month 19-21 | Hypercare support, issue resolution |
| Month 22-24 | Regular maintenance, minor enhancements |
| Month 25-27 | Final warranty period, knowledge transfer |

**Warranty Deliverables:**
- Monthly support reports
- Bug fix releases
- System optimization
- Final project handover

---

## 3. PROJECT GANTT CHART (Simplified)

```
Activity                    M1 M2 M3 M4 M5 M6 M7 M8 M9 M10 M11 M12 M13 M14 M15 M16 M17 M18
                           ─────────────────────────────────────────────────────────────────
Phase 1: Requirements      ████████
  - URS Preparation        ████
  - SRS Preparation            ████
                           
Phase 2: Design                 ████████
  - Architecture                 ████
  - Database                         ████
  - UI/UX Design                         ████
                           
Phase 3: Development                    ████████████████████████████████████████████
  - Core/Framework                      ████████
  - User/Auth Module                            ████████
  - Laman Utama/Dashboard                             ████████
  - Modul Permohonan                                        ████████
  - Pengurusan Permohonan                                           ████████
  - Penilaian/Tapisan                                                     ████████
  - Majlis Pengurniaan                                                            ████████
  - Laporan/Pentadbir                                                                   ████████
  - Integration/Testing                                                                         ████████
                           
Phase 4: Deployment                                                                                    ████████████████
  - Environment Setup                                                                                    ████
  - Deployment                                                                                               ████
  - UAT                                                                                                          ████████████
  - Training                                                                                                                 ████████
  - Go-Live                                                                                                                          ████

Legend: ████ = Work Period
```

---

## 4. QUALITY ASSURANCE PLAN

### 4.1 Testing Strategy

| Test Type | Timing | Responsibility | Tools |
|-----------|--------|----------------|-------|
| **Unit Testing** | During development | Developers | PHPUnit |
| **Integration Testing** | End of each sprint | QA Team | Laravel Dusk |
| **System Testing** | Month 14 | QA Team | Manual + Automated |
| **UAT** | Month 15-16 | Client + SESB | Manual testing |
| **Security Testing** | Month 13-14 | Security Team | Burp Suite, OWASP ZAP |
| **Performance Testing** | Month 14 | DevOps | Apache JMeter |

### 4.2 Quality Gates

| Gate | Criteria | Sign-off |
|------|----------|----------|
| **Gate 1** | URS/SRS approved by client | Client Representative |
| **Gate 2** | Design documents approved | Solution Architect |
| **Gate 3** | Code review passed, unit tests >80% | Tech Lead |
| **Gate 4** | System testing passed | QA Lead |
| **Gate 5** | UAT sign-off by client | Client Representative |
| **Gate 6** | Go-live approved | Project Director |

---

## 5. RISK MANAGEMENT

### 5.1 Risk Register

| Risk | Probability | Impact | Mitigation Strategy |
|------|-------------|--------|---------------------|
| **Scope Creep** | High | High | Strict change control process |
| **Resource Availability** | Medium | High | Resource backup plan, cross-training |
| **Technical Complexity** | Medium | Medium | Proof of concepts, expert consultation |
| **User Adoption** | Medium | Medium | Early user engagement, training |
| **Integration Issues** | Low | High | Thorough interface analysis |

### 5.2 Contingency Plans

| Scenario | Response |
|----------|----------|
| **Schedule Delay** | Add resources, reduce scope, extend timeline |
| **Budget Overrun** | Phase implementation, defer non-critical features |
| **Key Resource Loss** | Immediate backfill, knowledge transfer |
| **Technical Blocker** | Escalate to architecture board |

---

## 6. CHANGE MANAGEMENT

### 6.1 Training Plan

| Audience | Training Content | Duration | Timing |
|----------|------------------|----------|--------|
| **Administrator** | System administration, user management | 3 days | Month 17 |
| **Urus Setia** | Application processing, workflow management | 2 days | Month 17 |
| **End Users** | Portal usage, nomination submission | 1 day | Month 18 |
| **IT Support** | Troubleshooting, maintenance | 2 days | Month 17 |

### 6.2 Communication Plan

| Stakeholder | Frequency | Channel | Content |
|-------------|-----------|---------|---------|
| **Steering Committee** | Monthly | Meeting | Strategic updates |
| **Project Board** | Weekly | Email + Meeting | Progress, issues |
| **Development Team** | Daily | Stand-up | Task coordination |
| **Client Users** | Bi-weekly | Demo | Sprint reviews |

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
