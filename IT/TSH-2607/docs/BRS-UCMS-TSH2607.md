# BUSINESS REQUIREMENTS SPECIFICATION (BRS)

## UNIVERSAL SERVICE PROVISION (USP) CLAIMS MANAGEMENT SYSTEM (UCMS)

**Tender Reference:** TSH-2607 / MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)

**Version:** 1.0

**Date:** February 2026

**Classification:** CONFIDENTIAL

---

## DOCUMENT CONTROL

### Version History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 0.1 | 15 Feb 2026 | Business Analyst | Initial Draft | - |
| 0.2 | 17 Feb 2026 | Solution Architect | Technical Review | - |
| 0.3 | 18 Feb 2026 | Project Manager | Consolidation | - |
| 1.0 | 18 Feb 2026 | Project Manager | Final Release | MCMC Representative |

### Approval Signatures

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Project Sponsor | [Name] | _________________ | _______ |
| Project Manager | [Name] | _________________ | _______ |
| Business Analyst | [Name] | _________________ | _______ |
| MCMC Representative | [Name] | _________________ | _______ |

---

## TABLE OF CONTENTS

1. [Executive Summary](#1-executive-summary)
2. [Business Context](#2-business-context)
3. [Business Objectives](#3-business-objectives)
4. [Current State Analysis (As-Is)](#4-current-state-analysis-as-is)
5. [Future State Vision (To-Be)](#5-future-state-vision-to-be)
6. [Business Process Requirements](#6-business-process-requirements)
7. [Claims Processing Lifecycle](#7-claims-processing-lifecycle)
8. [Payment Processing Lifecycle](#8-payment-processing-lifecycle)
9. [Budget Management Lifecycle](#9-budget-management-lifecycle)
10. [Business Rules](#10-business-rules)
11. [Compliance Requirements](#11-compliance-requirements)
12. [Risk Management](#12-risk-management)
13. [Stakeholder Requirements](#13-stakeholder-requirements)
14. [Business Metrics and KPIs](#14-business-metrics-and-kpis)
15. [Glossary](#15-glossary)
16. [Appendices](#16-appendices)

---

## 1. EXECUTIVE SUMMARY

### 1.1 Purpose and Scope

This Business Requirements Specification (BRS) defines the business needs, objectives, and requirements for the Universal Service Provision (USP) Claims Management System (UCMS). The document establishes the foundation for system development by articulating what the business needs to achieve, independent of technical implementation details.

### 1.2 Business Problem Statement

The Malaysian Communications and Multimedia Commission (MCMC) currently manages USP claims through a combination of manual processes, email communications, spreadsheet tracking, and the USP Financial System (Oracle EBS). This fragmented approach results in:

- **Processing Delays**: Average claim processing time of 45-60 days
- **High Error Rates**: 12-15% error rate requiring rework
- **Limited Visibility**: Lack of real-time status for external stakeholders
- **Resource Intensity**: 8-12 manual hours per claim
- **Compliance Challenges**: Difficult audit trails and governance gaps

### 1.3 Proposed Solution

UCMS will transform USP claims management through:

1. **End-to-End Automation**: Digital workflows replacing paper-based processes
2. **Self-Service Portal**: 24/7 access for DUSPs and subcontractors
3. **Intelligent Validation**: AI-powered document verification and fraud detection
4. **Integrated Platform**: Seamless connection with USPFS and digital signature systems
5. **Comprehensive Analytics**: Real-time dashboards and reporting

### 1.4 Expected Business Benefits

| Benefit Category | Current State | Target State | Improvement |
|------------------|---------------|--------------|-------------|
| Processing Time | 45-60 days | 15-20 days | 67% reduction |
| Error Rate | 12-15% | <2% | 87% reduction |
| Manual Effort | 8-12 hrs/claim | 2-3 hrs/claim | 75% reduction |
| User Satisfaction | 55% | 85% | 55% improvement |
| Audit Findings | 8-12 per audit | 0-2 per audit | 83% reduction |

### 1.5 Investment Summary

- **Indicative Project Value**: RM 3,500,000
- **Project Duration**: 67 months (16 development + 3 testing + 12 warranty + 36 extended support)
- **ROI Period**: 24 months
- **Ongoing Value**: RM 1.2M annually (efficiency gains)

---

## 2. BUSINESS CONTEXT

### 2.1 Organizational Overview

#### 2.1.1 MCMC Mission and Mandate

The Malaysian Communications and Multimedia Commission (MCMC) is the regulatory body for the communications and multimedia industry in Malaysia. Established under the Communications and Multimedia Act 1998 (Act 588), MCMC's mission includes ensuring universal service provision across the nation.

**Key Responsibilities:**
- Regulation of communications and multimedia services
- Management of Universal Service Provision (USP) fund
- Ensuring equitable access to communication services
- Industry development and consumer protection

#### 2.1.2 Universal Service Provision (USP) Program

The USP program ensures that basic communications services are accessible to all Malaysians, particularly in rural and underserved areas. The program is funded through industry contributions and managed by MCMC.

**Program Components:**
- Infrastructure development in rural areas
- Community broadband centers
- School connectivity programs
- Emergency services communications

### 2.2 Business Environment

#### 2.2.1 Regulatory Environment

MCMC operates within a comprehensive regulatory framework:

| Regulation | Relevance to UCMS |
|------------|-------------------|
| Communications and Multimedia Act 1998 | Primary enabling legislation |
| USP Regulations 2002 | USP program governance |
| Personal Data Protection Act 2010 | Data privacy requirements |
| Electronic Commerce Act 2006 | Digital signature legality |
| Financial Procedures Act 1957 | Payment processing compliance |

#### 2.2.2 Industry Landscape

The telecommunications industry in Malaysia includes:

- **Major DUSPs**: Telekom Malaysia, Maxis, CelcomDigi, U Mobile
- **Service Coverage**: Voice, broadband, mobile services
- **Investment Scale**: RM 500M+ annually in USP projects
- **Beneficiaries**: 5M+ rural residents

### 2.3 Current Business Architecture

#### 2.3.1 Business Units Involved

```
┌─────────────────────────────────────────────────────────┐
│                    MCMC ORGANIZATION                     │
├─────────────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │   USP Dept   │  │   Finance    │  │    Legal     │  │
│  │   (Primary)  │  │   (Payment)  │  │  (Contracts) │  │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  │
│         │                  │                  │          │
│         └──────────────────┼──────────────────┘          │
│                            │                            │
│                   ┌────────▼────────┐                   │
│                   │   UCMS (New)    │                   │
│                   └────────┬────────┘                   │
│                            │                            │
│         ┌──────────────────┼──────────────────┐          │
│         │                  │                  │          │
│  ┌──────▼───────┐  ┌──────▼───────┐  ┌──────▼───────┐  │
│  │    DUSPs     │  │ Subcontractors│  │   Auditors   │  │
│  │  (External)  │  │  (External)  │  │  (External)  │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
└─────────────────────────────────────────────────────────┘
```

#### 2.3.2 External Stakeholders

| Stakeholder | Relationship | Impact |
|-------------|--------------|--------|
| DUSPs | Primary beneficiaries | High - direct system users |
| Subcontractors | Secondary beneficiaries | Medium - limited access |
| Banks | Payment processing | Medium - integration required |
| Auditors | Compliance verification | Medium - audit trail users |
| Ministry of Finance | Funding oversight | Low - reporting recipients |

### 2.4 Business Drivers

#### 2.4.1 Strategic Drivers

1. **Digital Transformation**: MCMC's initiative to modernize operations
2. **Transparency Mandate**: Government push for transparent grant management
3. **Efficiency Imperative**: Need to process increasing claim volumes
4. **Compliance Requirements**: Strengthened audit and governance standards

#### 2.4.2 Operational Drivers

1. **Volume Growth**: 30% annual increase in claim submissions
2. **Complexity Increase**: More complex project structures and variations
3. **Resource Constraints**: Limited staff for manual processing
4. **Error Reduction**: Need to minimize rework and corrections

#### 2.4.3 Technology Drivers

1. **System Integration**: Opportunity to leverage USPFS investment
2. **Automation Maturity**: RPA and AI technologies now viable
3. **Digital Signature**: Legal framework now supports digital processes
4. **Cloud Adoption**: Scalable infrastructure available

---

## 3. BUSINESS OBJECTIVES

### 3.1 Primary Business Objectives

#### 3.1.1 Objective 1: Reduce Claim Processing Time

**Description**: Decrease the average time from claim submission to payment from 45-60 days to 15-20 days.

**Business Value**:
- Improved DUSP cash flow
- Enhanced stakeholder satisfaction
- Faster project implementation
- Reduced administrative burden

**Success Criteria**:
- 90% of claims processed within 20 days
- 50% reduction in processing time
- Zero claims exceeding 30 days without valid reason

**Measurement Approach**:
- Track cycle time from submission to payment
- Monitor stage-wise processing times
- Analyze bottlenecks and delays

#### 3.1.2 Objective 2: Improve Data Accuracy

**Description**: Reduce error rates in claim submissions and processing from 12-15% to less than 2%.

**Business Value**:
- Reduced rework and corrections
- Faster processing
- Improved audit outcomes
- Enhanced data quality for reporting

**Success Criteria**:
- <2% claim rejection rate due to errors
- <1% payment correction rate
- 95% first-time approval rate

**Measurement Approach**:
- Track claim rejection reasons
- Monitor correction transactions
- Analyze audit findings

#### 3.1.3 Objective 3: Enhance Transparency and Visibility

**Description**: Provide real-time visibility into claim status and payment progress for all stakeholders.

**Business Value**:
- Reduced inquiry calls and emails
- Improved stakeholder trust
- Better cash flow planning for DUSPs
- Enhanced accountability

**Success Criteria**:
- 100% of claims trackable online
- <5 inquiry calls per day
- 85%+ user satisfaction score

**Measurement Approach**:
- Monitor self-service portal usage
- Track inquiry volumes
- Conduct user satisfaction surveys

#### 3.1.4 Objective 4: Strengthen Compliance and Audit Readiness

**Description**: Ensure complete audit trails and compliance with all regulatory requirements.

**Business Value**:
- Reduced audit findings
- Faster audit completion
- Improved governance posture
- Regulatory confidence

**Success Criteria**:
- 100% audit trail coverage
- <2 findings per audit
- 4-hour audit query response time

**Measurement Approach**:
- Track audit findings
- Monitor audit completion times
- Verify audit log completeness

### 3.2 Secondary Business Objectives

#### 3.2.1 Cost Reduction

**Target**: Reduce administrative cost per claim by 50%

**Approach**:
- Automation of manual processes
- Self-service for DUSPs
- Reduced rework
- Efficient resource utilization

#### 3.2.2 Scalability

**Target**: Support 50% volume increase without proportional resource increase

**Approach**:
- Automated processing
- Scalable infrastructure
- Efficient workflows
- Self-service capabilities

#### 3.2.3 Stakeholder Satisfaction

**Target**: Achieve 85%+ satisfaction score from all user categories

**Approach**:
- User-centric design
- Responsive support
- Clear communication
- Reliable service

### 3.3 Business Objective Prioritization

| Objective | Priority | Timeline | Dependencies |
|-----------|----------|----------|--------------|
| Reduce Processing Time | Critical | 6 months | Workflow automation |
| Improve Data Accuracy | Critical | 6 months | Validation rules |
| Enhance Transparency | High | 3 months | Portal deployment |
| Strengthen Compliance | High | 9 months | Audit trail complete |
| Cost Reduction | Medium | 12 months | Process optimization |
| Scalability | Medium | 12 months | Infrastructure scaling |
| Stakeholder Satisfaction | High | Ongoing | All components |

---

## 4. CURRENT STATE ANALYSIS (AS-IS)

### 4.1 Current Business Processes

#### 4.1.1 Claims Submission Process (As-Is)

```
┌─────────────────────────────────────────────────────────────────┐
│                    AS-IS CLAIMS SUBMISSION PROCESS               │
└─────────────────────────────────────────────────────────────────┘

Phase 1: Preparation (DUSP)
├── DUSP prepares claim documents manually
├── Documents compiled from multiple sources
├── Spreadsheets used for calculations
└── Physical documents printed and signed
    ↓ (2-5 days)

Phase 2: Submission (DUSP to MCMC)
├── Documents sent via email or physical delivery
├── Receipt acknowledged manually
└── Documents logged in tracking spreadsheet
    ↓ (1-2 days)

Phase 3: Initial Review (MCMC USP)
├── Documents printed and distributed
├── Manual verification against records
├── Discrepancies identified and documented
└── Clarification requests sent to DUSP
    ↓ (5-10 days, may iterate)

Phase 4: Detailed Verification (MCMC USP)
├── Technical verification performed
├── Financial calculations checked
├── Supporting documents validated
└── Verification report prepared
    ↓ (5-10 days)

Phase 5: Approval Routing (MCMC)
├── Physical approval forms prepared
├── Documents routed for signatures
├── Multiple approval levels visited sequentially
└── Approval status tracked manually
    ↓ (10-15 days)

Phase 6: Payment Processing (MCMC Finance)
├── Approved claim entered into USPFS
├── Payment voucher generated
├── Bank instructions prepared
└── Payment executed
    ↓ (3-5 days)

Phase 7: Notification (MCMC to DUSP)
├── Payment advice prepared
├── Notification sent to DUSP
└── Records filed manually

Total Cycle Time: 45-60 days
Touch Points: 15+ manual handoffs
Rework Rate: 12-15%
```

#### 4.1.2 Budget Management Process (As-Is)

```
┌─────────────────────────────────────────────────────────────────┐
│                   AS-IS BUDGET MANAGEMENT PROCESS                │
└─────────────────────────────────────────────────────────────────┘

Budget Allocation:
├── Annual budget approved by Ministry
├── Budget manually allocated to projects
├── Allocation recorded in spreadsheets
└── Distribution communicated via email

Budget Monitoring:
├── Monthly manual reconciliation
├── Spreadsheet-based tracking
├── Variance analysis performed manually
└── Reports compiled for management

Budget Adjustment:
├── Adjustment requests submitted
├── Manual review and approval
├── Spreadsheets updated
└── Stakeholders notified

Challenges:
- No real-time visibility
- Version control issues
- Inconsistent data
- Delayed variance detection
```

#### 4.1.3 Payment Processing Process (As-Is)

```
┌─────────────────────────────────────────────────────────────────┐
│                  AS-IS PAYMENT PROCESSING PROCESS                │
└─────────────────────────────────────────────────────────────────┘

Payment Initiation:
├── Approved claim documents received
├── Payment memo prepared manually
├── Supporting documents attached
└── Routing for approval signatures

Payment Approval:
├── Physical signatures obtained
├── Minimum 3 approval levels
├── Sequential processing
└── Average 10-15 days for approval

Payment Execution:
├── Details entered into USPFS
├── Voucher generated
├── Bank transfer initiated
└── Confirmation received

Payment Notification:
├── Payment advice prepared manually
├── Letter sent to DUSP
└── Records filed

Issues:
- Paper-based approvals cause delays
- No visibility during routing
- Manual entry errors
- Limited payment tracking
```

### 4.2 Current Pain Points Analysis

#### 4.2.1 Pain Points by Process Area

| Process Area | Pain Point | Impact | Frequency |
|--------------|------------|--------|-----------|
| Data Entry | Manual data entry from documents | High errors, slow | Every claim |
| Document Management | Multiple versions, no central repository | Confusion, delays | Daily |
| Communication | Email-based, no audit trail | Misunderstanding | Daily |
| Approval | Physical routing, sequential | Bottlenecks | Every claim |
| Reporting | Manual compilation | Time-consuming | Weekly |
| Reconciliation | Manual spreadsheet matching | Errors, delays | Monthly |
| Audit Support | Scattered documentation | Audit findings | Quarterly |

#### 4.2.2 Pain Points by Stakeholder

**Internal MCMC Users:**

1. **Data Fragmentation** (Severity: High)
   - Information scattered across emails, spreadsheets, and files
   - No single source of truth
   - Time wasted searching for information
   - Inconsistent data across sources

2. **Manual Verification Burden** (Severity: High)
   - Each claim requires extensive manual checking
   - Cross-referencing multiple sources
   - High cognitive load
   - Risk of human error

3. **Approval Bottlenecks** (Severity: High)
   - Physical routing causes delays
   - Approver unavailability blocks progress
   - No visibility into approval status
   - Difficult to expedite urgent items

4. **Limited Reporting Capability** (Severity: Medium)
   - Manual report compilation
   - Time-consuming aggregation
   - Limited analytical depth
   - Out-of-date information

**External DUSP Users:**

1. **Status Visibility Gap** (Severity: High)
   - No real-time claim status
   - Uncertainty about payment timing
   - Repeated follow-up queries
   - Impact on cash flow planning

2. **Documentation Challenges** (Severity: High)
   - Unclear requirements
   - Repeated submissions for corrections
   - No confirmation of receipt
   - Version control issues

3. **Communication Barriers** (Severity: Medium)
   - Email-only communication
   - Delayed responses
   - Misunderstandings
   - No central communication log

4. **Payment Uncertainty** (Severity: Medium)
   - Unpredictable payment dates
   - Reconciliation difficulties
   - Limited payment advice detail

### 4.3 Current System Landscape

#### 4.3.1 System Inventory

| System | Type | Purpose | Users | Integration |
|--------|------|---------|-------|-------------|
| USPFS | Oracle EBS | Financial processing | 20 | Core financial system |
| Excel/Access | Desktop | Data tracking | 40 | Manual data entry |
| Email | Communication | Communication | All | Ad-hoc |
| Shared Drives | Storage | Document storage | All | File-based |
| MS Word | Desktop | Document preparation | All | Manual |

#### 4.3.2 Integration Analysis

**Current Integration Points:**

1. **USPFS Integration**: Limited to final payment entry
   - Manual data entry into USPFS
   - No automated data exchange
   - Duplicate data entry required

2. **Document Management**: No integration
   - Documents stored in file shares
   - No version control
   - Search capabilities limited

3. **Communication**: Email only
   - No system integration
   - Information scattered
   - No audit trail

**Integration Gaps:**

| Gap | Impact | Priority |
|-----|--------|----------|
| No real-time USPFS sync | Data inconsistency | High |
| No document workflow | Processing delays | High |
| No automated notifications | Communication gaps | Medium |
| No reporting integration | Manual reporting | Medium |

### 4.4 Quantified Current State

#### 4.4.1 Processing Metrics

| Metric | Value | Benchmark | Assessment |
|--------|-------|-----------|------------|
| Average Processing Time | 52 days | 15 days | Poor |
| Minimum Processing Time | 30 days | 10 days | Poor |
| Maximum Processing Time | 120 days | 30 days | Critical |
| Claims per FTE per Month | 15 | 50 | Poor |
| First-Pass Approval Rate | 75% | 95% | Poor |

#### 4.4.2 Quality Metrics

| Metric | Value | Target | Assessment |
|--------|-------|--------|------------|
| Error Rate | 13% | <2% | Critical |
| Rework Rate | 15% | <5% | Poor |
| Audit Findings | 10/audit | <2/audit | Poor |
| Data Accuracy | 87% | 98% | Poor |

#### 4.4.3 Cost Metrics

| Cost Category | Current (RM) | Per Claim (RM) |
|---------------|--------------|----------------|
| Labor Cost | 1,200,000/year | 480 |
| System Cost | 150,000/year | 60 |
| Error/Rework Cost | 300,000/year | 120 |
| **Total Cost** | **1,650,000/year** | **660** |

---

## 5. FUTURE STATE VISION (TO-BE)

### 5.1 Future Business Processes

#### 5.1.1 Claims Submission Process (To-Be)

```
┌─────────────────────────────────────────────────────────────────┐
│                   TO-BE CLAIMS SUBMISSION PROCESS                │
└─────────────────────────────────────────────────────────────────┘

Phase 1: Preparation and Submission (DUSP - Self-Service)
├── DUSP logs into UCMS portal
├── System guides through claim preparation
├── AI validates documents during upload
├── OCR extracts data automatically
├── Digital signature applied
└── Submit with confirmation
    ↓ (1-2 days, mostly automated)

Phase 2: Automated Validation (UCMS)
├── System validates against budget
├── Performance bond status checked
├── Milestone achievements verified
├── Document completeness confirmed
├── Fraud detection algorithms applied
└── Claim queued for review or auto-approved
    ↓ (Minutes to hours)

Phase 3: Review and Verification (MCMC - Assisted)
├── Reviewer receives notification
├── All documents and data pre-validated
├── Reviewer verifies exception items only
├── Digital approval provided
└── Claim routed to payment workflow
    ↓ (2-3 days)

Phase 4: Payment Processing (Automated)
├── Payment memo auto-generated
├── Digital approval workflow executed
├── USPFS integration for voucher creation
├── Bank integration for payment
└── DUSP notified automatically
    ↓ (1-2 days)

Total Cycle Time: 15-20 days
Touch Points: 3-5 automated handoffs
Rework Rate: <2%
```

#### 5.1.2 Budget Management Process (To-Be)

```
┌─────────────────────────────────────────────────────────────────┐
│                  TO-BE BUDGET MANAGEMENT PROCESS                 │
└─────────────────────────────────────────────────────────────────┘

Budget Allocation:
├── Annual budget entered in UCMS
├── Automatic allocation to projects
├── Real-time budget dashboard available
└── Stakeholders access current view

Budget Monitoring:
├── Real-time budget utilization tracking
├── Automated variance alerts
├── Predictive budget forecasting
└── Self-service reporting

Budget Adjustment:
├── Electronic adjustment requests
├── Workflow-based approval
├── Automatic updates upon approval
└── Notification to stakeholders

Benefits:
- Real-time visibility
- Single source of truth
- Proactive alerts
- Enhanced control
```

#### 5.1.3 Payment Processing Process (To-Be)

```
┌─────────────────────────────────────────────────────────────────┐
│                 TO-BE PAYMENT PROCESSING PROCESS                 │
└─────────────────────────────────────────────────────────────────┘

Payment Initiation:
├── Approved claim triggers payment workflow
├── Payment memo auto-generated from claim data
├── Supporting documents attached automatically
└── Digital routing initiated

Payment Approval:
├── Digital signatures obtained
├── Parallel approval where appropriate
├── Mobile approval supported
└── Average 2-3 days for approval

Payment Execution:
├── Automatic USPFS integration
├── Voucher generated automatically
├── Bank transfer initiated
└── Real-time status tracking

Payment Notification:
├── Automatic payment advice generation
├── Email notification to DUSP
├── Portal status updated
└── Records archived automatically

Improvements:
- 80% reduction in approval time
- Zero manual data entry
- Full audit trail
- Real-time visibility
```

### 5.2 Future State Benefits

#### 5.2.1 Quantified Benefits

| Benefit Category | Current | Future | Improvement |
|------------------|---------|--------|-------------|
| Processing Time | 52 days | 17 days | 67% faster |
| Error Rate | 13% | 1.5% | 88% reduction |
| Manual Hours/Claim | 10 hours | 2.5 hours | 75% reduction |
| User Satisfaction | 55% | 87% | 58% increase |
| Audit Findings | 10/audit | 1/audit | 90% reduction |
| Claims/FTE/Month | 15 | 60 | 300% increase |

#### 5.2.2 Qualitative Benefits

1. **Enhanced Transparency**
   - Real-time visibility for all stakeholders
   - Audit trail for all actions
   - Standardized processes

2. **Improved Compliance**
   - Automated compliance checks
   - Complete documentation
   - Regulatory alignment

3. **Better Decision Making**
   - Real-time analytics
   - Predictive insights
   - Comprehensive reporting

4. **Stakeholder Satisfaction**
   - Self-service capabilities
   - Faster processing
   - Clear communication

5. **Resource Optimization**
   - Staff focus on value-added activities
   - Reduced manual effort
   - Efficient resource utilization

### 5.3 Business Transformation Roadmap

#### 5.3.1 Transformation Phases

| Phase | Timeline | Focus | Key Outcomes |
|-------|----------|-------|--------------|
| Foundation | Months 1-6 | Core functionality | Basic claims processing |
| Enhancement | Months 7-12 | Advanced features | AI, analytics, mobile |
| Optimization | Months 13-18 | Performance tuning | 99.9% uptime, <2% errors |
| Maturity | Months 19-67 | Continuous improvement | Predictive capabilities |

#### 5.3.2 Change Impact Summary

| Area | Current State | Future State | Impact Level |
|------|---------------|--------------|--------------|
| Processes | Manual, paper-based | Automated, digital | High |
| Roles | Transaction processing | Exception handling | Medium |
| Skills | Data entry | Analysis, review | Medium |
| Systems | Multiple, disconnected | Integrated platform | High |
| Culture | Siloed operations | Collaborative, transparent | Medium |

---

## 6. BUSINESS PROCESS REQUIREMENTS

### 6.1 Process Hierarchy

```
┌─────────────────────────────────────────────────────────────┐
│              UCMS BUSINESS PROCESS HIERARCHY                 │
└─────────────────────────────────────────────────────────────┘

Level 1: Process Areas
├── 1.0 Master Data Management
├── 2.0 Claims Management
├── 3.0 Budget Management
├── 4.0 Payment Management
├── 5.0 Reporting and Analytics
└── 6.0 System Administration

Level 2: Process Groups
1.0 Master Data Management
├── 1.1 Project Setup
├── 1.2 Contract Management
├── 1.3 Vendor Management
└── 1.4 Reference Data

2.0 Claims Management
├── 2.1 Claim Submission
├── 2.2 Claim Verification
├── 2.3 Claim Approval
└── 2.4 Claim Tracking

3.0 Budget Management
├── 3.1 Budget Setup
├── 3.2 Budget Monitoring
└── 3.3 Budget Adjustment

4.0 Payment Management
├── 4.1 Payment Preparation
├── 4.2 Payment Approval
└── 4.3 Payment Execution

5.0 Reporting and Analytics
├── 5.1 Standard Reporting
├── 5.2 Ad-Hoc Reporting
└── 5.3 Dashboard Analytics

6.0 System Administration
├── 6.1 User Management
├── 6.2 Security Management
└── 6.3 Configuration Management
```

### 6.2 Master Data Management Processes

#### 6.2.1 Project Setup Process

**Process ID**: BRS-MD-001

**Process Name**: Project Master Data Setup

**Process Description**: Establish and maintain project master data including Project IDs, NOA details, and project hierarchies.

**Process Owner**: USP Department Head

**Trigger**: New project approval received

**Pre-conditions**:
- Project approval documentation available
- DUSP registered in system
- Budget allocation confirmed

**Post-conditions**:
- Project master data created
- Project hierarchy established
- Stakeholders notified

**Business Requirements**:

1. **BRS-MD-001.1**: System shall support creation of Project IDs with auto-numbering
2. **BRS-MD-001.2**: System shall capture all NOA details including value, duration, milestones
3. **BRS-MD-001.3**: System shall support hierarchical structure (Project → Sub-project → Cluster → Site)
4. **BRS-MD-001.4**: System shall validate uniqueness of all identifiers
5. **BRS-MD-001.5**: System shall maintain complete audit trail of all changes

**Process Flow**:
```
Start → Validate Approval → Create Project ID → Capture NOA Details → 
Setup Hierarchy → Configure Budget → Notify Stakeholders → End
```

**Performance Requirements**:
- Project setup completion within 1 business day
- Real-time validation of identifiers
- Automatic notification within 15 minutes

#### 6.2.2 Contract Management Process

**Process ID**: BRS-MD-002

**Process Name**: Contract and Variation Management

**Process Description**: Manage contract documents, amendments, and variation orders throughout project lifecycle.

**Business Rules**:
1. All contracts must be linked to approved Project ID
2. Variation orders must reference original contract
3. Cumulative variations cannot exceed 20% without additional approval
4. All contract changes require documented approval

**Process Requirements**:

1. **BRS-MD-002.1**: System shall store contract documents with version control
2. **BRS-MD-002.2**: System shall track contract amendments with change history
3. **BRS-MD-002.3**: System shall generate alerts for contract expiry (90, 60, 30 days)
4. **BRS-MD-002.4**: System shall support VO creation with approval workflow
5. **BRS-MD-002.5**: System shall validate VO against approved capped cost

### 6.3 Claims Management Processes

#### 6.3.1 Claim Submission Process

**Process ID**: BRS-CM-001

**Process Name**: DUSP Claim Submission

**Process Description**: Enable DUSPs to submit claims through self-service portal with automated validation.

**Process Owner**: DUSP (External)

**Trigger**: DUSP ready to claim for completed work

**Business Requirements**:

1. **BRS-CM-001.1**: System shall provide guided claim submission wizard
2. **BRS-CM-001.2**: System shall support draft saving and resumption
3. **BRS-CM-001.3**: System shall validate required documents before submission
4. **BRS-CM-001.4**: System shall perform OCR on uploaded documents
5. **BRS-CM-001.5**: System shall validate against budget and project status
6. **BRS-CM-001.6**: System shall generate unique claim reference
7. **BRS-CM-001.7**: System shall confirm submission with acknowledgment

**Process Flow**:
```
Start → Select Project → Enter Claim Details → Upload Documents → 
OCR Processing → Validate Data → Review Submission → Submit → 
Receive Confirmation → End
```

**Claim Types Supported**:
- Advance Claims (with performance bond validation)
- Quarterly Claims (with progress validation)
- Major Contributor Claims (with milestone validation)
- Yearly Claims (with auditor declaration)

#### 6.3.2 Claim Verification Process

**Process ID**: BRS-CM-002

**Process Name**: MCMC Claim Verification

**Process Description**: MCMC review and verification of submitted claims with automated and manual checks.

**Process Owner**: USP Officer

**Business Requirements**:

1. **BRS-CM-002.1**: System shall present claims in verification queue
2. **BRS-CM-002.2**: System shall highlight pre-validation results
3. **BRS-CM-002.3**: System shall support document viewing and comparison
4. **BRS-CM-002.4**: System shall enable verification of calculations
5. **BRS-CM-002.5**: System shall allow request for additional information
6. **BRS-CM-002.6**: System shall support approval, rejection, or return actions
7. **BRS-CM-002.7**: System shall maintain complete verification audit trail

**Verification Checklist**:
- [ ] Document completeness
- [ ] Budget availability
- [ ] Performance bond validity
- [ ] Milestone achievement
- [ ] Calculation accuracy
- [ ] Compliance with NOA terms
- [ ] Supporting evidence adequacy

#### 6.3.3 Claim Approval Workflow

**Process ID**: BRS-CM-003

**Process Name**: Multi-Level Claim Approval

**Process Description**: Route verified claims through appropriate approval hierarchy based on value and type.

**Approval Matrix**:

| Amount Range | Level 1 | Level 2 | Level 3 | Level 4 |
|--------------|---------|---------|---------|---------|
| < RM 100K | Department Head | - | - | - |
| RM 100K - 500K | Department Head | Finance Manager | - | - |
| RM 500K - 1M | Department Head | Finance Manager | Director | - |
| > RM 1M | Department Head | Finance Manager | Director | Commissioner |

**Business Requirements**:

1. **BRS-CM-003.1**: System shall route claims based on approval matrix
2. **BRS-CM-003.2**: System shall notify approvers via email and in-app
3. **BRS-CM-003.3**: System shall support delegation of approval authority
4. **BRS-CM-003.4**: System shall escalate overdue approvals
5. **BRS-CM-003.5**: System shall support approval comments and conditions
6. **BRS-CM-003.6**: System shall maintain approval audit trail

### 6.4 Budget Management Processes

#### 6.4.1 Budget Setup Process

**Process ID**: BRS-BM-001

**Process Name**: Approved Capped Cost Setup

**Process Description**: Establish and configure approved budgets and capped costs for projects.

**Business Requirements**:

1. **BRS-BM-001.1**: System shall capture approved capped cost by project
2. **BRS-BM-001.2**: System shall support budget breakdown by cost component
3. **BRS-BM-001.3**: System shall establish BOQ line items
4. **BRS-BM-001.4**: System shall validate total against allocation
5. **BRS-BM-001.5**: System shall notify on budget setup completion

#### 6.4.2 Budget Monitoring Process

**Process ID**: BRS-BM-002

**Process Name**: Real-Time Budget Monitoring

**Process Description**: Monitor budget utilization and provide alerts for approaching limits.

**Business Requirements**:

1. **BRS-BM-002.1**: System shall calculate real-time budget utilization
2. **BRS-BM-002.2**: System shall generate alerts at 80% utilization
3. **BRS-BM-002.3**: System shall block claims exceeding available budget
4. **BRS-BM-002.4**: System shall provide variance analysis
5. **BRS-BM-002.5**: System shall support budget forecasting

**Alert Thresholds**:
- 80% - Warning (Yellow)
- 90% - Alert (Orange)
- 100% - Critical (Red) - Block submission

### 6.5 Payment Management Processes

#### 6.5.1 Payment Preparation Process

**Process ID**: BRS-PM-001

**Process Name**: Payment Requisition Preparation

**Process Description**: Generate payment memorandums and prepare for approval.

**Business Requirements**:

1. **BRS-PM-001.1**: System shall auto-generate payment memo from approved claim
2. **BRS-PM-001.2**: System shall support memo template customization
3. **BRS-PM-001.3**: System shall attach all supporting documents
4. **BRS-PM-001.4**: System shall validate payment details
5. **BRS-PM-001.5**: System shall route for approval

#### 6.5.2 Payment Execution Process

**Process ID**: BRS-PM-002

**Process Name**: Payment Processing and Execution

**Process Description**: Execute approved payments through USPFS and banking integration.

**Business Requirements**:

1. **BRS-PM-002.1**: System shall integrate with USPFS for voucher creation
2. **BRS-PM-002.2**: System shall support digital signature for payment authorization
3. **BRS-PM-002.3**: System shall transmit payment instructions to bank
4. **BRS-PM-002.4**: System shall receive and record payment confirmation
5. **BRS-PM-002.5**: System shall notify DUSP of payment

---

## 7. CLAIMS PROCESSING LIFECYCLE

### 7.1 Lifecycle Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                  CLAIMS PROCESSING LIFECYCLE                     │
└─────────────────────────────────────────────────────────────────┘

    ┌──────────┐
    │  DRAFT   │
    └────┬─────┘
         │ Submit
         ▼
    ┌──────────┐     ┌──────────┐
    │SUBMITTED │────▶│VALIDATING│
    └──────────┘     └────┬─────┘
                          │ Auto/Manual
                          ▼
                     ┌──────────┐
                     │ VERIFIED │
                     └────┬─────┘
                          │ Approve
                          ▼
                     ┌──────────┐
                     │ APPROVED │
                     └────┬─────┘
                          │ Process
                          ▼
                     ┌──────────┐
                     │  PAID    │
                     └──────────┘
                          │
         ┌────────────────┼────────────────┐
         │                │                │
         ▼                ▼                ▼
    ┌──────────┐    ┌──────────┐    ┌──────────┐
    │ RETURNED │    │ REJECTED │    │ CLOSED   │
    └──────────┘    └──────────┘    └──────────┘
```

### 7.2 Lifecycle Stages

#### 7.2.1 Draft Stage

**Description**: DUSP prepares claim with option to save and resume

**Entry Criteria**: DUSP initiates new claim

**Exit Criteria**: DUSP submits claim or cancels

**Business Rules**:
- Drafts auto-saved every 5 minutes
- Drafts retained for 30 days
- DUSP can delete own drafts

**Time Limit**: None (until auto-deletion)

#### 7.2.2 Submitted Stage

**Description**: Claim submitted awaiting validation

**Entry Criteria**: DUSP submits completed claim

**Exit Criteria**: Validation completed

**Business Rules**:
- System sends confirmation to DUSP
- Claim enters validation queue
- DUSP cannot modify submitted claim

**Time Limit**: 24 hours for initial validation

#### 7.2.3 Validating Stage

**Description**: System and/or MCMC performs validation

**Entry Criteria**: Claim submission confirmed

**Exit Criteria**: Validation results determined

**Business Rules**:
- Automated validation runs first
- Manual review for exceptions
- All validation results logged

**Time Limit**: 2-5 business days

#### 7.2.4 Verified Stage

**Description**: Claim verified and ready for approval

**Entry Criteria**: Validation passed

**Exit Criteria**: Approval decision made

**Business Rules**:
- Claim routed to appropriate approver
- Notification sent to approver
- Full documentation package available

**Time Limit**: 5-10 business days (approval)

#### 7.2.5 Approved Stage

**Description**: Claim approved for payment

**Entry Criteria**: Final approval obtained

**Exit Criteria**: Payment initiated or rejected

**Business Rules**:
- Payment memo auto-generated
- Payment workflow triggered
- DUSP notified of approval

**Time Limit**: 2-3 business days (payment processing)

#### 7.2.6 Paid Stage

**Description**: Payment executed and confirmed

**Entry Criteria**: Payment confirmation received

**Exit Criteria**: Record archived

**Business Rules**:
- DUSP notified of payment
- Records updated
- Transaction logged

**Time Limit**: N/A (final state)

### 7.3 Exception States

#### 7.3.1 Returned Status

**Trigger**: Additional information required

**Process**:
1. Reviewer returns claim with comments
2. DUSP receives notification
3. DUSP updates and resubmits
4. Claim returns to verification queue

#### 7.3.2 Rejected Status

**Trigger**: Claim does not meet requirements

**Process**:
1. Approver rejects with reason
2. DUSP receives notification
3. Appeal process available
4. Record retained for audit

---

## 8. PAYMENT PROCESSING LIFECYCLE

### 8.1 Payment Lifecycle Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                 PAYMENT PROCESSING LIFECYCLE                     │
└─────────────────────────────────────────────────────────────────┘

Claim Approved
     │
     ▼
┌──────────┐
│  MEMO    │ ──▶ Auto-generate from claim data
│ PREPARATION│
└────┬─────┘
     │
     ▼
┌──────────┐
│  APPROVAL │ ──▶ Digital signature workflow
│  WORKFLOW │
└────┬─────┘
     │
     ▼
┌──────────┐
│  VOUCHER  │ ──▶ USPFS integration
│ GENERATION│
└────┬─────┘
     │
     ▼
┌──────────┐
│  BANK     │ ──▶ Banking integration
│ TRANSFER  │
└────┬─────┘
     │
     ▼
┌──────────┐
│CONFIRMATION│ ──▶ Notification to DUSP
│  & CLOSE  │
└──────────┘
```

### 8.2 Payment Approval Hierarchy

| Payment Type | Approver 1 | Approver 2 | Approver 3 | Final Authority |
|--------------|------------|------------|------------|-----------------|
| Advance (<500K) | USP Head | Finance Manager | - | Director |
| Advance (>500K) | USP Head | Finance Manager | Director | Commissioner |
| Quarterly (<1M) | USP Head | Finance Manager | - | Director |
| Quarterly (>1M) | USP Head | Finance Manager | Director | Commissioner |
| Yearly (any) | USP Head | Finance Manager | Director | Commissioner |

### 8.3 Payment Processing Requirements

#### 8.3.1 Payment Memo Requirements

**Business Requirements**:

1. **BRS-PAY-001**: Memo shall auto-populate from claim data
2. **BRS-PAY-002**: Memo shall include claim reference, amount, payee
3. **BRS-PAY-003**: Memo shall attach all supporting documents
4. **BRS-PAY-004**: Memo shall route through approval workflow
5. **BRS-PAY-005**: Memo shall support digital signature

#### 8.3.2 USPFS Integration Requirements

1. **BRS-PAY-006**: System shall transmit payment data to USPFS
2. **BRS-PAY-007**: System shall receive voucher number from USPFS
3. **BRS-PAY-008**: System shall reconcile UCMS and USPFS records
4. **BRS-PAY-009**: System shall handle integration errors

#### 8.3.3 Banking Integration Requirements

1. **BRS-PAY-010**: System shall generate payment instruction file
2. **BRS-PAY-011**: System shall receive payment confirmation
3. **BRS-PAY-012**: System shall update payment status
4. **BRS-PAY-013**: System shall notify DUSP of payment

---

## 9. BUDGET MANAGEMENT LIFECYCLE

### 9.1 Budget Lifecycle Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                  BUDGET MANAGEMENT LIFECYCLE                     │
└─────────────────────────────────────────────────────────────────┘

Budget Approved by Ministry
           │
           ▼
    ┌──────────────┐
    │   ALLOCATE   │ ──▶ Distribute to projects
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   COMMIT     │ ──▶ Reserve for approved projects
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   UTILIZE    │ ──▶ Claims against budget
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   MONITOR    │ ──▶ Track vs actual
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   FORECAST   │ ──▶ Predict future needs
    └──────────────┘
```

### 9.2 Budget Control Rules

#### 9.2.1 Hard Controls

1. **BRS-BUD-001**: System shall block claims exceeding available budget
2. **BRS-BUD-002**: System shall require additional approval for budget overruns
3. **BRS-BUD-003**: System shall maintain budget reserve (5% minimum)

#### 9.2.2 Soft Controls

1. **BRS-BUD-004**: System shall warn at 80% budget utilization
2. **BRS-BUD-005**: System shall alert at 90% budget utilization
3. **BRS-BUD-006**: System shall provide budget forecasting

### 9.3 Budget Adjustment Process

**Trigger**: Need to modify approved budget

**Process Flow**:
1. Budget adjustment request submitted
2. Justification and impact analysis provided
3. Approval workflow executed
4. Upon approval, budget updated
5. Stakeholders notified

**Approval Requirements**:
- < 10% increase: Director approval
- 10-20% increase: Commissioner approval
- > 20% increase: Board approval required

---

## 10. BUSINESS RULES

### 10.1 Master Data Rules

| Rule ID | Rule Description | Enforcement | Exception Process |
|---------|------------------|-------------|-------------------|
| BR-MD-001 | Project ID must be unique | System enforced | N/A |
| BR-MD-002 | NOA end date must be after start date | System enforced | N/A |
| BR-MD-003 | Site ID must belong to valid Cluster | System enforced | N/A |
| BR-MD-004 | Performance bond must cover contract value | System enforced | Commissioner approval |
| BR-MD-005 | EOT cannot exceed 24 months total | System enforced | Board approval |

### 10.2 Claims Rules

| Rule ID | Rule Description | Enforcement | Exception Process |
|---------|------------------|-------------|-------------------|
| BR-CM-001 | Advance claim requires valid performance bond | System enforced | N/A |
| BR-CM-002 | Claim amount cannot exceed approved BOQ | System enforced | VO approval |
| BR-CM-003 | Quarterly claim requires progress report | System enforced | N/A |
| BR-CM-004 | Yearly claim requires auditor declaration | System enforced | Extension approval |
| BR-CM-005 | Claim submission within 90 days of period end | System enforced | EOT approval |
| BR-CM-006 | Supporting documents mandatory for all claims | System enforced | N/A |
| BR-CM-007 | CEO declaration required for claims > RM 100K | System enforced | N/A |

### 10.3 Budget Rules

| Rule ID | Rule Description | Enforcement | Exception Process |
|---------|------------------|-------------|-------------------|
| BR-BM-001 | Claims blocked if insufficient budget | System enforced | Budget transfer |
| BR-BM-002 | VO cannot increase budget without approval | System enforced | Approval workflow |
| BR-BM-003 | Cost components must sum to total claim | System enforced | N/A |
| BR-BM-004 | Site costing must reconcile to project budget | System enforced | N/A |

### 10.4 Payment Rules

| Rule ID | Rule Description | Enforcement | Exception Process |
|---------|------------------|-------------|-------------------|
| BR-PM-001 | Payment only for approved claims | System enforced | N/A |
| BR-PM-002 | Digital signature required for all payments | System enforced | Manual process |
| BR-PM-003 | Payment memo must match claim amount | System enforced | N/A |
| BR-PM-004 | Bank account must be validated before payment | System enforced | N/A |

### 10.5 Security Rules

| Rule ID | Rule Description | Enforcement | Exception Process |
|---------|------------------|-------------|-------------------|
| BR-SEC-001 | Users can only access authorized data | System enforced | Admin override |
| BR-SEC-002 | Approver cannot approve own submission | System enforced | N/A |
| BR-SEC-003 | All financial actions require 2-person rule | System enforced | N/A |
| BR-SEC-004 | Password change required every 90 days | System enforced | Admin exception |

---

## 11. COMPLIANCE REQUIREMENTS

### 11.1 Regulatory Compliance

#### 11.1.1 Communications and Multimedia Act 1998

**Requirement**: System must support MCMC's statutory obligations under Act 588.

**Compliance Measures**:
1. Complete audit trail of all USP-related decisions
2. Transparent claims processing
3. Equitable treatment of all DUSPs
4. Regulatory reporting capabilities

#### 11.1.2 Personal Data Protection Act 2010

**Requirement**: System must protect personal data of all users.

**Compliance Measures**:
1. Data encryption at rest and in transit
2. Access controls based on need-to-know
3. Data retention policies
4. Consent management for data processing
5. Right to access and deletion

#### 11.1.3 Electronic Commerce Act 2006

**Requirement**: Digital signatures and electronic records must be legally valid.

**Compliance Measures**:
1. Certified digital signature provider integration
2. Tamper-evident document storage
3. Timestamp and non-repudiation
4. Electronic record retention

#### 11.1.4 Financial Procedures

**Requirement**: System must comply with government financial regulations.

**Compliance Measures**:
1. Segregation of duties
2. Multi-level approvals
3. Complete audit trails
4. Reconciliation capabilities

### 11.2 Audit Requirements

#### 11.2.1 Internal Audit

**Requirements**:
1. Complete audit trail of all transactions
2. User activity logs
3. Data change tracking
4. Report generation for audit queries

#### 11.2.2 External Audit

**Requirements**:
1. Auditor access to system (read-only)
2. Standard audit reports
3. Data export capabilities
4. Audit query response within 4 hours

### 11.3 Governance Requirements

#### 11.3.1 Transparency

**Requirements**:
1. Real-time status visibility for DUSPs
2. Public dashboard (where appropriate)
3. Standardized processes
4. Documented decision rationale

#### 11.3.2 Accountability

**Requirements**:
1. Clear roles and responsibilities
2. Approval authority matrix
3. Performance metrics
4. Exception reporting

---

## 12. RISK MANAGEMENT

### 12.1 Business Risk Assessment

| Risk ID | Risk Description | Likelihood | Impact | Mitigation Strategy |
|---------|------------------|------------|--------|---------------------|
| RISK-001 | System downtime during critical period | Medium | High | 99.9% uptime SLA, DR plan |
| RISK-002 | Data breach or unauthorized access | Low | Critical | Encryption, MFA, RBAC |
| RISK-003 | Integration failure with USPFS | Medium | High | Fallback procedures, testing |
| RISK-004 | User adoption challenges | Medium | Medium | Training, change management |
| RISK-005 | Fraudulent claims submission | Medium | High | AI fraud detection, validation |
| RISK-006 | Budget overrun | Low | Medium | Alerts, controls, forecasting |
| RISK-007 | Non-compliance with regulations | Low | Critical | Compliance monitoring, audits |
| RISK-008 | Vendor lock-in | Low | Medium | Open standards, documentation |

### 12.2 Risk Mitigation Strategies

#### 12.2.1 Technical Risks

**Strategy**: Robust architecture and testing
- Redundant infrastructure
- Comprehensive testing (UAT, FAT, SIT)
- Penetration testing
- Regular security audits

#### 12.2.2 Operational Risks

**Strategy**: Change management and training
- Comprehensive training program
- User manuals and guides
- Helpdesk support
- Change management workshops

#### 12.2.3 Compliance Risks

**Strategy**: Proactive compliance monitoring
- Regular compliance audits
- Policy enforcement
- Audit trail review
- Regulatory updates

### 12.3 Business Continuity

#### 12.3.1 Continuity Requirements

1. **RTO**: 4 hours maximum
2. **RPO**: 1 hour maximum
3. **Backup Frequency**: Daily incremental, weekly full
4. **DR Testing**: Quarterly drills

#### 12.3.2 Continuity Procedures

1. Automatic failover to DR site
2. Data replication in real-time
3. Regular restoration testing
4. Documented recovery procedures

---

## 13. STAKEHOLDER REQUIREMENTS

### 13.1 Internal Stakeholders

#### 13.1.1 MCMC Management

**Requirements**:
1. Executive dashboards with KPIs
2. Exception alerts and notifications
3. Strategic reporting
4. Mobile access for approvals

**Success Criteria**:
- Real-time visibility into program status
- Proactive risk identification
- Efficient decision-making support

#### 13.1.2 USP Department

**Requirements**:
1. Efficient claim processing tools
2. DUSP management capabilities
3. Project tracking and monitoring
4. Verification and validation tools

**Success Criteria**:
- 67% reduction in processing time
- 90% user satisfaction
- <2% error rate

#### 13.1.3 Finance Department

**Requirements**:
1. Budget management tools
2. Payment processing integration
3. Financial reporting
4. Reconciliation support

**Success Criteria**:
- Real-time budget visibility
- Automated reconciliation
- Accurate financial reporting

### 13.2 External Stakeholders

#### 13.2.1 DUSPs

**Requirements**:
1. Self-service portal
2. Real-time status tracking
3. Mobile access
4. Clear communication

**Success Criteria**:
- 24/7 access to information
- Transparent processing
- Timely payments

#### 13.2.2 Subcontractors

**Requirements**:
1. Limited portal access
2. Document submission
3. Progress reporting
4. Payment visibility

**Success Criteria**:
- Easy access to relevant information
- Streamlined submission process

---

## 14. BUSINESS METRICS AND KPIs

### 14.1 Performance Metrics

| Metric | Current | Target | Measurement Frequency |
|--------|---------|--------|---------------------|
| Average Processing Time | 52 days | 17 days | Weekly |
| First-Pass Approval Rate | 75% | 95% | Monthly |
| Claims per FTE | 15/month | 60/month | Monthly |
| System Uptime | N/A | 99.9% | Continuous |
| User Satisfaction | 55% | 85% | Quarterly |

### 14.2 Quality Metrics

| Metric | Current | Target | Measurement Frequency |
|--------|---------|--------|---------------------|
| Error Rate | 13% | <2% | Monthly |
| Rework Rate | 15% | <5% | Monthly |
| Audit Findings | 10/audit | <2/audit | Per audit |
| Data Accuracy | 87% | 98% | Monthly |

### 14.3 Financial Metrics

| Metric | Current | Target | Measurement Frequency |
|--------|---------|--------|---------------------|
| Cost per Claim | RM 660 | RM 250 | Monthly |
| Processing Cost | RM 1.65M/year | RM 625K/year | Annual |
| ROI | N/A | 150% at 24 months | Annual |

### 14.4 Dashboard Requirements

**Executive Dashboard**:
- Program overview
- Financial summary
- Risk indicators
- Exception alerts

**Operational Dashboard**:
- Claim pipeline
- Processing bottlenecks
- Workload distribution
- Quality metrics

**DUSP Dashboard**:
- Claim status
- Payment status
- Project progress
- Document status

---

## 15. GLOSSARY

| Term | Definition |
|------|------------|
| **Advance Claim** | Claim for upfront payment before work completion |
| **BOQ** | Bill of Quantity - detailed list of work items and costs |
| **Capped Cost** | Maximum approved cost for a project |
| **Cluster** | Grouping of related sites within a project |
| **DUSP** | Designated Universal Service Provider |
| **EOT** | Extension of Time - approved project timeline extension |
| **FAT** | Final Acceptance Testing |
| **FTE** | Full-Time Equivalent - measure of staffing |
| **KPI** | Key Performance Indicator |
| **MCMC** | Malaysian Communications and Multimedia Commission |
| **NOA** | Notification of Approval - contract award document |
| **OCR** | Optical Character Recognition |
| **RPA** | Robotic Process Automation |
| **SIT** | System Integration Testing |
| **SLA** | Service Level Agreement |
| **USP** | Universal Service Provision |
| **USPFS** | USP Financial System (Oracle EBS) |
| **UAT** | User Acceptance Testing |
| **VO** | Variation Order - approved change to contract |

---

## 16. APPENDICES

### Appendix A: Business Process Model Diagrams

#### A.1 High-Level Process Model

```
┌─────────────────────────────────────────────────────────────────┐
│              UCMS HIGH-LEVEL BUSINESS PROCESS MODEL              │
└─────────────────────────────────────────────────────────────────┘

┌─────────────┐      ┌─────────────┐      ┌─────────────┐
│   DUSP      │─────▶│    UCMS     │─────▶│    MCMC     │
│  (External) │      │   (System)  │      │  (Internal) │
└─────────────┘      └──────┬──────┘      └─────────────┘
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
        ┌─────────┐   ┌─────────┐   ┌─────────┐
        │ USPFS   │   │  Bank   │   │ Digital │
        │(Oracle) │   │         │   │  Sig    │
        └─────────┘   └─────────┘   └─────────┘
```

### Appendix B: Stakeholder Matrix

| Stakeholder | Interest | Influence | Engagement Strategy |
|-------------|----------|-----------|---------------------|
| MCMC Management | High | High | Regular briefings, dashboard access |
| USP Department | High | High | Daily interaction, training |
| Finance Department | High | Medium | Weekly reviews, reports |
| DUSPs | High | Medium | Portal, newsletters, support |
| Subcontractors | Medium | Low | Limited portal access, FAQs |
| Auditors | Medium | Medium | Audit access, reports |

### Appendix C: Business Rule Summary

| Category | Rule Count | Validation Type |
|----------|------------|-----------------|
| Master Data | 5 | System enforced |
| Claims | 7 | System + Manual |
| Budget | 4 | System enforced |
| Payment | 4 | System enforced |
| Security | 4 | System enforced |
| **Total** | **24** | - |

### Appendix D: Compliance Checklist

| Requirement | Status | Evidence |
|-------------|--------|----------|
| Act 588 Compliance | Pending | Audit trail design |
| PDPA 2010 Compliance | Pending | Privacy impact assessment |
| ECA 2006 Compliance | Pending | Digital signature integration |
| Financial Procedures | Pending | Approval workflow design |

### Appendix E: Risk Register Summary

| Risk Category | Count | High Priority |
|---------------|-------|---------------|
| Technical | 3 | 1 |
| Operational | 2 | 1 |
| Compliance | 2 | 2 |
| External | 1 | 0 |
| **Total** | **8** | **4** |

---

## DOCUMENT CERTIFICATION

This Business Requirements Specification has been reviewed and approved by the following stakeholders:

**Prepared by:**

Name: _________________________

Title: Business Analyst

Signature: _________________________

Date: _________________________

**Reviewed by:**

Name: _________________________

Title: Solution Architect

Signature: _________________________

Date: _________________________

**Approved by:**

Name: _________________________

Title: Project Sponsor

Signature: _________________________

Date: _________________________

---

**END OF DOCUMENT**

---

*Document Control: This document is controlled and maintained by the Project Management Office. Any changes must be approved and documented in the version history.*
