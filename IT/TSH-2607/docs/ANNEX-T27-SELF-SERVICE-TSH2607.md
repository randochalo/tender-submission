# ANNEX T27: SELF-SERVICE PORTAL

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the Self-Service Portal design for Service Providers to independently manage their USP claim submissions, track status, access documents, and communicate with MCMC without direct staff intervention.

### 1.1 KRISA Compliance
- **KRISA Section 12**: Digital government service delivery
- **KRISA Section 9**: User-centric service design
- **MCMC Digital Strategy**: Online service channels

---

## 2. PORTAL OVERVIEW

### 2.1 Portal Objectives

| Objective | Description | Success Metric |
|-----------|-------------|----------------|
| Reduce Call Volume | Decrease inquiry calls by 60% | < 100 calls/month |
| 24/7 Access | Round-the-clock availability | 99.9% uptime |
| Self-Sufficiency | Enable SP autonomy | 80% transactions self-service |
| Transparency | Real-time status visibility | < 1 min status lookup |
| Efficiency | Faster claim processing | -2 days average |

### 2.2 User Categories

| User Type | Description | Access Level |
|-----------|-------------|--------------|
| SP Primary Contact | Main authorized representative | Full access |
| SP Finance User | Finance team member | Financial data only |
| SP Technical User | Technical coordinator | Project data only |
| SP Read-Only User | View-only access | View all, edit none |
| Guest User | Prospective SP | Registration only |

---

## 3. PORTAL ARCHITECTURE

### 3.1 Technical Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    SELF-SERVICE PORTAL                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              PRESENTATION LAYER                          │   │
│  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │   │
│  │  │   Web Portal │  │ Mobile App   │  │   API Access │   │   │
│  │  │  (Responsive)│  │  (iOS/Android)│  │   (REST)     │   │   │
│  │  └──────────────┘  └──────────────┘  └──────────────┘   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                          │                                      │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              APPLICATION LAYER (Oracle APEX)             │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │   │
│  │  │Authentication│Claim Mgmt│Document  │Communication│   │   │
│  │  │Service   │Service   │Service   │Service    │   │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                          │                                      │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              INTEGRATION LAYER                           │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │   │
│  │  │   UCMS   │  │ Digital  │  │   SMS/   │  │  Email   │   │   │
│  │  │   Core   │  │  Sign    │  │  WhatsApp│  │ Service  │   │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2 Security Architecture

| Layer | Security Control | Implementation |
|-------|------------------|----------------|
| Network | WAF, DDoS Protection | CloudFlare/AWF |
| Transport | TLS 1.3 | All connections |
| Authentication | Multi-factor | PKI + OTP |
| Session | JWT tokens | 30-min timeout |
| Application | RBAC | Role-based access |
| Data | Encryption | AES-256 at rest |

---

## 4. PORTAL MODULES

### 4.1 Module 1: Dashboard & Overview

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ SELF-SERVICE PORTAL - Dashboard                               [Help] [Logout]│
├─────────────────────────────────────────────────────────────────────────────┤
│ Welcome, [Provider Name]          │ Last Login: [Date/Time] from [IP]       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  QUICK STATS                                                    [Refresh]   │
│  ┌───────────────┐ ┌───────────────┐ ┌───────────────┐ ┌───────────────┐   │
│  │   Active      │ │   Pending     │ │   Approved    │ │   Total Paid  │   │
│  │   Claims      │ │   Payment     │ │   This Year   │ │   To Date     │   │
│  │     [X]       │ │   RM[X]       │ │   RM[X]M      │ │   RM[X]M      │   │
│  │   [View All]  │ │   [Details]   │ │   [Reports]   │ │   [History]   │   │
│  └───────────────┘ └───────────────┘ └───────────────┘ └───────────────┘   │
│                                                                             │
│  RECENT ACTIVITY                                                            │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ Time           │ Activity                    │ Status                │   │
│  ├─────────────────────────────────────────────────────────────────────┤   │
│  │ [HH:MM]        │ Claim UCMS-25-089 approved  │ ✅ Processed          │   │
│  │ [HH:MM]        │ Document uploaded           │ ✅ Received           │   │
│  │ [Yesterday]    │ Query response submitted    │ ⏳ Under Review       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  ALERTS & NOTIFICATIONS                                         [Mark All] │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ 🔴 Your claim UCMS-25-089 requires additional documents             │   │
│  │ 🟡 Policy update: New submission guidelines effective 1 July 2025   │   │
│  │ 🟢 Payment of RM 250,000 has been processed for claim UCMS-25-076   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  QUICK ACTIONS                                                              │
│  [+ Submit New Claim]  [📤 Upload Documents]  [💬 Send Message]  [📊 Reports]│
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Module 2: Claim Management

| Feature | Description | User Value |
|---------|-------------|------------|
| New Claim Wizard | Step-by-step submission | Reduces errors |
| Draft Claims | Save and resume later | Flexibility |
| Claim History | Complete claim record | Transparency |
| Clone Claim | Duplicate previous claim | Efficiency |
| Bulk Upload | Excel template upload | Volume handling |

#### New Claim Wizard Flow

```
┌─────────────────────────────────────────────────────────────────┐
│              NEW CLAIM SUBMISSION WIZARD                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Step [1] ─── Step [2] ─── Step [3] ─── Step [4] ─── Step [5]  │
│   ●──────────○───────────○───────────○───────────○              │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  STEP 1: SELECT CLAIM TYPE                              │   │
│  │                                                         │   │
│  │  ○ Capital Expenditure (CAPEX)                          │   │
│  │    Infrastructure, equipment, installation              │   │
│  │                                                         │   │
│  │  ○ Operational Expenditure (OPEX)                       │   │
│  │    Maintenance, leasing, utilities                      │   │
│  │                                                         │   │
│  │  ○ Shared Infrastructure                                │   │
│  │    Multi-party investments                              │   │
│  │                                                         │   │
│  │  ○ Technology Upgrade                                   │   │
│  │    Equipment modernization                              │   │
│  │                                                         │   │
│  │              [Cancel]              [Next ▶]             │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 4.3 Module 3: Document Management

| Function | Features | Limits |
|----------|----------|--------|
| Upload | Drag-drop, progress bar | 50MB per file |
| Organize | Folder structure, tags | Unlimited folders |
| Preview | PDF, image, Office docs | In-browser |
| Download | Individual or bulk zip | 1GB per batch |
| Version Control | Auto-versioning | 10 versions |
| Virus Scan | Real-time scanning | All uploads |

### 4.4 Module 4: Communication Center

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ COMMUNICATION CENTER                                          [New Message] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────┐  ┌──────────────────────────────────────────────┐│
│  │ CONVERSATIONS        │  │ MESSAGE THREAD                               ││
│  │                      │  │                                              ││
│  │ 🔵 Claim UCMS-25-089 │  │ ┌────────────────────────────────────────┐  ││
│  │    3 new messages    │  │ │ MCMC Officer (15/06 10:30)             │  ││
│  │                      │  │ │────────────────────────────────────────│  ││
│  │ Claim UCMS-25-076    │  │ │ We require the following additional    │  ││
│  │    Resolved          │  │ │ documents for your claim:              │  ││
│  │                      │  │ │ • Signed project completion certificate│  ││
│  │ General Inquiry      │  │ │ • Updated bank statement               │  ││
│  │    1 message         │  │ │                                        │  ││
│  │                      │  │ │ Please upload via the Documents section│  ││
│  │                      │  │ │ within 7 days.                         │  ││
│  │                      │  │ └────────────────────────────────────────┘  ││
│  │                      │  │                                             ││
│  │                      │  │ ┌────────────────────────────────────────┐  ││
│  │                      │  │ │ You (15/06 14:45)                      │  ││
│  │                      │  │ │────────────────────────────────────────│  ││
│  │                      │  │ │ Documents uploaded as requested:       │  ││
│  │                      │  │ │ • completion_cert.pdf                  │  ││
│  │                      │  │ │ • bank_statement_may2025.pdf           │  ││
│  │                      │  │ │                                        │  ││
│  │                      │  │ │ Please confirm receipt.                │  ││
│  │                      │  │ └────────────────────────────────────────┘  ││
│  │                      │  │                                             ││
│  │                      │  │ [Type your message...]          [Send] [📎]││
│  └──────────────────────┘  └──────────────────────────────────────────────┘│
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. PORTAL FEATURES

### 5.1 Claim Tracking

| Tracking Feature | Description | Updates |
|------------------|-------------|---------|
| Status Timeline | Visual workflow progress | Real-time |
| Estimated Completion | ML-based prediction | Daily |
| Delay Notifications | Proactive alerts | Immediate |
| Document Checklist | Required vs submitted | Real-time |
| Payment Tracking | Disbursement status | Hourly |

### 5.2 Reporting & Analytics

| Report | Description | Export |
|--------|-------------|--------|
| Claim Summary | All claims summary | PDF/Excel |
| Payment History | Complete payment record | PDF/Excel |
| Performance Metrics | Processing time analysis | Excel |
| Document Status | Upload checklist | PDF |
| Tax Reports | Withholding tax summary | Excel |

### 5.3 Mobile Features

| Feature | iOS | Android | Description |
|---------|-----|---------|-------------|
| Push Notifications | ✓ | ✓ | Real-time alerts |
| Biometric Login | ✓ | ✓ | Face/Touch ID |
| Document Scan | ✓ | ✓ | Camera to PDF |
| Offline Mode | ✓ | ✓ | View cached data |
| Quick Status | ✓ | ✓ | Widget support |

---

## 6. USER MANAGEMENT

### 6.1 Account Management

| Function | Self-Service | Approval Required |
|----------|--------------|-------------------|
| Password Reset | Yes | Email verification |
| Profile Update | Yes | - |
| Contact Change | Yes | Email confirmation |
| Add User | No | MCMC approval |
| Remove User | No | MCMC approval |
| Role Change | No | MCMC approval |
| Bank Details | No | Document verification |

### 6.2 Delegation Features

| Delegation Type | Description | Duration |
|-----------------|-------------|----------|
| Temporary Absence | Delegate to colleague | 1-30 days |
| Project Specific | Delegate for one claim | Claim lifecycle |
| Read-Only Access | View-only delegation | Custom |

---

## 7. INTEGRATION CAPABILITIES

### 7.1 External System Integration

| System | Integration | Purpose |
|--------|-------------|---------|
| UCMS Core | Real-time API | Data sync |
| Digital Signature | PKI service | Document signing |
| SMS Gateway | REST API | OTP & alerts |
| Email Service | SMTP/API | Notifications |
| Payment Gateway | Bank API | Status inquiry |
| Document OCR | AI service | Auto-extraction |

---

## 8. ACCESSIBILITY & USABILITY

### 8.1 Accessibility Compliance

| Standard | Level | Features |
|----------|-------|----------|
| WCAG 2.1 | AA | Keyboard nav, screen reader |
| MyGov Accessibility | Full | Malay language support |
| Mobile Responsive | All devices | Adaptive layouts |

### 8.2 Language Support

| Language | Interface | Documents | Support |
|----------|-----------|-----------|---------|
| English | Full | Full | 24/7 |
| Bahasa Malaysia | Full | Full | Business hours |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T25-DASHBOARD-DESIGNS | Portal Dashboards |
| CR-002 | ANNEX-T31-SECURITY-FRAMEWORK | Portal Security |
| CR-003 | ANNEX-T38-TRAINING-PLAN | User Training |
| CR-004 | ANNEX-T40-SUPPORT-PLAN | Portal Support |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
