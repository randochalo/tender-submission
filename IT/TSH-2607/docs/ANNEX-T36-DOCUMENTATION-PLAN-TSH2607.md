# ANNEX T36: DOCUMENTATION PLAN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the documentation plan for the USP Claims Management System, ensuring comprehensive, accurate, and accessible documentation is delivered for all system components, processes, and user needs.

### 1.1 Documentation Standards
- **ISO/IEC/IEEE 26514**: Systems and software documentation
- **ITIL 4**: Service management documentation
- **KRISA Section 18**: ICT documentation requirements

---

## 2. DOCUMENTATION CATEGORIES

### 2.1 Documentation Matrix

| Category | Audience | Format | Delivery |
|----------|----------|--------|----------|
| Technical | IT Staff, Developers | Markdown/PDF | Repository |
| User | End Users, SPs | PDF/Online Help | Portal |
| Administrative | System Administrators | PDF/Wiki | SharePoint |
| Training | Learners, Trainers | PPT/PDF/eLearning | LMS |
| Compliance | Auditors, Regulators | PDF | Document Control |
| Project | Stakeholders, Management | PPT/PDF | Project Share |

### 2.2 Documentation Inventory

| Doc ID | Document Name | Type | Owner | Frequency |
|--------|---------------|------|-------|-----------|
| DOC-001 | System Architecture | Technical | Architect | Per major release |
| DOC-002 | Installation Guide | Technical | DevOps | Per release |
| DOC-003 | API Reference | Technical | Development | Continuous |
| DOC-004 | Database Schema | Technical | DBA | Per schema change |
| DOC-005 | User Manual | User | Technical Writer | Quarterly |
| DOC-006 | Admin Guide | Administrative | System Admin | Per release |
| DOC-007 | Troubleshooting Guide | Administrative | Support | Continuous |
| DOC-008 | Training Materials | Training | Trainer | Per update |
| DOC-009 | SOPs | Compliance | Process Owner | Annual |
| DOC-010 | System Contracts | Compliance | Legal | As needed |

---

## 3. TECHNICAL DOCUMENTATION

### 3.1 Architecture Documentation

| Section | Content | Format |
|---------|---------|--------|
| Overview | System context, high-level architecture | Diagrams + Text |
| Components | Module descriptions, interfaces | Markdown |
| Data Flow | Information flow between components | Data flow diagrams |
| Integration | External system connections | Integration diagrams |
| Security | Security architecture, controls | Security diagrams |
| Deployment | Infrastructure, deployment model | Architecture diagrams |

### 3.2 Development Documentation

```
┌─────────────────────────────────────────────────────────────────┐
│              TECHNICAL DOCUMENTATION STRUCTURE                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  /docs                                                          │
│  ├── /architecture                                              │
│  │   ├── system-overview.md                                     │
│  │   ├── component-diagrams/                                    │
│  │   ├── data-flow/                                             │
│  │   └── security-architecture.md                               │
│  │                                                              │
│  ├── /development                                               │
│  │   ├── coding-standards.md                                    │
│  │   ├── api-reference/                                         │
│  │   ├── database/                                              │
│  │   │   ├── schema.md                                          │
│  │   │   ├── er-diagrams/                                       │
│  │   │   └── migration-scripts/                                 │
│  │   └── deployment-guide.md                                    │
│  │                                                              │
│  ├── /operations                                                │
│  │   ├── installation-guide.md                                  │
│  │   ├── configuration-guide.md                                 │
│  │   ├── monitoring-guide.md                                    │
│  │   ├── backup-recovery.md                                     │
│  │   └── troubleshooting.md                                     │
│  │                                                              │
│  └── /release-notes                                             │
│      ├── changelog.md                                            │
│      └── version-history/                                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.3 API Documentation

| Specification | Standard | Tool | Output |
|---------------|----------|------|--------|
| REST API | OpenAPI 3.0 | Swagger | Interactive docs |
| GraphQL | GraphQL Schema | GraphiQL | Explorer |
| WebSocket | AsyncAPI | AsyncAPI Generator | Docs |

---

## 4. USER DOCUMENTATION

### 4.1 User Manual Structure

| Chapter | Content | Format |
|---------|---------|--------|
| 1. Introduction | System overview, navigation | PDF + Online |
| 2. Getting Started | Login, dashboard, settings | PDF + Video |
| 3. Claim Submission | Step-by-step guide | PDF + Interactive |
| 4. Document Management | Upload, organize, view | PDF + Video |
| 5. Tracking & Monitoring | Status, notifications | PDF + Online |
| 6. Reporting | Reports, exports | PDF + Video |
| 7. Troubleshooting | Common issues, FAQs | Online help |
| 8. Glossary | Terms and definitions | Online help |

### 4.2 Role-Based Guides

| Role | Document | Focus |
|------|----------|-------|
| Claims Officer | Processing Guide | Review, approval, workflow |
| Finance Officer | Payment Guide | Payment processing, reconciliation |
| Manager | Oversight Guide | Dashboards, reporting, exceptions |
| System Admin | Admin Guide | Configuration, user management |
| Service Provider | SP User Guide | Submission, tracking, communication |

### 4.3 Online Help System

| Feature | Description | Implementation |
|---------|-------------|----------------|
| Context-Sensitive Help | Help relevant to current page | Tooltips, popovers |
| Search | Full-text search | Elasticsearch |
| Interactive Guides | Step-by-step walkthroughs | WalkMe/Pendo |
| Video Tutorials | Visual demonstrations | Embedded videos |
| FAQ | Common questions | Expandable sections |
| Feedback | Rate help usefulness | Star ratings |

---

## 5. ADMINISTRATIVE DOCUMENTATION

### 5.1 System Administration Guide

| Section | Topics |
|---------|--------|
| Installation | Prerequisites, installation, verification |
| Configuration | System settings, parameters, customization |
| User Management | Creating users, roles, permissions |
| Monitoring | Health checks, metrics, alerts |
| Maintenance | Scheduled tasks, cleanup, optimization |
| Backup/Recovery | Backup procedures, restore, DR |
| Troubleshooting | Common issues, logs, diagnostics |
| Upgrade | Version upgrades, patching |

### 5.2 Standard Operating Procedures (SOPs)

| SOP ID | Title | Purpose |
|--------|-------|---------|
| SOP-001 | New User Onboarding | Standard user creation process |
| SOP-002 | Password Reset | Secure password reset procedure |
| SOP-003 | Access Revocation | Terminating user access |
| SOP-004 | Incident Response | Handling system incidents |
| SOP-005 | Change Request | System change procedure |
| SOP-006 | Backup Verification | Validating backup integrity |
| SOP-007 | Performance Tuning | Optimization procedures |
| SOP-008 | Security Patch | Applying security updates |

---

## 6. TRAINING DOCUMENTATION

### 6.1 Training Materials

| Material | Format | Audience | Duration |
|----------|--------|----------|----------|
| Instructor Guide | PDF | Trainers | Reference |
| Participant Workbook | PDF | Learners | Course companion |
| Slide Deck | PPT | All | 3 days |
| Exercise Guide | PDF | Learners | Hands-on |
| Quick Reference Card | PDF | All | Desk reference |
| eLearning Modules | SCORM | Self-paced | 4 hours |
| Video Tutorials | MP4 | All | 5-10 min each |

### 6.2 Assessment Materials

| Type | Format | Purpose |
|------|--------|---------|
| Knowledge Check | Quiz | Concept validation |
| Practical Exercise | Hands-on | Skill demonstration |
| Certification Exam | Proctored | Competency verification |

---

## 7. DOCUMENT MANAGEMENT

### 7.1 Document Lifecycle

```
┌─────────────────────────────────────────────────────────────────┐
│                    DOCUMENT LIFECYCLE                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐  │
│  │  DRAFT   │───▶│  REVIEW  │───▶│ APPROVED │───▶│ PUBLISHED│  │
│  │          │    │          │    │          │    │          │  │
│  │ Author   │    │ SME/Peer │    │ Owner    │    │ Public   │  │
│  │ creates  │    │ reviews  │    │ approves │    │ access   │  │
│  └──────────┘    └──────────┘    └────┬─────┘    └────┬─────┘  │
│                                       │               │        │
│                    ┌──────────────────┘               │        │
│                    ▼                                  ▼        │
│              ┌──────────┐                       ┌──────────┐   │
│              │ REJECTED │                       │ OBSOLETE │   │
│              │ (revise) │                       │ (archive)│   │
│              └──────────┘                       └──────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 7.2 Version Control

| Element | Convention | Example |
|---------|------------|---------|
| Version Number | Major.Minor.Revision | 2.1.3 |
| Document Date | YYYY-MM-DD | 2025-06-15 |
| Status | Draft/Review/Approved/Obsolete | Approved |
| Author | Name/Team | Technical Writing |

### 7.3 Document Repository

| Repository | Content | Access | Retention |
|------------|---------|--------|-----------|
| Git/Bitbucket | Technical docs | Development team | Permanent |
| SharePoint | Project docs | Project team | 7 years |
| Confluence | Wiki, SOPs | All staff | Permanent |
| LMS | Training materials | Trainees | Permanent |
| Document Control | Compliance docs | Authorized users | 10 years |

---

## 8. DOCUMENTATION SCHEDULE

| Phase | Deliverable | Due Date | Owner |
|-------|-------------|----------|-------|
| Design | Architecture docs | Month 3 | Architect |
| Development | API docs, Dev guides | Month 6 | Tech Lead |
| SIT | Admin guides | Month 8 | System Admin |
| UAT | User manuals | Month 9 | Tech Writer |
| Training | Training materials | Month 9 | Trainer |
| Go-Live | All docs finalized | Month 10 | Doc Manager |
| Post-Go-Live | Updates based on feedback | Ongoing | Tech Writer |

---

## 9. QUALITY ASSURANCE

### 9.1 Documentation Review Process

| Review Type | Reviewer | Focus | Timing |
|-------------|----------|-------|--------|
| Technical | SME | Accuracy, completeness | Draft |
| Editorial | Tech Writer | Grammar, style, consistency | Draft |
| Usability | Target User | Clarity, usefulness | Pre-release |
| Approval | Document Owner | Sign-off | Final |

### 9.2 Documentation Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Completeness | 100% required docs | Checklist |
| Accuracy | < 2 errors per page | Review |
| Timeliness | 100% on schedule | Schedule tracking |
| User Satisfaction | > 4.0/5 | Survey |
| Findability | < 3 clicks to content | Usability test |

---

## 10. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T38-TRAINING-PLAN | Training Documentation |
| CR-002 | ANNEX-T32-TESTING-STRATEGY | Test Documentation |
| CR-003 | ANNEX-T35-DEPLOYMENT-PLAN | Deployment Guides |
| CR-004 | ANNEX-T40-SUPPORT-PLAN | Support Documentation |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
