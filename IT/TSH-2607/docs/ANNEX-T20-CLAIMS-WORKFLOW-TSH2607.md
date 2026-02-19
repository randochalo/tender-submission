# ANNEX-T20-CLAIMS-WORKFLOW-TSH2607.md

# ANNEX T20: CLAIMS WORKFLOW
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T20  
**Version:** 1.0  
**Date:** February 2026  

---

## CLAIM TYPES

| Claim Type | Frequency | Key Documents | Approval Levels |
|------------|-----------|---------------|-----------------|
| Advance | One-time at project start | CEO Declaration | L1, L2, L3 |
| Quarterly | Every 3 months | Progress Report, Invoices, CEO Declaration | L1, L2, L3 |
| Yearly | Annual | Auditor Report, Financial Statements, CEO Declaration | L1, L2, L3 |

## CLAIM WORKFLOW

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         CLAIM PROCESSING WORKFLOW                                        │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  DUSP                    UCMS SYSTEM                      MCMC APPROVERS                 │
│    │                         │                                │                          │
│    │ Submit Claim            │                                │                          │
│    │────────────────────────►│                                │                          │
│    │                         │ Validate Claim                 │                          │
│    │                         │ (Budget, Documents)            │                          │
│    │                         │        │                       │                          │
│    │    ◄────────────────────│ Valid  │                       │                          │
│    │    Confirmation         │        │                       │                          │
│    │                         │        ▼                       │                          │
│    │                         │ Route to L1 Approver           │                          │
│    │                         │───────────────────────────────►│                          │
│    │                         │                                │ Review                   │
│    │                         │◄───────────────────────────────│ Approve/Reject/Return    │
│    │                         │        │                       │                          │
│    │    ◄────────────────────┘      Reject ──► [Notify DUSP] │                          │
│    │    Rejection                      │                       │                          │
│    │                                   │                      │                          │
│    │                         Approve   │                       │                          │
│    │                         │         │                       │                          │
│    │                         │ Route to L2 Approver            │                          │
│    │                         │───────────────────────────────►│                          │
│    │                         │                                │ (Similar to L1)          │
│    │                         │◄───────────────────────────────│                          │
│    │                         │                                │                          │
│    │                         │ Route to L3 Approver            │                          │
│    │                         │───────────────────────────────►│                          │
│    │                         │                                │ (Similar + Digital Sig)  │
│    │                         │◄───────────────────────────────│                          │
│    │                         │                                │                          │
│    │    ◄────────────────────┐ Approve ──► [Payment Workflow]│                          │
│    │    Approval Notice      │                                │                          │
│    │                         │                                │                          │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

**END OF ANNEX T20**
