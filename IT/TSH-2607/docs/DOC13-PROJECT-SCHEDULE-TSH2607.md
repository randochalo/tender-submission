# DOCUMENT 13: PROPOSED PROJECT SCHEDULE

## TSH-2607: USP Claims Management System (UCMS)
### Tender Reference: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

---

## 1.0 EXECUTIVE SUMMARY

This document presents the comprehensive 67-month project schedule for the USP Claims Management System (UCMS) implementation. The schedule is structured into seven distinct phases, ensuring systematic delivery from inception through extended support.

**Schedule Overview:**
- **Total Duration:** 67 months (5 years, 7 months)
- **Development Phase:** 16 months
- **Testing Phase:** 3 months
- **Deployment Phase:** 1 month
- **Warranty Phase:** 12 months
- **Extended Support:** 36 months

---

## 2.0 HIGH-LEVEL TIMELINE

```
YEAR 1 (2026)          YEAR 2 (2027)          YEAR 3 (2028)
JFMAMJJASOND          JFMAMJJASOND          JFMAMJJASOND
|----|----|            |----|----|            |----|----|
████░░░░░░░░            ░░░░░░░░░░            ░░░░░░░░░░


YEAR 4 (2029)          YEAR 5 (2030)          YEAR 6 (2031)
JFMAMJJASOND          JFMAMJJASOND          JFMAMJJASOND
|----|----|            |----|----|            |----|----|
░░░░░░░░░░░░            ░░░░░░░░░░            ░░░░░░░░░░


LEGEND:
████ Inception & Elaboration (Months 1-4)
████ Construction Phase (Months 5-18)
████ Testing Phase (Months 17-19)
████ Deployment (Months 19-20)
████ Warranty Phase (Months 20-31)
████ Extended Support (Months 32-67)
```

---

## 3.0 DETAILED PROJECT SCHEDULE

### 3.1 Phase Summary

| Phase | Name | Duration | Start Month | End Month | Key Deliverables |
|-------|------|----------|-------------|-----------|------------------|
| 1 | Inception | 2 months | Month 1 | Month 2 | SRS, Project Plan |
| 2 | Elaboration | 2 months | Month 3 | Month 4 | SDD, Prototype |
| 3 | Construction | 14 months | Month 5 | Month 18 | All 10 Modules |
| 4 | Testing | 3 months | Month 17 | Month 19 | UAT, FAT, SIT |
| 5 | Deployment | 1 month | Month 19 | Month 20 | Go-Live |
| 6 | Warranty | 12 months | Month 20 | Month 31 | Support & Fixes |
| 7 | Extended Support | 36 months | Month 32 | Month 67 | Maintenance |

---

### 3.2 Phase 1: Inception (Months 1-2)

#### Month 1

| Week | Activity | Deliverable | Resources |
|------|----------|-------------|-----------|
| 1 | Project Kick-off Meeting | Kick-off Minutes | PM, Sponsor |
| 1 | Team Mobilization | Team Onboarding Complete | HR, PM |
| 1 | Infrastructure Setup | Dev Environment Ready | Infrastructure |
| 2 | Stakeholder Identification | Stakeholder Register | PM, BA |
| 2 | Requirements Workshop 1 | Workshop Report #1 | BA, Solution Architect |
| 2 | Requirements Workshop 2 | Workshop Report #2 | BA, Solution Architect |
| 3 | As-Is Process Documentation | As-Is Process Maps | BA |
| 3 | Gap Analysis | Gap Analysis Report | BA, PM |
| 4 | To-Be Process Design | To-Be Process Maps | BA |
| 4 | Risk Assessment (Initial) | Initial Risk Register | PM |

#### Month 2

| Week | Activity | Deliverable | Resources |
|------|----------|-------------|-----------|
| 5 | Requirements Workshop 3 | Workshop Report #3 | BA |
| 5 | Non-Functional Requirements | NFR Document | Solution Architect |
| 6 | System Requirements Specification | Draft SRS | BA |
| 6 | Security Requirements | Security Requirements Doc | Security Lead |
| 7 | SRS Review & Refinement | Final SRS | BA, PM |
| 7 | Project Initiation Document | PID | PM |
| 8 | SRS Sign-off | Approved SRS | MCMC Sponsor |
| 8 | Phase 1 Gate Review | Phase 1 Approval | Steering Committee |

**Phase 1 Milestone:** Requirements Baseline Established

---

### 3.3 Phase 2: Elaboration (Months 3-4)

#### Month 3

| Week | Activity | Deliverable | Resources |
|------|----------|-------------|-----------|
| 9 | System Architecture Design | Architecture Document | Solution Architect |
| 9 | Technology Stack Finalization | Technology Decision Log | Tech Lead |
| 10 | Database Design | Database Design Document | DBA |
| 10 | Security Architecture | Security Design Document | Security Lead |
| 11 | Interface Design | Interface Design Document | Integration Lead |
| 11 | UI/UX Design | UI Design Specifications | UX Designer |
| 12 | Test Strategy Development | Test Strategy Document | QA Lead |

#### Month 4

| Week | Activity | Deliverable | Resources |
|------|----------|-------------|-----------|
| 13 | System Design Document | Draft SDD | Solution Architect |
| 13 | Prototype Development (Core Screens) | Working Prototype | Development Team |
| 14 | SDD Review & Refinement | Final SDD | Solution Architect |
| 14 | Prototype Demonstration | Prototype Demo | BA, UX Designer |
| 15 | Development Standards | Coding Standards | Tech Lead |
| 15 | CI/CD Pipeline Setup | Build Pipeline | DevOps |
| 16 | Test Environment Setup | Test Environment | Infrastructure |
| 16 | Phase 2 Gate Review | Phase 2 Approval | Project Board |

**Phase 2 Milestone:** Design Baseline Established, Ready for Construction

---

### 3.4 Phase 3: Construction (Months 5-18)

#### Sprint Schedule Overview

```
Sprint Breakdown:

Months 5-6 (Sprints 1-4): Foundation Modules
┌─────────────────────────────────────────────────────────────┐
│ Sprint 1: Master Data - Core Entities                       │
│ Sprint 2: Master Data - Hierarchies & Relationships         │
│ Sprint 3: User Management - Authentication & SSO            │
│ Sprint 4: User Management - Roles & Permissions             │
└─────────────────────────────────────────────────────────────┘

Months 7-8 (Sprints 5-8): Budget Module
┌─────────────────────────────────────────────────────────────┐
│ Sprint 5: Budget - Core Structure & Capped Cost             │
│ Sprint 6: Budget - Site Costing & BOQ                       │
│ Sprint 7: Budget - USPFS Integration                        │
│ Sprint 8: Budget - Reports & Validation                     │
└─────────────────────────────────────────────────────────────┘

Months 9-12 (Sprints 9-16): Claims & Payment Modules
┌─────────────────────────────────────────────────────────────┐
│ Sprint 9:  Claims - Submission Framework                    │
│ Sprint 10: Claims - Advance & Quarterly Processing          │
│ Sprint 11: Claims - Major Contributor & Yearly              │
│ Sprint 12: Claims - Validation & AI Integration             │
│ Sprint 13: Payment - Memo & Workflow                        │
│ Sprint 14: Payment - Digital Signature Integration          │
│ Sprint 15: Payment - Voucher Generation                     │
│ Sprint 16: Payment - Bank Integration & Letters             │
└─────────────────────────────────────────────────────────────┘

Months 13-14 (Sprints 17-20): Reporting & Dashboards
┌─────────────────────────────────────────────────────────────┐
│ Sprint 17: Reports - Standard Report Framework              │
│ Sprint 18: Reports - DUSP & Financial Reports               │
│ Sprint 19: Dashboard - Core Dashboards                      │
│ Sprint 20: Dashboard - Executive & Analytics                │
└─────────────────────────────────────────────────────────────┘

Months 15-16 (Sprints 21-24): Advanced Modules
┌─────────────────────────────────────────────────────────────┐
│ Sprint 21: Self-Service Portal - DUSP Features              │
│ Sprint 22: Self-Service Portal - Subcontractor Features     │
│ Sprint 23: Value-Added Functions - Analytics                │
│ Sprint 24: Value-Added Functions - RPA & Automation         │
└─────────────────────────────────────────────────────────────┘

Months 17-18 (Sprints 25-28): Integration & Finalization
┌─────────────────────────────────────────────────────────────┐
│ Sprint 25: System Integration - USPFS                       │
│ Sprint 26: System Integration - Azure AD & Digital Sign     │
│ Sprint 27: Audit Trail & Security Hardening                 │
│ Sprint 28: System Polish & Performance Optimization         │
└─────────────────────────────────────────────────────────────┘
```

#### Detailed Sprint Schedule

| Sprint | Period | Focus | Key Deliverables |
|--------|--------|-------|------------------|
| 1 | Month 5, Weeks 1-2 | Master Data Core | Project entities, ID structures |
| 2 | Month 5, Weeks 3-4 | Master Data Extended | NOA, VO, Bonds management |
| 3 | Month 6, Weeks 1-2 | User Mgmt - Auth | SSO integration, login |
| 4 | Month 6, Weeks 3-4 | User Mgmt - RBAC | Roles, permissions matrix |
| 5 | Month 7, Weeks 1-2 | Budget Core | Budget structure, capped cost |
| 6 | Month 7, Weeks 3-4 | Budget Detailed | Site costing, BOQ |
| 7 | Month 8, Weeks 1-2 | Budget Integration | USPFS sync, validation |
| 8 | Month 8, Weeks 3-4 | Budget Complete | Budget reports, alerts |
| 9 | Month 9, Weeks 1-2 | Claims Framework | Submission portal |
| 10 | Month 9, Weeks 3-4 | Claims Types | Advance, quarterly claims |
| 11 | Month 10, Weeks 1-2 | Claims Advanced | Major contributor, yearly |
| 12 | Month 10, Weeks 3-4 | Claims Intelligence | AI validation, fraud detection |
| 13 | Month 11, Weeks 1-2 | Payment Core | Memo framework, workflow |
| 14 | Month 11, Weeks 3-4 | Payment Signatures | Digital signature integration |
| 15 | Month 12, Weeks 1-2 | Payment Execution | Voucher, USPFS posting |
| 16 | Month 12, Weeks 3-4 | Payment Complete | Bank integration, letters |
| 17 | Month 13, Weeks 1-2 | Reports Framework | Report engine, templates |
| 18 | Month 13, Weeks 3-4 | Reports Implementation | All standard reports |
| 19 | Month 14, Weeks 1-2 | Dashboards Core | Operational dashboards |
| 20 | Month 14, Weeks 3-4 | Dashboards Advanced | Executive, Excel export |
| 21 | Month 15, Weeks 1-2 | Self-Service DUSP | DUSP portal features |
| 22 | Month 15, Weeks 3-4 | Self-Service Extended | Subcontractor features |
| 23 | Month 16, Weeks 1-2 | VAF - Analytics | Predictive analytics |
| 24 | Month 16, Weeks 3-4 | VAF - Automation | RPA bots, smart workflows |
| 25 | Month 17, Weeks 1-2 | Integration USPFS | Full USPFS connectivity |
| 26 | Month 17, Weeks 3-4 | Integration Security | Azure AD, signature full integration |
| 27 | Month 18, Weeks 1-2 | Audit & Security | Complete audit trail, hardening |
| 28 | Month 18, Weeks 3-4 | System Completion | Performance tuning, documentation |

**Phase 3 Milestone:** All Modules Developed and Integrated

---

### 3.5 Phase 4: Testing (Months 17-19)

#### Testing Schedule

```
┌─────────────────────────────────────────────────────────────┐
│                    TESTING TIMELINE                          │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  MONTH 17                                                    │
│  ├── Week 1-2: Unit Testing Completion                       │
│  ├── Week 2-3: Security Testing (3rd Party)                 │
│  └── Week 3-4: System Integration Testing (SIT) - Phase 1   │
│                                                              │
│  MONTH 18                                                    │
│  ├── Week 1-2: SIT Phase 2                                  │
│  ├── Week 2-3: SIT Completion & Defect Resolution           │
│  └── Week 3-4: User Acceptance Testing (UAT) - Preparation  │
│                                                              │
│  MONTH 19                                                    │
│  ├── Week 1-2: UAT Execution                                │
│  ├── Week 2-3: UAT Defect Resolution                        │
│  └── Week 4: Factory Acceptance Testing (FAT)               │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

| Period | Activity | Duration | Responsible |
|--------|----------|----------|-------------|
| Month 17, Week 1-2 | Complete Unit Testing | 2 weeks | Development Team |
| Month 17, Week 2-3 | Penetration Testing | 1 week | Security Vendor |
| Month 17, Week 3 - Month 18, Week 2 | System Integration Testing | 4 weeks | QA Team |
| Month 18, Week 3-4 | UAT Preparation | 2 weeks | BA, QA |
| Month 19, Week 1-2 | User Acceptance Testing | 2 weeks | MCMC Users |
| Month 19, Week 3 | UAT Issue Resolution | 1 week | Development Team |
| Month 19, Week 4 | Factory Acceptance Testing | 1 week | MCMC IT Team |

**Phase 4 Milestone:** System Tested and Approved for Deployment

---

### 3.6 Phase 5: Deployment (Month 19-20)

#### Deployment Schedule

| Week | Activity | Deliverable | Responsible |
|------|----------|-------------|-------------|
| 1 | Production Environment Setup | Prod Environment Ready | Infrastructure |
| 1 | Security Hardening | Hardened Environment | Security Lead |
| 2 | Data Migration - Extract | Extracted Data | DBA |
| 2 | Data Migration - Transform | Transformed Data | DBA |
| 3 | Data Migration - Load | Loaded Data | DBA |
| 3 | Migration Validation | Migration Report | QA |
| 4 | Application Deployment | Deployed Application | DevOps |
| 4 | Integration Activation | Live Integrations | Integration |
| 4 | User Training Completion | Training Certificates | Training Lead |
| 4 | Go-Live Execution | Live System | PM |
| 4 | Hypercare Start | 24/7 Support Active | Support Team |

**Phase 5 Milestone:** System Live and Operational

---

### 3.7 Phase 6: Warranty (Months 20-31)

#### Warranty Period Schedule

| Quarter | Months | Focus Area | Activities |
|---------|--------|------------|------------|
| Q1 | 20-22 | Hypercare | Intensive support, critical fixes |
| Q2 | 23-25 | Optimization | Performance tuning, enhancements |
| Q3 | 26-28 | Feature Enhancement | Minor features, user requests |
| Q4 | 29-31 | Stabilization | Documentation, knowledge transfer |

**Phase 6 Milestone:** Stable System with Full Documentation

---

### 3.8 Phase 7: Extended Support (Months 32-67)

#### Support Schedule

| Period | Months | Support Level | Activities |
|--------|--------|---------------|------------|
| Year 1 | 32-43 | Standard | Maintenance, patches, helpdesk |
| Year 2 | 44-55 | Standard | Maintenance, minor enhancements |
| Year 3 | 56-67 | Standard | Support, DR testing, handover prep |

**Phase 7 Milestone:** Successful Contract Completion

---

## 4.0 KEY MILESTONES

### 4.1 Milestone Summary

| Milestone ID | Description | Target Date | Success Criteria |
|--------------|-------------|-------------|------------------|
| M1 | Project Kick-off | Month 1, Week 1 | Team mobilized, infrastructure ready |
| M2 | Requirements Baseline | Month 2, Week 4 | SRS approved by MCMC |
| M3 | Design Baseline | Month 4, Week 4 | SDD approved, prototype validated |
| M4 | Foundation Modules | Month 6, Week 4 | Master Data & User Mgmt complete |
| M5 | Financial Modules | Month 8, Week 4 | Budget module complete |
| M6 | Core Claims Module | Month 10, Week 4 | Claims processing complete |
| M7 | Payment Module | Month 12, Week 4 | End-to-end payment flow working |
| M8 | Reporting Complete | Month 14, Week 4 | All reports and dashboards |
| M9 | All Modules Complete | Month 18, Week 4 | All 10 modules developed |
| M10 | Testing Complete | Month 19, Week 4 | UAT, FAT sign-off obtained |
| M11 | Go-Live | Month 20, Week 1 | System in production |
| M12 | Warranty End | Month 31, Week 4 | CFA issued |
| M13 | Project Close | Month 67, Week 4 | Contract completion |

### 4.2 Milestone Gantt Chart

```
Milestone │M1│  │M2│  │M3│  │M4│  │M5│  │M6│  │M7│  │M8│  │M9│  │M10│ │M11│ │M12│ │M13│
          │  │  │  │  │  │  │  │  │  │  │  │  │  │  │  │  │  │  │   │ │   │ │   │ │   │
Month     │1 │2 │3 │4 │5 │6 │7 │8 │9 │10│11│12│13│14│15│16│17│18│19 │20│21-31│32-67│
          └──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴──┴───┴┴─────┴─────┘
          ████ Inception
              ████ Elaboration
                  ████████████████████████████████████████ Construction
                                                          █████ Testing
                                                              █ Deployment
                                                               ████████████ Warranty
                                                                           ████████████████████████████████████ Extended Support

Legend: █ = Active Phase
```

---

## 5.0 RESOURCE LOADING

### 5.1 Resource Allocation by Phase

| Phase | Peak Resources | Average Resources | Key Roles |
|-------|----------------|-------------------|-----------|
| Inception | 5 | 4 | PM, BA, Architect |
| Elaboration | 8 | 6 | PM, Architect, Dev Lead, UX |
| Construction | 25 | 20 | Full Development Team |
| Testing | 15 | 12 | QA, Dev (partial), Security |
| Deployment | 12 | 10 | DevOps, DBA, Trainers |
| Warranty | 8 | 5 | Support, Dev (partial) |
| Extended Support | 5 | 3 | Support Engineers |

---

## 6.0 DEPENDENCIES AND CONSTRAINTS

### 6.1 External Dependencies

| Dependency | Impact | Mitigation |
|------------|--------|------------|
| MCMC Stakeholder Availability | Requirements sign-off delays | Early scheduling, backup contacts |
| USPFS Integration Access | Integration delays | Early engagement, sandbox access |
| Azure AD Setup | SSO implementation | Advance notice to MCMC IT |
| Digital Signature Procurement | Payment module | Early procurement process |

### 6.2 Constraints

| Constraint | Description | Impact |
|------------|-------------|--------|
| Fixed Timeline | 67 months contract duration | Strict milestone adherence |
| User Count | 60 internal + 190 external | Scalability design required |
| Compliance | KRISA, PDPA requirements | Documentation overhead |
| Integration | Must integrate with USPFS | Technical complexity |

---

## 7.0 RISK ADJUSTMENTS

### 7.1 Schedule Risk Mitigation

| Risk | Schedule Buffer | Contingency |
|------|-----------------|-------------|
| Requirements changes | 2 weeks in Month 2 | Change control process |
| Integration delays | 2 weeks in Month 17 | Early prototyping |
| Testing issues | 2 weeks in Month 19 | Parallel defect fixing |
| Deployment issues | 1 week in Month 20 | Rollback plan ready |

---

## 8.0 APPROVAL

This project schedule has been prepared in accordance with the tender requirements and represents our commitment to timely delivery.

**Prepared by:**

_______________________________  
Project Manager

Date: ___________________________

**Reviewed by:**

_______________________________  
Solution Architect

Date: ___________________________

**Approved by:**

_______________________________  
Steering Committee Representative

Date: ___________________________
