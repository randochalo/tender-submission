# ANNEX T22: PAYMENT WORKFLOW

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive Payment Workflow for the USP Claims Management System, governing the end-to-end processing of approved claims from validation through to final disbursement.

### 1.1 KRISA Compliance
- **KRISA Section 15**: Financial management and accountability
- **Government Financial Procedures**: Treasury circulars and directives
- **MCMC Financial Regulations**: Internal control requirements

---

## 2. PAYMENT WORKFLOW OVERVIEW

### 2.1 Workflow Scope

The payment workflow encompasses:
- Claims validation and approval routing
- Budget availability verification
- Payment authorization hierarchies
- Disbursement processing
- Reconciliation and reporting

### 2.2 Payment Types

| Payment Type | Description | Processing SLA | Authority Level |
|--------------|-------------|----------------|-----------------|
| Standard Claim Payment | Approved USP claims | 14 working days | Director |
| Advance Payment | Pre-funded project costs | 10 working days | CEO |
| Milestone Payment | Phased project payments | 7 working days | Director |
| Reimbursement | Post-expense recovery | 21 working days | Director |
| Retention Release | Holdback release | 14 working days | CEO |
| Interest Payment | Late payment compensation | 30 working days | Director |

---

## 3. DETAILED WORKFLOW PROCESS

### 3.1 Stage 1: Claim Receipt and Validation

```
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 1: CLAIM RECEIPT & VALIDATION                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │   SP Submit │───▶│   System    │───▶│  Automated  │         │
│  │   Claim     │    │   Capture   │    │  Validation │         │
│  └─────────────┘    └─────────────┘    └──────┬──────┘         │
│                                               │                 │
│                    ┌──────────────────────────┘                 │
│                    ▼                                            │
│         ┌─────────────────┐                                     │
│         │ Validation Pass │────▶ PROCEED TO STAGE 2             │
│         └─────────────────┘                                     │
│                    │                                            │
│         ┌─────────────────┐                                     │
│         │ Validation Fail │────▶ RETURN TO SP                   │
│         └─────────────────┘                                     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Validation Checks:**

| Check ID | Check Description | System/Manual | Time |
|----------|-------------------|---------------|------|
| PV-001 | Document completeness | System | Real-time |
| PV-002 | Financial calculation accuracy | System | Real-time |
| PV-003 | Supporting documentation | System + OCR | < 2 hours |
| PV-004 | Duplicate claim detection | System | Real-time |
| PV-005 | SP eligibility status | System | Real-time |
| PV-006 | Project authorization | System | Real-time |
| PV-007 | Budget code validity | System | Real-time |

### 3.2 Stage 2: Eligibility Assessment

| Task | Responsible | Duration | Output |
|------|-------------|----------|--------|
| Technical review | Technical Officer | 3 days | Technical Assessment Report |
| Financial review | Finance Officer | 2 days | Financial Verification Report |
| Eligibility determination | Senior Officer | 1 day | Eligibility Decision |
| Site verification (if required) | Field Team | 5 days | Site Inspection Report |

### 3.3 Stage 3: Approval Workflow

#### 3.3.1 Approval Matrix

| Claim Value (RM) | Technical Approval | Financial Approval | Final Approval |
|------------------|-------------------|-------------------|----------------|
| ≤ 100,000 | Senior Officer | Finance Officer | Director |
| 100,001 - 500,000 | Principal Assistant | Senior Finance | Director |
| 500,001 - 1,000,000 | Director | Finance Manager | Deputy CEO |
| 1,000,001 - 5,000,000 | Director | CFO | CEO |
| > 5,000,000 | Board Committee | CFO | Board Chairman |

#### 3.3.2 Approval Workflow Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 3: APPROVAL HIERARCHY                                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐                                                │
│  │  Eligibility│                                                │
│  │  Confirmed  │                                                │
│  └──────┬──────┘                                                │
│         │                                                       │
│         ▼                                                       │
│  ┌─────────────────────────────────────────┐                    │
│  │      DETERMINE APPROVAL PATH            │                    │
│  │  Based on claim value and type          │                    │
│  └────────────────────┬────────────────────┘                    │
│                       │                                         │
│         ┌─────────────┼─────────────┐                          │
│         ▼             ▼             ▼                          │
│    ┌─────────┐   ┌─────────┐   ┌─────────┐                     │
│    │ Level 1 │   │ Level 2 │   │ Level 3 │                     │
│    │  ≤500K  │   │  ≤5M    │   │  >5M    │                     │
│    └───┬─────┘   └───┬─────┘   └───┬─────┘                     │
│        │             │             │                            │
│        ▼             ▼             ▼                            │
│   ┌─────────┐   ┌─────────┐   ┌─────────┐                      │
│   │ Director│   │  CEO    │   │  Board  │                      │
│   │ Approve │   │ Approve │   │ Approve │                      │
│   └────┬────┘   └────┬────┘   └────┬────┘                      │
│        │             │             │                            │
│        └─────────────┴─────────────┘                            │
│                      │                                          │
│                      ▼                                          │
│              ┌─────────────┐                                    │
│              │   PAYMENT   │                                    │
│              │  GENERATED  │                                    │
│              └─────────────┘                                    │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.4 Stage 4: Payment Processing

#### 4.4.1 Payment Instruction Generation

| Step | Activity | System | Duration |
|------|----------|--------|----------|
| 4.4.1.1 | Generate Payment Voucher | Oracle Financials | Automated |
| 4.4.1.2 | Budget reservation check | Oracle Budgets | Real-time |
| 4.4.1.3 | Vendor account verification | Oracle Payables | Real-time |
| 4.4.1.4 | Tax calculation (if applicable) | Oracle Tax Engine | Automated |
| 4.4.1.5 | Generate payment instruction | UCMS | Automated |

#### 4.4.2 Payment Method Selection

| Payment Method | Threshold (RM) | Processing Time | Use Case |
|----------------|----------------|-----------------|----------|
| Electronic Funds Transfer (EFT) | All amounts | 1-2 days | Standard payments |
| Real-Time Payment (RPP/DuitNow) | ≤ 50,000 | Immediate | Urgent payments |
| Bank Draft | > 500,000 | 3-5 days | High-value security |
| Telegraphic Transfer | International | 3-7 days | Foreign currency |

### 3.5 Stage 5: Disbursement and Confirmation

```
┌─────────────────────────────────────────────────────────────────┐
│  STAGE 5: DISBURSEMENT                                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │   Payment   │───▶│   Banking   │───▶│  Fund       │         │
│  │   Approved  │    │   Interface │    │  Transfer   │         │
│  └─────────────┘    └─────────────┘    └──────┬──────┘         │
│                                               │                 │
│                    ┌──────────────────────────┘                 │
│                    ▼                                            │
│         ┌─────────────────┐                                     │
│         │  Bank Processes │                                     │
│         │  Payment        │                                     │
│         └────────┬────────┘                                     │
│                  │                                              │
│    ┌─────────────┼─────────────┐                                │
│    ▼             ▼             ▼                                │
│ ┌───────┐    ┌───────┐    ┌───────┐                            │
│ │Success│    │Pending│    │Failed │                            │
│ └───┬───┘    └───┬───┘    └───┬───┘                            │
│     │            │            │                                 │
│     ▼            ▼            ▼                                 │
│ ┌────────┐   ┌────────┐   ┌────────┐                           │
│ │Notify  │   │Monitor │   │Investigate│                        │
│ │Confirm │   │24-48hrs│   │& Retry    │                        │
│ └────────┘   └────────┘   └────────┘                           │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 4. PAYMENT CONTROLS AND SECURITY

### 4.1 Segregation of Duties

| Function | Role | Separation Requirement |
|----------|------|----------------------|
| Claim Review | Technical Officer | Cannot approve payments |
| Payment Preparation | Finance Officer | Cannot authorize release |
| Payment Authorization | Director/CEO | Cannot process payments |
| Bank Reconciliation | Accountant | Independent of processing |

### 4.2 Security Controls

| Control | Implementation | Verification |
|---------|---------------|--------------|
| Dual authorization | Two-person rule for > RM 100K | System enforced |
| Digital signatures | PKI certificates | MSC Trustgate |
| Bank account validation | Pre-registered accounts only | Master data control |
| Amount limits | Role-based thresholds | Workflow engine |
| Audit logging | All actions recorded | Immutable log |

---

## 5. EXCEPTION HANDLING

### 5.1 Exception Types and Resolution

| Exception | Trigger | Resolution Path | SLA |
|-----------|---------|-----------------|-----|
| Insufficient Budget | Budget check fail | Budget reallocation request | 5 days |
| Bank Account Mismatch | Account validation fail | SP verification required | 3 days |
| Duplicate Payment | System detection | Investigation and reversal | 7 days |
| Payment Return | Bank rejection | Account update and reprocess | 5 days |
| Disputed Amount | SP challenge | Reconciliation and adjustment | 14 days |

---

## 6. RECONCILIATION PROCESS

### 6.1 Daily Reconciliation

| Activity | Frequency | Responsible | Output |
|----------|-----------|-------------|--------|
| Payment status update | Daily | System | Status report |
| Bank statement import | Daily | Finance Officer | Import log |
| Unmatched item review | Daily | Senior Accountant | Exception list |
| Aging analysis | Daily | Finance Officer | Aging report |

### 6.2 Monthly Reconciliation

| Activity | Deadline | Responsible | Output |
|----------|----------|-------------|--------|
| GL to Bank reconciliation | Day 5 | Accountant | Rec statement |
| Outstanding payment review | Day 10 | Finance Manager | Action plan |
| SP statement reconciliation | Day 15 | Finance Officer | Confirmation |
| Management report | Day 20 | CFO | Financial summary |

---

## 7. SYSTEM INTEGRATION ARCHITECTURE

### 7.1 Integration Points

```
┌─────────────────────────────────────────────────────────────────┐
│                    PAYMENT WORKFLOW INTEGRATION                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐         ┌─────────────┐         ┌───────────┐ │
│  │    UCMS     │◀───────▶│    Oracle   │◀───────▶│   Bank    │ │
│  │   Module    │  APIs   │ Financials  │  Host   │  Systems  │ │
│  └─────────────┘         │             │  to Host│           │ │
│         │                │  ┌───────┐  │         └───────────┘ │
│         │                │  │ GL    │  │                       │
│         │                │  │ AP    │  │                       │
│         │                │  │ Cash  │  │                       │
│         │                │  └───────┘  │                       │
│         │                └─────────────┘                       │
│         │                                                       │
│         ▼                                                       │
│  ┌─────────────┐                                                │
│  │    RPA      │───▶ Bank portal automation                     │
│  │   Engine    │───> Status retrieval                           │
│  └─────────────┘                                                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 8. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T21-YEARLY-CLAIM-TEMPLATE | Claim Structure |
| CR-002 | ANNEX-T26-AUDIT-TRAIL | Payment Logging |
| CR-003 | ANNEX-T37-BACKUP-RECOVERY | Data Protection |
| CR-004 | ANNEX-T40-SUPPORT-PLAN | Payment Support |

---

## 9. KEY PERFORMANCE INDICATORS

| KPI | Target | Measurement |
|-----|--------|-------------|
| Payment processing time | ≤ 14 days | Claim to disbursement |
| Payment accuracy | 99.9% | Error-free payments |
| First-time approval rate | 85% | No rework required |
| Bank reconciliation | 100% monthly | Complete matching |
| SP satisfaction | ≥ 4.0/5.0 | Post-payment survey |

---

## 10. VERSION CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | June 2025 | UCMS Team | Initial release for TSH-2607 |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
