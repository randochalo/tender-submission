# ANNEX-T20: Claims Workflow
## TSH-2607 MCMC UCMS Tender

**Document Reference:** TSH-2607-ANNEX-T20  
**Date:** February 2026  
**Version:** 1.0

---

## 1. OVERVIEW

### 1.1 Purpose
This annex describes the comprehensive Claims Management workflow for UCMS, covering all claim types including Advance Claims, Quarterly Claims, Major Contributor Claims, and Yearly Claims.

### 1.2 Claim Types Supported

| Claim Type | Frequency | Description | Workflow Complexity |
|------------|-----------|-------------|---------------------|
| Advance Claim | On-demand | Initial project funding | Medium |
| Quarterly Claim | Quarterly | Regular progress claims | High |
| Major Contributor | Milestone-based | Large project milestones | High |
| Yearly Claim | Annual | Subsidiary ledger reconciliation | Very High |

---

## 2. CLAIMS WORKFLOW ARCHITECTURE

### 2.1 End-to-End Process Flow

```
┌─ CLAIMS MANAGEMENT WORKFLOW ───────────────────────────────────────────────┐
│                                                                             │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐  │
│  │  CREATE  │──▶│  SUBMIT  │──▶│ VALIDATE │──▶│  REVIEW  │──▶│ APPROVE  │  │
│  └──────────┘   └──────────┘   └──────────┘   └──────────┘   └──────────┘  │
│       │              │              │              │              │        │
│       ▼              ▼              ▼              ▼              ▼        │
│  [Draft]        [Pending]      [Checking]    [Verification]  [Approved]   │
│                                                                             │
│       │              │              │              │              │        │
│       ▼              ▼              ▼              ▼              ▼        │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐  │
│  │  DUSP    │   │  DUSP    │   │   UCMS   │   │  MCMC    │   │  MCMC    │  │
│  │  User    │   │  Admin   │   │  System  │   │  Finance │   │  Director│  │
│  └──────────┘   └──────────┘   └──────────┘   └──────────┘   └──────────┘  │
│                                                                             │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐                               │
│  │  PAYMENT │◀──│  VOUCHER │◀──│  MEMO    │                               │
│  │ PROCESS  │   │  CREATE  │   │  SIGN    │                               │
│  └──────────┘   └──────────┘   └──────────┘                               │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Claim Lifecycle States

```
                    ┌──────────┐
                    │  DRAFT   │
                    └────┬─────┘
                         │ Submit
                         ▼
                    ┌──────────┐
              ┌────│ SUBMITTED │────┐
              │    └────┬─────┘    │
         Reject│         │ Validate  │Invalid
              │         ▼            │
              │    ┌──────────┐      │
              └────│VALIDATING│◀─────┘
                   └────┬─────┘
                        │ Pass
                        ▼
                   ┌──────────┐
              ┌────│ UNDER    │────┐
         Query│    │ REVIEW   │    │Reject
              │    └────┬─────┘    │
              │         │ Approve   │
              │         ▼            │
              └────┌──────────┐─────┘
                   │ APPROVED │
                   └────┬─────┘
                        │ Sign Memo
                        ▼
                   ┌──────────┐
                   │  MEMO    │
                   │  SIGNED  │
                   └────┬─────┘
                        │ Generate Voucher
                        ▼
                   ┌──────────┐
                   │ VOUCHER  │
                   │ CREATED  │
                   └────┬─────┘
                        │ Process Payment
                        ▼
                   ┌──────────┐
                   │  PAID    │
                   └──────────┘
```

---

## 3. CLAIM CREATION WORKFLOW

### 3.1 Self-Service Claim Submission (DUSP View)

```
┌─ CREATE NEW CLAIM ─────────────────────────────────────────────────────────┐
│                                                                             │
│  DUSP: Telekom Malaysia Berhad                                             │
│  User: Ahmad (DUSP Submitter)                                              │
│                                                                             │
│  STEP 1: SELECT CLAIM TYPE                                                  │
│  ─────────────────────────────────────────────────────────────────────────  │
│  ○ Advance Claim                     ○ Quarterly Claim                     │
│  ○ Major Contributor Claim           ○ Yearly Claim                        │
│                                                                             │
│  Selected: ● Quarterly Claim (Q1 2026)                                     │
│                                                                             │
│  STEP 2: SELECT PROJECT                                                     │
│  ─────────────────────────────────────────────────────────────────────────  │
│  Project: [Project A - USP Broadband Deployment ▼]                         │
│  Project ID: USP-2024-001                                                  │
│  Approved Capped Cost: RM 45,000,000                                       │
│  Previous Claims: RM 12,300,000 (27%)                                      │
│  Available Budget: RM 32,700,000                                           │
│                                                                             │
│  STEP 3: CLAIM DETAILS                                                      │
│  ─────────────────────────────────────────────────────────────────────────  │
│  Claim Period: 01/01/2026 - 31/03/2026                                     │
│  Physical Progress: [________] % (Target: 35%, Achieved: 38%)              │
│  Claim Amount: RM [___________]                                            │
│                                                                             │
│  STEP 4: SUPPORTING DOCUMENTS                                               │
│  ─────────────────────────────────────────────────────────────────────────  │
│  ☑ CEO Declaration/Financial Self-Declaration [📄 uploaded]                │
│  ☑ Auditor's Declaration [📄 uploaded]                                     │
│  ☑ Supporting Invoices [📄 5 files uploaded]                               │
│  ☑ Progress Report [📄 uploaded]                                           │
│  ☐ Variation Order (if applicable)                                         │
│  ☐ EOT Approval (if applicable)                                            │
│                                                                             │
│  STEP 5: ATTESTATION                                                        │
│  ─────────────────────────────────────────────────────────────────────────  │
│  ☑ I hereby declare that all information provided is true and accurate.    │
│  ☑ I confirm that all supporting documents are authentic.                  │
│  ☑ I understand that false claims may result in penalties.                 │
│                                                                             │
│  Authorized Signatory: [________________]                                  │
│  Date: [19/02/2026]                                                        │
│                                                                             │
│  [💾 Save Draft]  [👁️ Preview]  [✓ Submit Claim]                           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Claim Validation Rules Engine

```python
# Claim Validation Pseudocode

class ClaimValidator:
    """
    Validates claim submission against business rules
    """
    
    def validate(self, claim):
        validations = [
            self.check_project_active(),
            self.check_bond_valid(),
            self.check_budget_available(),
            self.check_progress_reasonable(),
            self.check_previous_claims(),
            self.check_documents_complete(),
            self.check_duplicate_claim(),
        ]
        return all(validations)
    
    def check_bond_valid(self):
        """Validate performance bond is active and sufficient"""
        bond = get_performance_bond(self.project_id)
        assert bond.status == "ACTIVE"
        assert bond.expiry_date > today() + timedelta(days=30)
        assert bond.value >= self.claim_amount * 0.05
        return True
    
    def check_budget_available(self):
        """Validate claim amount within remaining budget"""
        budget = get_project_budget(self.project_id)
        assert self.claim_amount <= budget.remaining
        return True
    
    def check_progress_reasonable(self):
        """Validate physical progress aligns with financial claim"""
        variance = abs(self.physical_progress - self.financial_progress)
        assert variance <= 10  # Max 10% variance
        return True
    
    def check_documents_complete(self):
        """Validate all required documents uploaded"""
        required = get_required_documents(self.claim_type)
        for doc in required:
            assert doc in self.attachments
        return True
```

---

## 4. APPROVAL WORKFLOW

### 4.1 Multi-Level Approval Matrix

```
┌─ APPROVAL HIERARCHY ───────────────────────────────────────────────────────┐
│                                                                             │
│  CLAIM AMOUNT           │ LEVEL 1          │ LEVEL 2         │ LEVEL 3    │
│  ───────────────────────┼──────────────────┼─────────────────┼────────────│
│  < RM 100,000          │ Finance Analyst  │ Finance Manager │ -          │
│  RM 100K - 500K        │ Finance Manager  │ USP Director    │ -          │
│  RM 500K - 1M          │ Finance Manager  │ USP Director    │ CFO        │
│  > RM 1,000,000        │ Finance Manager  │ USP Director    │ CEO/MCMC   │
│                                                                             │
│  DIGITAL SIGNATURE REQUIRED FOR ALL APPROVALS ≥ RM 100,000                 │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Approval Screen (MCMC Finance View)

```
┌─ CLAIM APPROVAL ───────────────────────────────────────────────────────────┐
│                                                                             │
│  Claim ID: CLAIM-2026-Q1-00456                                             │
│  Status: ⏳ PENDING APPROVAL                                               │
│                                                                             │
│  ┌─ CLAIM SUMMARY ──────────────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  DUSP: Telekom Malaysia Berhad                                       │  │
│  │  Project: Project A - USP Broadband Deployment                       │  │
│  │  Claim Type: Quarterly Claim (Q1 2026)                               │  │
│  │                                                                       │  │
│  │  Claim Amount: RM 3,450,000.00                                       │  │
│  │  Physical Progress: 38% (Target: 35%)                                │  │
│  │  Cumulative Claimed: 63% of Capped Cost                              │  │
│  │                                                                       │  │
│  │  Bond Status: ✓ VALID (Expiry: 31/12/2026)                           │  │
│  │  Budget Status: ✓ SUFFICIENT (Remaining: RM 19.6M)                   │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌─ VALIDATION RESULTS ─────────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  ☑ Bond Validation         ✓ PASSED                                  │  │
│  │  ☑ Budget Check            ✓ PASSED                                  │  │
│  │  ☑ Document Completeness   ✓ PASSED                                  │  │
│  │  ☑ Progress Verification   ✓ PASSED                                  │  │
│  │  ☑ Duplicate Check         ✓ PASSED                                  │  │
│  │  ☑ USPFS Sync Check        ✓ PASSED                                  │  │
│  │                                                                       │  │
│  │  Overall Status: ✓ READY FOR APPROVAL                                │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌─ APPROVAL ACTION ─────────────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  [✓ APPROVE]  [⏸️ HOLD]  [❌ REJECT]  [❓ QUERY]                      │  │
│  │                                                                       │  │
│  │  Comments: [                                                          │  │
│  │            ________________________________________________          │  │
│  │            ________________________________________________          │  │
│  │  ]                                                                     │  │
│  │                                                                       │  │
│  │  Digital Signature Required: [🔐 Sign with MyKAD/Token]              │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [📎 View Documents]  [📊 View Project Dashboard]  [📞 Contact DUSP]       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. YEARLY CLAIM WORKFLOW (SPECIAL PROCESS)

### 5.1 Subsidiary Ledger Concept

```
┌─ YEARLY CLAIM PROCESS ─────────────────────────────────────────────────────┐
│                                                                             │
│  PURPOSE: Reconcile all quarterly claims with auditor-verified records     │
│                                                                             │
│  ┌─ YEARLY CLAIM WORKFLOW ──────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  1. SUBMISSION                                                        │  │
│  │     ├── DUSP submits Yearly Claim                                     │  │
│  │     ├── Attaches Auditors' Declaration                                │  │
│  │     ├── Includes Auditors' Working Template                           │  │
│  │     └── References all quarterly claims for the year                  │  │
│  │                                                                       │  │
│  │  2. AUDITOR VERIFICATION                                              │  │
│  │     ├── Independent auditor review                                    │  │
│  │     ├── Verification against supporting documents                     │  │
│  │     ├── Confirmation of claim amounts                                 │  │
│  │     └── Auditor's Declaration signed                                  │  │
│  │                                                                       │  │
│  │  3. EOT PROCESSING (if applicable)                                    │  │
│  │     ├── Identify projects with EOT                                    │  │
│  │     ├── Generate official EOT letters                                 │  │
│  │     ├── Link to bond extensions                                       │  │
│  │     └── Update project timelines                                      │  │
│  │                                                                       │  │
│  │  4. MCMC REVIEW                                                       │  │
│  │     ├── Finance team reconciliation                                   │  │
│  │     ├── Comparison with USPFS records                                 │  │
│  │     ├── Variance analysis                                             │  │
│  │     └── Final approval                                                │  │
│  │                                                                       │  │
│  │  5. PAYMENT PROCESSING                                                │  │
│  │     ├── Balance settlement calculation                                │  │
│  │     ├── Final payment or recovery                                     │  │
│  │     └── Year closure in system                                        │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Yearly Claim Template Structure

```
┌─ YEARLY CLAIM TEMPLATE (AUDITOR WORKING PAPER) ────────────────────────────┐
│                                                                             │
│  PROJECT: _________________________  YEAR: _______  DUSP: _______________  │
│                                                                             │
│  ┌─ SECTION A: QUARTERLY CLAIMS SUMMARY ────────────────────────────────┐  │
│  │                                                                       │  │
│  │  Quarter │ Claim ID      │ Amount (RM) │ Status    │ Auditor Check   │  │
│  │  ────────┼───────────────┼─────────────┼───────────┼─────────────────│  │
│  │  Q1      │ CLAIM-Q1-XXX  │ 3,450,000   │ Approved  │ ✓ Verified      │  │
│  │  Q2      │ CLAIM-Q2-XXX  │ 4,200,000   │ Approved  │ ✓ Verified      │  │
│  │  Q3      │ CLAIM-Q3-XXX  │ 3,800,000   │ Approved  │ ✓ Verified      │  │
│  │  Q4      │ CLAIM-Q4-XXX  │ 4,500,000   │ Approved  │ ✓ Verified      │  │
│  │  ────────┼───────────────┼─────────────┼───────────┼─────────────────│  │
│  │  TOTAL   │               │ 15,950,000  │           │ ✓ Match         │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌─ SECTION B: AUDIT VERIFICATION ──────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  ☑ Supporting invoices verified against claim amounts                │  │
│  │  ☑ Payment receipts confirmed                                         │  │
│  │  ☑ Physical progress validated                                        │  │
│  │  ☑ BOQ compliance checked                                             │  │
│  │  ☑ Budget allocation confirmed                                        │  │
│  │                                                                       │  │
│  │  Exceptions/Notes: ________________________________________________  │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌─ SECTION C: AUDITOR DECLARATION ─────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  We have reviewed the yearly claim submission and confirm that the    │  │
│  │  amounts claimed are accurate and supported by appropriate            │  │
│  │  documentation.                                                       │  │
│  │                                                                       │  │
│  │  Auditor Name: __________________  Signature: __________________      │  │
│  │  Firm: ___________________________  Date: ______________________      │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 6. CLAIM TRACKING & MONITORING

### 6.1 Claim Status Dashboard

```
┌─ CLAIM STATUS DASHBOARD ───────────────────────────────────────────────────┐
│                                                                             │
│  OVERVIEW (All Projects)                                                    │
│  ├── Total Claims: 156                                                      │
│  ├── Pending Submission: 12                                                 │
│  ├── Under Review: 23                                                       │
│  ├── Approved (Pending Payment): 8                                          │
│  ├── Paid: 108                                                              │
│  └── Rejected/Returned: 5                                                   │
│                                                                             │
│  ┌─ CLAIMS BY STATUS ───────────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  🟡 Pending Submission │████░░░░░░░░░░░░│ 12 (8%)                    │  │
│  │  🔵 Under Validation   │████████░░░░░░░│ 23 (15%)                   │  │
│  │  🟠 Under Review       │██████░░░░░░░░░│ 18 (12%)                   │  │
│  │  🟢 Approved           │██░░░░░░░░░░░░░│ 8 (5%)                     │  │
│  │  💰 Paid              │████████████████│ 108 (69%)                  │  │
│  │  🔴 Rejected          │█░░░░░░░░░░░░░░│ 5 (3%)                     │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [🔍 Advanced Search]  [📤 Export Report]  [📊 Analytics]                   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Automated Notifications

| Trigger | Recipient | Notification Type | Timing |
|---------|-----------|-------------------|--------|
| Claim Submitted | DUSP Admin | Email | Immediate |
| Validation Failed | DUSP Submitter | Email + In-app | Immediate |
| Approval Required | Approver | Email + In-app | Immediate |
| Claim Approved | DUSP Admin | Email | Immediate |
| Payment Processed | DUSP Admin | Email + SMS | Immediate |
| Query Raised | DUSP Submitter | Email + In-app | Immediate |
| Deadline Approaching | DUSP Submitter | Email | 3 days before |

---

**END OF ANNEX T20**
