# ANNEX T41: PROJECT TIMELINE

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive project timeline for the USP Claims Management System implementation, including phases, milestones, deliverables, and dependencies.

### 1.1 Project Duration
- **Total Duration**: 12 months from contract award
- **Go-Live Target**: Month 12
- **Warranty Period**: Months 13-15

---

## 2. PROJECT PHASES OVERVIEW

### 2.1 Phase Summary

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    PROJECT PHASES - 12 MONTH TIMELINE                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  MONTH:  1   2   3   4   5   6   7   8   9   10  11  12                     │
│         │   │   │   │   │   │   │   │   │   │   │   │                       │
│         ▓▓▓▓▓▓▓▓▓▓░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  INITIATION            │
│         ░░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░░░░░░░░░░░░░░  ANALYSIS & DESIGN      │
│         ░░░░░░░░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓░░░░░░░░░  DEVELOPMENT            │
│         ░░░░░░░░░░░░░░░░░░░░░░░░▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  TESTING                │
│         ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░▓▓▓▓▓▓▓▓▓▓  DEPLOYMENT            │
│         ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░▓▓▓▓▓▓  HYPERCARE             │
│                                                                             │
│  LEGEND: ▓ = Active Phase  ░ = Not Started/Completed                       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Phase Details

| Phase | Duration | Start | End | Key Deliverable |
|-------|----------|-------|-----|-----------------|
| 1. Initiation | 2 months | Month 1 | Month 2 | Project Charter |
| 2. Analysis & Design | 4 months | Month 2 | Month 5 | Design Document |
| 3. Development | 6 months | Month 4 | Month 9 | Working System |
| 4. Testing | 3 months | Month 7 | Month 9 | UAT Sign-off |
| 5. Deployment | 2 months | Month 10 | Month 11 | Production Live |
| 6. Hypercare | 3 months | Month 11 | Month 13 | Stable Operations |
| 7. Warranty | 3 months | Month 13 | Month 15 | Support Handover |

---

## 3. DETAILED PROJECT SCHEDULE

### 3.1 Phase 1: Initiation (Months 1-2)

| Week | Activity | Deliverable | Responsible |
|------|----------|-------------|-------------|
| 1-2 | Kick-off meetings | Meeting minutes | PM |
| 1-2 | Team mobilization | Team roster | PM |
| 2-3 | Requirements workshop | Requirements log | BA |
| 3-4 | Project planning | Project Plan | PM |
| 4-6 | Environment setup | Dev environment | Infrastructure |
| 5-8 | Technical architecture | Architecture doc | Architect |

**Milestone M1: Project Charter Approved (End Month 2)**

### 3.2 Phase 2: Analysis & Design (Months 2-5)

| Week | Activity | Deliverable | Responsible |
|------|----------|-------------|-------------|
| 6-10 | Detailed requirements | BRD | BA |
| 8-12 | UI/UX design | Design prototypes | UX Designer |
| 10-14 | Database design | ER diagrams, schema | DBA |
| 12-16 | Technical design | TDD | Tech Lead |
| 14-18 | Integration design | Interface specs | Integration Lead |
| 16-20 | Security design | Security architecture | Security Lead |

**Milestone M2: Design Review Complete (End Month 5)**

### 3.3 Phase 3: Development (Months 4-9)

| Module | Start | End | Sprints | Team |
|--------|-------|-----|---------|------|
| Core Framework | M4 | M5 | 4 sprints | Platform Team |
| Claim Management | M5 | M7 | 8 sprints | Dev Team A |
| Workflow Engine | M5 | M7 | 8 sprints | Dev Team B |
| Document Management | M6 | M8 | 8 sprints | Dev Team C |
| Payment Integration | M6 | M8 | 6 sprints | Dev Team D |
| Reporting & Analytics | M7 | M9 | 6 sprints | BI Team |
| Self-Service Portal | M7 | M9 | 6 sprints | Dev Team E |
| Integration Layer | M6 | M9 | 10 sprints | Integration Team |

**Sprint Cadence:**
- 2-week sprints
- Sprint Planning: Monday
- Daily Standups: 9:00 AM
- Sprint Review: Friday Week 2
- Retrospective: Friday Week 2

**Milestone M3: Feature Complete (End Month 9)**

### 3.4 Phase 4: Testing (Months 7-9)

| Activity | Start | End | Duration | Responsible |
|----------|-------|-----|----------|-------------|
| Unit Testing | M4 | M9 | Ongoing | Developers |
| Integration Testing | M7 | M8 | 6 weeks | QA Team |
| System Testing (SIT) | M8 | M9 | 4 weeks | QA Team |
| Performance Testing | M8 | M8 | 2 weeks | Perf Team |
| Security Testing (VAPT) | M8 | M9 | 3 weeks | Security |
| UAT Preparation | M8 | M9 | 4 weeks | BA/QA |
| User Acceptance Testing | M9 | M9 | 4 weeks | Business |

**Milestone M4: UAT Sign-off (End Month 9)**

### 3.5 Phase 5: Deployment (Months 10-11)

| Week | Activity | Deliverable | Responsible |
|------|----------|-------------|-------------|
| 1-2 | Production environment setup | Prod ready | Infrastructure |
| 2-3 | Data migration preparation | Migration scripts | DBA |
| 3-4 | Production deployment | Live system | Release Manager |
| 4-6 | User training delivery | Trained users | Training Team |
| 5-6 | Go-live support | Stable operations | Support Team |
| 6-8 | Hypercare initiation | Hypercare active | Support Team |

**Milestone M5: Production Go-Live (Month 11)**

### 3.6 Phase 6: Hypercare (Months 11-13)

| Period | Focus | Support Level |
|--------|-------|---------------|
| Week 1-2 | Stability | 24/7 on-site |
| Week 3-4 | Optimization | 16/5 on-site |
| Month 3 | Transition | Business hours |

---

## 4. KEY MILESTONES

### 4.1 Milestone Summary

| ID | Milestone | Target Date | Success Criteria | Owner |
|----|-----------|-------------|------------------|-------|
| M1 | Project Kick-off | M1 | Team mobilized | PM |
| M2 | Requirements Sign-off | M3 | BRD approved | BA Lead |
| M3 | Design Complete | M5 | All designs approved | Architect |
| M4 | SIT Complete | M8 | All tests passed | QA Lead |
| M5 | UAT Complete | M9 | Business sign-off | BA Lead |
| M6 | Production Ready | M10 | Pre-prod passed | Tech Lead |
| M7 | Go-Live | M11 | System live | PM |
| M8 | Hypercare Complete | M13 | Stable operations | Support Mgr |
| M9 | Project Closure | M15 | Warranty started | PM |

### 4.2 Go/No-Go Criteria

| Gate | Criteria | Decision Maker |
|------|----------|----------------|
| G1: Start Development | Design approved, team ready | Steering Committee |
| G2: Start Testing | Code complete, unit tested | Tech Lead |
| G3: Start UAT | SIT passed, VAPT clear | QA Lead |
| G4: Go-Live | UAT passed, training complete | Steering Committee |

---

## 5. RESOURCE PLAN

### 5.1 Team Allocation

| Role | Month 1-3 | Month 4-6 | Month 7-9 | Month 10-12 |
|------|-----------|-----------|-----------|-------------|
| Project Manager | 1 | 1 | 1 | 1 |
| Business Analyst | 3 | 2 | 2 | 1 |
| Technical Architect | 1 | 1 | 0.5 | 0.5 |
| Developers | 4 | 12 | 12 | 4 |
| QA Engineers | 1 | 2 | 6 | 2 |
| DBA | 1 | 1 | 1 | 1 |
| DevOps | 1 | 2 | 2 | 2 |
| UX Designer | 1 | 1 | 0.5 | 0 |
| Security Specialist | 0.5 | 0.5 | 1 | 0.5 |
| Trainer | 0 | 0 | 1 | 2 |
| Support Staff | 0 | 0 | 0 | 4 |

### 5.2 Peak Resource Period

**Months 7-9: Testing and Stabilization**
- Total team size: 32 FTEs
- Critical for project success
- Extended hours may be required

---

## 6. RISK MITIGATION SCHEDULE

| Risk | Impact | Mitigation | Schedule Buffer |
|------|--------|------------|-----------------|
| Requirements changes | High | Change control | 2 weeks in M6-7 |
| Integration delays | High | Early start | 1 week buffer |
| Resource availability | Medium | Backup resources | Cross-training |
| Technical complexity | Medium | Proof of concepts | Built into design |
| User adoption | Medium | Early involvement | Training in M9-10 |

---

## 7. DELIVERABLES TIMELINE

| Deliverable | Planned Date | Status Gate |
|-------------|--------------|-------------|
| Project Charter | M1 | G0 |
| Requirements Document | M3 | G1 |
| Design Document | M5 | G1 |
| Development Complete | M8 | G2 |
| Test Reports | M8 | G3 |
| Training Materials | M9 | G3 |
| Deployment Plan | M10 | G4 |
| User Manual | M10 | G4 |
| Go-Live | M11 | G4 |
| Warranty Handover | M13 | - |
| Project Closure Report | M15 | - |

---

## 8. GOVERNANCE & REPORTING

### 8.1 Reporting Schedule

| Report | Frequency | Audience | Distribution |
|--------|-----------|----------|--------------|
| Status Report | Weekly | Project Team | Email |
| Executive Summary | Bi-weekly | Steering Committee | Meeting |
| Risk Register | Weekly | PM, Sponsor | Email |
| Budget Report | Monthly | Finance, Sponsor | Meeting |
| Milestone Report | Per milestone | All stakeholders | Meeting |

### 8.2 Steering Committee Meetings

| Meeting | Frequency | Timing | Purpose |
|---------|-----------|--------|---------|
| Steering Committee | Monthly | Last Friday | Strategic decisions |
| Technical Review | Bi-weekly | Wednesday | Technical issues |
| Sprint Review | Every 2 weeks | Friday | Progress demo |
| Go/No-Go | Per gate | As scheduled | Phase decisions |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T34-CHANGE-MGMT | Change Schedule |
| CR-002 | ANNEX-T35-DEPLOYMENT-PLAN | Deployment Timeline |
| CR-003 | ANNEX-T38-TRAINING-PLAN | Training Schedule |
| CR-004 | ANNEX-T40-SUPPORT-PLAN | Support Transition |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
