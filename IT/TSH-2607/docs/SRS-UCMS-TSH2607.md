# SYSTEM REQUIREMENTS SPECIFICATION (SRS)

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
| 0.1 | 15 Feb 2026 | System Analyst | Initial Draft | - |
| 0.2 | 17 Feb 2026 | Solution Architect | Technical Review | - |
| 0.3 | 18 Feb 2026 | Project Manager | Consolidation | - |
| 1.0 | 18 Feb 2026 | Project Manager | Final Release | MCMC Representative |

### Approval Signatures

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Solution Architect | [Name] | _________________ | _______ |
| System Analyst | [Name] | _________________ | _______ |
| Technical Lead | [Name] | _________________ | _______ |
| MCMC Representative | [Name] | _________________ | _______ |

---

## TABLE OF CONTENTS

1. [Introduction](#1-introduction)
2. [System Overview](#2-system-overview)
3. [Functional Requirements](#3-functional-requirements)
4. [System Modules Requirements](#4-system-modules-requirements)
5. [Integration Requirements](#5-integration-requirements)
6. [Data Requirements](#6-data-requirements)
7. [Security Requirements](#7-security-requirements)
8. [Performance Requirements](#8-performance-requirements)
9. [Interface Requirements](#9-interface-requirements)
10. [Non-Functional Requirements](#10-non-functional-requirements)
11. [System Constraints](#11-system-constraints)
12. [Assumptions and Dependencies](#12-assumptions-and-dependencies)
13. [Glossary](#13-glossary)
14. [Appendices](#14-appendices)

---

## 1. INTRODUCTION

### 1.1 Purpose

This System Requirements Specification (SRS) document provides a comprehensive description of the technical and functional requirements for the Universal Service Provision (USP) Claims Management System (UCMS). The document serves as the primary technical reference for system design, development, testing, and acceptance.

### 1.2 Scope

The SRS covers:
- Complete functional requirements for all 10 system modules
- Integration requirements with external systems
- Data and database requirements
- Security and access control requirements
- Performance and non-functional requirements
- Interface specifications
- System constraints and assumptions

### 1.3 Intended Audience

- System architects and designers
- Application developers
- Quality assurance and testing teams
- System integrators
- Technical project managers
- MCMC IT department

### 1.4 Reference Documents

- User Requirements Specification (URS) - UCMS TSH-2607
- Business Requirements Specification (BRS) - UCMS TSH-2607
- Tender Document: MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)
- USP Financial System Integration Specifications
- MCMC IT Security Standards
- Oracle EBS Technical Documentation

### 1.5 Document Conventions

**Requirement ID Format**: SRS-[Module]-[Category]-[Number]

Example: SRS-MD-FUNC-001 (Master Data - Functional - Requirement 1)

**Priority Levels**:
- **Mandatory (M)**: Must be implemented for system acceptance
- **High (H)**: Critical for system effectiveness
- **Medium (Med)**: Important for user satisfaction
- **Low (L)**: Desirable but not critical

---

## 2. SYSTEM OVERVIEW

### 2.1 System Context

```
┌─────────────────────────────────────────────────────────────────────┐
│                        SYSTEM CONTEXT DIAGRAM                        │
└─────────────────────────────────────────────────────────────────────┘

                        ┌─────────────┐
                        │   Users     │
                        │ (MCMC/DUSP) │
                        └──────┬──────┘
                               │ HTTPS
                               ▼
┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐
│  Azure   │  │   UCMS   │  │   AI/    │  │   RPA    │  │  Digital │
│    AD    │◀─┤  Web App │◀─┤   ML     │◀─┤  Engine  │◀─┤  Signature│
│   SSO    │  │          │  │ Services │  │          │  │ Provider │
└──────────┘  └────┬─────┘  └──────────┘  └──────────┘  └──────────┘
                   │
                   │ API
                   ▼
┌─────────────────────────────────────────────────────────────────┐
│                      Integration Layer                           │
├──────────┬──────────┬──────────┬──────────┬─────────────────────┤
│  USPFS   │   OCR    │  Banking │  Email/  │       Audit         │
│ (Oracle  │ Service  │   API    │  SMS     │       Logging       │
│  EBS)    │          │          │          │                     │
└──────────┴──────────┴──────────┴──────────┴─────────────────────┘
```

### 2.2 System Architecture Overview

UCMS follows a modern, scalable architecture:

**Presentation Layer**:
- React/Angular frontend
- Responsive design (desktop, tablet, mobile)
- Bilingual support (BM/English)

**Application Layer**:
- Microservices architecture
- RESTful APIs
- Business logic implementation
- Workflow engine

**Data Layer**:
- Oracle Database (primary)
- Document storage (file system/cloud)
- Cache layer (Redis)
- Search index (Elasticsearch)

**Integration Layer**:
- API Gateway
- Message queue (RabbitMQ/Kafka)
- Integration adapters
- Webhook handlers

### 2.3 Technology Stack

| Layer | Technology |
|-------|------------|
| Frontend | React.js 18+, TypeScript, Redux |
| Backend | Node.js 20+ / Java Spring Boot |
| Database | Oracle 19c |
| Cache | Redis 7+ |
| Message Queue | RabbitMQ 3.12+ |
| Search | Elasticsearch 8+ |
| OCR | Tesseract / AWS Textract |
| AI/ML | Python, TensorFlow/PyTorch |
| RPA | UiPath / Blue Prism |
| Container | Docker, Kubernetes |
| CI/CD | Jenkins, GitLab CI |

### 2.4 System Boundaries

**In-Scope**:
- Web application for all users
- Integration with USPFS (Oracle EBS)
- Digital signature integration
- OCR and AI/ML services
- RPA automation
- Mobile-responsive interface
- Reporting and analytics

**Out-of-Scope**:
- Modification to USPFS core functionality
- Mobile native apps (initial phase)
- External regulatory reporting systems
- Physical infrastructure management

---

## 3. FUNCTIONAL REQUIREMENTS

### 3.1 Core System Functions

#### 3.1.1 User Authentication and Authorization

**SRS-CORE-AUTH-001 (M)**: System shall support Azure AD Single Sign-On

**Description**: Users shall authenticate using their corporate Azure AD credentials.

**Specifications**:
- Support SAML 2.0 and OAuth 2.0 protocols
- Automatic user provisioning from Azure AD
- Session timeout after 30 minutes of inactivity
- Support for conditional access policies

**Acceptance Criteria**:
- Given valid Azure AD credentials, user logs in successfully
- Given invalid credentials, system denies access with appropriate message
- Given session timeout, system requires re-authentication

**SRS-CORE-AUTH-002 (M)**: System shall implement Role-Based Access Control (RBAC)

**Description**: Access to system functions shall be controlled by user roles.

**Specifications**:
- Predefined roles: System Admin, USP Manager, USP Officer, Finance Manager, Finance Officer, DUSP Admin, DUSP User, Subcontractor
- Custom role creation capability
- Permission assignment at function and data level
- Role hierarchy support

**Acceptance Criteria**:
- Given user with specific role, system enforces role permissions
- Given permission change, system applies immediately
- Given unauthorized access attempt, system logs and blocks

#### 3.1.2 Audit Logging

**SRS-CORE-AUDIT-001 (M)**: System shall log all user activities

**Description**: Complete audit trail of all system interactions.

**Specifications**:
- Log user ID, timestamp, action type, IP address, device info
- Store before and after values for data changes
- Tamper-evident log storage
- Minimum 7-year retention

**Log Format**:
```json
{
  "timestamp": "2026-02-18T10:30:00+08:00",
  "userId": "user@example.com",
  "action": "CLAIM_SUBMIT",
  "resource": "claim_12345",
  "ipAddress": "192.168.1.100",
  "userAgent": "Mozilla/5.0...",
  "beforeValue": null,
  "afterValue": {"status": "SUBMITTED"},
  "result": "SUCCESS"
}
```

### 3.2 Notification System

**SRS-CORE-NOTIF-001 (M)**: System shall send notifications via multiple channels

**Description**: Automated notifications for events and alerts.

**Specifications**:
- Email notifications (SMTP integration)
- In-app notifications
- SMS notifications (for critical alerts)
- Configurable notification preferences
- Notification templates

**Notification Events**:
- Claim submission confirmation
- Approval required
- Status changes
- Payment processed
- System alerts
- Deadline reminders

---

## 4. SYSTEM MODULES REQUIREMENTS

### 4.1 MODULE 1: MASTER DATA MANAGEMENT

#### 4.1.1 Project ID Management

**SRS-MD-PROJ-001 (M)**: System shall generate unique Project IDs

**Specifications**:
- Format: USP-YYYY-NNNN (e.g., USP-2026-0001)
- Auto-incrementing sequence
- Year reset for sequence
- Validation for uniqueness

**Data Model**:
```
Project ID Structure:
- project_id (PK, VARCHAR(15))
- project_name (VARCHAR(255))
- description (TEXT)
- start_date (DATE)
- end_date (DATE)
- total_budget (DECIMAL(15,2))
- status (ENUM: ACTIVE, COMPLETED, CANCELLED)
- created_by (VARCHAR(100))
- created_date (TIMESTAMP)
- modified_by (VARCHAR(100))
- modified_date (TIMESTAMP)
```

**SRS-MD-PROJ-002 (M)**: System shall support hierarchical project structure

**Specifications**:
- 4-tier hierarchy: Project → Sub-project → Cluster → Site
- Parent-child relationship enforcement
- Cascading updates where appropriate
- Roll-up reporting capability

**Hierarchy Rules**:
- Project can have multiple Sub-projects
- Sub-project can have multiple Clusters
- Cluster can have multiple Sites
- Each level has unique identifier
- Deletion of parent requires child cleanup

#### 4.1.2 NOA (Notification of Approval) Management

**SRS-MD-NOA-001 (M)**: System shall capture complete NOA details

**Data Elements**:
- NOA Reference Number
- Contract Value
- Contract Start Date
- Contract End Date
- Project Milestones
- Performance Bond Requirements
- Payment Terms
- Variation Limits

**SRS-MD-NOA-002 (M)**: System shall manage contract variations

**Specifications**:
- VO ID generation (VO-YYYY-NNNN)
- Variation type tracking (Scope, Cost, Time)
- Approval workflow for variations
- Cumulative variation tracking
- Limit enforcement (e.g., max 20% of original)

#### 4.1.3 Performance Bond Management

**SRS-MD-BOND-001 (M)**: System shall track performance bonds

**Data Model**:
```
Performance Bond:
- bond_id (PK)
- project_id (FK)
- dusp_id (FK)
- bond_type (ENUM: CASH, BANK_GUARANTEE, INSURANCE)
- bond_amount (DECIMAL(15,2))
- issue_date (DATE)
- expiry_date (DATE)
- issuing_bank (VARCHAR(255))
- bond_document (BLOB/File reference)
- status (ENUM: ACTIVE, EXPIRED, CLAIMED, RELEASED)
```

**SRS-MD-BOND-002 (M)**: System shall provide bond expiry alerts

**Specifications**:
- Alert at 90 days before expiry
- Alert at 60 days before expiry
- Alert at 30 days before expiry
- Daily alert within final 7 days
- Alert to DUSP and MCMC

#### 4.1.4 Master Data Integration Requirements

**SRS-MD-INT-001 (M)**: System shall synchronize with USPFS

**Specifications**:
- Real-time or near-real-time synchronization
- Bidirectional data flow where applicable
- Conflict resolution rules
- Synchronization logging
- Error handling and retry mechanism

**Synchronization Frequency**:
- Project data: Real-time
- Budget data: Hourly
- Vendor data: Daily
- Payment data: Real-time

### 4.2 MODULE 2: DUSP, SUBCONTRACTORS & USER MANAGEMENT

#### 4.2.1 User Account Management

**SRS-UM-ACCT-001 (M)**: System shall support comprehensive user lifecycle

**Functions**:
- User registration (invitation-based for external)
- Profile management
- Password management
- Account suspension/activation
- Account termination
- Bulk user operations

**SRS-UM-ACCT-002 (M)**: System shall support organization management

**Specifications**:
- DUSP organization profiles
- Subcontractor organization profiles
- Organization hierarchy
- Contact management
- Bank account details

**Data Model**:
```
Organization:
- org_id (PK)
- org_type (ENUM: DUSP, SUBCONTRACTOR, MCMC)
- registration_number (VARCHAR(50))
- org_name (VARCHAR(255))
- address (TEXT)
- contact_person (VARCHAR(100))
- contact_email (VARCHAR(100))
- contact_phone (VARCHAR(20))
- bank_account_number (VARCHAR(50))
- bank_name (VARCHAR(100))
- status (ENUM: ACTIVE, SUSPENDED, INACTIVE)
```

#### 4.2.2 Role and Permission Management

**SRS-UM-ROLE-001 (M)**: System shall implement granular permissions

**Permission Categories**:
- Module access permissions
- Function permissions (Create, Read, Update, Delete)
- Data permissions (Own, Department, Organization, All)
- Field-level permissions
- Report permissions

**SRS-UM-ROLE-002 (M)**: System shall enforce segregation of duties

**Rules**:
- Submitter cannot approve own claim
- Creator cannot approve own data changes
- Financial approver cannot be verifier
- System admin cannot approve transactions

#### 4.2.3 Delegation Management

**SRS-UM-DELEG-001 (H)**: System shall support delegation of authority

**Specifications**:
- Delegation by function (approval, verification, etc.)
- Date range for delegation
- Delegation history tracking
- Automatic revocation
- Notification to delegate

### 4.3 MODULE 3: BUDGET MANAGEMENT

#### 4.3.1 Budget Setup

**SRS-BM-SETUP-001 (M)**: System shall support budget allocation

**Specifications**:
- Multi-level budget structure
- Budget allocation by project/component
- Budget version control
- Budget transfer capability
- Approval workflow for changes

**Budget Structure**:
```
Budget Hierarchy:
- Total USP Allocation
  - By Program
    - By Project
      - By Component
        - By Cost Category
          - By Site
```

**SRS-BM-SETUP-002 (M)**: System shall manage approved capped costs

**Data Model**:
```
Capped Cost:
- capped_cost_id (PK)
- project_id (FK)
- noa_id (FK)
- total_capped_cost (DECIMAL(15,2))
- cost_breakdown (JSON)
  - preliminary_costs
  - equipment_costs
  - installation_costs
  - other_costs
- effective_date (DATE)
- expiry_date (DATE)
- status (ENUM: ACTIVE, EXHAUSTED, SUPERSEDED)
```

#### 4.3.2 Budget Control

**SRS-BM-CTRL-001 (M)**: System shall enforce budget limits

**Specifications**:
- Hard stop at 100% utilization
- Warning at 80% utilization
- Alert at 90% utilization
- Reserve calculation (minimum 5%)
- Block submission when exceeded

**SRS-BM-CTRL-002 (M)**: System shall provide real-time budget visibility

**Dashboard Elements**:
- Total budget
- Committed amount
- Spent amount
- Available balance
- Utilization percentage
- Variance analysis
- Forecast projection

#### 4.3.3 Bill of Quantity (BOQ)

**SRS-BM-BOQ-001 (M)**: System shall support BOQ management

**Specifications**:
- Itemized list of works/materials
- Quantity and unit management
- Rate and amount calculation
- BOQ template library
- Import from Excel

**Data Model**:
```
BOQ Item:
- boq_item_id (PK)
- project_id (FK)
- item_number (VARCHAR(20))
- description (TEXT)
- unit_of_measure (VARCHAR(20))
- quantity (DECIMAL(12,2))
- rate (DECIMAL(12,2))
- amount (DECIMAL(15,2))
- category (VARCHAR(50))
- milestone_link (VARCHAR(50))
```

### 4.4 MODULE 4: CLAIMS MANAGEMENT

#### 4.4.1 Claim Submission

**SRS-CM-SUBMIT-001 (M)**: System shall support multiple claim types

**Claim Types**:
1. **Advance Claim**: Upfront payment (typically 10-30%)
2. **Quarterly Claim**: Progress-based claims
3. **Major Contributor Claim**: Specific milestone payments
4. **Yearly Claim**: Annual consolidation

**SRS-CM-SUBMIT-002 (M)**: System shall provide guided submission wizard

**Wizard Steps**:
1. Select project and claim type
2. Enter claim details and amounts
3. Upload supporting documents
4. OCR processing and data extraction
5. Data validation and review
6. Digital signature (if required)
7. Submit and receive confirmation

**SRS-CM-SUBMIT-003 (M)**: System shall validate claim eligibility

**Validation Rules**:
- Project status must be ACTIVE
- NOA must be valid
- Budget must be available
- Performance bond must be valid (for advance)
- Previous claims must be reconciled
- Submission within time limits

#### 4.4.2 Document Management

**SRS-CM-DOC-001 (M)**: System shall support document upload

**Specifications**:
- Supported formats: PDF, DOC, DOCX, XLS, XLSX, JPG, PNG
- Maximum file size: 50MB per file
- Batch upload capability
- Virus scanning on upload
- Metadata capture

**SRS-CM-DOC-002 (M)**: System shall implement OCR processing

**OCR Capabilities**:
- Text extraction from PDFs and images
- Invoice data extraction
- Receipt validation
- Document classification
- Confidence scoring

**SRS-CM-DOC-003 (M)**: System shall support AI-powered document validation

**AI Validation**:
- Document authenticity check
- Tampering detection
- Duplicate detection
- Expired document detection
- Fraud pattern recognition

#### 4.4.3 Claim Verification

**SRS-CM-VERIFY-001 (M)**: System shall provide verification queue

**Specifications**:
- Prioritized queue based on age/urgency
- Batch verification capability
- Side-by-side document viewing
- Comparison tools
- Annotation capability

**SRS-CM-VERIFY-002 (M)**: System shall support verification checklist

**Checklist Items**:
- [ ] Document completeness
- [ ] Budget availability verified
- [ ] Performance bond valid
- [ ] Milestones achieved
- [ ] Calculations correct
- [ ] Supporting evidence adequate
- [ ] Compliance with NOA terms
- [ ] No duplicate claims

#### 4.4.4 Claim Approval Workflow

**SRS-CM-APPROVE-001 (M)**: System shall implement configurable workflow

**Workflow Features**:
- Dynamic routing based on amount/type
- Parallel approval where applicable
- Escalation rules
- Delegation support
- Approval comments

**Approval Actions**:
- Approve
- Approve with conditions
- Reject
- Return for correction
- Request additional information
- Escalate

#### 4.4.5 Claim Status Tracking

**SRS-CM-STATUS-001 (M)**: System shall maintain claim status

**Status Values**:
- DRAFT
- SUBMITTED
- UNDER_REVIEW
- ADDITIONAL_INFO_REQUIRED
- VERIFIED
- APPROVED
- REJECTED
- PAYMENT_PROCESSING
- PAID
- CLOSED

**Status Transitions**:
```
DRAFT → SUBMITTED
SUBMITTED → UNDER_REVIEW
UNDER_REVIEW → VERIFIED | ADDITIONAL_INFO_REQUIRED | REJECTED
ADDITIONAL_INFO_REQUIRED → UNDER_REVIEW
VERIFIED → APPROVED | REJECTED
APPROVED → PAYMENT_PROCESSING
PAYMENT_PROCESSING → PAID
PAID → CLOSED
```

### 4.5 MODULE 5: PAYMENT PROCESSING

#### 4.5.1 Payment Preparation

**SRS-PM-PREP-001 (M)**: System shall generate payment memos

**Specifications**:
- Auto-generation from approved claim
- Template-based with customization
- Pre-population of claim data
- Supporting document attachment
- Digital signature placeholder

**SRS-PM-PREP-002 (M)**: System shall support payment batching

**Specifications**:
- Group payments by date/bank
- Batch approval capability
- Batch payment advice generation
- Batch notification

#### 4.5.2 Payment Approval

**SRS-PM-APPROVE-001 (M)**: System shall implement payment approval workflow

**Specifications**:
- Minimum 3 approval levels
- Amount-based routing
- Digital signature integration
- Mobile approval support
- Approval deadline tracking

**SRS-PM-APPROVE-002 (M)**: System shall support digital signatures

**Specifications**:
- Integration with certified providers
- Multiple signature types (approval, authorization)
- Signature validation
- Timestamp and audit trail
- Non-repudiation

#### 4.5.3 Payment Execution

**SRS-PM-EXEC-001 (M)**: System shall integrate with USPFS

**Specifications**:
- Voucher creation via API
- Payment instruction generation
- Status tracking
- Reconciliation support
- Error handling

**SRS-PM-EXEC-002 (M)**: System shall provide payment tracking

**Tracking Information**:
- Payment instruction sent
- Bank acknowledgment
- Payment executed
- Credit confirmed
- Notification sent

### 4.6 MODULE 6: REPORTS

#### 4.6.1 Standard Reports

**SRS-RPT-STANDARD-001 (M)**: System shall provide comprehensive report library

**Report Categories**:

| Report ID | Report Name | Audience | Frequency |
|-----------|-------------|----------|-----------|
| RPT-001 | Claim Status Summary | Operations | Daily |
| RPT-002 | Budget Utilization | Finance | Weekly |
| RPT-003 | DUSP Performance | Management | Monthly |
| RPT-004 | Payment Pipeline | Finance | Weekly |
| RPT-005 | Exception Report | Operations | Daily |
| RPT-006 | Audit Trail Summary | Audit | On-demand |
| RPT-007 | Project Progress | Management | Monthly |
| RPT-008 | User Activity | Admin | Monthly |
| RPT-009 | Financial Forecast | Management | Quarterly |
| RPT-010 | Compliance Status | Compliance | Monthly |

**SRS-RPT-STANDARD-002 (M)**: System shall support report scheduling

**Specifications**:
- Schedule definition (daily, weekly, monthly)
- Email distribution list
- Format selection (PDF, Excel)
- Parameter saving
- Schedule management

#### 4.6.2 Ad-Hoc Reporting

**SRS-RPT-ADHOC-001 (H)**: System shall provide query builder

**Features**:
- Drag-and-drop interface
- Field selection
- Filter conditions
- Sort and group
- Aggregation functions
- Save and share queries

**SRS-RPT-ADHOC-002 (H)**: System shall support data export

**Export Formats**:
- Excel (.xlsx)
- PDF
- CSV
- JSON (for integration)

### 4.7 MODULE 7: DASHBOARD

#### 4.7.1 Dashboard Types

**SRS-DB-TYPES-001 (M)**: System shall provide role-based dashboards

**Dashboard Categories**:

1. **Executive Dashboard**
   - Program overview
   - Financial summary
   - Key risk indicators
   - Exception alerts

2. **Operational Dashboard**
   - Claim pipeline
   - Processing bottlenecks
   - Workload distribution
   - Quality metrics

3. **DUSP Dashboard**
   - Claim status
   - Payment status
   - Project progress
   - Document status

4. **Finance Dashboard**
   - Budget utilization
   - Payment status
   - Reconciliation status
   - Forecast vs actual

#### 4.7.2 Dashboard Widgets

**SRS-DB-WIDGET-001 (M)**: System shall provide configurable widgets

**Widget Types**:
- KPI cards
- Line/bar charts
- Pie/donut charts
- Data tables
- Gauges
- Maps (geographic visualization)
- Alert panels
- Trend indicators

**SRS-DB-WIDGET-002 (M)**: System shall support real-time updates

**Specifications**:
- Auto-refresh every 5 minutes
- Manual refresh option
- Push notifications for critical changes
- Data freshness indicators

#### 4.7.3 Required Dashboards

**SRS-DB-REQUIRED-001 (M)**: System shall implement 12 required dashboards

Per tender requirement:
1. Fund Position Dashboard (High Level)
2. Project Delivery/Milestone Dashboard (High Level)
3. Payment Disbursement Dashboard (High Level)
4. Compliance & Exception Dashboard
5. Integration & System Dashboard
6. Project & Site Monitoring Dashboard
7. Claims & Payment Status Dashboard
8. Budget Utilisation Dashboard
9. DUSP/Subcontractor Performance Dashboard
10. Security & Backup Monitoring Dashboard
11. Exception & Workflow Dashboard
12. Dynamic Data Export Report (Excel)

### 4.8 MODULE 8: AUDIT TRAIL

#### 4.8.1 Audit Logging

**SRS-AT-LOG-001 (M)**: System shall log all activities

**Logged Events**:
- User login/logout
- Data creation, modification, deletion
- Approval actions
- Document access
- Report generation
- Configuration changes
- Security events

**SRS-AT-LOG-002 (M)**: System shall provide tamper-evident logging

**Specifications**:
- Immutable log storage
- Cryptographic hashing
- Chain of custody
- Backup and archival
- 7-year retention minimum

#### 4.8.2 Audit Reporting

**SRS-AT-RPT-001 (M)**: System shall provide audit query capabilities

**Query Parameters**:
- Date range
- User
- Action type
- Resource type
- Resource ID
- Result (success/failure)

**SRS-AT-RPT-002 (M)**: System shall generate audit reports

**Report Types**:
- Activity summary
- Detailed transaction log
- User activity report
- Exception report
- Compliance report

### 4.9 MODULE 9: SELF-SERVICE APPLICATION

#### 4.9.1 Portal Features

**SRS-SS-PORTAL-001 (M)**: System shall provide self-service portal

**Features**:
- Claim submission
- Document upload
- Status tracking
- Report access
- Profile management
- Notification preferences
- Help and support access

**SRS-SS-PORTAL-002 (M)**: System shall support mobile access

**Specifications**:
- Responsive design
- Touch-friendly interface
- Mobile-optimized forms
- Camera integration for document capture
- Push notifications

#### 4.9.2 User Experience

**SRS-SS-UX-001 (H)**: System shall provide guided user experience

**Features**:
- Contextual help
- Tooltips and hints
- Progress indicators
- Validation feedback
- Confirmation dialogs
- Error recovery guidance

### 4.10 MODULE 10: VALUE-ADDED FUNCTIONS

#### 4.10.1 Analytics and Insights

**SRS-VA-ANALYTICS-001 (H)**: System shall provide predictive analytics

**Capabilities**:
- Claim pattern analysis
- Budget forecasting
- Risk prediction
- Anomaly detection
- Trend identification

**SRS-VA-ANALYTICS-002 (H)**: System shall provide intelligent alerts

**Alert Types**:
- Upcoming deadlines
- Budget threshold breaches
- Unusual claim patterns
- Performance bond expirations
- Approval bottlenecks

#### 4.10.2 Automation Features

**SRS-VA-AUTO-001 (H)**: System shall support RPA integration

**RPA Use Cases**:
- Data entry automation
- Report distribution
- Reconciliation tasks
- Notification processing
- Document routing

---

## 5. INTEGRATION REQUIREMENTS

### 5.1 USPFS (Oracle EBS) Integration

#### 5.1.1 Integration Architecture

**SRS-INT-USPFS-001 (M)**: System shall integrate with Oracle EBS

**Integration Pattern**: API-based with message queue

**Integration Points**:
- Master data synchronization
- Payment voucher creation
- Budget data retrieval
- Vendor information
- Payment status updates

#### 5.1.2 Data Synchronization

**SRS-INT-SYNC-001 (M)**: System shall synchronize master data

**Synchronization Scope**:
- Project master data
- Vendor master data
- Chart of accounts
- Cost centers
- Budget data

**Frequency**:
- Real-time for critical data
- Hourly for standard data
- Daily for reference data

#### 5.1.3 API Specifications

**SRS-INT-API-001 (M)**: System shall use REST APIs for integration

**API Standards**:
- RESTful architecture
- JSON format
- OAuth 2.0 authentication
- HTTPS transport
- API versioning

**Error Handling**:
- Retry mechanism (3 attempts)
- Exponential backoff
- Error logging
- Alerting for failures
- Manual retry capability

### 5.2 Digital Signature Integration

#### 5.2.1 Provider Integration

**SRS-INT-SIG-001 (M)**: System shall integrate with certified providers

**Supported Providers**:
- MSC TrustSign
- Docusign
- Adobe Sign
- Other certified Malaysian providers

**Integration Requirements**:
- API integration
- Webhook support
- Document templates
- Signature workflows
- Certificate validation

#### 5.2.2 Signature Workflows

**SRS-INT-SIG-002 (M)**: System shall support signature workflows

**Workflow Types**:
- Sequential signing
- Parallel signing
- Counter-signing
- Witness signing

### 5.3 Banking Integration

#### 5.3.1 Payment Advice Integration

**SRS-INT-BANK-001 (H)**: System shall receive payment confirmations

**Integration Method**: File-based or API

**Data Exchange**:
- Payment instruction files
- Payment confirmation files
- Bank statement reconciliation
- Return/rejection handling

### 5.4 Azure AD Integration

#### 5.4.1 SSO Implementation

**SRS-INT-AAD-001 (M)**: System shall implement Azure AD SSO

**Protocols**:
- SAML 2.0
- OpenID Connect
- OAuth 2.0

**Features**:
- Automatic user provisioning
- Group synchronization
- MFA support
- Conditional access
- Session management

### 5.5 OCR Service Integration

#### 5.5.1 OCR Provider

**SRS-INT-OCR-001 (M)**: System shall integrate OCR services

**Options**:
- Tesseract (open source)
- AWS Textract
- Google Document AI
- Azure Form Recognizer

**Capabilities**:
- Text extraction
- Form field extraction
- Table extraction
- Handwriting recognition
- Confidence scoring

### 5.6 AI/ML Service Integration

#### 5.6.1 Fraud Detection

**SRS-INT-AI-001 (H)**: System shall integrate AI fraud detection

**Features**:
- Anomaly detection
- Pattern recognition
- Risk scoring
- Predictive modeling

#### 5.6.2 Document Classification

**SRS-INT-AI-002 (H)**: System shall classify documents automatically

**Classification Types**:
- Invoice
- Receipt
- Contract
- Report
- Certificate
- Other

---

## 6. DATA REQUIREMENTS

### 6.1 Data Model Overview

#### 6.1.1 Entity Relationship Summary

```
┌─────────────────────────────────────────────────────────────────────┐
│                     ENTITY RELATIONSHIP OVERVIEW                     │
└─────────────────────────────────────────────────────────────────────┘

┌─────────────┐       ┌─────────────┐       ┌─────────────┐
│  Project    │◀─────▶│    NOA      │◀─────▶│    VO       │
│  (Master)   │       │  (Contract) │       │(Variation)  │
└──────┬──────┘       └─────────────┘       └─────────────┘
       │
       │ 1:N
       ▼
┌─────────────┐       ┌─────────────┐       ┌─────────────┐
│   Cluster   │◀─────▶│    Site     │◀─────▶│    BOQ      │
│             │       │             │       │             │
└─────────────┘       └──────┬──────┘       └─────────────┘
                             │
                             │ 1:N
                             ▼
                       ┌─────────────┐
                       │    Claim    │
                       │             │
                       └──────┬──────┘
                              │
              ┌───────────────┼───────────────┐
              │               │               │
              ▼               ▼               ▼
        ┌──────────┐    ┌──────────┐    ┌──────────┐
        │ Document │    │ Payment  │    │  Audit   │
        │          │    │          │    │  Log     │
        └──────────┘    └──────────┘    └──────────┘
```

### 6.2 Database Requirements

#### 6.2.1 Database Platform

**SRS-DATA-DB-001 (M)**: System shall use Oracle Database 19c

**Specifications**:
- Oracle Enterprise Edition
- RAC configuration for high availability
- Partitioning for large tables
- Advanced compression
- Data encryption (TDE)

#### 6.2.2 Database Schema

**Schema Design Principles**:
- Normalized design (3NF)
- Referential integrity
- Indexing strategy
- Partitioning by date
- Archival strategy

#### 6.2.3 Key Tables

**Projects Table**:
```sql
CREATE TABLE projects (
    project_id VARCHAR2(15) PRIMARY KEY,
    project_name VARCHAR2(255) NOT NULL,
    description CLOB,
    status VARCHAR2(20) CHECK (status IN ('ACTIVE', 'COMPLETED', 'CANCELLED')),
    start_date DATE,
    end_date DATE,
    total_budget NUMBER(15,2),
    created_by VARCHAR2(100),
    created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    modified_by VARCHAR2(100),
    modified_date TIMESTAMP,
    version NUMBER DEFAULT 1
);
```

**Claims Table**:
```sql
CREATE TABLE claims (
    claim_id VARCHAR2(20) PRIMARY KEY,
    project_id VARCHAR2(15) REFERENCES projects(project_id),
    claim_type VARCHAR2(30),
    claim_amount NUMBER(15,2),
    claim_status VARCHAR2(30),
    submission_date TIMESTAMP,
    submitted_by VARCHAR2(100),
    approval_date TIMESTAMP,
    approved_by VARCHAR2(100),
    payment_date TIMESTAMP,
    payment_reference VARCHAR2(50),
    created_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    modified_date TIMESTAMP
) PARTITION BY RANGE (submission_date);
```

### 6.3 Data Retention

#### 6.3.1 Retention Policies

**SRS-DATA-RET-001 (M)**: System shall implement data retention policies

| Data Category | Retention Period | Archive After | Destruction |
|---------------|------------------|---------------|-------------|
| Transaction Data | 7 years | 3 years | After 7 years |
| Audit Logs | 10 years | 5 years | After 10 years |
| Documents | 7 years | 3 years | After 7 years |
| System Logs | 2 years | 1 year | After 2 years |
| Backup Data | 1 year | 6 months | After 1 year |

#### 6.3.2 Archival Strategy

**SRS-DATA-ARCH-001 (H)**: System shall support data archival

**Approach**:
- Automated archival job (monthly)
- Archive to separate tablespace
- Compressed storage
- Online access to archived data
- Restore capability

### 6.4 Data Quality

#### 6.4.1 Data Validation

**SRS-DATA-QUAL-001 (M)**: System shall enforce data quality rules

**Validation Types**:
- Format validation
- Range validation
- Referential integrity
- Business rule validation
- Cross-field validation

#### 6.4.2 Data Cleansing

**SRS-DATA-QUAL-002 (H)**: System shall provide data cleansing capabilities

**Features**:
- Duplicate detection
- Standardization
- Validation reporting
- Correction workflows

---

## 7. SECURITY REQUIREMENTS

### 7.1 Authentication

#### 7.1.1 Password Policy

**SRS-SEC-PWD-001 (M)**: System shall enforce strong password policy

**Requirements**:
- Minimum 12 characters
- Uppercase, lowercase, number, special character required
- Password history (last 12)
- Maximum age: 90 days
- Lockout after 5 failed attempts

#### 7.1.2 Multi-Factor Authentication

**SRS-SEC-MFA-001 (M)**: System shall support MFA

**Methods**:
- SMS OTP
- Email OTP
- Authenticator app (TOTP)
- Hardware tokens

**MFA Triggers**:
- External user login
- Administrative functions
- High-value transactions
- New device detection

### 7.2 Authorization

#### 7.2.1 Role-Based Access Control

**SRS-SEC-RBAC-001 (M)**: System shall implement RBAC

**Components**:
- Users
- Roles
- Permissions
- Resources
- Access control lists

#### 7.2.2 Data-Level Security

**SRS-SEC-DATA-001 (M)**: System shall enforce data-level security

**Features**:
- Row-level security
- Column-level security
- Data masking
- Encryption at rest

### 7.3 Data Protection

#### 7.3.1 Encryption

**SRS-SEC-ENC-001 (M)**: System shall encrypt sensitive data

**Encryption Standards**:
- At Rest: AES-256
- In Transit: TLS 1.3
- Key Management: Oracle TDE / AWS KMS

#### 7.3.2 Data Masking

**SRS-SEC-MASK-001 (H)**: System shall support data masking

**Masking Rules**:
- Bank account numbers: Show last 4 digits only
- IC/Passport: Mask middle digits
- Phone numbers: Mask middle digits
- Email: Mask local part

### 7.4 Audit and Compliance

#### 7.4.1 Security Logging

**SRS-SEC-LOG-001 (M)**: System shall log security events

**Logged Events**:
- Login attempts (success/failure)
- Privilege escalation
- Data access violations
- Configuration changes
- Security exceptions

#### 7.4.2 Vulnerability Management

**SRS-SEC-VULN-001 (M)**: System shall undergo security testing

**Requirements**:
- Vulnerability assessment
- Penetration testing
- Code review
- Security audit

---

## 8. PERFORMANCE REQUIREMENTS

### 8.1 Response Time

#### 8.1.1 Page Load Times

**SRS-PERF-RESP-001 (M)**: System shall meet response time targets

| Operation | Target Response Time | Maximum Response Time |
|-----------|---------------------|----------------------|
| Page Load | < 3 seconds | 5 seconds |
| Search | < 5 seconds | 10 seconds |
| Report Generation | < 30 seconds | 60 seconds |
| Dashboard Load | < 5 seconds | 10 seconds |
| API Response | < 2 seconds | 5 seconds |
| File Upload | < 10 seconds | 30 seconds |

### 8.2 Throughput

#### 8.2.1 Transaction Volumes

**SRS-PERF-THRU-001 (M)**: System shall support required throughput

| Metric | Target |
|--------|--------|
| Concurrent Users | 250+ |
| Claims per Day | 1,000+ |
| Transactions per Hour | 10,000+ |
| Document Uploads per Hour | 500+ |
| Reports per Hour | 100+ |

### 8.3 Scalability

#### 8.3.1 Horizontal Scaling

**SRS-PERF-SCALE-001 (H)**: System shall support horizontal scaling

**Requirements**:
- Load balancing
- Stateless application design
- Shared session storage
- Database read replicas
- Caching layer

### 8.4 Availability

#### 8.4.1 System Uptime

**SRS-PERF-AVAIL-001 (M)**: System shall maintain high availability

**Target**: 99.9% uptime

**Calculation**:
- Maximum downtime: 43.8 minutes/month
- Excluding planned maintenance

#### 8.4.2 Disaster Recovery

**SRS-PERF-DR-001 (M)**: System shall have DR capabilities

**Requirements**:
- RTO: 4 hours
- RPO: 1 hour
- Hot standby
- Automated failover
- Quarterly DR drills

---

## 9. INTERFACE REQUIREMENTS

### 9.1 User Interface

#### 9.1.1 Web Interface

**SRS-UI-WEB-001 (M)**: System shall provide responsive web interface

**Requirements**:
- Responsive design (mobile, tablet, desktop)
- Cross-browser compatibility (Chrome, Firefox, Edge, Safari)
- Accessibility compliance (WCAG 2.1 AA)
- Bilingual support (BM, English)

#### 9.1.2 Mobile Interface

**SRS-UI-MOB-001 (H)**: System shall support mobile access

**Requirements**:
- Responsive layout
- Touch-friendly controls
- Optimized forms
- Camera integration
- Push notifications

### 9.2 API Interface

#### 9.2.1 REST API

**SRS-API-REST-001 (M)**: System shall provide REST APIs

**Standards**:
- OpenAPI 3.0 specification
- JSON format
- OAuth 2.0 authentication
- Rate limiting
- API versioning

#### 9.2.2 API Documentation

**SRS-API-DOC-001 (M)**: System shall provide API documentation

**Requirements**:
- Interactive API documentation (Swagger/OpenAPI)
- Code samples
- Authentication guide
- Error code reference
- Change log

### 9.3 File Interface

#### 9.3.1 File Upload

**SRS-FILE-UP-001 (M)**: System shall support file uploads

**Requirements**:
- Multiple file upload
- Drag and drop support
- Progress indicator
- Virus scanning
- File type validation
- Size limit (50MB per file)

#### 9.3.2 File Download

**SRS-FILE-DOWN-001 (M)**: System shall support file downloads

**Requirements**:
- Bulk download
- Compressed archives
- Download tracking
- Resume capability

---

## 10. NON-FUNCTIONAL REQUIREMENTS

### 10.1 Usability

#### 10.1.1 User Experience

**SRS-NFR-UX-001 (M)**: System shall be user-friendly

**Requirements**:
- Intuitive navigation
- Consistent design patterns
- Context-sensitive help
- Error prevention
- Error recovery

#### 10.1.2 Training Requirements

**SRS-NFR-TRAIN-001 (M)**: System shall be easy to learn

**Requirements**:
- New users productive within 1 day
- Comprehensive documentation
- Video tutorials
- Interactive help
- FAQ section

### 10.2 Reliability

#### 10.2.1 Error Handling

**SRS-NFR-ERR-001 (M)**: System shall handle errors gracefully

**Requirements**:
- Clear error messages
- Error logging
- Recovery options
- User notification
- Support escalation

#### 10.2.2 Data Integrity

**SRS-NFR-DATA-001 (M)**: System shall maintain data integrity

**Requirements**:
- Transaction integrity
- Referential integrity
- Data validation
- Backup and recovery
- Audit trails

### 10.3 Maintainability

#### 10.3.1 Code Quality

**SRS-NFR-MAINT-001 (M)**: System shall follow coding standards

**Requirements**:
- Documented code
- Naming conventions
- Modular design
- Unit testing
- Code reviews

#### 10.3.2 Documentation

**SRS-NFR-DOC-001 (M)**: System shall be well documented

**Documentation Types**:
- Technical documentation
- User manuals
- API documentation
- Deployment guides
- Runbooks

### 10.4 Portability

#### 10.4.1 Platform Independence

**SRS-NFR-PORT-001 (H)**: System shall be platform independent

**Requirements**:
- Containerized deployment
- Cloud-native architecture
- Database abstraction
- Configuration externalization

### 10.5 Internationalization

#### 10.5.1 Multi-Language Support

**SRS-NFR-I18N-001 (M)**: System shall support multiple languages

**Requirements**:
- Complete interface translation
- Right-to-left support (future)
- Locale-specific formatting
- Date/time localization
- Number/currency formatting

---

## 11. SYSTEM CONSTRAINTS

### 11.1 Technical Constraints

| Constraint | Description | Impact |
|------------|-------------|--------|
| Oracle Database | Must use Oracle 19c | Database design, licensing |
| Azure AD | Must use Azure AD for SSO | Authentication architecture |
| USPFS Integration | Must integrate with Oracle EBS | Integration complexity |
| Bilingual | Must support BM and English | Development effort |
| Responsive | Must work on mobile devices | UI design complexity |

### 11.2 Business Constraints

| Constraint | Description | Impact |
|------------|-------------|--------|
| 67 Month Timeline | Fixed project duration | Phased delivery |
| Budget | RM 3.5M indicative | Scope management |
| Compliance | Must meet regulatory requirements | Additional testing |
| Data Residency | Data must stay in Malaysia | Infrastructure location |

### 11.3 Regulatory Constraints

**SRS-CONST-REG-001 (M)**: System shall comply with Malaysian regulations

- Communications and Multimedia Act 1998
- Personal Data Protection Act 2010
- Electronic Commerce Act 2006
- Financial procedures and guidelines

---

## 12. ASSUMPTIONS AND DEPENDENCIES

### 12.1 Assumptions

| ID | Assumption | Risk if Invalid |
|----|------------|-----------------|
| ASS-001 | USPFS APIs are available and stable | Integration delays |
| ASS-002 | Network connectivity is reliable | System availability |
| ASS-003 | Users have basic computer literacy | Training requirements |
| ASS-004 | DUSPs will adopt the system | Change management |
| ASS-005 | Sufficient infrastructure exists | Performance issues |

### 12.2 Dependencies

| ID | Dependency | Owner | Impact |
|----|------------|-------|--------|
| DEP-001 | USPFS integration availability | MCMC IT | Critical |
| DEP-002 | Azure AD configuration | MCMC IT | Critical |
| DEP-003 | Network infrastructure | MCMC IT | High |
| DEP-004 | User training completion | MCMC | High |
| DEP-005 | DUSP onboarding | DUSPs | Medium |

### 12.3 External Dependencies

**SRS-DEP-EXT-001 (H)**: System depends on external services

| Service | Provider | Criticality |
|---------|----------|-------------|
| Azure AD | Microsoft | Critical |
| Digital Signature | MSC TrustSign/DocuSign | Critical |
| OCR Service | AWS/Google | High |
| SMS Gateway | Local Telco | Medium |
| Email Service | Internal/MCMC | High |

---

## 13. GLOSSARY

| Term | Definition |
|------|------------|
| **API** | Application Programming Interface |
| **BOQ** | Bill of Quantity |
| **DUSP** | Designated Universal Service Provider |
| **EBS** | E-Business Suite (Oracle) |
| **EOT** | Extension of Time |
| **MFA** | Multi-Factor Authentication |
| **NOA** | Notification of Approval |
| **OCR** | Optical Character Recognition |
| **RAC** | Real Application Clusters (Oracle) |
| **RBAC** | Role-Based Access Control |
| **REST** | Representational State Transfer |
| **RPA** | Robotic Process Automation |
| **RPO** | Recovery Point Objective |
| **RTO** | Recovery Time Objective |
| **SAML** | Security Assertion Markup Language |
| **SLA** | Service Level Agreement |
| **SRS** | System Requirements Specification |
| **SSO** | Single Sign-On |
| **TDE** | Transparent Data Encryption |
| **TLS** | Transport Layer Security |
| **UAT** | User Acceptance Testing |
| **UCMS** | USP Claims Management System |
| **URS** | User Requirements Specification |
| **USP** | Universal Service Provision |
| **USPFS** | USP Financial System |
| **VO** | Variation Order |
| **WCAG** | Web Content Accessibility Guidelines |

---

## 14. APPENDICES

### Appendix A: Requirements Traceability Matrix

| Req ID | Description | URS Ref | BRS Ref | Priority | Status |
|--------|-------------|---------|---------|----------|--------|
| SRS-CORE-AUTH-001 | Azure AD SSO | URS-11.1 | BRS-13.1 | M | Draft |
| SRS-CORE-AUTH-002 | RBAC | URS-11.2 | BRS-10.5 | M | Draft |
| SRS-MD-PROJ-001 | Project ID | URS-6.1.1 | BRS-6.2.1 | M | Draft |
| SRS-CM-SUBMIT-001 | Claim Types | URS-6.4.1 | BRS-7.2 | M | Draft |
| ... | ... | ... | ... | ... | ... |

### Appendix B: Data Dictionary

| Table | Column | Data Type | Constraints | Description |
|-------|--------|-----------|-------------|-------------|
| projects | project_id | VARCHAR2(15) | PK, NOT NULL | Unique project identifier |
| projects | project_name | VARCHAR2(255) | NOT NULL | Project name |
| claims | claim_id | VARCHAR2(20) | PK, NOT NULL | Unique claim identifier |
| claims | claim_amount | NUMBER(15,2) | NOT NULL | Claim amount |
| ... | ... | ... | ... | ... |

### Appendix C: Interface Specifications

#### C.1 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | /api/v1/claims | Create claim | Yes |
| GET | /api/v1/claims/{id} | Get claim | Yes |
| PUT | /api/v1/claims/{id} | Update claim | Yes |
| DELETE | /api/v1/claims/{id} | Delete claim | Yes |
| GET | /api/v1/projects | List projects | Yes |
| ... | ... | ... | ... |

### Appendix D: Security Matrix

| Resource | Create | Read | Update | Delete | Admin |
|----------|--------|------|--------|--------|-------|
| Projects | USP Admin | All | USP Admin | USP Admin | Yes |
| Claims | DUSP | Own | Own | - | All |
| Payments | System | Finance | - | - | All |
| Users | Admin | Own/Admin | Own | Admin | All |

### Appendix E: Performance Test Scenarios

| Scenario | Users | Duration | Target |
|----------|-------|----------|--------|
| Login | 250 | 5 min | < 3 sec |
| Claim Submission | 100 | 10 min | < 5 sec |
| Report Generation | 20 | 15 min | < 30 sec |
| Dashboard Load | 250 | 5 min | < 5 sec |
| File Upload | 50 | 10 min | < 10 sec |

---

## DOCUMENT CERTIFICATION

This System Requirements Specification has been reviewed and approved by the following stakeholders:

**Prepared by:**

Name: _________________________

Title: System Analyst

Signature: _________________________

Date: _________________________

**Reviewed by:**

Name: _________________________

Title: Solution Architect

Signature: _________________________

Date: _________________________

**Approved by:**

Name: _________________________

Title: Technical Lead

Signature: _________________________

Date: _________________________

---

**END OF DOCUMENT**

---

*Document Control: This document is controlled and maintained by the Technical Team. Any changes must be approved and documented in the version history.*
