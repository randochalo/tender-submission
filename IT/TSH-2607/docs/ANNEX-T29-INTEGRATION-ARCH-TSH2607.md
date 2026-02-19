# ANNEX T29: INTEGRATION ARCHITECTURE

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive integration architecture for the USP Claims Management System, detailing how UCMS connects with internal MCMC systems, external government systems, banking networks, and third-party services.

### 1.1 KRISA Compliance
- **KRISA Section 14**: System interoperability requirements
- **MyGOV Standards**: Government system integration protocols
- **MEASAT**: Malaysian e-Government standards

---

## 2. INTEGRATION LANDSCAPE

### 2.1 Integration Categories

| Category | Systems | Integration Type | Criticality |
|----------|---------|------------------|-------------|
| Internal Core | Oracle ERP, HR, Finance | Real-time | Critical |
| Government | MyGov, Treasury, JPN, SSM | Near real-time | High |
| Financial | Banks, Payment Gateways | Real-time | Critical |
| Security | Digital Signatures, PKI | Real-time | Critical |
| Communication | Email, SMS, WhatsApp | Near real-time | Medium |
| External | SP Systems, Audit | Batch/Real-time | Medium |

### 2.2 Integration Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         INTEGRATION ARCHITECTURE                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│                           ┌─────────────┐                                   │
│                           │    UCMS     │                                   │
│                           │    CORE     │                                   │
│                           │  (Oracle)   │                                   │
│                           └──────┬──────┘                                   │
│                                  │                                          │
│              ┌───────────────────┼───────────────────┐                      │
│              │                   │                   │                      │
│              ▼                   ▼                   ▼                      │
│      ┌───────────────┐  ┌───────────────┐  ┌───────────────┐              │
│      │  API Gateway  │  │  Message Bus  │  │  File Gateway │              │
│      │  (REST/SOAP)  │  │   (Kafka)     │  │   (SFTP/EDI)  │              │
│      └───────┬───────┘  └───────┬───────┘  └───────┬───────┘              │
│              │                   │                   │                      │
│    ┌─────────┼─────────┐        │         ┌─────────┼─────────┐            │
│    ▼         ▼         ▼        ▼         ▼         ▼         ▼            │
│ ┌─────┐  ┌─────┐  ┌─────┐  ┌─────┐   ┌─────┐  ┌─────┐  ┌─────┐           │
│ │Gov  │  │Bank │  │Sec  │  │Comms│   │ERP  │  │Audit│  │Ext  │           │
│ │Sys  │  │Net  │  │Serv │  │Serv │   │Int  │  │Sys  │  │SP   │           │
│ └─────┘  └─────┘  └─────┘  └─────┘   └─────┘  └─────┘  └─────┘           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. INTERNAL INTEGRATIONS

### 3.1 Oracle ERP Integration

#### Integration Scope

| Module | Data Direction | Frequency | Volume |
|--------|---------------|-----------|--------|
| General Ledger | Outbound | Real-time | High |
| Accounts Payable | Bidirectional | Real-time | High |
| Procurement | Outbound | Daily | Medium |
| Budget | Inbound | Hourly | Medium |
| Fixed Assets | Outbound | Daily | Low |
| Cash Management | Bidirectional | Real-time | High |

#### API Specifications

```yaml
# Oracle ERP Integration - Payment Request
endpoint: /api/v1/erp/payments
method: POST
authentication: OAuth 2.0 + Client Certificate
request_format: JSON

request_body:
  payment_reference: "UCMS-2025-001234"
  vendor_id: "SP001234"
  amount: 250000.00
  currency: "MYR"
  budget_account: "24000-USP-001"
  description: "USP CAPEX Claim - Project XYZ"
  supporting_docs:
    - doc_id: "DOC001"
      doc_type: "APPROVAL_LETTER"
    - doc_id: "DOC002"
      doc_type: "INVOICE"

response:
  status: "ACCEPTED"
  erp_voucher_id: "PV-2025-56789"
  estimated_payment_date: "2025-07-15"
```

### 3.2 HR Systems Integration

| Data | Direction | Purpose |
|------|-----------|---------|
| Employee Master | Inbound | User authentication |
| Organization Structure | Inbound | Approval hierarchy |
| Roles & Responsibilities | Inbound | Access control |
| Leave Status | Inbound | Delegation handling |

---

## 4. GOVERNMENT SYSTEM INTEGRATIONS

### 4.1 MyGov Integration Platform

| System | Service | Purpose | Frequency |
|--------|---------|---------|-----------|
| MyGov Portal | Single Sign-On | User authentication | Per login |
| MyGov Notify | Messaging | Notifications | Real-time |
| MyGov Analytics | Reporting | Statutory reports | Daily |

### 4.2 Treasury Systems

```
┌─────────────────────────────────────────────────────────────────┐
│              TREASURY INTEGRATION FLOW                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  UCMS                    Treasury Systems                       │
│  ┌─────────────┐         ┌─────────────┐                       │
│  │  Payment    │────────▶│  e-Keuda    │                       │
│  │  Approved   │  API    │  Validation │                       │
│  └─────────────┘         └──────┬──────┘                       │
│                                 │                               │
│                                 ▼                               │
│                         ┌─────────────┐                         │
│                         │  e-SPKB     │                         │
│                         │  Budget     │                         │
│                         │  Check      │                         │
│                         └──────┬──────┘                         │
│                                │                                │
│                                ▼                                │
│                         ┌─────────────┐                         │
│                         │  e-Gaji/    │                         │
│                         │  Payment    │                         │
│                         │  Execution  │                         │
│                         └─────────────┘                         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 4.3 SSM (Companies Commission) Integration

| Service | Purpose | Data Retrieved |
|---------|---------|----------------|
| Company Search | SP Verification | Registration details |
| Company Profile | Due Diligence | Directors, shareholders |
| Compliance Status | Eligibility Check | Annual return status |

### 4.4 JPN (National Registration) Integration

| Service | Purpose | Data Verified |
|---------|---------|---------------|
| IC Verification | Identity Check | NRIC validity |
| Address Lookup | Contact Verification | Registered address |

---

## 5. FINANCIAL INTEGRATIONS

### 5.1 Banking Network Integration

| Bank | Service | Integration Method |
|------|---------|-------------------|
| CIMB | PayNet/RPP | API |
| Maybank | MEPS/Fund Transfer | Host-to-Host |
| Public Bank | FPX | API |
| Bank Islam | IBFT | API |
| RHB | Rentas | SWIFT/Host-to-Host |

#### Payment Status Inquiry

```json
{
  "inquiry_request": {
    "reference_id": "UCMS-PAY-2025-001234",
    "bank_reference": "CIMB-987654321",
    "account_number": "XXXXX1234",
    "inquiry_timestamp": "2025-06-15T10:30:00+08:00"
  },
  "inquiry_response": {
    "status": "COMPLETED",
    "value_date": "2025-06-15",
    "utr_number": "CIMB20250615098765",
    "credited_amount": 250000.00,
    "response_timestamp": "2025-06-15T10:30:02+08:00"
  }
}
```

### 5.2 FPX Integration

| Feature | Implementation |
|---------|----------------|
| Online Payment | For SP fees/charges |
| Real-time Verification | Transaction confirmation |
| Reconciliation | Daily settlement reports |

---

## 6. SECURITY INTEGRATIONS

### 6.1 Digital Signature Integration

| Provider | Service | Use Case |
|----------|---------|----------|
| MSC Trustgate | PKI Certificates | User authentication |
| Digicert | Document Signing | Claim approval signing |
| MyPKI | Government PKI | Official correspondence |

#### Signature Verification Flow

```
┌─────────────────────────────────────────────────────────────────┐
│              DIGITAL SIGNATURE VERIFICATION                     │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. DOCUMENT SUBMITTED                                          │
│     ↓                                                           │
│  2. EXTRACT SIGNATURE METADATA                                  │
│     ↓                                                           │
│  3. VALIDATE CERTIFICATE CHAIN                                  │
│     ↓                                                           │
│  4. CHECK CERTIFICATE STATUS (OCSP)                             │
│     ↓                                                           │
│  5. VERIFY SIGNATURE INTEGRITY                                  │
│     ↓                                                           │
│  6. VALIDATE SIGNER IDENTITY                                    │
│     ↓                                                           │
│  7. AUDIT LOG RESULT                                            │
│     ↓                                                           │
│  8. RETURN VERIFICATION STATUS                                  │
│                                                                 │
│  Verification Result:                                           │
│  ┌─────────────┬─────────────┬─────────────┬─────────────┐     │
│  │  Valid      │  Invalid    │  Expired    │  Revoked    │     │
│  │  ✅         │  ❌         │  ⚠️         │  🚫         │     │
│  │  Proceed    │  Reject     │  Reject     │  Reject     │     │
│  └─────────────┴─────────────┴─────────────┴─────────────┘     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 6.2 Identity and Access Management

| Component | Technology | Purpose |
|-----------|------------|---------|
| Identity Provider | Oracle IDCS | SSO authentication |
| MFA | Oracle Authenticator | Second factor |
| Directory | Active Directory | User synchronization |
| Access Control | RBAC | Authorization |

---

## 7. COMMUNICATION INTEGRATIONS

### 7.1 Email Services

| Provider | Service | Usage |
|----------|---------|-------|
| MCMC Exchange | Official Email | Internal notifications |
| AWS SES | Transactional | System-generated emails |
| GovMail | Secure | Confidential communications |

### 7.2 SMS Gateway

| Provider | Coverage | Use Cases |
|----------|----------|-----------|
| Twilio | Global | OTP, notifications |
| SMS123 | Malaysia | Bulk alerts |
| MCMC SMS | Government | Official alerts |

### 7.3 WhatsApp Business API

| Feature | Implementation |
|---------|----------------|
| Notifications | Claim status updates |
| Two-way Chat | Support queries |
| Document Sharing | Limited attachments |

---

## 8. EXTERNAL SP INTEGRATIONS

### 8.1 Service Provider API

| Endpoint | Method | Purpose |
|----------|--------|---------|
| /api/v1/sp/claims | POST | Submit claim |
| /api/v1/sp/claims/{id} | GET | Check status |
| /api/v1/sp/documents | POST | Upload document |
| /api/v1/sp/payments | GET | Payment history |

### 8.2 Audit Systems Integration

| System | Data | Frequency |
|--------|------|-----------|
| National Audit | Financial summaries | Quarterly |
| Internal Audit | Transaction logs | Real-time |
| External Audit | Extract files | On-request |

---

## 9. INTEGRATION SECURITY

### 9.1 Security Controls

| Layer | Control | Implementation |
|-------|---------|----------------|
| Transport | TLS 1.3 | All connections |
| Authentication | mTLS + OAuth 2.0 | Mutual authentication |
| Authorization | Scope-based | Least privilege |
| Rate Limiting | Token bucket | DDoS protection |
| Payload | Encryption | AES-256-GCM |
| Logging | Immutable | SIEM integration |

### 9.2 API Security Standards

```yaml
security_requirements:
  authentication:
    method: OAuth 2.0 with PKCE
    token_type: JWT
    token_lifetime: 3600 seconds
    refresh_token_lifetime: 86400 seconds
  
  transport:
    protocol: HTTPS
    tls_version: "1.3"
    cipher_suites:
      - TLS_AES_256_GCM_SHA384
      - TLS_CHACHA20_POLY1305_SHA256
  
  rate_limiting:
    tier_premium: 10000 requests/hour
    tier_standard: 1000 requests/hour
    tier_basic: 100 requests/hour
  
  monitoring:
    failed_auth_threshold: 5
    lockout_duration: 900 seconds
    alert_channels:
      - security@mcmc.gov.my
      - SIEM
```

---

## 10. INTEGRATION MONITORING

### 10.1 Monitoring Dashboard

| Metric | Threshold | Alert |
|--------|-----------|-------|
| API Response Time | > 2s | Warning |
| Error Rate | > 1% | Critical |
| Failed Auth | > 5/min | Security |
| Message Queue Depth | > 1000 | Warning |
| Downstream Timeout | Any | Critical |

### 10.2 Health Check Endpoints

| System | Endpoint | Frequency |
|--------|----------|-----------|
| Oracle ERP | /health/erp | Every 60s |
| Banking | /health/bank | Every 60s |
| PKI | /health/pki | Every 300s |
| Email | /health/email | Every 300s |

---

## 11. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T31-SECURITY-FRAMEWORK | Security Architecture |
| CR-002 | ANNEX-T26-AUDIT-TRAIL | Audit Integration |
| CR-003 | ANNEX-T22-PAYMENT-WORKFLOW | Payment Integration |
| CR-004 | ANNEX-T27-SELF-SERVICE | SP API Integration |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
