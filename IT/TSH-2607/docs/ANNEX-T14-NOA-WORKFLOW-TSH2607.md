# ANNEX-T14-NOA-WORKFLOW-TSH2607.md

# ANNEX T14: NOA WORKFLOW
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T14  
**Version:** 1.0  
**Date:** February 2026  

---

## NOA (NOTICE OF AWARD) WORKFLOW

### NOA Recording Process

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         NOA RECORDING WORKFLOW                                           │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐               │
│  │ Receive  │──►│ Validate │──►│ Create   │──►│ Link to  │──►│ Update   │               │
│  │ NOA      │   │ NOA      │   │ NOA      │   │ Project  │   │ USPFS    │               │
│  │ Document │   │ Details  │   │ Record   │   │          │   │          │               │
│  └──────────┘   └──────────┘   └──────────┘   └──────────┘   └──────────┘               │
│       │             │              │              │              │                       │
│       ▼             ▼              ▼              ▼              ▼                       │
│    MCMC Staff    System Check   Auto-number   Associate      Sync data                   │
│    receives      against        NOA_ID        with Project   with Oracle                 │
│    NOA from      USPFS                                         EBS                       │
│    Procurement                                                                              │
│                                                                                            │
│  NOA Data Captured:                                                                      │
│  • NOA Reference Number                                                                  │
│  • NOA Date                                                                              │
│  • Award Amount                                                                          │
│  • Contract Period                                                                       │
│  • DUSP Information                                                                      │
│  • Performance Bond Requirements                                                         │
│  • Milestone Schedule                                                                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### NOA Validation Rules

| Field | Validation | Action on Failure |
|-------|------------|-------------------|
| NOA Reference | Must be unique | Error message |
| NOA Date | Cannot be future | Warning |
| Award Amount | Must match USPFS | Reconciliation required |
| DUSP ID | Must exist in master | Block creation |
| Project ID | Auto-assigned or selected | - |

---

**END OF ANNEX T14**
