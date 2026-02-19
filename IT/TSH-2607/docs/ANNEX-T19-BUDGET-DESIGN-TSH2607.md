# ANNEX-T19: Budget Module Design
## TSH-2607 MCMC UCMS Tender

**Document Reference:** TSH-2607-ANNEX-T19  
**Date:** February 2026  
**Version:** 1.0

---

## 1. OVERVIEW

### 1.1 Purpose
This annex describes the Budget Management Module design for UCMS, including financial controls, capped cost tracking, Bill of Quantity (BOQ) management, and cost component allocation.

### 1.2 Key Features

| Feature | Description |
|---------|-------------|
| Capped Cost Tracking | Monitor approved budget vs. actual expenditure |
| BOQ Management | Itemized quantity and cost breakdown |
| Cost Component Allocation | Preliminaries, CME, Software, Shared costs |
| Variance Monitoring | Automated alerts for budget deviations |
| USPFS Integration | Real-time sync with Oracle EBS |
| Multi-level Approval | Workflow-governed budget changes |

---

## 2. BUDGET MODULE ARCHITECTURE

### 2.1 System Context

```
┌─────────────────────────────────────────────────────────────────────────┐
│                           BUDGET MODULE                                  │
│                                                                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐ │
│  │ Capped Cost  │  │     BOQ      │  │   Cost Comp  │  │   Variance   │ │
│  │  Management  │  │  Management  │  │  Allocation  │  │   Analysis   │ │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘ │
│         │                 │                 │                 │         │
│         └─────────────────┴─────────────────┴─────────────────┘         │
│                                  │                                       │
│                         ┌────────┴────────┐                             │
│                         │ Budget Engine   │                             │
│                         │ (Rules + Logic) │                             │
│                         └────────┬────────┘                             │
│                                  │                                       │
│         ┌────────────────────────┼────────────────────────┐             │
│         ▼                        ▼                        ▼             │
│  ┌──────────────┐        ┌──────────────┐        ┌──────────────┐      │
│  │    USPFS     │        │  Claims Mod  │        │   Reports    │      │
│  │  (Oracle)    │◀──────▶│  (Validate)  │◀──────▶│  & Dashboard │      │
│  └──────────────┘        └──────────────┘        └──────────────┘      │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Data Model

```
┌─ BUDGET DATA STRUCTURE ─────────────────────────────────────────────────┐
│                                                                          │
│  PROJECT BUDGET                                                          │
│  ├── Project ID (FK to Master Data)                                     │
│  ├── Approved Capped Cost (RM)                                          │
│  ├── Financial Year                                                     │
│  ├── Status (Active/Closed/Frozen)                                      │
│  └── Created/Modified timestamps                                        │
│                                                                          │
│  ├── BILL OF QUANTITY (BOQ)                                              │
│  │   ├── BOQ ID                                                         │
│  │   ├── Item Code                                                      │
│  │   ├── Item Description                                               │
│  │   ├── Unit of Measure                                                │
│  │   ├── Quantity                                                       │
│  │   ├── Unit Price (RM)                                                │
│  │   ├── Total Amount (RM)                                              │
│  │   └── Cost Component (Category)                                      │
│  │                                                                      │
│  ├── COST COMPONENTS                                                     │
│  │   ├── Preliminaries                                                  │
│  │   ├── CME Works                                                       │
│  │   ├── Software Cost                                                   │
│  │   ├── Shared Cost                                                     │
│  │   └── Contingency                                                    │
│  │                                                                      │
│  └── BUDGET TRANSACTIONS                                                 │
│      ├── Transaction ID                                                 │
│      ├── Type (Allocation/Utilization/Adjustment)                       │
│      ├── Amount                                                         │
│      ├── Reference (Claim ID/VO ID)                                     │
│      └── Timestamp                                                      │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

---

## 3. BUDGET SCREEN DESIGN

### 3.1 Budget Overview Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  BUDGET MANAGEMENT                                  MCMC UCMS v1.0          │
├─────────────────────────────────────────────────────────────────────────────┤
│  Project: [Project A - USP Broadband Deployment ▼]    FY: [2026 ▼]         │
│  DUSP: Telekom Malaysia Berhad                                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─ BUDGET SUMMARY ──────────────────────────────────────────────────────┐  │
│  │                                                                       │  │
│  │  Approved Capped Cost:        RM 45,000,000.00                        │  │
│  │  Total Committed:             RM 32,450,000.00   [███████░░░] 72%     │  │
│  │  Total Claimed:               RM 28,230,000.00   [██████░░░░] 63%     │  │
│  │  Total Paid:                  RM 25,400,000.00   [█████░░░░░] 56%     │  │
│  │  Remaining Budget:            RM 19,600,000.00   [████░░░░░░] 44%     │  │
│  │                                                                       │  │
│  │  Status: 🟢 HEALTHY  (Remaining > 20% threshold)                      │  │
│  │                                                                       │  │
│  │  [View Details]  [Export Report]  [Budget Timeline]                   │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌─ COST BREAKDOWN ─────────────────────────┐  ┌─ VARIANCE ALERTS ───────┐ │
│  │                                           │  │                          │ │
│  │  Preliminaries    RM 4.5M  [10%]  ████  │  │  🟡 VO-2026-0045       │ │
│  │  CME Works       RM 31.5M  [70%]  ██████│  │     +RM 1.2M pending   │ │
│  │  Software         RM 4.5M  [10%]  ████  │  │                          │ │
│  │  Shared Cost      RM 2.25M  [5%]  ██    │  │  🟢 No overspend alerts │ │
│  │  Contingency     RM 2.25M  [5%]  ██    │  │                          │ │
│  │                                           │  │  [View All Alerts]     │ │
│  │  [View BOQ Details]                       │  │                          │ │
│  │                                           │  └──────────────────────────┘ │
│  └───────────────────────────────────────────┘                               │
│                                                                             │
│  [💾 Save]  [🔄 Refresh from USPFS]  [📊 Generate Report]                   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 BOQ Management Screen

```
┌─ BILL OF QUANTITY (BOQ) ───────────────────────────────────────────────────┐
│                                                                             │
│  Project: Project A - USP Broadband Deployment                             │
│  Total BOQ Value: RM 42,750,000.00                                         │
│                                                                             │
│  Item │ Description          │ UOM  │ Qty  │ Unit Price │ Total      │ %  │
│  ─────┼──────────────────────┼──────┼──────┼────────────┼────────────┼────│
│  1.1  │ Site Preparation     │ Lot  │ 150  │ RM 15,000  │ RM 2.25M   │ 5% │
│  1.2  │ Fiber Cable (SM)     │ km   │ 500  │ RM 12,000  │ RM 6.00M   │14% │
│  1.3  │ Duct Installation    │ km   │ 500  │ RM 8,000   │ RM 4.00M   │ 9% │
│  1.4  │ Handhole Construction│ each │ 200  │ RM 5,000   │ RM 1.00M   │ 2% │
│  2.1  │ OLT Equipment        │ set  │ 10   │ RM 250,000 │ RM 2.50M   │ 6% │
│  2.2  │ ONT/CPE Devices      │ unit │ 5000 │ RM 800     │ RM 4.00M   │ 9% │
│  ...  │ ...                  │ ...  │ ...  │ ...        │ ...        │... │
│                                                                             │
│  Cost Component Filter: [All ▼]  [Preliminaries] [CME] [Software] [Shared]│
│                                                                             │
│  [+ Add BOQ Item]  [✏️ Edit]  [❌ Remove]  [📥 Import Excel]  [📤 Export]   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. FINANCIAL CONTROL MECHANISMS

### 4.1 Budget Validation Rules

```python
# Budget Validation Pseudocode

def validate_claim_against_budget(claim):
    """
    Validates if claim can be processed within budget constraints
    """
    project_budget = get_budget(claim.project_id)
    
    # Rule 1: Claim amount must not exceed remaining capped cost
    if claim.amount > project_budget.remaining:
        raise BudgetExceededError(
            f"Claim {claim.id} exceeds remaining budget"
        )
    
    # Rule 2: Physical progress vs financial progress variance check
    if claim.physical_progress < claim.financial_progress - 10%:
        raise VarianceWarning(
            "Financial progress exceeds physical progress by > 10%"
        )
    
    # Rule 3: BOQ item validation
    for item in claim.boq_items:
        boq_remaining = get_boq_remaining(item.boq_id)
        if item.quantity > boq_remaining:
            raise BOQExceededError(
                f"BOQ item {item.code} quantity exceeded"
            )
    
    # Rule 4: Cost component allocation check
    component_totals = calculate_component_totals(claim)
    for component, amount in component_totals.items():
        remaining = get_component_budget_remaining(component)
        if amount > remaining:
            raise ComponentBudgetError(
                f"{component} budget exceeded"
            )
    
    return ValidationResult.PASSED
```

### 4.2 Alert Thresholds

| Threshold Level | Trigger | Notification | Action Required |
|-----------------|---------|--------------|-----------------|
| 🟢 Normal | < 70% utilized | None | Continue monitoring |
| 🟡 Caution | 70-85% utilized | Email to PM | Review spend rate |
| 🟠 Warning | 85-95% utilized | Email + In-app | Budget review meeting |
| 🔴 Critical | > 95% utilized | Email + SMS | Immediate approval required |
| 🚨 Breach | > 100% utilized | Escalation | Director approval + VO required |

### 4.3 Budget vs Actual Comparison

```
┌─ BUDGET UTILIZATION REPORT ────────────────────────────────────────────────┐
│                                                                             │
│  Project: Project A                    Period: Jan 2026 - Feb 2026         │
│                                                                             │
│  Category      │ Budget        │ Actual        │ Variance    │ % Used     │
│  ──────────────┼───────────────┼───────────────┼─────────────┼────────────│
│  Preliminaries │ RM 4,500,000  │ RM 3,200,000  │ RM 1.3M ↓   │ 71% 🟢     │
│  CME Works     │ RM 31,500,000 │ RM 22,100,000 │ RM 9.4M ↓   │ 70% 🟢     │
│  Software      │ RM 4,500,000  │ RM 4,800,000  │ RM 0.3M ↑   │ 107% 🔴    │
│  Shared Cost   │ RM 2,250,000  │ RM 1,800,000  │ RM 0.45M ↓  │ 80% 🟡     │
│  Contingency   │ RM 2,250,000  │ RM 0,000,000  │ RM 2.25M ↓  │ 0% 🟢      │
│  ──────────────┼───────────────┼───────────────┼─────────────┼────────────│
│  TOTAL         │ RM 45,000,000 │ RM 31,900,000 │ RM 13.1M ↓  │ 71% 🟢     │
│                                                                             │
│  [Drill Down]  [View Claims]  [Export PDF]  [Schedule Review]             │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 5. USPFS INTEGRATION

### 5.1 Data Synchronization

| Data Element | Direction | Frequency | Method |
|--------------|-----------|-----------|--------|
| Approved Capped Cost | USPFS → UCMS | Real-time | API Push |
| Budget Adjustments | USPFS → UCMS | Real-time | API Push |
| Claim Validation | UCMS → USPFS | On-demand | API Query |
| Payment Posting | USPFS → UCMS | Real-time | API Callback |
| Budget Status | Bidirectional | Hourly | Batch Sync |

### 5.2 API Integration Flow

```
┌─ BUDGET VALIDATION FLOW ───────────────────────────────────────────────────┐
│                                                                             │
│  UCMS                              USPFS API                              │
│   │                                     │                                   │
│   │  1. Validate Claim Against Budget   │                                   │
│   │ ──────────────────────────────────▶ │                                   │
│   │     {claim_id, amount, project_id}  │                                   │
│   │                                     │                                   │
│   │  2. Query Approved Capped Cost      │                                   │
│   │ ──────────────────────────────────▶ │                                   │
│   │                                     │  3. Query Oracle EBS              │
│   │                                     │ ─────────────────▶               │
│   │                                     │                                   │
│   │                                     │  4. Return Budget Data            │
│   │                                     │ ◀────────────────                │
│   │                                     │                                   │
│   │  5. Return Validation Result        │                                   │
│   │ ◀────────────────────────────────── │                                   │
│   │     {valid: true/false,             │                                   │
│   │      remaining_budget,              │                                   │
│   │      validation_rules_passed}       │                                   │
│   │                                     │                                   │
│   ▼                                     ▼                                   │
│  Proceed/Reject Claim                                                     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 6. VARIATION ORDER (VO) IMPACT

### 6.1 VO Processing Workflow

```
┌─ VO IMPACT ON BUDGET ──────────────────────────────────────────────────────┐
│                                                                             │
│  1. VO Request Received                                                     │
│     ├── Scope Change Description                                           │
│     ├── Cost Impact: +RM 1,200,000                                         │
│     └── Timeline Impact: +3 months                                         │
│                                                                             │
│  2. Budget Impact Analysis                                                  │
│     ├── Current Capped Cost: RM 45,000,000                                 │
│     ├── Proposed New Capped Cost: RM 46,200,000                            │
│     ├── Contingency Available: RM 2,250,000                                │
│     └── Decision: Use Contingency + Request Budget Increase                │
│                                                                             │
│  3. Approval Workflow                                                       │
│     ├── PM Review: ✓ Approved                                              │
│     ├── Finance Review: ✓ Approved                                         │
│     ├── USP Director: ⏳ Pending                                            │
│     └── MCMC Approval: ⏳ Pending                                           │
│                                                                             │
│  4. Budget Update (Upon Approval)                                           │
│     ├── UCMS Budget Updated                                                │
│     ├── USPFS Budget Updated                                               │
│     ├── BOQ Adjustments Applied                                            │
│     └── Stakeholders Notified                                              │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

**END OF ANNEX T19**
