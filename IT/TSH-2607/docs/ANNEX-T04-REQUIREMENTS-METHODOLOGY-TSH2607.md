# ANNEX-T04-REQUIREMENTS-METHODOLOGY-TSH2607.md

# ANNEX T4: REQUIREMENTS METHODOLOGY
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T4  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [Requirements Engineering Approach](#1-requirements-engineering-approach)
2. [Requirements Elicitation Methods](#2-requirements-elicitation-methods)
3. [Requirements Analysis Framework](#3-requirements-analysis-framework)
4. [Requirements Documentation Standards](#4-requirements-documentation-standards)
5. [Requirements Validation Process](#5-requirements-validation-process)
6. [Requirements Management](#6-requirements-management)
7. [Change Control Procedure](#7-change-control-procedure)

---

## 1. REQUIREMENTS ENGINEERING APPROACH

### 1.1 Methodology Overview

The UCMS project employs a **hybrid requirements engineering approach** combining:
- **Traditional (Waterfall)** elements for regulatory compliance and documentation
- **Agile** elements for iterative development and stakeholder feedback
- **Domain-Driven Design (DDD)** for complex business logic

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    REQUIREMENTS ENGINEERING METHODOLOGY                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                                                                                  │   │
│   │   ELICITATION        ANALYSIS         SPECIFICATION        VALIDATION           │   │
│   │       │                  │                  │                  │                │   │
│   │       ▼                  ▼                  ▼                  ▼                │   │
│   │   ┌───────┐          ┌───────┐          ┌───────┐          ┌───────┐           │   │
│   │   │Workshops│        │Modeling │        │  SRS   │        │ Reviews│           │   │
│   │   │Interviews│   →   │Prototyping│  →   │  BRS   │   →   │ Prototype│          │   │
│   │   │Observations│     │Analysis  │        │  SDS   │        │ Testing  │          │   │
│   │   │Documentation│    │         │        │Use Cases│       │Sign-off  │          │   │
│   │   └───────┘          └───────┘          └───────┘          └───────┘           │   │
│   │       │                  │                  │                  │                │   │
│   │       └──────────────────┴──────────────────┴──────────────────┘                │   │
│   │                              │                                                  │   │
│   │                              ▼                                                  │   │
│   │                    ┌─────────────────┐                                          │   │
│   │                    │  REQUIREMENTS   │                                          │   │
│   │                    │    BASELINE     │                                          │   │
│   │                    │   (Version 1.0) │                                          │   │
│   │                    └────────┬────────┘                                          │   │
│   │                             │                                                   │   │
│   │                    ┌────────▼────────┐                                          │   │
│   │                    │  CHANGE CONTROL │◄────────────────────────────┐            │   │
│   │                    │    PROCESS      │                             │            │   │
│   │                    └────────┬────────┘                             │            │   │
│   │                             │                                      │            │   │
│   │                             ▼                                      │            │   │
│   │                    ┌─────────────────┐                             │            │   │
│   │                    │  ITERATIVE REFINEMENT (Agile Sprints)         │            │   │
│   │                    └─────────────────┘                             │            │   │
│   │                                                                    │            │   │
│   │                    Feedback Loop ──────────────────────────────────┘            │   │
│   │                                                                                  │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Requirements Hierarchy

| Level | Document | Content | Audience |
|-------|----------|---------|----------|
| L1 | Business Requirements Specification (BRS) | Business goals, objectives, scope | Executives, Business Owners |
| L2 | User Requirements Specification (URS) | User needs, use cases, workflows | Business Analysts, Users |
| L3 | System Requirements Specification (SRS) | Functional & non-functional requirements | Architects, Developers |
| L4 | System Design Specification (SDS) | Technical design, interfaces, data model | Technical Team |
| L5 | Interface Control Document (ICD) | API specifications, integration details | Integration Team |

---

## 2. REQUIREMENTS ELICITATION METHODS

### 2.1 Elicitation Techniques

| Technique | Purpose | Participants | Duration | Output |
|-----------|---------|--------------|----------|--------|
| **Joint Application Development (JAD)** | Collaborative requirements gathering | MCMC stakeholders, DUSP reps, Project Team | 2-3 days per workshop | Workshop minutes, draft requirements |
| **Interviews** | In-depth understanding of individual needs | Department heads, key users | 1-2 hours per session | Interview notes, requirements |
| **Document Analysis** | Understanding existing systems and processes | Business Analysts | Ongoing | AS-IS process documentation |
| **Observation** | Understanding actual work patterns | Process owners, end users | Half-day sessions | Observation reports |
| **Prototyping** | Visual validation of requirements | End users, business analysts | Iterative | Wireframes, mockups |
| **Questionnaires** | Gathering quantitative data from large groups | All user groups | 1-2 weeks | Survey results |

### 2.2 Workshop Schedule

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                        REQUIREMENTS WORKSHOP SCHEDULE                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  PHASE 1: BUSINESS CONTEXT (Week 1-2)                                                    │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  Workshop 1: Project Kick-off & Business Context                                 │   │
│  │  ├── MCMC Vision and Objectives                                                  │   │
│  │  ├── Current State Assessment                                                    │   │
│  │  ├── Success Criteria Definition                                                 │   │
│  │  └── Stakeholder Identification                                                  │   │
│  │  Participants: MCMC Directors, Project Sponsors, Key Users                       │   │
│  │                                                                                  │   │
│  │  Workshop 2: Process Mapping - Master Data & Budget Management                   │   │
│  │  ├── Project ID creation workflow                                                │   │
│  │  ├── NOA/Contract management                                                     │   │
│  │  ├── Budget allocation process                                                   │   │
│  │  └── USPFS integration requirements                                              │   │
│  │  Participants: Finance Team, USP Team, Contract Managers                         │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  PHASE 2: FUNCTIONAL REQUIREMENTS (Week 3-4)                                             │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  Workshop 3: Claims Processing Workflow                                          │   │
│  │  ├── Advance claim process                                                       │   │
│  │  ├── Quarterly claim process                                                     │   │
│  │  ├── Yearly claim with auditor template                                          │   │
│  │  └── Supporting documents requirements                                           │   │
│  │  Participants: Claims Processing Team, DUSP Representatives                      │   │
│  │                                                                                  │   │
│  │  Workshop 4: Payment Processing & Approval Workflow                              │   │
│  │  ├── Multi-level approval requirements                                           │   │
│  │  ├── Digital signature integration                                               │   │
│  │  ├── Voucher generation process                                                  │   │
│  │  └── Letter generation requirements                                              │   │
│  │  Participants: Finance Officers, Approvers, Legal Team                           │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  PHASE 3: NON-FUNCTIONAL REQUIREMENTS (Week 5)                                           │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  Workshop 5: Security, Integration & Technical Requirements                      │   │
│  │  ├── Security and access control requirements                                    │   │
│  │  ├── USPFS integration specifications                                            │   │
│  │  ├── RPA and OCR requirements                                                    │   │
│  │  ├── Reporting and dashboard needs                                               │   │
│  │  └── Performance and scalability expectations                                    │   │
│  │  Participants: IT Team, Security Officer, System Architects                      │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  PHASE 4: VALIDATION (Week 6)                                                            │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  Workshop 6: Requirements Review & Prioritization                                │   │
│  │  ├── Complete requirements walkthrough                                           │   │
│  │  ├── MoSCoW prioritization                                                       │   │
│  │  ├── Risk identification                                                         │   │
│  │  └── Sign-off preparation                                                        │   │
│  │  Participants: All Stakeholders                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 2.3 Stakeholder Engagement Matrix

| Stakeholder Group | Role in Requirements | Elicitation Method | Frequency |
|-------------------|---------------------|-------------------|-----------|
| MCMC Management | Strategic direction, approval | Interviews, Steering Committee | Monthly |
| Finance Department | Budget, payment processes | Workshops, Document review | Weekly (Phase 1-2) |
| USP Team | Claims processing, DUSP management | Workshops, Interviews | Weekly |
| Internal Users (60) | Daily operational needs | Workshops, Observation, Surveys | Weekly |
| DUSP Users (120) | External portal requirements | Workshops, Questionnaires | Bi-weekly |
| IT Department | Technical constraints, integration | Technical workshops | Weekly |
| Internal Audit | Compliance, audit trail requirements | Interviews, Document review | Bi-weekly |
| BAC/Auditors | Reporting, verification needs | Interviews | Phase 2, 5 |

---

## 3. REQUIREMENTS ANALYSIS FRAMEWORK

### 3.1 Analysis Techniques

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         REQUIREMENTS ANALYSIS FRAMEWORK                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  REQUIREMENTS INPUT              ANALYSIS ACTIVITIES           OUTPUT           │   │
│  │                                                                                  │   │
│  │  ┌───────────────────┐           ┌───────────────────┐        ┌───────────────┐ │   │
│  │  │ Raw requirements  │──────────►│ 1. Classification │───────►│ Categorized   │ │   │
│  │  │ from workshops    │           │    (F/NF/D)       │        │ requirements  │ │   │
│  │  └───────────────────┘           └───────────────────┘        └───────┬───────┘ │   │
│  │                                                                     │          │   │
│  │  ┌───────────────────┐           ┌───────────────────┐              │          │   │
│  │  │ Process inputs    │──────────►│ 2. Modeling       │──────────────┤          │   │
│  │  │ and outputs       │           │    (BPMN/UML)     │              │          │   │
│  │  └───────────────────┘           └───────────────────┘              │          │   │
│  │                                                                     ▼          │   │
│  │  ┌───────────────────┐           ┌───────────────────┐        ┌───────────────┐ │   │
│  │  │ Business rules    │──────────►│ 3. Decomposition  │◄───────│ Analyzed      │ │   │
│  │  │ and constraints   │           │    (Epics/Stories)│        │ requirements  │ │   │
│  │  └───────────────────┘           └───────────────────┘        └───────┬───────┘ │   │
│  │                                                                     │          │   │
│  │  ┌───────────────────┐           ┌───────────────────┐              │          │   │
│  │  │ External systems  │──────────►│ 4. Interface      │──────────────┤          │   │
│  │  │ documentation     │           │    Analysis       │              │          │   │
│  │  └───────────────────┘           └───────────────────┘              ▼          │   │
│  │                                                               ┌───────────────┐ │   │
│  │  ┌───────────────────┐           ┌───────────────────┐        │ Prioritized   │ │   │
│  │  │ User feedback     │──────────►│ 5. Prioritization │───────►│ requirements  │ │   │
│  │  │ and surveys       │           │    (MoSCoW)       │        └───────────────┘ │   │
│  │  └───────────────────┘           └───────────────────┘                         │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Requirements Classification

| Category | Definition | Examples |
|----------|------------|----------|
| **Functional (F)** | What the system must do | "System shall validate claim amount against approved capped cost" |
| **Non-Functional (NF)** | Quality attributes | "System response time shall be under 2 seconds" |
| **Domain (D)** | Business rules and constraints | "All claims above RM 1M require director-level approval" |
| **Interface (I)** | Integration requirements | "System shall integrate with USPFS via REST API" |
| **Data (Da)** | Data-related requirements | "Claim records shall be retained for 7 years" |

### 3.3 MoSCoW Prioritization

| Priority | Definition | Criteria | Allocation |
|----------|------------|----------|------------|
| **M - Must Have** | Critical for system operation | Regulatory requirement, core business function | 60% of requirements |
| **S - Should Have** | Important but not critical | Significant value, workarounds exist | 25% of requirements |
| **C - Could Have** | Desirable if time permits | Nice to have, low impact if omitted | 10% of requirements |
| **W - Won't Have** | Out of scope for this release | Future consideration, explicitly excluded | 5% of requirements |

---

## 4. REQUIREMENTS DOCUMENTATION STANDARDS

### 4.1 Requirements ID Convention

```
Format: REQ-[TYPE]-[MODULE]-[NNNN]

Examples:
├── REQ-F-MD-0001  (Functional - Master Data)
├── REQ-F-CL-0001  (Functional - Claims)
├── REQ-F-PY-0001  (Functional - Payment)
├── REQ-NF-SE-0001 (Non-Functional - Security)
├── REQ-NF-PE-0001 (Non-Functional - Performance)
├── REQ-I-US-0001  (Interface - USPFS)
└── REQ-D-BR-0001  (Domain - Business Rule)
```

### 4.2 Requirement Template

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                              REQUIREMENT TEMPLATE                                        │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  Requirement ID: REQ-F-CL-0001                                                          │
│  ═══════════════════════════════════════                                                │
│                                                                                          │
│  Title: Claim Amount Validation Against Approved Capped Cost                            │
│                                                                                          │
│  Priority: MUST HAVE (M)                                                                │
│                                                                                          │
│  Source: Workshop 3 - Claims Processing (15 Jan 2026)                                   │
│  Stakeholder: Finance Department, USP Team                                              │
│                                                                                          │
│  Description:                                                                           │
│  ┌───────────────────────────────────────────────────────────────────────────────────┐ │
│  │ The system shall validate the claim amount entered by DUSP against the approved │ │
│  │ capped cost for the respective project before allowing claim submission. If     │ │
│  │ the claim amount exceeds the remaining balance, the system shall reject the     │ │
│  │ submission and display an appropriate error message.                            │ │
│  └───────────────────────────────────────────────────────────────────────────────────┘ │
│                                                                                          │
│  Rationale:                                                                             │
│  Prevents overspending beyond approved project budgets and ensures compliance with      │
│  financial regulations.                                                                 │
│                                                                                          │
│  Acceptance Criteria:                                                                   │
│  ┌───────────────────────────────────────────────────────────────────────────────────┐ │
│  │ 1. Given a project with approved capped cost of RM 1,000,000                     │ │
│  │    And previous claims totaling RM 600,000                                       │ │
│  │    When DUSP submits a new claim for RM 450,000                                  │ │
│  │    Then the system shall reject the submission                                   │ │
│  │    And display message: "Claim amount exceeds remaining budget balance of         │ │
│  │    RM 400,000"                                                                   │ │
│  │                                                                                  │ │
│  │ 2. Given same scenario with claim for RM 350,000                                 │ │
│  │    When DUSP submits the claim                                                   │ │
│  │    Then the system shall accept the submission                                   │ │
│  │    And proceed to document upload step                                           │ │
│  └───────────────────────────────────────────────────────────────────────────────────┘ │
│                                                                                          │
│  Related Requirements:                                                                  │
│  • REQ-F-MD-0005 (Capped Cost Maintenance)                                              │
│  • REQ-F-BG-0003 (Budget Validation Rules)                                              │
│  • REQ-I-US-0002 (USPFS Budget Sync)                                                    │
│                                                                                          │
│  Business Rules:                                                                        │
│  • Validation formula: Remaining = Approved Capped Cost - Total Claimed to Date        │
│  • Exception: Variation Order (VO) approved amounts may increase capped cost           │
│                                                                                          │
│  UI/UX Considerations:                                                                  │
│  • Real-time validation during amount entry                                             │
│  • Visual indicator showing remaining budget (progress bar)                             │
│  • Warning at 80% of budget utilization                                                 │
│                                                                                          │
│  Assumptions:                                                                           │
│  • Approved capped cost is synchronized daily from USPFS                                │
│  • VO adjustments are processed before claim validation                                 │
│                                                                                          │
│  Dependencies:                                                                          │
│  • USPFS integration for budget data                                                    │
│  • Master Data Module for project information                                           │
│                                                                                          │
│  Status: APPROVED                                                                       │
│  Approved By: [Name], [Date]                                                            │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 4.3 Traceability Matrix Structure

| Requirement ID | Description | Source | Priority | SRS Section | Design Element | Test Case | Status |
|----------------|-------------|--------|----------|-------------|----------------|-----------|--------|
| REQ-F-CL-0001 | Claim validation | WS3 | M | 4.2.1 | ValidationService.java | TC-CL-001 | Implemented |
| REQ-F-CL-0002 | Document upload | WS3 | M | 4.2.2 | DocumentUpload.vue | TC-CL-005 | Implemented |

---

## 5. REQUIREMENTS VALIDATION PROCESS

### 5.1 Validation Activities

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         REQUIREMENTS VALIDATION PROCESS                                  │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                                                                                  │   │
│   │   REQUIREMENTS DOCUMENT                VALIDATION ACTIVITIES                    │   │
│   │                                                                                  │   │
│   │   ┌─────────────────────┐              ┌─────────────────────────────────────┐  │   │
│   │   │ Draft Requirements  │─────────────►│ 1. Peer Review                      │  │   │
│   │   │ (BA Team)           │              │    - Technical feasibility check    │  │   │
│   │   └─────────────────────┘              │    - Completeness review            │  │   │
│   │            │                           │    - Consistency check              │  │   │
│   │            ▼                           └─────────────────────────────────────┘  │   │
│   │   ┌─────────────────────┐                           │                           │   │
│   │   │ Reviewed            │◄──────────────────────────┘                           │   │
│   │   │ Requirements        │                                                       │   │
│   │   └─────────────────────┘                                                       │   │
│   │            │                                                                    │   │
│   │            ▼                           ┌─────────────────────────────────────┐  │   │
│   │   ┌─────────────────────┐              │ 2. Stakeholder Review               │  │   │
│   │   │                     │─────────────►│    - Workshop walkthrough           │  │   │
│   │   │ Requirements        │              │    - Feedback collection            │  │   │
│   │   │ for Validation      │              │    - Clarification of ambiguities   │  │   │
│   │   │                     │              └─────────────────────────────────────┘  │   │
│   │   └─────────────────────┘                           │                           │   │
│   │            │                                        │                           │   │
│   │            ▼                                        ▼                           │   │
│   │   ┌─────────────────────┐              ┌─────────────────────────────────────┐  │   │
│   │   │ Validated           │◄─────────────│ 3. Prototype Review                 │  │   │
│   │   │ Requirements        │              │    - UI/UX mockup validation        │  │   │
│   │   │                     │              │    - Workflow simulation            │  │   │
│   │   └─────────────────────┘              │    - User acceptance preview        │  │   │
│   │            │                           └─────────────────────────────────────┘  │   │
│   │            │                                                                    │   │
│   │            ▼                           ┌─────────────────────────────────────┐  │   │
│   │   ┌─────────────────────┐              │ 4. Approval & Baseline              │  │   │
│   │   │ BASELINED           │◄─────────────│    - Steering Committee approval    │  │   │
│   │   │ REQUIREMENTS        │              │    - Baseline establishment         │  │   │
│   │   │ (Version 1.0)       │              │    - Change control initiation      │  │   │
│   │   └─────────────────────┘              └─────────────────────────────────────┘  │   │
│   │                                                                                  │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Review Checklist

| Review Category | Check Item | Pass/Fail | Comments |
|-----------------|------------|-----------|----------|
| **Completeness** | All requirements traced to business need | | |
| | All user scenarios covered | | |
| | Integration points identified | | |
| **Consistency** | No conflicting requirements | | |
| | Terminology used consistently | | |
| | Units of measure consistent | | |
| **Clarity** | Each requirement has single interpretation | | |
| | No ambiguous terms | | |
| | Acceptance criteria defined | | |
| **Feasibility** | Technically achievable | | |
| | Within budget constraints | | |
| | Complies with standards | | |
| **Testability** | Acceptance criteria measurable | | |
| | Test scenarios identified | | |

---

## 6. REQUIREMENTS MANAGEMENT

### 6.1 Tools and Repository

| Tool | Purpose | Configuration |
|------|---------|---------------|
| **JIRA/Azure DevOps** | Requirements tracking, user stories | Custom workflow for requirements |
| **Confluence** | Documentation repository | Structured spaces per document type |
| **Visio/draw.io** | Process modeling | BPMN 2.0 standards |
| **Enterprise Architect** | UML modeling, traceability | Integrated with JIRA |
| **Git** | Version control for documents | Branching strategy for releases |

### 6.2 Requirements Attributes

Each requirement shall maintain the following attributes:

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         REQUIREMENT ATTRIBUTES                                           │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  Identification Attributes:                                                              │
│  ├── ID (Unique identifier)                                                              │
│  ├── Title (Short description)                                                           │
│  ├── Version (Current version number)                                                    │
│  └── Source (Origin: Workshop/Interview/Document)                                        │
│                                                                                          │
│  Classification Attributes:                                                              │
│  ├── Type (Functional/Non-Functional/Domain/Interface)                                   │
│  ├── Priority (MoSCoW)                                                                   │
│  ├── Module (Master Data/Claims/Payment/etc.)                                            │
│  └── Category (Security/Performance/Usability/etc.)                                      │
│                                                                                          │
│  Status Attributes:                                                                      │
│  ├── Status (Draft/Under Review/Approved/Baselined/Implemented/Verified)                 │
│  ├── Author (Created by)                                                                 │
│  ├── Creation Date                                                                       │
│  ├── Last Modified By                                                                    │
│  └── Last Modified Date                                                                  │
│                                                                                          │
│  Relationship Attributes:                                                                │
│  ├── Parent Epic/Feature                                                                 │
│  ├── Related Requirements                                                                │
│  ├── Dependencies                                                                        │
│  └── Conflicts                                                                           │
│                                                                                          │
│  Development Attributes:                                                                 │
│  ├── Sprint (Agile iteration)                                                            │
│  ├── Story Points (Effort estimate)                                                      │
│  ├── Design Reference                                                                    │
│  └── Code Reference                                                                      │
│                                                                                          │
│  Test Attributes:                                                                        │
│  ├── Test Case ID                                                                        │
│  ├── Test Status                                                                         │
│  └── Defect ID (if applicable)                                                           │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 7. CHANGE CONTROL PROCEDURE

### 7.1 Change Request Process

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         CHANGE CONTROL PROCESS                                           │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│   │                                                                                  │   │
│   │  CHANGE ORIGIN                    CHANGE REQUEST WORKFLOW                       │   │
│   │                                                                                  │   │
│   │  ┌─────────────────┐                                                            │   │
│   │  │ • New business  │                                                            │   │
│   │  │   requirement   │                                                            │   │
│   │  │ • Regulatory    │                                                            │   │
│   │  │   change        │                                                            │   │
│   │  │ • Technical     │                                                            │   │
│   │  │   constraint    │                                                            │   │
│   │  │ • Stakeholder   │                                                            │   │
│   │  │   feedback      │                                                            │   │
│   │  └────────┬────────┘                                                            │   │
│   │           │                                                                     │   │
│   │           ▼                                                                     │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │  STEP 1: CHANGE IDENTIFICATION                                           │   │   │
│   │  │  ├── Originator submits Change Request (CR)                              │   │   │
│   │  │  ├── BA logs CR in Change Register                                       │   │   │
│   │  │  └── CR assigned unique ID (CR-YYYY-NNNN)                                │   │   │
│   │  └────────────────────────────────┬────────────────────────────────────────┘   │   │
│   │                                   │                                              │   │
│   │                                   ▼                                              │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │  STEP 2: IMPACT ASSESSMENT                                               │   │   │
│   │  │  ├── Technical impact (Architecture Team)                                │   │   │
│   │  │  ├── Schedule impact (Project Manager)                                   │   │   │
│   │  │  ├── Cost impact (Finance)                                               │   │   │
│   │  │  └── Risk assessment (QA Team)                                           │   │   │
│   │  └────────────────────────────────┬────────────────────────────────────────┘   │   │
│   │                                   │                                              │   │
│   │                                   ▼                                              │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │  STEP 3: CHANGE CONTROL BOARD (CCB) REVIEW                               │   │   │
│   │  │  ├── CCB convenes (weekly or emergency)                                  │   │   │
│   │  │  ├── Review impact assessment                                            │   │   │
│   │  │  ├── Decision: Approve / Reject / Defer / Request Info                   │   │   │
│   │  │  └── Document decision rationale                                         │   │   │
│   │  └────────────────────────────────┬────────────────────────────────────────┘   │   │
│   │                                   │                                              │   │
│   │                                   ▼                                              │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │  STEP 4: IMPLEMENTATION (If Approved)                                    │   │   │
│   │  │  ├── Update requirements document                                        │   │   │
│   │  │  ├── Update traceability matrix                                          │   │   │
│   │  │  ├── Update design (if needed)                                           │   │   │
│   │  │  └── Communicate to development team                                     │   │   │
│   │  └────────────────────────────────┬────────────────────────────────────────┘   │   │
│   │                                   │                                              │   │
│   │                                   ▼                                              │   │
│   │  ┌─────────────────────────────────────────────────────────────────────────┐   │   │
│   │  │  STEP 5: VERIFICATION & CLOSURE                                          │   │   │
│   │  │  ├── Implement change in system                                          │   │   │
│   │  │  ├── Verify implementation meets requirement                             │   │   │
│   │  │  ├── Update change register status to "Closed"                           │   │   │
│   │  │  └── Archive change documentation                                        │   │   │
│   │  └─────────────────────────────────────────────────────────────────────────┘   │   │
│   │                                                                                  │   │
│   └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│   CCB Composition:                                                                       │
│   • Project Manager (Chair)                                                              │
│   • MCMC Representative                                                                  │
│   • Solution Architect                                                                   │
│   • Business Analyst                                                                     │
│   • QA Lead                                                                              │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 7.2 Change Request Template

| Field | Description |
|-------|-------------|
| CR ID | CR-2026-0001 |
| Date Submitted | [Date] |
| Submitted By | [Name/Role] |
| Priority | Critical/High/Medium/Low |
| Related Requirement | REQ-XX-XX-XXXX |
| Change Description | [Detailed description] |
| Business Justification | [Why change is needed] |
| Impact Assessment | Technical/Schedule/Cost |
| CCB Decision | Approved/Rejected/Deferred |
| Decision Date | [Date] |
| Implementation Sprint | [Sprint number] |

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Business Analysis Team | Initial methodology |

---

**END OF ANNEX T4**
