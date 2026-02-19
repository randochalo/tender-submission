# ANNEX-T22-PAYMENT-WORKFLOW-TSH2607.md

# ANNEX T22: PAYMENT WORKFLOW
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T22  
**Version:** 1.0  
**Date:** February 2026  

---

## PAYMENT AUTHORIZATION WORKFLOW

```
Claim Approved
      │
      ▼
[Generate Payment Memo]
      │
      ▼
[Route for Digital Signatures]
      │
      ├── Level 1 Signature
      ├── Level 2 Signature
      └── Level 3 Signature (with Digital Certificate)
      │
      ▼
[All Signatures Complete?]
      │
      Yes
      │
      ▼
[Create Voucher in USPFS]
      │
      ▼
[Update Payment Status]
      │
      ▼
[Generate DUSP Notification Letter]
      │
      ▼
[Send Payment Advice]
      │
      ▼
[Record in Audit Trail]
```

---

**END OF ANNEX T22**
