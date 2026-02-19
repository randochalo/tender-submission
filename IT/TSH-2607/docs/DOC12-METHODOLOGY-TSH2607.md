# DOC12: Project Methodology Statement
## TSH-2607 MCMC UCMS Tender

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Date:** February 2026

---

## 1. METHODOLOGY OVERVIEW

### 1.1 Hybrid Approach: PRINCE2 + Agile SCRUM

We employ a **hybrid project methodology** combining the governance and control of PRINCE2 with the flexibility and iterative delivery of Agile SCRUM.

```
┌─ HYBRID METHODOLOGY FRAMEWORK ────────────────────────────────────────────┐
│                                                                           │
│  STRATEGIC LAYER (PRINCE2)                                                │
│  ├── Project Board oversight                                              │
│  ├── Stage Gate approvals                                                 │
│  ├── Business case management                                             │
│  └── Risk and issue escalation                                            │
│                                                                           │
│  TACTICAL LAYER (Agile SCRUM)                                             │
│  ├── 2-week Sprints                                                       │
│  ├── Daily stand-ups                                                      │
│  ├── Sprint planning/reviews                                              │
│  └── Continuous delivery                                                  │
│                                                                           │
└───────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Why This Approach?

| Aspect | PRINCE2 Benefit | SCRUM Benefit |
|--------|-----------------|---------------|
| Governance | Clear accountability | Team empowerment |
| Documentation | Comprehensive records | Just-enough docs |
| Change Control | Formal process | Adaptive planning |
| Delivery | Stage-wise releases | Continuous value |
| Stakeholder Engagement | Board-level updates | Sprint demos |

---

## 2. PROJECT PHASES

### 2.1 Phase Overview

| Phase | Duration | Methodology Focus | Key Deliverables |
|-------|----------|-------------------|------------------|
| Inception | 2 months | PRINCE2 | Charter, detailed plan |
| Elaboration | 2 months | Hybrid | Architecture, POCs |
| Construction | 12 months | SCRUM | Working software |
| Transition | 3 months | PRINCE2 | UAT, training, deployment |
| Warranty | 12 months | PRINCE2 | Support, fixes |
| Support | 36 months | ITIL | Maintenance |

### 2.2 Inception Phase (PRINCE2)

**Objectives:**
- Establish project governance
- Define detailed requirements
- Confirm technical architecture
- Set up development environment

**Activities:**
- Project initiation
- Stakeholder identification
- Requirements workshops
- Technical POCs
- Infrastructure setup

**Deliverables:**
- Project Initiation Document (PID)
- Detailed SRS and SDS
- Approved architecture
- Development environment ready

### 2.3 Elaboration Phase (Hybrid)

**Objectives:**
- Validate architecture
- Develop proof-of-concepts
- Establish development standards
- Plan construction sprints

**Activities:**
- Architecture validation
- Integration POCs (USPFS)
- Security framework setup
- CI/CD pipeline establishment

### 2.4 Construction Phase (SCRUM)

**Objectives:**
- Deliver working software iteratively
- Continuous stakeholder feedback
- Adapt to changing requirements

**Sprint Structure:**

| Ceremony | Frequency | Duration | Participants |
|----------|-----------|----------|--------------|
| Sprint Planning | Bi-weekly | 4 hours | Team + PO |
| Daily Stand-up | Daily | 15 min | Team |
| Sprint Review | Bi-weekly | 2 hours | Team + Stakeholders |
| Sprint Retrospective | Bi-weekly | 1 hour | Team |
| Backlog Refinement | Weekly | 2 hours | Team + PO |

**Sprint Deliverables:**
- Working software (potentially shippable)
- Updated documentation
- Test results
- Sprint report

### 2.5 Transition Phase (PRINCE2)

**Objectives:**
- Ensure production readiness
- Train users and administrators
- Deploy to production
- Knowledge transfer

**Activities:**
- UAT execution
- Performance testing
- Security hardening
- Training delivery
- Go-live support

---

## 3. GOVERNANCE STRUCTURE

### 3.1 Project Organization

```
                    ┌─ PROJECT BOARD ─┐
                    │  (Steering)     │
                    │  MCMC Directors │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │ PROJECT MANAGER │
                    │  (PRINCE2 PM)   │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
┌────────▼────────┐ ┌────────▼────────┐ ┌────────▼────────┐
│ SCRUM MASTER     │ │ TECH LEAD        │ │ BUSINESS ANALYST│
│ (Delivery)       │ │ (Architecture)   │ │ (Requirements)  │
└────────┬────────┘ └────────┬────────┘ └────────┬────────┘
         │                   │                   │
    ┌────┴────┐         ┌───┴───┐         ┌────┴────┐
    │ DEV TEAM│         │ QA/SEC│         │ TRAINERS│
    └─────────┘         └───────┘         └─────────┘
```

### 3.2 RACI Matrix

| Activity | PM | SM | Tech Lead | BA | Dev Team |
|----------|:--:|:--:|:---------:|:--:|:--------:|
| Sprint Planning | A | R | C | C | R |
| Architecture Decisions | A | C | R | I | C |
| Requirements Sign-off | R | I | C | R | I |
| Code Reviews | I | C | A | I | R |
| UAT Coordination | R | C | C | R | I |
| Deployment | A | C | R | I | C |

---

## 4. QUALITY ASSURANCE

### 4.1 Quality Gates

| Gate | Criteria | Owner |
|------|----------|-------|
| Code Complete | 100% unit test coverage | Tech Lead |
| Integration Ready | All interfaces tested | QA Lead |
| UAT Ready | Zero critical defects | PM |
| Production Ready | Security scan passed | Security Lead |

### 4.2 Definition of Done

For each user story:
- [ ] Code developed and reviewed
- [ ] Unit tests passing (>80% coverage)
- [ ] Integration tests passing
- [ ] Documentation updated
- [ ] PO acceptance
- [ ] No critical/major defects

---

## 5. CHANGE MANAGEMENT

### 5.1 Change Control Process

| Change Type | Authority | Timeline |
|-------------|-----------|----------|
| Sprint scope | Product Owner | Within sprint |
| Technical design | Tech Lead | 2 days |
| Requirements | Change Control Board | 1 week |
| Budget/Schedule | Project Board | 2 weeks |

### 5.2 Change Request Form

All changes require:
1. Change description
2. Business justification
3. Impact assessment
4. Approval signature

---

## 6. RISK MANAGEMENT

### 6.1 Risk Approach

| Risk Level | Response Strategy | Review Frequency |
|------------|-------------------|------------------|
| High | Mitigate/Transfer | Weekly |
| Medium | Mitigate/Accept | Bi-weekly |
| Low | Accept/Monitor | Monthly |

### 6.2 Top Project Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| USPFS integration issues | Medium | High | Early POC, dedicated integration team |
| Resource availability | Medium | Medium | Backup resources, cross-training |
| Scope creep | High | Medium | Strict change control, MVP focus |
| Performance issues | Low | High | Performance testing from sprint 1 |

---

## 7. COMMUNICATION PLAN

| Stakeholder | Communication | Frequency | Method |
|-------------|---------------|-----------|--------|
| Project Board | Status report | Monthly | Meeting + Report |
| MCMC PMO | Sprint demo | Bi-weekly | Demo + Slides |
| End Users | Training updates | Monthly | Email + Portal |
| Development Team | Daily stand-up | Daily | Meeting |

---

## 8. TOOLS & TECHNOLOGY

| Category | Tool | Purpose |
|----------|------|---------|
| Project Management | JIRA | Sprint management |
| Documentation | Confluence | Wiki, specs |
| Code Repository | GitHub | Version control |
| CI/CD | Jenkins | Build automation |
| Testing | Selenium | Test automation |
| Collaboration | MS Teams | Communication |

---

*This Project Methodology Statement is part of TSH-2607 tender submission.*
