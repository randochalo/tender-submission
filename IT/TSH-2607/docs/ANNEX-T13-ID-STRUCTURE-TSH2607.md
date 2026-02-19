# ANNEX-T13-ID-STRUCTURE-TSH2607.md

# ANNEX T13: ID STRUCTURE DIAGRAM
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T13  
**Version:** 1.0  
**Date:** February 2026  

---

## ID HIERARCHY STRUCTURE

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         UCMS IDENTIFIER HIERARCHY                                        │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  LEVEL 1: PROGRAM                                                                        │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  USP-YYYY-NNN  (e.g., USP-2026-001)                                              │   │
│  │  • USP = Universal Service Provision                                            │   │
│  │  • YYYY = Year approved                                                         │   │
│  │  • NNN = Sequential number                                                      │   │
│  └──────────────────────────┬──────────────────────────────────────────────────────┘   │
│                             │                                                            │
│                             │ 1:N                                                        │
│                             ▼                                                            │
│  LEVEL 2: PROJECT/CONTRACT                                                               │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  USP-YYYY-NNN-SS  (e.g., USP-2026-001-01)                                        │   │
│  │  • SS = Sub-project / Contract sequence                                         │   │
│  └──────────────────────────┬──────────────────────────────────────────────────────┘   │
│                             │                                                            │
│                             │ 1:N                                                        │
│                             ▼                                                            │
│  LEVEL 3: CLUSTER                                                                        │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  CL-NNNN  (e.g., CL-0001)                                                        │   │
│  │  • CL = Cluster                                                                  │   │
│  │  • NNNN = Sequential within program                                             │   │
│  └──────────────────────────┬──────────────────────────────────────────────────────┘   │
│                             │                                                            │
│                             │ 1:N                                                        │
│                             ▼                                                            │
│  LEVEL 4: SITE                                                                           │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  ST-NNNN  (e.g., ST-0001)                                                        │   │
│  │  • ST = Site                                                                     │   │
│  │  • NNNN = Sequential within cluster                                             │   │
│  └──────────────────────────┬──────────────────────────────────────────────────────┘   │
│                             │                                                            │
│                             │ 1:N                                                        │
│                             ▼                                                            │
│  LEVEL 5: ITEM                                                                           │
│  ┌─────────────────────────────────────────────────────────────────────────────────┐   │
│  │  IT-NNNN  (e.g., IT-0001)                                                        │   │
│  │  • IT = Item                                                                     │   │
│  │  • NNNN = Sequential within site                                                │   │
│  └─────────────────────────────────────────────────────────────────────────────────┘   │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

## TRANSACTION ID FORMATS

| Entity | ID Format | Example | Description |
|--------|-----------|---------|-------------|
| **Project** | USP-YYYY-NNN | USP-2026-001 | Main project identifier |
| **NOA** | NOA-YYYY-NNNN | NOA-2026-0001 | Notice of Award |
| **VO** | VO-YYYY-NNNN | VO-2026-0001 | Variation Order |
| **EOT** | EOT-YYYY-NNNN | EOT-2026-0001 | Extension of Time |
| **Claim** | CLM-YYYY-NNNNNN | CLM-2026-000001 | Claim submission |
| **Payment** | PAY-YYYY-NNNNNN | PAY-2026-000001 | Payment record |
| **Voucher** | VCH-YYYY-NNNNNN | VCH-2026-000001 | USPFS voucher |
| **Bond** | BND-YYYY-NNNN | BND-2026-0001 | Performance bond |
| **Cluster** | CL-NNNN | CL-0001 | Project cluster |
| **Site** | ST-NNNN | ST-0001 | Implementation site |
| **Item** | IT-NNNN | IT-0001 | Billable item |

---

**END OF ANNEX T13**
