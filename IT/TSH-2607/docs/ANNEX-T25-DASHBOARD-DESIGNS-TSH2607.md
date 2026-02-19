# ANNEX T25: DASHBOARD DESIGNS

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the dashboard designs for the USP Claims Management System, providing interactive visual interfaces for monitoring, analysis, and decision-making across all user roles.

### 1.1 KRISA Compliance
- **KRISA Section 12**: Digital service delivery interfaces
- **MCMC Design Guidelines**: Corporate visual standards
- **Accessibility Standards**: WCAG 2.1 Level AA compliance

---

## 2. DASHBOARD ARCHITECTURE

### 2.1 Dashboard Categories

| Category | Target Users | Purpose | Count |
|----------|--------------|---------|-------|
| Executive | CEO, Directors, Board | Strategic oversight | 3 |
| Operational | Managers, Team Leads | Process monitoring | 5 |
| Functional | Specialists, Analysts | Detailed analysis | 8 |
| Self-Service | Service Providers | Claim tracking | 2 |
| Public | General public | Transparency | 1 |

### 2.2 Technical Specifications

| Specification | Requirement |
|---------------|-------------|
| Platform | Oracle Analytics Cloud (OAC) |
| Framework | Oracle DV (Data Visualization) |
| Responsive | Desktop, Tablet, Mobile |
| Refresh Rate | Real-time to Hourly (configurable) |
| Export | PDF, PNG, Excel, CSV |
| Interactivity | Drill-down, Filter, Zoom |
| Accessibility | WCAG 2.1 Level AA |

---

## 3. EXECUTIVE DASHBOARDS

### 3.1 Executive Summary Dashboard

#### Purpose
High-level overview of USP program performance for C-suite executives.

#### Layout Design

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ EXECUTIVE SUMMARY - USP CLAIMS MANAGEMENT                     [Refresh] [?] │
├─────────────────────────────────────────────────────────────────────────────┤
│ Period: [Year/Quarter/Month ▼]          Last Updated: [DD/MM/YYYY HH:MM]    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐          │
│  │                  │  │                  │  │                  │          │
│  │   RM[X] Billion  │  │     [X,XXX]      │  │      [XX]        │          │
│  │   Total Claims   │  │   Claims Processed│  │   Service Providers│         │
│  │   Approved YTD   │  │   This Period    │  │      Active      │          │
│  │                  │  │                  │  │                  │          │
│  │   [▲ X% vs PY]   │  │   [▲ X% vs PP]   │  │   [▲ X new]      │          │
│  │                  │  │                  │  │                  │          │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘          │
│                                                                             │
│  ┌─────────────────────────┐  ┌─────────────────────────┐                  │
│  │                         │  │                         │                  │
│  │   CLAIMS BY STATUS      │  │   MONTHLY TREND         │                  │
│  │                         │  │                         │                  │
│  │    [Pie Chart]          │  │    [Line Chart]         │                  │
│  │                         │  │                         │                  │
│  │  • Approved  [XX%]      │  │  RM(M)                  │                  │
│  │  • Pending   [XX%]      │  │    │                     │                  │
│  │  • Rejected  [XX%]      │  │  50├────/\____           │                  │
│  │  • Under Review [XX%]   │  │    │   /    \___         │                  │
│  │                         │  │  25├__/        \__       │                  │
│  │                         │  │    │              \      │                  │
│  │                         │  │   0├───────────────\─────│                  │
│  │                         │  │     J F M A M J J A S O N D                │
│  │                         │  │                         │                  │
│  └─────────────────────────┘  └─────────────────────────┘                  │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────┐               │
│  │              GEOGRAPHIC COVERAGE MAP                    │               │
│  │                                                         │               │
│  │              [Interactive Malaysia Map]                 │               │
│  │                                                         │               │
│  │    Color-coded by claim density and coverage status     │               │
│  │    Click state for drill-down to district level         │               │
│  │                                                         │               │
│  └─────────────────────────────────────────────────────────┘               │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────┐               │
│  │ TOP 5 SERVICE PROVIDERS        │ ALERTS & NOTIFICATIONS │               │
│  │ ┌────┬────────────────┬──────────────┐                  │               │
│  │ │Rank│ Provider       │ Amount (RM)  │  ⚠ 3 claims require │               │
│  │ ├────┼────────────────┼──────────────┤    urgent review    │               │
│  │ │ 1  │ Provider A     │ 150,000,000  │                     │               │
│  │ │ 2  │ Provider B     │ 125,000,000  │  ℹ Budget utilization│               │
│  │ │ 3  │ Provider C     │ 98,000,000   │    at 85% of annual  │               │
│  │ │ 4  │ Provider D     │ 87,000,000   │    allocation        │               │
│  │ │ 5  │ Provider E     │ 76,000,000   │                     │               │
│  │ └────┴────────────────┴──────────────┘                  │               │
│  └─────────────────────────────────────────────────────────┘               │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

#### KPI Widgets

| Widget | Metric | Refresh | Drill-Down |
|--------|--------|---------|------------|
| Total Approved | Sum of approved claims | Hourly | By SP, By Quarter |
| Claims Processed | Count of processed claims | Real-time | By Status, By Type |
| Active SPs | Count of active providers | Daily | SP Details |
| Avg Processing Time | Days from submission to payment | Daily | By Officer |
| Budget Utilization | % of annual budget committed | Daily | By Category |

### 3.2 Financial Performance Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ FINANCIAL PERFORMANCE DASHBOARD                               [Refresh] [?] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  BUDGET UTILIZATION              PAYMENT PIPELINE                           │
│  ┌─────────────────────────┐    ┌─────────────────────────┐                │
│  │                         │    │                         │                │
│  │    [Gauge Chart]        │    │    [Waterfall Chart]    │                │
│  │                         │    │                         │                │
│  │      78.5%              │    │  Approved │███████│     │                │
│  │    ┌───────┐            │    │  Pending  │█████│       │                │
│  │   /   78.5%  \           │    │  Held     │███│         │                │
│  │  │  /─────\  │           │    │  Paid     │████████│    │                │
│  │  │ │       │ │           │    │                         │                │
│  │   \│       |/            │    │  Total: RM[X]M          │                │
│  │    └───────┘             │    │                         │                │
│  │                         │    │                         │                │
│  │  Budget: RM[X]B          │    │                         │                │
│  │  Committed: RM[X]B       │    │                         │                │
│  │  Available: RM[X]B       │    │                         │                │
│  │                         │    │                         │                │
│  └─────────────────────────┘    └─────────────────────────┘                │
│                                                                             │
│  EXPENDITURE BY CATEGORY         MONTHLY CASH FLOW                          │
│  ┌─────────────────────────┐    ┌─────────────────────────┐                │
│  │  [Stacked Bar Chart]    │    │  [Area Chart]           │                │
│  │                         │    │                         │                │
│  │  CAPEX ████████████     │    │  Inflow  │▓▓▓▓▓▓▓▓▓▓│   │                │
│  │  OPEX  ████████         │    │  Outflow │░░░░░░░░░░│   │                │
│  │  Shared██████           │    │  Net     │▒▒▒▒▒▒▒▒▒▒│   │                │
│  │                         │    │                         │                │
│  └─────────────────────────┘    └─────────────────────────┘                │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. OPERATIONAL DASHBOARDS

### 4.1 Claims Processing Dashboard

#### Purpose
Monitor claim workflow and identify bottlenecks.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ CLAIMS PROCESSING WORKFLOW                                    [Refresh] [?] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  WORKFLOW PIPELINE                                                          │
│  ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐   ┌─────────┐       │
│  │  NEW    │──▶│VALIDATION│──▶│ REVIEW  │──▶│APPROVAL │──▶│ PAYMENT │       │
│  │  [45]   │   │  [28]   │   │  [15]   │   │  [12]   │   │  [8]    │       │
│  │  2.1d   │   │  1.5d   │   │  3.2d   │   │  2.8d   │   │  1.2d   │       │
│  └─────────┘   └─────────┘   └─────────┘   └─────────┘   └─────────┘       │
│      │            │            │            │            │                  │
│      └────────────┴────────────┴────────────┴────────────┘                  │
│                                                                             │
│  TOTAL PIPELINE: 108 CLAIMS    AVG CYCLE TIME: 10.8 DAYS                    │
│                                                                             │
│  ┌─────────────────────────┐  ┌─────────────────────────┐                  │
│  │  CLAIMS BY TYPE         │  │  PROCESSING TIME TREND  │                  │
│  │  [Donut Chart]          │  │  [Line Chart with SLAs] │                  │
│  │                         │  │                         │                  │
│  │   CAPEX 45%             │  │   Days                  │                  │
│  │   OPEX  30%             │  │   15 ├────────Target    │                  │
│  │   Shared 15%            │  │   10 ├────Actual        │                  │
│  │   Tech 10%              │  │    5 ├                  │                  │
│  │                         │  │    0 ├────────────────  │                  │
│  └─────────────────────────┘  └─────────────────────────┘                  │
│                                                                             │
│  EXCEPTION QUEUE                                                            │
│  ┌───────────┬────────────┬──────────────┬────────────────┐                │
│  │ Type      │ Count      │ Oldest (Days)│ Action Required│                │
│  ├───────────┼────────────┼──────────────┼────────────────┤                │
│  │ Info Req  │ 12         │ 8            │ Contact SP     │                │
│  │ Doc Issue │ 5          │ 5            │ Request resub  │                │
│  │ System Err│ 2          │ 1            │ IT Escalation  │                │
│  │ Approval  │ 3          │ 12           │ Escalate Mgmt  │                │
│  └───────────┴────────────┴──────────────┴────────────────┘                │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Team Performance Dashboard

| Widget | Description | Target |
|--------|-------------|--------|
| Individual Workload | Claims per officer | Balance ±10% |
| Processing Velocity | Claims completed/day | > 5 per officer |
| Quality Score | Error rate % | < 2% |
| SLA Compliance | % within target time | > 95% |
| Backlog Aging | Days in queue | < 5 days avg |

---

## 5. FUNCTIONAL DASHBOARDS

### 5.1 Service Provider Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ SERVICE PROVIDER ANALYTICS                                    [Refresh] [?] │
├─────────────────────────────────────────────────────────────────────────────┤
│ Provider: [All Providers ▼]    Region: [All Regions ▼]    Status: [All ▼]   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  SP PERFORMANCE SCORECARD                                                   │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐       │
│  │ Provider │Claims YTD│ Avg Value│ Avg Proc │ Approval │  Status  │       │
│  │          │          │   (RM)   │  (Days)  │   Rate   │          │       │
│  ├──────────┼──────────┼──────────┼──────────┼──────────┼──────────┤       │
│  │ ProviderA│    45    │ 850,000  │   8.5    │   94%    │  🟢 Good │       │
│  │ ProviderB│    38    │ 720,000  │   9.2    │   91%    │  🟢 Good │       │
│  │ ProviderC│    22    │ 1.2M     │   12.3   │   87%    │  🟡 Watch│       │
│  │ ProviderD│    15    │ 650,000  │   15.1   │   82%    │  🔴 Alert│       │
│  └──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘       │
│                                                                             │
│  SP CLAIM HISTORY TREND                                                     │
│  [Multi-line chart showing monthly claim submission by top 5 providers]     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Geographic Coverage Dashboard

| Layer | Data Points | Visualization |
|-------|-------------|---------------|
| State Level | Total claims, coverage % | Choropleth map |
| District Level | Project locations, status | Bubble map |
| Site Level | Individual project points | Pin markers |
| Coverage Gap | Unserved areas | Heat map |

---

## 6. SELF-SERVICE PORTAL DASHBOARD

### 6.1 Service Provider Self-Service View

```
┌─────────────────────────────────────────────────────────────────────────────┐
│ SERVICE PROVIDER PORTAL - [Provider Name]                     [Refresh] [?] │
├─────────────────────────────────────────────────────────────────────────────┤
│ Welcome, [Contact Name]              │  Account Status: 🟢 Active           │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  QUICK STATS                                                                │
│  ┌───────────────┐ ┌───────────────┐ ┌───────────────┐ ┌───────────────┐   │
│  │ Total Claims  │ │  Total Paid   │ │  Pending Amt  │ │  Avg Process  │   │
│  │     [XX]      │ │   RM[X]M      │ │   RM[X]M      │ │   [X] days    │   │
│  └───────────────┘ └───────────────┘ └───────────────┘ └───────────────┘   │
│                                                                             │
│  ACTIVE CLAIMS                                                              │
│  ┌─────────────┬──────────────┬────────────┬──────────────┬──────────┐     │
│  │ Claim Ref   │ Project      │ Submitted  │ Status       │ Amount   │     │
│  ├─────────────┼──────────────┼────────────┼──────────────┼──────────┤     │
│  │ UCMS-25-089 │ Project XYZ  │ 15/06/2025 │ Under Review │ 250,000  │     │
│  │ UCMS-25-076 │ Project ABC  │ 01/06/2025 │ Approved     │ 500,000  │     │
│  │ UCMS-25-045 │ Project DEF  │ 15/05/2025 │ Paid         │ 180,000  │     │
│  └─────────────┴──────────────┴────────────┴──────────────┴──────────┘     │
│                                                                             │
│  ACTIONS:  [+ Submit New Claim]  [📥 Download Forms]  [💬 Contact Support]  │
│                                                                             │
│  NOTIFICATIONS                                                              │
│  • Your claim UCMS-25-076 has been approved                                 │
│  • Additional documentation required for UCMS-25-089                        │
│  • Policy update: New claim template effective July 2025                    │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 7. DASHBOARD INTERACTION DESIGN

### 7.1 Common Interactions

| Action | Gesture/Input | Result |
|--------|---------------|--------|
| Drill Down | Click on element | Navigate to detailed view |
| Filter | Dropdown/Multi-select | Filter dashboard data |
| Time Range | Date picker/Slider | Change time period |
| Export | Button click | Download current view |
| Refresh | Button/Auto | Update data |
| Search | Text input | Find specific items |
| Bookmark | Star icon | Save view configuration |
| Share | Share icon | Send to other users |

### 7.2 Responsive Behavior

| Device | Layout | Features |
|--------|--------|----------|
| Desktop (1920+) | Full 3-column grid | All features |
| Laptop (1366+) | 2-column grid | All features |
| Tablet (768+) | Single column, scroll | Touch optimized |
| Mobile (< 768) | Stacked cards | Essential KPIs only |

---

## 8. ACCESS CONTROL MATRIX

| Dashboard | CEO | Director | Manager | Officer | Analyst | SP |
|-----------|-----|----------|---------|---------|---------|-----|
| Executive Summary | ✓ | ✓ | ✓ | - | - | - |
| Financial Performance | ✓ | ✓ | ✓ | - | - | - |
| Claims Processing | ✓ | ✓ | ✓ | ✓ | ✓ | - |
| Team Performance | - | ✓ | ✓ | View Only | - | - |
| SP Analytics | ✓ | ✓ | ✓ | ✓ | ✓ | - |
| Geographic Coverage | ✓ | ✓ | ✓ | ✓ | ✓ | - |
| SP Self-Service | - | - | - | - | - | Own Data |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T24-REPORT-CATALOG | Report Specifications |
| CR-002 | ANNEX-T27-SELF-SERVICE | Portal Design |
| CR-003 | ANNEX-T31-SECURITY-FRAMEWORK | Access Control |
| CR-004 | ANNEX-T30-AI-ML-ARCH | Predictive Widgets |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
