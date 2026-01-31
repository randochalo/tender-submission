# ANNEX F: IMPLEMENTATION PLAN & METHODOLOGY

**Tender Reference:** MMFSB/TD 02/2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Project:** Support IT System (EMS, PS, HRMS)  
**Date:** 31 January 2026

---

## 1. IMPLEMENTATION METHODOLOGY

### 1.1 Hybrid Agile-Waterfall Approach

SESB employs a **hybrid Agile-Waterfall methodology** tailored for enterprise system implementations, combining the structure of Waterfall with the flexibility of Agile.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    HYBRID IMPLEMENTATION METHODOLOGY                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    WATERFALL (Planning & Foundation)                  │  │
│  │                                                                       │  │
│  │   ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐              │  │
│  │   │ Project │──▶│ Business│──▶│ System  │──▶│Technical│              │  │
│  │   │Setup    │   │Analysis │   │ Design  │   │Design   │              │  │
│  │   └─────────┘   └─────────┘   └─────────┘   └─────────┘              │  │
│  │        Week 1-2      Week 3-6      Week 7-8      Week 9-10           │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    AGILE (Development & Delivery)                     │  │
│  │                                                                       │  │
│  │   ┌─────────────────────────────────────────────────────────────┐    │  │
│  │   │                    SPRINT CYCLES (2 weeks each)               │    │  │
│  │   │                                                                 │    │  │
│  │   │   Sprint 1    Sprint 2    Sprint 3    Sprint 4    Sprint 5    │    │  │
│  │   │   ┌─────┐    ┌─────┐    ┌─────┐    ┌─────┐    ┌─────┐        │    │  │
│  │   │   │Dev  │───▶│Dev  │───▶│Dev  │───▶│Dev  │───▶│Dev  │        │    │  │
│  │   │   │Test │    │Test │    │Test │    │Test │    │Test │        │    │  │
│  │   │   └──┬──┘    └──┬──┘    └──┬──┘    └──┬──┘    └──┬──┘        │    │  │
│  │   │      └────┬─────┘          │          │          │            │    │  │
│  │   │           ▼                ▼          ▼          ▼            │    │  │
│  │   │        Review            Review    Review    Review           │    │  │
│  │   │                                                                 │    │  │
│  │   └─────────────────────────────────────────────────────────────┘    │  │
│  │                         Week 11-22                                   │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    WATERFALL (Deployment & Closure)                   │  │
│  │                                                                       │  │
│  │   ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐              │  │
│  │   │   UAT   │──▶│ Go-Live │──▶│Hypercare│──▶│ Project │              │  │
│  │   │Testing  │   │Deploy   │   │Support  │   │ Closure │              │  │
│  │   └─────────┘   └─────────┘   └─────────┘   └─────────┘              │  │
│  │        Week 23-26     Week 27-28    Week 29-32     Week 33           │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Methodology Rationale

| Phase | Method | Rationale |
|-------|--------|-----------|
| **Planning** | Waterfall | Clear requirements, fixed scope, stakeholder alignment |
| **Design** | Waterfall | Architecture decisions need stability |
| **Development** | Agile | Flexibility for changing requirements, early feedback |
| **Testing** | Hybrid | Structured UAT with iterative bug fixes |
| **Deployment** | Waterfall | Controlled rollout with minimal risk |

---

## 2. IMPLEMENTATION TIMELINE

### 2.1 Master Project Schedule

| Phase | Duration | Start Date | End Date | Key Milestones |
|-------|----------|------------|----------|----------------|
| **Phase 1: Initiation** | 2 weeks | Week 1 | Week 2 | Project kick-off, team mobilization |
| **Phase 2: Analysis** | 4 weeks | Week 3 | Week 6 | Requirements sign-off |
| **Phase 3: Design** | 4 weeks | Week 7 | Week 10 | Design approval |
| **Phase 4: Development** | 12 weeks | Week 11 | Week 22 | Sprint deliveries |
| **Phase 5: Testing** | 4 weeks | Week 23 | Week 26 | UAT sign-off |
| **Phase 6: Deployment** | 2 weeks | Week 27 | Week 28 | Go-live |
| **Phase 7: Hypercare** | 4 weeks | Week 29 | Week 32 | Stabilization |
| **Phase 8: Closure** | 1 week | Week 33 | Week 33 | Project handover |
| **TOTAL** | **33 weeks** | **~8 months** | | |

### 2.2 Detailed Gantt Chart

```
Phase / Activity                Week: 1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33
────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
PHASE 1: INITIATION
├─ Project Kick-off            ████
├─ Team Mobilization           ████
├─ Infrastructure Setup        ████
└─ Project Planning            ████

PHASE 2: BUSINESS ANALYSIS
├─ Requirements Workshops         ████████
├─ Current State Analysis         ████████
├─ Future State Design            ████████
├─ Gap Analysis                      ████
└─ Requirements Sign-off                ██

PHASE 3: SYSTEM DESIGN
├─ Solution Architecture             ████████
├─ System Configuration              ████████
├─ Integration Design                ████████
├─ Security Architecture                ████
└─ Design Approval                         ██

PHASE 4: DEVELOPMENT (Agile Sprints)
├─ Sprint 1: Core Setup                    ████
├─ Sprint 2: EMS Development                  ████
├─ Sprint 3: PS Development                      ████
├─ Sprint 4: HRMS Development                       ████
├─ Sprint 5: Integration                               ████
├─ Sprint 6: Enhancements                                 ████
└─ Sprint Reviews                    ████ ████ ████ ████ ████ ████

PHASE 5: TESTING
├─ System Integration Testing                             ████████
├─ Security Testing                                       ████████
├─ Performance Testing                                    ████████
├─ UAT Execution                                              ████████
└─ UAT Sign-off                                                    ██

PHASE 6: DEPLOYMENT
├─ Data Migration                                                  ████
├─ Production Setup                                                ████
├─ User Training                                                   ████
└─ Go-Live                                                            ██

PHASE 7: HYPERCARE
├─ Go-Live Support                                                     ████████
├─ Issue Resolution                                                    ████████
├─ Performance Tuning                                                  ████████
└─ Knowledge Transfer                                                  ████████

PHASE 8: CLOSURE
├─ Final Documentation                                                                  ████
├─ Warranty Handover                                                                    ████
└─ Project Sign-off                                                                          ██

LEGEND: ████ = Work Period
```

---

## 3. PHASE DELIVERABLES

### 3.1 Phase 1: Initiation (Week 1-2)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Project Charter | Signed project authorization | PM |
| Project Plan | Detailed WBS and schedule | PM |
| Communication Plan | Stakeholder communication matrix | PM |
| Risk Register | Initial risk identification | PM |
| Team Mobilization | Resources onboarded | PD |
| Infrastructure Setup | Development environment ready | DevOps |

### 3.2 Phase 2: Business Analysis (Week 3-6)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Requirements Document | Functional & non-functional requirements | BA |
| Process Maps | AS-IS and TO-BE process flows | BA |
| Gap Analysis | Current vs. future state gaps | BA |
| Data Migration Plan | Data cleansing and migration strategy | Architect |
| Interface Requirements | Integration specifications | BA |
| User Stories | Agile user story backlog | BA |

### 3.3 Phase 3: Design (Week 7-10)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Solution Architecture | System architecture document | SA |
| Technical Design | Detailed technical specifications | TLs |
| Database Design | Data model and schema | SA |
| Security Design | Authentication and authorization design | Security |
| UI/UX Design | Screen mockups and prototypes | BA |
| Integration Design | API specifications | SA |

### 3.4 Phase 4: Development (Week 11-22)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| EMS Module | Equipment Management System | EMS Team |
| PS Module | Procurement System | PS Team |
| HRMS Module | HR Management System | HRMS Team |
| Integration Layer | FMS/HMS/API integrations | Integration Team |
| Unit Test Results | Test coverage report | Developers |
| Sprint Demos | Bi-weekly demonstrations | Scrum Master |

### 3.5 Phase 5: Testing (Week 23-26)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Test Plan | Comprehensive test strategy | QA Lead |
| Test Scripts | UAT test cases (105 total) | QA Team |
| SIT Results | System integration test report | QA Lead |
| UAT Results | User acceptance test report | QA Lead |
| Security Report | Vulnerability assessment | Security |
| Performance Report | Load test results | QA Lead |

### 3.6 Phase 6: Deployment (Week 27-28)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Data Migration | Production data migrated | Data Team |
| Production Environment | Live system configured | DevOps |
| Training Completion | All users trained | OCM Lead |
| Go-Live Checklist | Pre-launch verification | PM |
| Rollback Plan | Contingency procedures | DevOps |
| Go-Live Sign-off | Formal launch approval | Steering |

### 3.7 Phase 7: Hypercare (Week 29-32)

| Deliverable | Description | Owner |
|-------------|-------------|-------|
| Support Log | Issue tracking and resolution | Support |
| Bug Fixes | Critical issue resolution | Dev Team |
| Performance Tuning | System optimization | DevOps |
| User Feedback | Enhancement requests | OCM |
| Knowledge Base | Documentation and FAQs | Support |
| Handover Report | Transition to BAU | PM |

---

## 4. RISK MANAGEMENT

### 4.1 Risk Register

| Risk | Probability | Impact | Mitigation Strategy |
|------|-------------|--------|---------------------|
| **Requirements Creep** | High | High | Change control board, scope freeze after design |
| **Resource Availability** | Medium | High | Resource contingency plan, cross-training |
| **Integration Complexity** | Medium | High | Early integration testing, sandbox environments |
| **User Adoption** | Medium | Medium | Change management, comprehensive training |
| **Data Quality Issues** | Medium | High | Data profiling, cleansing before migration |
| **Vendor Delays** | Low | Medium | Vendor SLAs, penalty clauses |
| **Technical Debt** | Medium | Medium | Code reviews, refactoring sprints |

### 4.2 Contingency Plans

| Scenario | Contingency Action |
|----------|-------------------|
| **Schedule Slippage** | Add resources, reduce scope, extend timeline |
| **Budget Overrun** | Phase implementation, defer non-critical features |
| **Key Resource Loss** | Immediate backfill from bench, knowledge transfer |
| **Technical Blocker** | Escalate to architecture board, seek external expertise |
| **UAT Failures** | Extend testing phase, daily bug triage sessions |

---

## 5. QUALITY MANAGEMENT

### 5.1 Quality Gates

| Gate | Criteria | Sign-off Required |
|------|----------|-------------------|
| **Gate 1: Requirements** | 100% requirements documented and approved | MMF Business Owner |
| **Gate 2: Design** | All designs reviewed and approved | Solution Architect |
| **Gate 3: Development** | Code review passed, unit tests >80% coverage | Tech Lead |
| **Gate 4: SIT** | All critical tests passed, zero critical defects | QA Lead |
| **Gate 5: UAT** | UAT sign-off from MMF business users | MMF Project Sponsor |
| **Gate 6: Go-Live** | Go-live checklist 100% complete | Steering Committee |

### 5.2 Quality Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Requirements Traceability** | 100% | All requirements linked to test cases |
| **Code Coverage** | >80% | Unit test coverage report |
| **Defect Density** | <5 per 1000 LOC | Defect tracking system |
| **UAT Pass Rate** | >95% | UAT execution results |
| **User Satisfaction** | >4.0/5.0 | Post-implementation survey |

---

## 6. CHANGE MANAGEMENT

### 6.1 Change Control Process

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    CHANGE CONTROL PROCESS                                   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐  │
│  │   Change    │───▶│   Impact    │───▶│   Change    │───▶│  Approved   │  │
│  │  Requested  │    │ Assessment  │    │  Board Review│   │   Changes   │  │
│  │             │    │ (Effort/$)  │    │             │    │             │  │
│  └─────────────┘    └─────────────┘    └─────────────┘    └──────┬──────┘  │
│       │                                                            │        │
│       │  Rejected                                                  │        │
│       └────────────────────────────────────────────────────────────┘        │
│                                                                             │
│  Change Categories:                                                         │
│  ├─ Type A: Scope Change (>5% effort) → Steering Committee approval        │
│  ├─ Type B: Functional Change → Project Board approval                     │
│  └─ Type C: Minor Change → PM approval                                     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Communication & Training Plan

| Activity | Timing | Audience |
|----------|--------|----------|
| **Project Announcement** | Week 1 | All MMF employees |
| **Department Briefings** | Week 3-6 | Department heads |
| **Champion Training** | Week 24-25 | Super users (15) |
| **Administrator Training** | Week 26-27 | IT team (5) |
| **End-User Training** | Week 27 | All users (227) |
| **Executive Demo** | Week 28 | Leadership team |
| **Post-Go-Live Clinic** | Week 29-32 | All users |

---

## 7. SUCCESS CRITERIA

### 7.1 Project Success Metrics

| Category | Metric | Target | Measurement Method |
|----------|--------|--------|-------------------|
| **Schedule** | On-time delivery | 100% | Actual vs. planned dates |
| **Budget** | On-budget delivery | 100% | Actual vs. approved budget |
| **Scope** | Requirements delivered | 100% | Requirements traceability |
| **Quality** | Defect rate | <2% | Production defect tracking |
| **User Adoption** | System usage | >90% | Login analytics |
| **User Satisfaction** | Satisfaction score | >4.0/5.0 | Post-implementation survey |
| **Performance** | System uptime | 99.5% | Monitoring tools |

### 7.2 Business Success Metrics

| Metric | Baseline | Target (6 months) | Target (12 months) |
|--------|----------|-------------------|-------------------|
| **Maintenance Cost** | RM 2.4M/year | RM 2.0M/year | RM 1.6M/year |
| **Procurement Savings** | 0% | 5% | 8-12% |
| **HR Admin Time** | 40 hrs/week | 20 hrs/week | 15 hrs/week |
| **Equipment Downtime** | 15% | 8% | 4% |
| **Report Generation Time** | 2 days | 4 hours | 1 hour |

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
