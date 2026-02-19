# ANNEX-T17-USER-MANAGEMENT-TSH2607.md

# ANNEX T17: USER MANAGEMENT MODULE
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T17  
**Version:** 1.0  
**Date:** February 2026  

---

## USER MANAGEMENT ARCHITECTURE

### User Types

| User Type | Count | Access Level | Authentication |
|-----------|-------|--------------|----------------|
| MCMC Admin | 5 | Full system access | Azure AD + MFA |
| MCMC Staff | 55 | Module-specific access | Azure AD + MFA |
| DUSP Users | 120 | Project-specific access | Azure AD + MFA |
| Subcontractors | 50 | View-only access | Username/Password + MFA |
| Auditors | 10 | Read-only reports | Azure AD + MFA |

### User Lifecycle

```
┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐
│  Create  │──►│  Approve │──►│ Activate │──►│ Maintain │──►│Deactivate│
│  Request │   │  (L2)    │   │  Account │   │  Access  │   │  Account │
└──────────┘   └──────────┘   └──────────┘   └──────────┘   └──────────┘
                                                                  │
                                                                  ▼
                                                            ┌──────────┐
                                                            │ Archive  │
                                                            └──────────┘
```

---

**END OF ANNEX T17**
