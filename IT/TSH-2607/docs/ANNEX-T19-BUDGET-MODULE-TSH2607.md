# ANNEX-T19-BUDGET-MODULE-TSH2607.md

# ANNEX T19: BUDGET MODULE DESIGN
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T19  
**Version:** 1.0  
**Date:** February 2026  

---

## BUDGET MODULE ARCHITECTURE

### Budget Hierarchy

```
Program Budget (USP Fund)
    └── Project Budget (Capped Cost)
            ├── Site Budget
            │       └── Item Budget
            └── Variation Order (VO) Adjustments
```

### Budget Components

| Component | Description | Source |
|-----------|-------------|--------|
| Approved Capped Cost | Maximum project allocation | NOA |
| Site Costing | Budget per site | Project breakdown |
| BOQ | Bill of Quantities | Contract documents |
| Cost Components | Preliminaries, CME, Software, Shared | Cost structure |
| VO Adjustments | Approved variations | VO documents |

### Budget Validation

```
Claim Submission
      │
      ▼
[Check Against Capped Cost]
      │
      ├── Available ──► [Proceed with Claim]
      │
      └── Exceeded ──► [Block Submission]
              │
              ▼
        [Check for Approved VO]
              │
              ├── VO Exists ──► [Recalculate with VO]
              │
              └── No VO ──► [Error: Budget Exceeded]
```

---

**END OF ANNEX T19**
