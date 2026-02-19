# ANNEX-T08-AGILE-PROJECT-PLAN-TSH2607.md

# ANNEX T8: AGILE PROJECT PLAN
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T8  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [Agile Methodology Overview](#1-agile-methodology-overview)
2. [Project Timeline](#2-project-timeline)
3. [Sprint Structure](#3-sprint-structure)
4. [Release Planning](#4-release-planning)
5. [Resource Allocation](#5-resource-allocation)
6. [Risk Management in Agile](#6-risk-management-in-agile)

---

## 1. AGILE METHODOLOGY OVERVIEW

### 1.1 Agile Approach

The UCMS project follows a **Scrum-based Agile methodology** with the following characteristics:

| Aspect | Implementation |
|--------|----------------|
| Framework | Scrum with SAFe (Scaled Agile Framework) elements |
| Sprint Duration | 2 weeks |
| Team Structure | Cross-functional squads |
| Ceremonies | Daily Standup, Sprint Planning, Review, Retrospective |
| Artifacts | Product Backlog, Sprint Backlog, Burndown Charts |
| Tools | JIRA/Azure DevOps, Confluence, MS Teams |

### 1.2 Agile Ceremonies Schedule

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         AGILE CEREMONIES CALENDAR                                        │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  SPRINT CYCLE (2 Weeks)                                                                  │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  Week 1                        Week 2                                            │   │
│  │  ═══════                       ═══════                                           │   │
│  │                                                                                  │   │
│  │  Mon    Tue    Wed    Thu    Fri    Mon    Tue    Wed    Thu    Fri            │   │
│  │  ───    ───    ───    ───    ───    ───    ───    ───    ───    ───            │   │
│  │                                                                                  │   │
│  │  [Sprint Planning]              [Review]  [Retro]                                │   │
│  │  4 hours                        2 hours   1.5 hours                              │   │
│  │  (Mon AM)                       (Thu PM)  (Fri AM)                               │   │
│  │                                                                                  │   │
│  │  [Daily Standup] every day @ 9:00 AM (15 minutes)                                │   │
│  │                                                                                  │   │
│  │  [Backlog Refinement] Wednesdays 2:00 PM (2 hours)                               │   │
│  │                                                                                  │   │
│  │  [Sprint Demo with MCMC] Every 2nd Thursday 10:00 AM                             │   │
│  │                                                                                  │   │
│  │  ─────────────────────────────────────────────────────                           │   │
│  │                                                                                  │   │
│  │  Development: 8 days                                                             │   │
│  │  Testing: Ongoing throughout                                                     │   │
│  │  Documentation: Parallel track                                                   │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.3 Definition of Done

| Criterion | Description |
|-----------|-------------|
| Code Complete | All code written and peer-reviewed |
| Unit Tests | Unit tests written with >80% coverage |
| Integration Tests | Integration tests passing |
| Code Quality | SonarQube quality gate passed |
| Documentation | Technical documentation updated |
| User Story | Acceptance criteria met and tested |
| UX Review | UI/UX review completed (if applicable) |
| Demo Ready | Feature demonstrable in Sprint Review |
| Security Scan | No critical/high vulnerabilities |
| Performance | Performance benchmarks met |

---

## 2. PROJECT TIMELINE

### 2.1 High-Level Timeline (16 Months Development)

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         UCMS PROJECT TIMELINE (16 Months)                                │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  2026                                          2027                                      │
│  ═══════════════════════════════════════════════════════════════════════════════         │
│  Q1        Q2        Q3        Q4        Q1        Q2                                    │
│  ───       ───       ───       ───       ───       ───                                   │
│                                                                                          │
│  ┌─────────┬─────────┬─────────┬─────────┬─────────┬─────────┐                          │
│  │PHASE 1  │PHASE 2  │PHASE 3  │PHASE 4  │PHASE 5  │PHASE 6  │                          │
│  │Foundation│Core     │Claims   │Payment  │Advanced │Integration│                        │
│  │         │Modules   │Processing│Processing│Features│& UAT    │                          │
│  │M1-M3    │M4-M6    │M7-M9    │M10-M12  │M13-M14  │M15-M16  │                          │
│  └─────────┴─────────┴─────────┴─────────┴─────────┴─────────┘                          │
│                                                                                          │
│  Sprints: S1-S6   S7-S12  S13-S18 S19-S24 S25-S28 S29-S32                               │
│                                                                                          │
│  Milestones:                                                                             │
│  ▲ M3: Foundation Complete (Architecture, DevOps, Core Platform)                        │
│  ▲ M6: Core Modules Ready (User Mgmt, Master Data, Budget)                              │
│  ▲ M9: Claims Processing Live (End-to-end claim submission)                             │
│  ▲ M12: Payment Processing Complete (Digital signatures, USPFS integration)             │
│  ▲ M14: Advanced Features (AI/ML, Analytics, RPA)                                       │
│  ▲ M16: UAT Complete & Go-Live Ready                                                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Detailed Phase Breakdown

| Phase | Duration | Sprints | Focus Areas | Key Deliverables |
|-------|----------|---------|-------------|------------------|
| **Phase 1: Foundation** | 3 months | S1-S6 | Architecture, DevOps, Security framework | Development environment, CI/CD pipeline, security framework |
| **Phase 2: Core Modules** | 3 months | S7-S12 | User Management, Master Data, Budget | Core modules operational, user authentication |
| **Phase 3: Claims Processing** | 3 months | S13-S18 | Claims submission, validation, workflows | End-to-end claim processing |
| **Phase 4: Payment Processing** | 3 months | S19-S24 | Payments, USPFS integration, digital signatures | Payment workflows complete |
| **Phase 5: Advanced Features** | 2 months | S25-S28 | AI/ML, Analytics, RPA, Dashboards | Value-added features |
| **Phase 6: Integration & UAT** | 2 months | S29-S32 | System integration, UAT, performance testing | Production-ready system |

---

## 3. SPRINT STRUCTURE

### 3.1 Sprint Planning Template

```markdown
## SPRINT XX: [Sprint Name]

### Sprint Information
| Attribute | Value |
|-----------|-------|
| Sprint Number | XX |
| Duration | 2 weeks |
| Start Date | DD/MM/YYYY |
| End Date | DD/MM/YYYY |
| Sprint Goal | [One-line goal] |

### Team Capacity
| Role | Count | Capacity (hours) |
|------|-------|------------------|
| Scrum Master | 1 | 80 |
| Product Owner | 1 | 60 |
| Backend Developers | 3 | 240 |
| Frontend Developers | 2 | 160 |
| QA Engineers | 2 | 160 |
| DevOps Engineer | 1 | 80 |
| UX Designer | 1 | 40 |
| **Total Capacity** | **11** | **820 hours** |

### Sprint Backlog
| ID | User Story | Points | Assignee | Status |
|----|------------|--------|----------|--------|
| US-XXX | As a [role], I want [feature] so that [benefit] | 5 | [Name] | To Do |
| US-XXX | As a [role], I want [feature] so that [benefit] | 8 | [Name] | To Do |
| US-XXX | As a [role], I want [feature] so that [benefit] | 3 | [Name] | To Do |

### Sprint Burndown Target
- Total Story Points: XX
- Target Burndown: Linear progression to 0 by Sprint end

### Risks and Impediments
| Risk | Impact | Mitigation | Owner |
|------|--------|------------|-------|
| | | | |

### Definition of Done
- [ ] All stories meet acceptance criteria
- [ ] Code reviewed and merged
- [ ] Unit tests >80% coverage
- [ ] QA testing complete
- [ ] Documentation updated
```

### 3.2 Sample Sprint Schedule

| Sprint | Theme | Key Deliverables | Story Points | MCMC Demo |
|--------|-------|------------------|--------------|-----------|
| S1 | Project Setup | Dev environment, CI/CD, base architecture | 45 | Architecture walkthrough |
| S2 | Core Platform | Database schema, API framework, security | 50 | API demo |
| S3 | User Management | Authentication, user profiles, RBAC | 48 | Login demo |
| S4 | Master Data (Part 1) | Project management, DUSP management | 52 | Master data demo |
| S5 | Master Data (Part 2) | NOA, Contract, VO, EOT management | 50 | Workflow demo |
| S6 | Budget Module | Budget allocation, tracking, integration | 48 | Budget module demo |
| S7 | Claims Foundation | Claim models, document management | 50 | Document upload demo |
| S8 | Quarterly Claims | Quarterly claim submission workflow | 52 | Quarterly claim demo |
| S9 | Advance Claims | Advance claim with recovery tracking | 48 | Advance claim demo |
| S10 | Yearly Claims | Yearly claim with auditor template | 50 | Yearly claim demo |
| S11 | Approval Workflow | 3-level approval with notifications | 52 | Approval flow demo |
| S12 | Payment Foundation | Payment memo, voucher preparation | 50 | Payment prep demo |
| S13 | Digital Signatures | Integration with signature provider | 48 | Digital signature demo |
| S14 | USPFS Integration | Voucher creation, payment sync | 52 | USPFS integration demo |
| S15 | Reporting | Standard reports, export functions | 50 | Reports demo |
| S16 | Dashboard | Real-time dashboard, KPIs | 48 | Dashboard demo |
| S17 | AI/OCR Integration | Document OCR, fraud detection | 52 | AI features demo |
| S18 | RPA Integration | Automated data extraction | 50 | RPA demo |
| S19 | Analytics | Predictive analytics, trends | 48 | Analytics demo |
| S20 | Self-Service Portal | DUSP portal enhancements | 52 | Portal demo |
| S21 | Mobile App | Mobile responsive features | 50 | Mobile demo |
| S22 | Integration Testing | End-to-end integration | 48 | Integration test demo |
| S23 | Performance Tuning | Optimization, load testing | 52 | Performance demo |
| S24 | Security Hardening | Security review, penetration testing | 50 | Security demo |
| S25 | UAT Support | Bug fixes, UAT support | 48 | UAT progress |
| S26 | Bug Fixes | Critical bug resolution | 52 | Bug fix demo |
| S27 | Final Polish | UI/UX refinements | 50 | Final UI demo |
| S28 | Go-Live Prep | Deployment preparation | 48 | Go-live readiness |

---

## 4. RELEASE PLANNING

### 4.1 Release Schedule

| Release | Version | Date | Scope | Environment |
|---------|---------|------|-------|-------------|
| R0 (Internal) | 0.1.0 | M3 | Core platform, basic functionality | Development |
| R1 (Alpha) | 0.5.0 | M6 | Core modules, limited features | Staging |
| R2 (Beta) | 0.8.0 | M9 | Full claims processing | Staging |
| R3 (RC1) | 0.9.0 | M12 | Payment processing complete | Staging |
| R4 (RC2) | 0.95.0 | M14 | All features, bug fixes | Staging |
| R5 (GA) | 1.0.0 | M16 | Production release | Production |

### 4.2 Release Criteria

| Criterion | R1 (Alpha) | R2 (Beta) | R3 (RC) | R5 (GA) |
|-----------|-----------|-----------|---------|---------|
| Feature Complete | 40% | 70% | 95% | 100% |
| Unit Test Coverage | 70% | 80% | 85% | 85% |
| Critical Bugs | <10 | <5 | 0 | 0 |
| High Bugs | <20 | <10 | <5 | 0 |
| Performance | Baseline | +20% | +30% | +30% |
| Security Scan | Major only | Medium+ | All | All |
| Documentation | Draft | Review | Complete | Complete |
| UAT Complete | No | Partial | Yes | Yes |

---

## 5. RESOURCE ALLOCATION

### 5.1 Team Structure

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         UCMS PROJECT TEAM STRUCTURE                                      │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│                         ┌─────────────────┐                                              │
│                         │  Project Manager│                                              │
│                         │  (Scrum Master) │                                              │
│                         └────────┬────────┘                                              │
│                                  │                                                       │
│        ┌─────────────────────────┼─────────────────────────┐                            │
│        │                         │                         │                            │
│        ▼                         ▼                         ▼                            │
│  ┌─────────────┐           ┌─────────────┐           ┌─────────────┐                    │
│  │  Product    │           │  Technical  │           │   QA/       │                    │
│  │  Owner      │           │  Architect  │           │   DevOps    │                    │
│  │  (Business) │           │             │           │   Lead      │                    │
│  └──────┬──────┘           └──────┬──────┘           └──────┬──────┘                    │
│         │                         │                         │                           │
│  ┌──────┴──────┐           ┌──────┴──────┐           ┌──────┴──────┐                   │
│  │             │           │             │           │             │                   │
│  ▼             ▼           ▼             ▼           ▼             ▼                   │
│ ┌───┐  ┌───┐  ┌───┐  ┌───┐ ┌───┐  ┌───┐  ┌───┐  ┌───┐  ┌───┐  ┌───┐                   │
│ │BA │  │UX │  │BE │  │FE │ │DB │  │INT│  │SEC│  │QA │  │AUTO│  │DEV │                   │
│ │x2 │  │x1 │  │x3 │  │x2 │ │x1 │  │x1 │  │x1 │  │x2 │  │x1 │  │x1 │                   │
│ └───┘  └───┘  └───┘  └───┘ └───┘  └───┘  └───┘  └───┘  └───┘  └───┘                   │
│                                                                                          │
│  Legend:                                                                                 │
│  BA = Business Analyst, UX = UX Designer, BE = Backend Developer                        │
│  FE = Frontend Developer, DB = Database Admin, INT = Integration Specialist             │
│  SEC = Security Engineer, QA = QA Engineer, AUTO = Automation Engineer                  │
│  DEV = DevOps Engineer                                                                   │
│                                                                                          │
│  Total Team Size: 16 members                                                             │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Resource Loading by Phase

| Phase | Duration | Team Size | Effort (Person-Months) |
|-------|----------|-----------|----------------------|
| Phase 1: Foundation | 3 months | 10 | 30 |
| Phase 2: Core Modules | 3 months | 14 | 42 |
| Phase 3: Claims Processing | 3 months | 16 | 48 |
| Phase 4: Payment Processing | 3 months | 16 | 48 |
| Phase 5: Advanced Features | 2 months | 14 | 28 |
| Phase 6: Integration & UAT | 2 months | 16 | 32 |
| **Total** | **16 months** | **-** | **228** |

---

## 6. RISK MANAGEMENT IN AGILE

### 6.1 Agile Risk Management Approach

| Risk Type | Detection | Mitigation Strategy |
|-----------|-----------|---------------------|
| Technical | Sprint retrospectives, code reviews | Spike stories, architectural runway |
| Scope | Sprint planning, backlog grooming | Prioritization, MVP definition |
| Schedule | Burndown charts, velocity tracking | Buffer sprints, scope adjustment |
| Quality | Definition of Done, test automation | Continuous integration, TDD |
| Resources | Daily standups, capacity planning | Cross-training, contractor backup |

### 6.2 Risk Burndown

```
Risk Level
   High │╲
        │ ╲
        │  ╲
        │   ╲
 Medium │    ╲
        │     ╲
        │      ╲
        │       ╲________
    Low │_________________▶ Time
        Start    Mid      End
        
        Risk mitigation through:
        • Early identification in retrospectives
        • Proactive mitigation stories
        • Continuous monitoring
```

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Project Management Team | Initial plan |

---

**END OF ANNEX T8**
