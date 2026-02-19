# DOC26-ICD-TSH2607.md
# Interface Control Document (ICD)
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC26-ICD-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Classification | Confidential |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Interface Control Document (ICD) defines the technical specifications, protocols, data formats, and communication standards for all interfaces within the Universal Service Provision (USP) Claims Management System (UCMS) and between UCMS and external systems.

### 1.2 Scope
This document covers:
- Internal system interfaces
- External system integrations
- API specifications
- Data exchange protocols
- Security requirements for interfaces

### 1.3 References
- TSH-2607 Tender Requirements
- MCMC Technical Standards
- Malaysian Government ICT Security Standards
- Industry Best Practices (REST, SOAP, JSON, XML)

---

## 2.0 INTERFACE ARCHITECTURE

### 2.1 Interface Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         EXTERNAL SYSTEMS                            │
├──────────────┬──────────────┬──────────────┬────────────────────────┤
│   MyIDENTITY │   SSM API    │  Bank APIs   │   Email/SMS Gateway    │
│   (JPN)      │   (Company)  │  (Payments)  │   (Notifications)      │
└──────┬───────┴──────┬───────┴──────┬───────┴───────────┬────────────┘
       │              │              │                   │
       └──────────────┴──────────────┴───────────────────┘
                              │
                    ┌─────────┴─────────┐
                    │   API GATEWAY     │
                    │  (WAF/Rate Limit) │
                    └─────────┬─────────┘
                              │
       ┌──────────────────────┼──────────────────────┐
       │                      │                      │
┌──────▼──────┐    ┌──────────▼──────────┐  ┌───────▼───────┐
│   UCMS      │    │   UCMS Reporting    │  │   Document    │
│   CORE      │◄──►│   & Analytics       │  │   Management  │
│   SYSTEM    │    │   Engine            │  │   System      │
└──────┬──────┘    └─────────────────────┘  └───────────────┘
       │
       ├───────────────────────────────────────────┐
       │                                           │
┌──────▼──────┐    ┌──────────────┐    ┌──────────▼──────────┐
│   Database  │    │   File       │    │   Message Queue     │
│   Layer     │    │   Storage    │    │   (Async Processing)│
└─────────────┘    └──────────────┘    └─────────────────────┘
```

### 2.2 Interface Categories

| Category | Description | Count |
|----------|-------------|-------|
| Internal | UCMS internal component communication | 8 |
| External | Third-party system integrations | 6 |
| User | End-user interface points | 4 |
| Admin | Administrative interfaces | 3 |

---

## 3.0 EXTERNAL INTERFACES

### 3.1 MyIDENTITY Integration (JPN)

**Interface ID:** EXT-001
**Description:** Identity verification for USP applicants

| Attribute | Specification |
|-----------|---------------|
| Protocol | REST API |
| Authentication | OAuth 2.0 + Client Certificate |
| Data Format | JSON |
| Endpoint Type | HTTPS |
| Timeout | 30 seconds |
| Retry Policy | 3 attempts with exponential backoff |

**Operations:**

| Operation | Method | Endpoint | Purpose |
|-----------|--------|----------|---------|
| Verify IC | POST | /api/v1/identity/verify | Validate Malaysian IC |
| Get Demographics | GET | /api/v1/identity/demographics | Retrieve citizen data |
| Check Status | GET | /api/v1/identity/status | Check verification status |

**Request/Response Format:**
```json
{
  "requestId": "UUID",
  "icNumber": "900101-01-1234",
  "timestamp": "2025-01-15T10:30:00Z",
  "signature": "HMAC-SHA256"
}
```

### 3.2 SSM Company Integration

**Interface ID:** EXT-002
**Description:** Company registration verification for corporate applicants

| Attribute | Specification |
|-----------|---------------|
| Protocol | SOAP/Web Services |
| Authentication | WS-Security + API Key |
| Data Format | XML |
| Endpoint Type | HTTPS |

**Operations:**

| Operation | Purpose |
|-----------|---------|
| VerifyCompany | Validate company registration |
| GetCompanyDetails | Retrieve company information |
| CheckCompliance | Verify good standing status |

### 3.3 Payment Gateway Integration

**Interface ID:** EXT-003
**Description:** Process USP grant disbursements and fee payments

| Attribute | Specification |
|-----------|---------------|
| Protocol | REST API |
| Authentication | OAuth 2.0 + HMAC |
| Data Format | JSON |
| Supported Banks | Maybank, CIMB, Public Bank, RHB |

**Operations:**

| Operation | Method | Purpose |
|-----------|--------|---------|
| InitiatePayment | POST | Start payment transaction |
| QueryStatus | GET | Check payment status |
| VerifyReceipt | POST | Confirm payment completion |
| RefundPayment | POST | Process refund if needed |

**Security Requirements:**
- End-to-end encryption
- PCI DSS compliance
- Transaction signing
- IP whitelisting

### 3.4 Notification Gateway

**Interface ID:** EXT-004
**Description:** Email and SMS notifications to stakeholders

| Attribute | Specification |
|-----------|---------------|
| Email Protocol | SMTP/SMTPS |
| SMS Protocol | REST API |
| Provider | Government-approved vendors |

**Operations:**

| Operation | Channel | Purpose |
|-----------|---------|---------|
| SendEmail | Email | Formal communications |
| SendSMS | SMS | Urgent alerts |
| SendBulk | Both | Mass notifications |
| ScheduleNotification | Both | Delayed delivery |

### 3.5 Document Management System (DMS)

**Interface ID:** EXT-005
**Description:** Storage and retrieval of claim documents

| Attribute | Specification |
|-----------|---------------|
| Protocol | REST API + SFTP |
| Storage | Object Storage (S3-compatible) |
| Max File Size | 50MB per file |
| Supported Formats | PDF, DOC, DOCX, XLS, XLSX, JPG, PNG |

### 3.6 Reporting/Business Intelligence

**Interface ID:** EXT-006
**Description:** Data export for analytics and reporting

| Attribute | Specification |
|-----------|---------------|
| Protocol | JDBC/ODBC, REST |
| Formats | CSV, Excel, JSON, XML |
| Authentication | Service Account |

---

## 4.0 INTERNAL INTERFACES

### 4.1 UCMS Core API

**Interface ID:** INT-001
**Base URL:** `/api/v1/ucms`

| Module | Endpoint Prefix | Description |
|--------|-----------------|-------------|
| Claims | /claims | Claim management operations |
| Applicants | /applicants | Applicant profile management |
| Payments | /payments | Payment processing |
| Workflow | /workflow | Workflow engine |
| Reports | /reports | Report generation |
| Admin | /admin | System administration |

### 4.2 Authentication Service

**Interface ID:** INT-002

| Endpoint | Method | Purpose |
|----------|--------|---------|
| /auth/login | POST | User authentication |
| /auth/logout | POST | Session termination |
| /auth/refresh | POST | Token refresh |
| /auth/verify | GET | Token validation |
| /auth/mfa | POST | Multi-factor authentication |

### 4.3 Workflow Engine Interface

**Interface ID:** INT-003

| Event | Direction | Description |
|-------|-----------|-------------|
| ClaimSubmitted | Inbound | New claim received |
| StatusChanged | Bidirectional | Status transition |
| ApprovalRequired | Outbound | Escalation trigger |
| NotificationTrigger | Outbound | Alert generation |

### 4.4 Database Interface

**Interface ID:** INT-004

| Layer | Technology | Purpose |
|-------|------------|---------|
| ORM | Entity Framework / Hibernate | Object-relational mapping |
| Connection Pool | HikariCP / ADO.NET | Connection management |
| Cache | Redis | Session and data caching |

### 4.5 Message Queue Interface

**Interface ID:** INT-005

| Queue | Purpose | Priority |
|-------|---------|----------|
| claim.processing | Asynchronous claim handling | High |
| notification.send | Email/SMS delivery | Medium |
| report.generate | Report generation | Low |
| audit.log | Audit trail logging | High |

---

## 5.0 DATA EXCHANGE FORMATS

### 5.1 Standard JSON Schema

```json
{
  "metadata": {
    "version": "1.0",
    "timestamp": "ISO8601",
    "requestId": "UUID",
    "source": "system-id"
  },
  "payload": {
    "data": {}
  },
  "security": {
    "signature": "HMAC-SHA256",
    "encryption": "AES-256-GCM"
  }
}
```

### 5.2 Error Response Format

```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human-readable description",
    "details": {},
    "timestamp": "ISO8601",
    "requestId": "UUID"
  }
}
```

### 5.3 Common Data Types

| Type | Format | Example |
|------|--------|---------|
| Date | YYYY-MM-DD | 2025-01-15 |
| DateTime | ISO 8601 | 2025-01-15T10:30:00+08:00 |
| Currency | Decimal (2 places) | 15000.00 |
| IC Number | XXXXXX-XX-XXXX | 900101-01-1234 |
| Company Reg | XXXXXXX-X | 1234567-A |

---

## 6.0 SECURITY SPECIFICATIONS

### 6.1 Authentication Requirements

| Interface Type | Authentication Method |
|----------------|----------------------|
| External APIs | OAuth 2.0 + mTLS |
| Internal APIs | JWT + Service Token |
| User Interfaces | Session + MFA |
| Admin Interfaces | Certificate + MFA |

### 6.2 Authorization Model

- Role-Based Access Control (RBAC)
- Attribute-Based Access Control (ABAC) for sensitive operations
- API Key management with rotation policy

### 6.3 Data Protection

| Protection | Method |
|------------|--------|
| In Transit | TLS 1.3 minimum |
| At Rest | AES-256 encryption |
| Sensitive Fields | Field-level encryption |
| API Payload | Request/response signing |

### 6.4 Rate Limiting

| Interface Tier | Requests/Minute | Burst Allowance |
|----------------|-----------------|-----------------|
| Public | 60 | 10 |
| Authenticated | 300 | 50 |
| Premium | 1000 | 100 |
| Internal | Unlimited | N/A |

---

## 7.0 INTERFACE MONITORING

### 7.1 Health Check Endpoints

| Endpoint | Purpose | Expected Response |
|----------|---------|-------------------|
| /health | System health | HTTP 200 + status JSON |
| /health/db | Database connectivity | Connection status |
| /health/ext | External services | Dependency status |

### 7.2 Monitoring Metrics

- Response time (p50, p95, p99)
- Error rate
- Throughput (requests/second)
- Availability percentage

### 7.3 Alerting Thresholds

| Metric | Warning | Critical |
|--------|---------|----------|
| Response Time | > 2s | > 5s |
| Error Rate | > 1% | > 5% |
| Availability | < 99.5% | < 99% |

---

## 8.0 ERROR HANDLING

### 8.1 HTTP Status Codes

| Code | Usage |
|------|-------|
| 200 | Success |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 429 | Rate Limited |
| 500 | Server Error |
| 503 | Service Unavailable |

### 8.2 Error Codes

| Code | Description | Recovery Action |
|------|-------------|-----------------|
| AUTH001 | Invalid credentials | Prompt re-authentication |
| AUTH002 | Token expired | Refresh token |
| VAL001 | Validation failed | Correct input data |
| SYS001 | System error | Retry with backoff |
| INT001 | Integration error | Check dependency status |

---

## 9.0 VERSION CONTROL

### 9.1 API Versioning Strategy

- URL-based versioning: `/api/v1/...`, `/api/v2/...`
- Deprecation notice: 6 months advance notice
- Support window: Current + previous version

### 9.2 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | Jan 2025 | Initial release |

---

## 10.0 APPENDICES

### Appendix A: Interface Inventory

| ID | Name | Type | Status |
|----|------|------|--------|
| EXT-001 | MyIDENTITY | External | Planned |
| EXT-002 | SSM | External | Planned |
| EXT-003 | Payment Gateway | External | Planned |
| EXT-004 | Notification | External | Planned |
| EXT-005 | DMS | External | Planned |
| EXT-006 | BI/Reporting | External | Planned |
| INT-001 | Core API | Internal | Planned |
| INT-002 | Auth Service | Internal | Planned |
| INT-003 | Workflow | Internal | Planned |
| INT-004 | Database | Internal | Planned |
| INT-005 | Message Queue | Internal | Planned |

### Appendix B: Network Diagram
[See Section 2.1]

### Appendix C: Data Flow Diagrams
[Available in technical specification documents]

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Technical Lead | | | |
| Security Officer | | | |
| Project Manager | | | |
| MCMC Representative | | | |

---

*Document Control: This document is maintained by the UCMS Project Team. All changes require approval from the Technical Lead and MCMC Representative.*
