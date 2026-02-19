# ANNEX-T06-SRS-SDD-TEMPLATES-TSH2607.md

# ANNEX T6: SRS/SDD TEMPLATES
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T6  
**Version:** 1.0  
**Date:** February 2026  

---

## TABLE OF CONTENTS

1. [Document Templates Overview](#1-document-templates-overview)
2. [SRS Template](#2-srs-template)
3. [SDD Template](#3-sdd-template)
4. [Use Case Template](#4-use-case-template)
5. [Interface Specification Template](#5-interface-specification-template)
6. [Data Dictionary Template](#6-data-dictionary-template)

---

## 1. DOCUMENT TEMPLATES OVERVIEW

### 1.1 Documentation Hierarchy

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         UCMS DOCUMENTATION HIERARCHY                                     │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  LEVEL 1: BUSINESS DOCUMENTATION                                                         │
│  ├── Business Requirements Specification (BRS)                                           │
│  ├── Stakeholder Analysis Document                                                       │
│  └── Business Process Documentation                                                      │
│                                                                                          │
│  LEVEL 2: SYSTEM REQUIREMENTS                                                            │
│  ├── User Requirements Specification (URS) ← PROVIDED                                    │
│  ├── System Requirements Specification (SRS) ← PROVIDED                                  │
│  └── Interface Requirements Specification (IRS)                                          │
│                                                                                          │
│  LEVEL 3: SYSTEM DESIGN                                                                  │
│  ├── System Design Specification (SDS) ← PROVIDED                                        │
│  ├── System Architecture Document                                                        │
│  └── Interface Control Document (ICD)                                                    │
│                                                                                          │
│  LEVEL 4: IMPLEMENTATION DOCUMENTATION                                                   │
│  ├── Database Design Document                                                            │
│  ├── API Specification                                                                   │
│  └── Security Design Document                                                            │
│                                                                                          │
│  LEVEL 5: OPERATIONS DOCUMENTATION                                                       │
│  ├── User Manual                                                                         │
│  ├── System Administrator Guide                                                          │
│  └── Operations Runbook                                                                  │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Template Standards

All templates comply with:
- **IEEE 830-1998** - Software Requirements Specifications
- **IEEE 1016-2009** - Software Design Descriptions
- **ISO/IEC/IEEE 29148:2018** - Systems and software engineering
- **KRISA Documentation Standards** (where applicable)

---

## 2. SRS TEMPLATE

### 2.1 SRS Document Structure

```markdown
# SYSTEM REQUIREMENTS SPECIFICATION (SRS)

## Document Information
| Field | Value |
|-------|-------|
| Document ID | SRS-UCMS-[MODULE]-[VERSION] |
| Project | Universal Service Provision Claims Management System (UCMS) |
| Client | Malaysian Communications and Multimedia Commission (MCMC) |
| Tender Reference | MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02) |
| Version | X.Y |
| Date | DD/MM/YYYY |
| Status | Draft/Review/Approved/Baselined |

## Revision History
| Version | Date | Author | Changes | Approved By |
|---------|------|--------|---------|-------------|
| 0.1 | DD/MM/YYYY | [Name] | Initial draft | - |
| 1.0 | DD/MM/YYYY | [Name] | Approved version | [Name] |

## Table of Contents
1. Introduction
2. Overall Description
3. System Features
4. External Interface Requirements
5. Non-Functional Requirements
6. Data Requirements
7. Appendices

---

## 1. INTRODUCTION

### 1.1 Purpose
[Describe the purpose of this SRS document]

### 1.2 Scope
[Define the scope of the system being described]

### 1.3 Definitions, Acronyms, and Abbreviations
| Term | Definition |
|------|------------|
| UCMS | Universal Claims Management System |
| USP | Universal Service Provision |
| DUSP | Designated Universal Service Provider |
| [Add more] | |

### 1.4 References
[List all reference documents]

### 1.5 Document Overview
[Describe the organization of this document]

---

## 2. OVERALL DESCRIPTION

### 2.1 Product Perspective
[Describe how the system fits into the larger context]

#### 2.1.1 System Context Diagram
[Insert context diagram]

#### 2.1.2 User Classes and Characteristics
| User Class | Description | Privileges | Count |
|------------|-------------|------------|-------|
| MCMC Admin | System administrators | Full access | 5 |
| MCMC Staff | Internal users | Module-specific | 55 |
| DUSP Users | External providers | Limited access | 120 |

### 2.2 Product Functions
[Summary of major functions]

### 2.3 User Characteristics
[Detailed description of end users]

### 2.4 Constraints
[List all design and implementation constraints]

### 2.5 Assumptions and Dependencies
[List assumptions and dependencies]

---

## 3. SYSTEM FEATURES

### 3.1 [Feature Name]

#### 3.1.1 Description and Priority
| Attribute | Value |
|-----------|-------|
| Feature ID | FEAT-XXX |
| Description | [Brief description] |
| Priority | High/Medium/Low |
| Stakeholder | [Primary stakeholder] |

#### 3.1.2 Stimulus/Response Sequences
| Stimulus | Response |
|----------|----------|
| [User action] | [System response] |

#### 3.1.3 Functional Requirements
**REQ-F-XXX-001:** [Requirement statement]
- Acceptance Criteria: [Criteria]
- Dependencies: [List]
- Priority: Must/Should/Could/Won't

**REQ-F-XXX-002:** [Requirement statement]
...

### 3.2 [Next Feature]
...

---

## 4. EXTERNAL INTERFACE REQUIREMENTS

### 4.1 User Interfaces
[Describe all user interfaces]

### 4.2 Hardware Interfaces
[Describe hardware interfaces if any]

### 4.3 Software Interfaces
| Interface | System | Protocol | Purpose |
|-----------|--------|----------|---------|
| USPFS Integration | Oracle EBS | REST/SOAP | Financial data |
| Azure AD | Microsoft | OIDC | Authentication |

### 4.4 Communications Interfaces
[Describe network protocols used]

---

## 5. NON-FUNCTIONAL REQUIREMENTS

### 5.1 Performance Requirements
| ID | Requirement | Metric | Target |
|----|-------------|--------|--------|
| REQ-NF-PERF-001 | Page load time | Seconds | < 2s |
| REQ-NF-PERF-002 | Concurrent users | Users | 180 |

### 5.2 Security Requirements
| ID | Requirement | Implementation |
|----|-------------|----------------|
| REQ-NF-SEC-001 | Data encryption | AES-256 |
| REQ-NF-SEC-002 | Session timeout | 30 minutes |

### 5.3 Availability Requirements
- System Availability: 99.95% uptime
- Scheduled Maintenance: Off-peak hours
- Recovery Time Objective (RTO): 4 hours
- Recovery Point Objective (RPO): 1 hour

### 5.4 Scalability Requirements
[Scalability targets]

### 5.5 Maintainability Requirements
[Maintainability requirements]

### 5.6 Portability Requirements
[Portability requirements]

---

## 6. DATA REQUIREMENTS

### 6.1 Logical Data Model
[ER diagram or data model]

### 6.2 Data Retention
[Data retention policies]

### 6.3 Data Migration
[Migration requirements]

---

## 7. APPENDICES

### Appendix A: Glossary
### Appendix B: Analysis Models
### Appendix C: Issues List

---

## SIGN-OFF

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Prepared By | | | |
| Reviewed By | | | |
| Approved By (MCMC) | | | |
| Approved By (Vendor PM) | | | |
```

---

## 3. SDD TEMPLATE

### 3.1 SDD Document Structure

```markdown
# SYSTEM DESIGN SPECIFICATION (SDD)

## Document Information
| Field | Value |
|-------|-------|
| Document ID | SDS-UCMS-[MODULE]-[VERSION] |
| Reference SRS | SRS-UCMS-[MODULE]-[VERSION] |
| Version | X.Y |
| Date | DD/MM/YYYY |
| Status | Draft/Review/Approved |

## Revision History
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| | | | |

## Table of Contents
1. Introduction
2. System Overview
3. Design Considerations
4. System Architecture
5. Detailed Design
6. Data Design
7. Interface Design
8. Security Design
9. Appendices

---

## 1. INTRODUCTION

### 1.1 Purpose
[Purpose of this design document]

### 1.2 Scope
[Scope of design covered]

### 1.3 Definitions and Acronyms
| Term | Definition |
|------|------------|
| | |

### 1.4 References
- SRS-UCMS-XXX: [Reference]
- BRS-UCMS-XXX: [Reference]

---

## 2. SYSTEM OVERVIEW

### 2.1 System Context
[Description of system in context]

### 2.2 Design Goals
[Key design goals and objectives]

### 2.3 Constraints
[Design constraints]

---

## 3. DESIGN CONSIDERATIONS

### 3.1 Goals and Guidelines
[Design philosophy and guidelines]

### 3.2 Architectural Strategies
| Strategy | Description | Rationale |
|----------|-------------|-----------|
| Microservices | Service decomposition | Scalability, maintainability |
| API-First | RESTful APIs | Integration flexibility |

### 3.3 Development Methods
[Development methodology]

---

## 4. SYSTEM ARCHITECTURE

### 4.1 Component Diagram
[Component architecture diagram]

### 4.2 Deployment Diagram
[Deployment architecture]

### 4.3 Technology Stack
| Layer | Technology | Version |
|-------|------------|---------|
| Frontend | React.js | 18.x |
| Backend | Spring Boot | 3.x |
| Database | Oracle | 19c |
| Cache | Redis | 7.x |

---

## 5. DETAILED DESIGN

### 5.1 [Component Name]

#### 5.1.1 Component Description
[Purpose and responsibilities]

#### 5.1.2 Class Diagram
```
[Class diagram using PlantUML or similar]
```

#### 5.1.3 Sequence Diagrams
```
[Key sequence diagrams]
```

#### 5.1.4 State Diagrams
[If applicable]

#### 5.1.5 Interface Definitions
```java
/**
 * [Interface description]
 */
public interface [InterfaceName] {
    /**
     * [Method description]
     * @param [param] [description]
     * @return [description]
     * @throws [exception]
     */
    [ReturnType] [methodName]([Parameters]);
}
```

### 5.2 [Next Component]
...

---

## 6. DATA DESIGN

### 6.1 Database Design

#### 6.1.1 ER Diagram
[Entity-Relationship diagram]

#### 6.1.2 Schema Definition
```sql
-- Table: UCMS_CLAIMS
CREATE TABLE UCMS_CLAIMS (
    CLAIM_ID VARCHAR2(50) PRIMARY KEY,
    PROJECT_ID VARCHAR2(50) NOT NULL,
    DUSP_ID VARCHAR2(50) NOT NULL,
    CLAIM_TYPE VARCHAR2(20) NOT NULL,
    CLAIM_AMOUNT NUMBER(15,2) NOT NULL,
    CLAIM_STATUS VARCHAR2(20) DEFAULT 'DRAFT',
    SUBMISSION_DATE TIMESTAMP,
    CREATED_BY VARCHAR2(100),
    CREATED_DATE TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    MODIFIED_BY VARCHAR2(100),
    MODIFIED_DATE TIMESTAMP,
    CONSTRAINT FK_CLAIM_PROJECT FOREIGN KEY (PROJECT_ID) 
        REFERENCES UCMS_PROJECTS(PROJECT_ID),
    CONSTRAINT FK_CLAIM_DUSP FOREIGN KEY (DUSP_ID) 
        REFERENCES UCMS_DUSP(DUSP_ID)
);

-- Indexes
CREATE INDEX IDX_CLAIM_PROJECT ON UCMS_CLAIMS(PROJECT_ID);
CREATE INDEX IDX_CLAIM_STATUS ON UCMS_CLAIMS(CLAIM_STATUS);
CREATE INDEX IDX_CLAIM_DATE ON UCMS_CLAIMS(SUBMISSION_DATE);
```

#### 6.1.3 Data Dictionary
| Table | Column | Data Type | Nullable | Description |
|-------|--------|-----------|----------|-------------|
| UCMS_CLAIMS | CLAIM_ID | VARCHAR2(50) | NO | Unique claim identifier |
| UCMS_CLAIMS | PROJECT_ID | VARCHAR2(50) | NO | Reference to project |

### 6.2 Data Migration Design
[Migration approach]

### 6.3 Data Retention and Archival
[Retention policies]

---

## 7. INTERFACE DESIGN

### 7.1 API Design

#### 7.1.1 REST API Specification

**Endpoint:** `POST /api/v1/claims`

**Description:** Submit a new claim

**Request Headers:**
| Header | Required | Description |
|--------|----------|-------------|
| Authorization | Yes | Bearer token |
| Content-Type | Yes | application/json |

**Request Body:**
```json
{
    "projectId": "USP-2024-001",
    "claimType": "QUARTERLY",
    "claimPeriod": {
        "startDate": "2025-10-01",
        "endDate": "2025-12-31"
    },
    "claimAmount": 500000.00,
    "description": "Q4 2025 claim for broadband expansion",
    "physicalProgress": 75,
    "financialProgress": 50,
    "documents": [
        {
            "documentType": "PROGRESS_REPORT",
            "documentId": "DOC-12345"
        }
    ]
}
```

**Response:**
- 201 Created: Claim submitted successfully
- 400 Bad Request: Validation error
- 401 Unauthorized: Authentication failed
- 403 Forbidden: Insufficient permissions

**Response Body (201):**
```json
{
    "claimId": "CLM-2026-0001234",
    "status": "SUBMITTED",
    "submissionDate": "2026-01-15T10:30:00Z",
    "estimatedProcessingDays": 5,
    "nextSteps": "Pending Level 1 approval"
}
```

### 7.2 External Interface Design
[Integration interface details]

---

## 8. SECURITY DESIGN

### 8.1 Authentication Design
[Authentication mechanism]

### 8.2 Authorization Design
[RBAC design]

### 8.3 Data Protection
[Encryption and data protection]

### 8.4 Audit Trail Design
[Audit logging mechanism]

---

## 9. APPENDICES

### Appendix A: Design Patterns Used
### Appendix B: Third-Party Libraries
### Appendix C: Open Issues

---

## SIGN-OFF

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Solution Architect | | | |
| Technical Lead | | | |
| Database Architect | | | |
```

---

## 4. USE CASE TEMPLATE

### 4.1 Use Case Specification Template

```markdown
## USE CASE: [UC-XXX] [Use Case Name]

### 4.1.1 Basic Information
| Attribute | Value |
|-----------|-------|
| Use Case ID | UC-XXX |
| Use Case Name | [Name] |
| Priority | High/Medium/Low |
| Actor(s) | [Primary actor(s)] |
| Stakeholder | [Stakeholders] |
| Trigger | [Event that starts the use case] |
| Preconditions | [Conditions that must be true] |
| Postconditions | [Conditions that will be true] |

### 4.1.2 Basic Flow (Main Success Scenario)
| Step | Actor Action | System Response |
|------|--------------|-----------------|
| 1 | [Action] | [Response] |
| 2 | [Action] | [Response] |
| 3 | [Action] | [Response] |
| ... | | |

### 4.1.3 Alternative Flows

#### Alternative Flow A: [Name]
| Step | Condition | Action |
|------|-----------|--------|
| A1 | [When condition] | [Action] |
| A2 | | |

#### Alternative Flow B: [Name]
...

### 4.1.4 Exception Flows

#### Exception Flow E1: [Error Condition]
| Step | Condition | System Response |
|------|-----------|-----------------|
| E1.1 | [Error condition] | [Error handling] |
| E1.2 | | |

### 4.1.5 Business Rules
| ID | Rule Description |
|----|------------------|
| BR-XXX-001 | [Rule] |

### 4.1.6 Data Requirements
| Data Element | Description | Source |
|--------------|-------------|--------|
| | | |

### 4.1.7 Non-Functional Requirements
| ID | Requirement |
|----|-------------|
| | |

### 4.1.8 User Interface
[UI mockup reference]

### 4.1.9 Related Use Cases
| Relationship | Use Case |
|--------------|----------|
| Includes | UC-XXX |
| Extends | UC-XXX |

### 4.1.10 Decision Table (if applicable)
| Condition | Rule 1 | Rule 2 | Rule 3 |
|-----------|--------|--------|--------|
| Condition A | Y | N | Y |
| Condition B | N | Y | Y |
| **Action** | | | |
| Action X | X | | X |
| Action Y | | X | X |
```

### 4.2 Example Use Case: Submit Quarterly Claim

```markdown
## USE CASE: UC-CLM-001 Submit Quarterly Claim

### Basic Information
| Attribute | Value |
|-----------|-------|
| Use Case ID | UC-CLM-001 |
| Use Case Name | Submit Quarterly Claim |
| Priority | High |
| Actor(s) | DUSP User (Primary), MCMC Staff (Secondary) |
| Stakeholder | DUSP, MCMC Finance, USP Team |
| Trigger | DUSP needs to claim reimbursement for quarterly expenses |
| Preconditions | 1. DUSP is logged in<br>2. Project exists and is active<br>3. Performance bond is valid |
| Postconditions | 1. Claim is recorded in system<br>2. Approval workflow is initiated<br>3. DUSP receives confirmation |

### Basic Flow
| Step | Actor Action | System Response |
|------|--------------|-----------------|
| 1 | DUSP navigates to "New Claim" page | System displays claim entry form with project dropdown |
| 2 | DUSP selects project from dropdown | System loads project details and remaining budget |
| 3 | DUSP selects "Quarterly Claim" type | System displays quarterly claim specific fields |
| 4 | DUSP enters claim period (start and end dates) | System validates period doesn't overlap with existing claims |
| 5 | DUSP enters claim amount | System validates amount against remaining budget |
| 6 | DUSP enters claim description and progress details | System validates all required fields |
| 7 | DUSP uploads required documents | System performs OCR and validates documents |
| 8 | DUSP reviews and clicks "Submit" | System validates all data and creates claim record |
| 9 | | System initiates 3-level approval workflow |
| 10 | | System sends confirmation email to DUSP |
| 11 | | System displays success message with claim reference number |

### Alternative Flow A: Save as Draft
| Step | Condition | Action |
|------|-----------|--------|
| A1 | At any point, DUSP clicks "Save as Draft" | System saves current progress |
| A2 | | System assigns draft ID |
| A3 | | System confirms draft saved |
| A4 | Use case ends | |

### Exception Flow E1: Budget Exceeded
| Step | Condition | System Response |
|------|-----------|-----------------|
| E1.1 | Claim amount exceeds remaining budget | System displays error message |
| E1.2 | | System shows available budget |
| E1.3 | | System allows DUSP to adjust amount or cancel |

### Business Rules
| ID | Rule Description |
|----|------------------|
| BR-CLM-001 | Quarterly claim must cover exactly 3 months |
| BR-CLM-002 | Claim period cannot overlap with existing approved claims |
| BR-CLM-003 | Maximum claim amount cannot exceed remaining capped cost |
| BR-CLM-004 | Physical progress percentage must be provided |
```

---

## 5. INTERFACE SPECIFICATION TEMPLATE

### 5.1 API Specification Template

```markdown
## API SPECIFICATION: [API-XXX] [API Name]

### General Information
| Attribute | Value |
|-----------|-------|
| API Name | [Name] |
| Version | v1 |
| Base URL | https://api.ucms.mcmc.gov.my/v1 |
| Protocol | HTTPS |
| Authentication | OAuth 2.0 (Bearer Token) |
| Content-Type | application/json |
| Rate Limit | 1000 requests/hour |

### Endpoints

#### [Method] [Path]

**Description:** [Brief description]

**Authorization:** Required

**Required Scopes:** [scope1, scope2]

**Request Parameters:**

| Parameter | Location | Type | Required | Description |
|-----------|----------|------|----------|-------------|
| param1 | Path | String | Yes | Description |
| param2 | Query | Integer | No | Description |

**Request Body:**
```json
{
    "field1": "string",
    "field2": 123,
    "field3": {
        "nested": "value"
    }
}
```

**Response Codes:**
| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

**Response Body (200):**
```json
{
    "status": "success",
    "data": {
        "id": "string",
        "createdAt": "2026-01-15T10:30:00Z"
    },
    "meta": {
        "requestId": "uuid",
        "timestamp": "2026-01-15T10:30:00Z"
    }
}
```

**Error Response (4xx/5xx):**
```json
{
    "status": "error",
    "error": {
        "code": "ERROR_CODE",
        "message": "Human-readable error message",
        "details": [
            {
                "field": "fieldName",
                "issue": "Validation error description"
            }
        ]
    },
    "meta": {
        "requestId": "uuid",
        "timestamp": "2026-01-15T10:30:00Z"
    }
}
```

**Example Request:**
```bash
curl -X POST https://api.ucms.mcmc.gov.my/v1/claims \
  -H "Authorization: Bearer {token}" \
  -H "Content-Type: application/json" \
  -d '{
    "projectId": "USP-2024-001",
    "claimType": "QUARTERLY",
    "claimAmount": 500000
  }'
```

**Example Response:**
```json
{
    "status": "success",
    "data": {
        "claimId": "CLM-2026-0001234",
        "status": "SUBMITTED",
        "submissionDate": "2026-01-15T10:30:00Z"
    }
}
```
```

### 5.2 USPFS Integration Interface

```markdown
## USPFS INTEGRATION INTERFACE

### Connection Details
| Attribute | Value |
|-----------|-------|
| System | Oracle E-Business Suite (EBS) |
| Protocol | REST API / Database Link |
| Authentication | Mutual TLS + API Key |
| Data Format | JSON / XML |
| Frequency | Real-time / Scheduled |

### Interface Methods

#### 1. Get Budget Balance
**Purpose:** Retrieve remaining budget for a project

**Request:**
```json
{
    "projectId": "USP-2024-001",
    "requestTimestamp": "2026-01-15T10:30:00Z"
}
```

**Response:**
```json
{
    "projectId": "USP-2024-001",
    "approvedCappedCost": 25000000.00,
    "totalClaimed": 12500000.00,
    "remainingBalance": 12500000.00,
    "currency": "MYR",
    "lastUpdated": "2026-01-15T00:00:00Z"
}
```

#### 2. Create Voucher
**Purpose:** Create payment voucher in USPFS

**Request:**
```json
{
    "claimId": "CLM-2026-0001234",
    "projectId": "USP-2024-001",
    "duspId": "DUSP-001",
    "amount": 500000.00,
    "description": "Q4 2025 Quarterly Claim",
    "approvals": [
        {
            "level": 1,
            "approver": "user1@mcmc.gov.my",
            "timestamp": "2026-01-15T09:00:00Z",
            "digitalSignature": "signed-data"
        }
    ]
}
```

**Response:**
```json
{
    "voucherId": "VCH-2026-008912",
    "status": "CREATED",
    "createdAt": "2026-01-15T10:30:00Z",
    "estimatedProcessingTime": "2 business days"
}
```

### Error Handling
| Error Code | Description | Action |
|------------|-------------|--------|
| USPFS-001 | Connection timeout | Retry with exponential backoff |
| USPFS-002 | Invalid project ID | Log error and alert admin |
| USPFS-003 | Insufficient budget | Reject claim with notification |
```

---

## 6. DATA DICTIONARY TEMPLATE

### 6.1 Entity Definition Template

```markdown
## ENTITY: [Entity Name]

### General Information
| Attribute | Value |
|-----------|-------|
| Entity Name | [Name] |
| Description | [Description] |
| Table Name | [Database table name] |
| Owner | [System/Module] |
| Volume Estimate | [Expected record count] |

### Attributes

| # | Attribute Name | Data Type | Length | Nullable | Default | Description |
|---|----------------|-----------|--------|----------|---------|-------------|
| 1 | PK_COLUMN | VARCHAR2 | 50 | NO | - | Primary key |
| 2 | FK_COLUMN | VARCHAR2 | 50 | NO | - | Foreign key to [table] |
| 3 | DATA_COLUMN | NUMBER | 15,2 | YES | 0 | [Description] |
| 4 | STATUS | VARCHAR2 | 20 | NO | 'DRAFT' | Status: DRAFT, PENDING, APPROVED, REJECTED |
| 5 | CREATED_DATE | TIMESTAMP | - | NO | CURRENT_TIMESTAMP | Record creation timestamp |

### Constraints

#### Primary Key
- PK_[TABLE_NAME]: (PK_COLUMN)

#### Foreign Keys
- FK_[TABLE]_[REF]: (FK_COLUMN) REFERENCES [REF_TABLE](REF_COLUMN)

#### Unique Constraints
- UK_[TABLE]_[COLUMN]: (COLUMN1, COLUMN2)

#### Check Constraints
- CK_[TABLE]_[COLUMN]: CHECK (STATUS IN ('DRAFT', 'PENDING', 'APPROVED', 'REJECTED'))

### Indexes

| Index Name | Type | Columns | Purpose |
|------------|------|---------|---------|
| IDX_[TABLE]_[COLUMN] | B-Tree | (COLUMN) | Search optimization |
| IDX_[TABLE]_[COMPOSITE] | B-Tree | (COL1, COL2) | Composite search |

### Relationships

| Relationship | Cardinality | Related Entity | Description |
|--------------|-------------|----------------|-------------|
| Belongs To | N:1 | PARENT_ENTITY | [Description] |
| Has Many | 1:N | CHILD_ENTITY | [Description] |

### Business Rules
- Rule 1: [Description]
- Rule 2: [Description]

### Audit Requirements
- Created by user tracking: YES
- Modified by user tracking: YES
- Full audit trail required: YES
```

### 6.2 Example: UCMS_CLAIMS Entity

```markdown
## ENTITY: Claim

### General Information
| Attribute | Value |
|-----------|-------|
| Entity Name | Claim |
| Description | Stores all claim submission records |
| Table Name | UCMS_CLAIMS |
| Owner | Claims Management Module |
| Volume Estimate | 10,000 records/year |

### Attributes

| # | Attribute Name | Data Type | Length | Nullable | Default | Description |
|---|----------------|-----------|--------|----------|---------|-------------|
| 1 | CLAIM_ID | VARCHAR2 | 50 | NO | - | Unique claim identifier (CLM-YYYY-NNNNNN) |
| 2 | PROJECT_ID | VARCHAR2 | 50 | NO | - | Reference to UCMS_PROJECTS |
| 3 | DUSP_ID | VARCHAR2 | 50 | NO | - | Reference to UCMS_DUSP |
| 4 | CLAIM_TYPE | VARCHAR2 | 20 | NO | - | ADVANCE, QUARTERLY, YEARLY |
| 5 | CLAIM_PERIOD_START | DATE | - | YES | - | Start of claim period |
| 6 | CLAIM_PERIOD_END | DATE | - | YES | - | End of claim period |
| 7 | CLAIM_AMOUNT | NUMBER | 15,2 | NO | - | Amount claimed in MYR |
| 8 | CLAIM_DESCRIPTION | VARCHAR2 | 4000 | YES | - | Detailed description |
| 9 | PHYSICAL_PROGRESS | NUMBER | 5,2 | YES | - | Physical completion % |
| 10 | FINANCIAL_PROGRESS | NUMBER | 5,2 | YES | - | Financial completion % |
| 11 | CLAIM_STATUS | VARCHAR2 | 20 | NO | 'DRAFT' | Current status |
| 12 | SUBMISSION_DATE | TIMESTAMP | - | YES | - | When submitted |
| 13 | CREATED_BY | VARCHAR2 | 100 | NO | - | User who created |
| 14 | CREATED_DATE | TIMESTAMP | - | NO | CURRENT_TIMESTAMP | Creation timestamp |
| 15 | MODIFIED_BY | VARCHAR2 | 100 | YES | - | User who last modified |
| 16 | MODIFIED_DATE | TIMESTAMP | - | YES | - | Last modification timestamp |

### Constraints

#### Primary Key
- PK_UCMS_CLAIMS: (CLAIM_ID)

#### Foreign Keys
- FK_CLAIMS_PROJECT: (PROJECT_ID) REFERENCES UCMS_PROJECTS(PROJECT_ID)
- FK_CLAIMS_DUSP: (DUSP_ID) REFERENCES UCMS_DUSP(DUSP_ID)

#### Check Constraints
- CK_CLAIMS_TYPE: CHECK (CLAIM_TYPE IN ('ADVANCE', 'QUARTERLY', 'YEARLY'))
- CK_CLAIMS_STATUS: CHECK (CLAIM_STATUS IN ('DRAFT', 'SUBMITTED', 'PENDING_L1', 'PENDING_L2', 'PENDING_L3', 'APPROVED', 'REJECTED', 'PAID'))
- CK_CLAIMS_AMOUNT: CHECK (CLAIM_AMOUNT > 0)
- CK_CLAIMS_PROGRESS: CHECK (PHYSICAL_PROGRESS BETWEEN 0 AND 100)

### Indexes

| Index Name | Type | Columns | Purpose |
|------------|------|---------|---------|
| PK_UCMS_CLAIMS | B-Tree | (CLAIM_ID) | Primary key access |
| IDX_CLAIMS_PROJECT | B-Tree | (PROJECT_ID) | Project-based queries |
| IDX_CLAIMS_DUSP | B-Tree | (DUSP_ID) | DUSP-based queries |
| IDX_CLAIMS_STATUS | B-Tree | (CLAIM_STATUS) | Status-based filtering |
| IDX_CLAIMS_DATE | B-Tree | (SUBMISSION_DATE) | Date range queries |
| IDX_CLAIMS_STATUS_DATE | B-Tree | (CLAIM_STATUS, SUBMISSION_DATE) | Dashboard queries |

### Relationships

| Relationship | Cardinality | Related Entity | Description |
|--------------|-------------|----------------|-------------|
| Belongs To | N:1 | Project | Each claim belongs to one project |
| Belongs To | N:1 | DUSP | Each claim is submitted by one DUSP |
| Has Many | 1:N | Claim Document | A claim can have multiple documents |
| Has Many | 1:N | Approval History | A claim has approval records |
| Has Many | 1:N | Payment | A claim can have multiple payments |

### Business Rules
1. Claim amount cannot exceed remaining project budget
2. Quarterly claims must cover exactly 3 months
3. Physical progress cannot decrease from previous claim
4. Rejected claims can be resubmitted after corrections
5. Paid claims cannot be modified

### Audit Requirements
- Created by user tracking: YES
- Modified by user tracking: YES
- Full audit trail required: YES (via UCMS_CLAIMS_AUDIT table)
- Retention Period: 7 years
```

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 2026 | Technical Documentation Team | Initial templates |

---

**END OF ANNEX T6**
