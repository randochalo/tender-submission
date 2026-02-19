# ANNEX-T15-VO-PROCESS-TSH2607.md

# ANNEX T15: VARIATION ORDER (VO) PROCESS FLOW
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T15  
**Version:** 1.0  
**Date:** February 2026  

---

## VO PROCESS FLOW

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    VARIATION ORDER PROCESS FLOW                                          │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │                                                                                  │   │
│  │  VO REQUEST IDENTIFIED                                                           │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  [Create VO Request]                                                             │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  {VO Type?}                                                                      │   │
│  │       │                                                                          │   │
│  │   ┌───┴───┬───────────┐                                                          │   │
│  │   ▼       ▼           ▼                                                          │   │
│  │ Scope   Cost      Time (EOT)                                                     │   │
│  │ Change  Change    Extension                                                      │   │
│  │   │       │           │                                                          │   │
│  │   ▼       ▼           ▼                                                          │   │
│  │ [Validate ───────────────────────►                                               │   │
│  │  Impact]                                                                         │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  {Within                                                         │   │
│  │   Authority?}                                                                    │   │
│  │       │                                                                          │   │
│  │   No  │  Yes                                                                     │   │
│  │       │                                                                          │   │
│  │       ▼                                                                          │   │
│  │  [Higher        [Level 2                                                         │   │
│  │   Authority      Approval]                                                       │   │
│  │   Required]          │                                                           │   │
│  │       │              │                                                           │   │
│  │       └──────────────┤                                                           │   │
│  │                      ▼                                                           │   │
│  │              [Update Budget]                                                     │   │
│  │                      │                                                           │   │
│  │                      ▼                                                           │   │
│  │              [Update USPFS]                                                      │   │
│  │                      │                                                           │   │
│  │                      ▼                                                           │   │
│  │              [Notify Stakeholders]                                               │   │
│  │                      │                                                           │   │
│  │                      ▼                                                           │   │
│  │                   (END)                                                          │   │
│  │                                                                                  │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
│  VO Authority Limits:                                                                    │
│  • Level 1 (Manager): Up to RM 50,000                                                   │
│  • Level 2 (Director): Up to RM 500,000                                                 │
│  • Level 3 (Board): Above RM 500,000                                                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

**END OF ANNEX T15**
