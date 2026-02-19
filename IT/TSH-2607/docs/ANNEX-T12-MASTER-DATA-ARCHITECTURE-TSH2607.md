# ANNEX-T12-MASTER-DATA-ARCHITECTURE-TSH2607.md

# ANNEX T12: MASTER DATA ARCHITECTURE
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T12  
**Version:** 1.0  
**Date:** February 2026  

---

## 1. MASTER DATA MODEL

### 1.1 Master Data Entities

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                         MASTER DATA ENTITY RELATIONSHIPS                                 │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│   ┌─────────────┐                                                                          │
│   │   DUSP      │                                                                          │
│   │  (Company)  │                                                                          │
│   │             │                                                                          │
│   │ • DUSP_ID   │                                                                          │
│   │ • Company   │                                                                          │
│   │   Name      │                                                                          │
│   │ • SSM No    │                                                                          │
│   │ • Bank Info │                                                                          │
│   └──────┬──────┘                                                                          │
│          │                                                                                 │
│          │ 1:N                                                                              │
│          ▼                                                                                 │
│   ┌─────────────┐       ┌─────────────┐       ┌─────────────┐                             │
│   │   PROJECT   │◄─────►│    NOA      │       │    VO       │                             │
│   │             │  1:N  │  (Notice of │       │ (Variation  │                             │
│   │ • Project_ID│       │  Award)     │       │  Order)     │                             │
│   │ • DUSP_ID   │       │             │       │             │                             │
│   │ • Name      │       │ • NOA_ID    │       │ • VO_ID     │                             │
│   │ • Capped    │       │ • NOA_Ref   │       │ • VO_Ref    │                             │
│   │   Cost      │       │ • NOA_Date  │       │ • VO_Date   │                             │
│   │ • Status    │       │ • Amount    │       │ • Amount    │                             │
│   └──────┬──────┘       └─────────────┘       └─────────────┘                             │
│          │                                                                                 │
│          │ 1:N                                                                              │
│          ▼                                                                                 │
│   ┌─────────────┐       ┌─────────────┐       ┌─────────────┐                             │
│   │   CLUSTER   │       │    SITE     │       │    ITEM     │                             │
│   │             │       │             │       │             │                             │
│   │ • Cluster_ID│       │ • Site_ID   │       │ • Item_ID   │                             │
│   │ • Project_ID│       │ • Cluster_ID│       │ • Project_ID│                             │
│   │ • Name      │       │ • Site_Name │       │ • Item_Code │                             │
│   └─────────────┘       │ • Location  │       │ • Cost      │                             │
│                         └─────────────┘       └─────────────┘                             │
│                                                                                            │
│   ┌─────────────┐       ┌─────────────┐       ┌─────────────┐                             │
│   │     EOT     │       │    BOND     │       │   CONTRACT  │                             │
│   │  (Extension │       │  (Performance│       │             │                             │
│   │   of Time)  │       │   Bond)     │       │ • Contract_ │                             │
│   │             │       │             │       │   ID        │                             │
│   │ • EOT_ID    │       │ • Bond_ID   │       │ • Contract  │                             │
│   │ • Project_ID│       │ • Project_ID│       │   Value     │                             │
│   │ • EOT_Days  │       │ • Amount    │       │ • Start_Date│                             │
│   └─────────────┘       │ • Expiry    │       │ • End_Date  │                             │
│                         └─────────────┘       └─────────────┘                             │
│                                                                                            │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Entity Definitions

| Entity | Description | Key Attributes | Relationships |
|--------|-------------|----------------|---------------|
| **DUSP** | Designated Universal Service Provider | DUSP_ID, Company_Name, SSM_Number, Bank_Account | 1:N with Projects |
| **PROJECT** | USP Project | Project_ID, Project_Name, Capped_Cost, Status | N:1 with DUSP, 1:N with Clusters |
| **NOA** | Notice of Award | NOA_ID, NOA_Reference, Award_Date, Amount | N:1 with Project |
| **VO** | Variation Order | VO_ID, VO_Reference, VO_Date, Amount, Type | N:1 with Project |
| **CLUSTER** | Project Cluster | Cluster_ID, Cluster_Name, Project_ID | N:1 with Project, 1:N with Sites |
| **SITE** | Project Site | Site_ID, Site_Name, Location, Cluster_ID | N:1 with Cluster |
| **ITEM** | Billable Item | Item_ID, Item_Code, Description, Unit_Cost | N:1 with Project |
| **BOND** | Performance Bond | Bond_ID, Bond_Amount, Issue_Date, Expiry_Date | N:1 with Project |
| **EOT** | Extension of Time | EOT_ID, EOT_Reference, Days_Requested, Status | N:1 with Project |
| **CONTRACT** | Project Contract | Contract_ID, Contract_Value, Start_Date, End_Date | 1:1 with Project |

---

## 2. DATA GOVERNANCE

### 2.1 Master Data Stewardship

| Entity | Data Owner | Data Steward | Approval Workflow |
|--------|-----------|--------------|-------------------|
| DUSP | Finance Director | Finance Manager | Create: Auto; Modify: L2 Approval |
| PROJECT | USP Director | USP Manager | Create: L2 Approval; Modify: L2 Approval |
| NOA | Contract Manager | USP Officer | Create: L1 Approval |
| VO | USP Director | USP Manager | Create: L2 Approval |
| BOND | Finance Director | Finance Manager | Create: L1 Approval |
| EOT | USP Director | USP Manager | Create: L2 Approval |

### 2.2 Data Quality Rules

| Entity | Validation Rule | Error Action |
|--------|-----------------|--------------|
| DUSP | SSM number must be valid format | Block creation |
| PROJECT | Capped cost must be > 0 | Block creation |
| NOA | NOA date cannot be future | Warning |
| VO | VO amount + Capped cost must be within budget limit | L3 Approval required |
| BOND | Expiry date must be > Contract end date | Warning |
| EOT | EOT days must be > 0 | Block creation |

---

**END OF ANNEX T12**
