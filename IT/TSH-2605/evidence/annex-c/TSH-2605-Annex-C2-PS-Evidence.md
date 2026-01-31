# ANNEX C2: PS - PROCUREMENT SYSTEM EVIDENCE

**Tender Reference:** MMFSB/TD 02/2026  
**System:** Procurement System (PS)  
**Version:** LogisticsPro PS v4.2  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Purchase Requisition Workflow](#1-purchase-requisition-workflow)
2. [Vendor Management](#2-vendor-management)
3. [Quotation & RFQ Management](#3-quotation--rfq-management)
4. [Purchase Order Processing](#4-purchase-order-processing)
5. [Goods Receipt & 3-Way Matching](#5-goods-receipt--3-way-matching)
6. [Procurement Analytics](#6-procurement-analytics)
7. [Budget Control](#7-budget-control)
8. [AI Procurement Intelligence](#8-ai-procurement-intelligence)

---

## 1. PURCHASE REQUISITION WORKFLOW

### 1.1 PR Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  PROCUREMENT DASHBOARD                                            [New PR] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ PENDING MY       │  │ PENDING APPROVAL │  │ YTD SAVINGS      │         │
│  │ APPROVAL         │  │ (All)            │  │                  │         │
│  │                  │  │                  │  │                  │         │
│  │      8           │  │      23          │  │   RM 245,000     │         │
│  │    PRs           │  │    PRs           │  │    ↑ 12%         │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  SPEND OVERVIEW (YTD 2026)                                                  │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Total Committed:    RM 4,250,000                                   │  │
│  │  Total Spent:        RM 2,180,000 (51%)                             │  │
│  │  Pending POs:        RM 1,320,000                                   │  │
│  │  Available Budget:   RM 450,000                                     │  │
│  │                                                                      │  │
│  │  Budget Utilization: ████████████████████████████████░░░░  89%      │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  RECENT PURCHASE REQUISITIONS                                               │
│  ┌────────────┬──────────────┬──────────────┬──────────────┬──────────────┐│
│  │ PR Number  │ Requestor    │ Amount       │ Status       │ Action       ││
│  ├────────────┼──────────────┼──────────────┼──────────────┼──────────────┤│
│  │ PR-2026-089│ Ahmad Khalid │ RM 12,500    │ 🟡 Pending   │ [Approve]    ││
│  │ PR-2026-088│ Siti Aminah  │ RM 45,000    │ 🟡 Pending   │ [Approve]    ││
│  │ PR-2026-087│ Kumar Raj    │ RM 8,900     │ 🟢 Approved  │ [View]       ││
│  │ PR-2026-086│ Fatimah Lee  │ RM 125,000   │ 🔴 Rejected  │ [View]       ││
│  └────────────┴──────────────┴──────────────┴──────────────┴──────────────┘│
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: PR Dashboard screenshot]
Caption: Procurement Dashboard with Real-time Spend Visibility
```

---

### 1.2 Purchase Requisition Creation

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📝 NEW PURCHASE REQUISITION                                      [Submit] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  REQUISITION HEADER                                                         │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Requestor:        Ahmad Khalid (Operations Dept)                   │  │
│  │  Date:             31 January 2026                                  │  │
│  │  Required Date:    15 February 2026                                 │  │
│  │  Department:       Operations - Port Klang                          │  │
│  │  Budget Code:      OPS-2026-MAINT (✅ Verified - Available)        │  │
│  │  Priority:         [Normal ▼]                                       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  LINE ITEMS                                                                 │
│  ┌──────────┬──────────────────────────┬──────────┬──────────┬──────────────┐│
│  │ #        │ Description              │ Qty      │ Est. Cost│ Total        ││
│  ├──────────┼──────────────────────────┼──────────┼──────────┼──────────────┤│
│  │ 1        │ Prime Mover Brake Pads   │ 10 sets  │ RM 450   │ RM 4,500     ││
│  │          │ (Volvo FH16 compatible)  │          │          │              ││
│  │ 2        │ Engine Oil 15W-40        │ 200L     │ RM 29/L  │ RM 5,800     ││
│  │ 3        │ Air Filter Element       │ 15 pcs   │ RM 85    │ RM 1,275     ││
│  └──────────┴──────────────────────────┴──────────┴──────────┴──────────────┘│
│                                                                             │
│  TOTAL ESTIMATED: RM 11,575                                                 │
│                                                                             │
│  🧠 AI RECOMMENDATIONS:                                                     │
│  • Preferred Vendor: TechCorp Sdn Bhd (Last price: RM 425 for brake pads)   │
│  • Alternative: AutoParts KL (RM 440, 3-day delivery)                       │
│  • Budget Check: ✅ Within allocated budget (RM 50,000 remaining)            │
│                                                                             │
│  ATTACHMENTS                                                                │
│  📎 brake_specs.pdf                                                         │
│  📎 vendor_quote_techcorp.pdf                                               │
│                                                                             │
│  APPROVAL ROUTE                                                             │
│  ┌──────────┬──────────────┬──────────────────────────────────────────────┐│
│  │ Step     │ Approver     │ Status                                       ││
│  ├──────────┼──────────────┼──────────────────────────────────────────────┤│
│  │ 1        │ Dept Head    │ ⏳ Pending (Auto-routed on submit)           ││
│  │ 2        │ Finance      │ ⏳ Pending (If >RM 10,000)                   ││
│  └──────────┴──────────────┴──────────────────────────────────────────────┘│
│                                                                             │
│  [💾 Save Draft]  [📤 Submit for Approval]                                  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: PR Creation screenshot]
Caption: Purchase Requisition with AI Vendor Recommendations
```

---

## 2. VENDOR MANAGEMENT

### 2.1 Vendor Scorecard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  👥 VENDOR: TechCorp Sdn Bhd                                     [Edit] [📊]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  VENDOR INFORMATION                                                         │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Vendor ID: VEN-001892                                              │  │
│  │  Company Reg: 201001012345 (201001012345)                           │  │
│  │  Tax ID: C1234567890                                                │  │
│  │  Category: Automotive Parts, Maintenance Services                   │  │
│  │  Status: 🟢 Active - Preferred Vendor                               │  │
│  │  Since: 15 March 2020                                               │  │
│  │                                                                      │  │
│  │  Contact: Encik Ahmad (Sales Manager)                               │  │
│  │  Phone: 03-7722 8888                                                │  │
│  │  Email: ahmad@techcorp.com.my                                       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  PERFORMANCE SCORECARD (Last 12 Months)                                     │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Overall Score: 87/100 ⭐⭐⭐⭐                                       │  │
│  │                                                                      │  │
│  │  Quality (30%)       ████████████████████████████░░░  28/30         │  │
│  │  Delivery (30%)      █████████████████████████░░░░░░  25/30         │  │
│  │  Price (20%)         ████████████████████████░░░░░░░  18/20         │  │
│  │  Service (20%)       ████████████████████████████░░░  16/20         │  │
│  │                                                                      │  │
│  │  Trend: ↑ Improving (Last quarter: 82 → This quarter: 87)          │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  TRANSACTION HISTORY                                                        │
│  ┌────────────┬──────────────┬──────────────┬──────────────┬──────────────┐│
│  │ Year       │ PO Count     │ Total Spend  │ Avg Delivery │ Defect Rate  ││
│  ├────────────┼──────────────┼──────────────┼──────────────┼──────────────┤│
│  │ 2026 YTD   │ 12           │ RM 145,000   │ 3.2 days     │ 0.5%         ││
│  │ 2025       │ 48           │ RM 580,000   │ 3.5 days     │ 0.8%         ││
│  │ 2024       │ 42           │ RM 495,000   │ 4.1 days     │ 1.2%         ││
│  └────────────┴──────────────┴──────────────┴──────────────┴──────────────┘│
│                                                                             │
│  🧠 AI VENDOR INTELLIGENCE:                                                 │
│  • TechCorp has improved delivery performance by 22% over 2 years           │
│  • Price competitiveness: 8% below market average                           │
│  • Credit Check: ✅ No adverse findings in last 6 months                    │
│  • Recommend for: Brake components, filtration systems, lubricants          │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Vendor Scorecard screenshot]
Caption: Comprehensive Vendor Performance Scorecard with AI Intelligence
```

---

## 3. QUOTATION & RFQ MANAGEMENT

### 3.1 RFQ Comparison

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📊 RFQ COMPARISON: RFQ-2026-0045                                [Award]   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  RFQ DETAILS                                                                │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  RFQ Number: RFQ-2026-0045                                          │  │
│  │  Description: Supply of Prime Mover Tires (295/80R22.5)             │  │
│  │  Quantity: 40 tires                                                 │  │
│  │  Delivery: Port Klang Depot                                         │  │
│  │  Closing Date: 28 January 2026                                      │  │
│  │  Status: 🟢 Quotations Received                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  QUOTATION COMPARISON                                                       │
│  ┌────────────────┬──────────────┬──────────────┬──────────────┬──────────┐│
│  │ Vendor         │ Unit Price   │ Total (40)   │ Delivery     │ Score    ││
│  ├────────────────┼──────────────┼──────────────┼──────────────┼──────────┤│
│  │ 🏆 TechCorp    │ RM 1,250     │ RM 50,000    │ 5 days       │ 94%      ││
│  │    Sdn Bhd     │              │              │              │          ││
│  ├────────────────┼──────────────┼──────────────┼──────────────┼──────────┤│
│  │ AutoParts KL   │ RM 1,320     │ RM 52,800    │ 3 days       │ 87%      ││
│  ├────────────────┼──────────────┼──────────────┼──────────────┼──────────┤│
│  │ Global Tire    │ RM 1,180     │ RM 47,200    │ 10 days      │ 82%      ││
│  └────────────────┴──────────────┴──────────────┴──────────────┴──────────┘│
│                                                                             │
│  🧠 AI RECOMMENDATION:                                                      │
│  Based on total cost of ownership (price + delivery + quality history),     │
│  TechCorp Sdn Bhd is recommended with 94% confidence score.                 │
│                                                                             │
│  Reasoning:                                                                 │
│  • Price is 5% below last purchase (RM 1,320)                               │
│  • 99.2% on-time delivery record                                            │
│  • 0.5% defect rate (lowest among bidders)                                  │
│  • Volume discount available for orders >50 tires                           │
│                                                                             │
│  Estimated Annual Savings vs. Highest Bid: RM 11,200                        │
│                                                                             │
│  HISTORICAL PRICING TREND                                                   │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  RM 1,400 │                                    ┌────┐               │  │
│  │  RM 1,350 │                              ┌────┐│    │               │  │
│  │  RM 1,300 │                        ┌────┐│    ││    │  ┌────┐       │  │
│  │  RM 1,250 │                  ┌────┐│    ││    ││    │  │    │       │  │
│  │  RM 1,200 │            ┌────┐│    ││    ││    ││    │  │    │       │  │
│  │          └────┬────┬────┬────┬────┬────┬────┬────┬────┬────┘       │  │
│  │             Q1   Q2   Q3   Q4   Q1   Q2   Q3   Q4   Q1               │  │
│  │            2024              2025              2026                 │  │
│  │                                                                      │  │
│  │  Trend: Stable with slight downward pressure                          │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [✅ Award to TechCorp]  [📧 Request Clarification]  [🔄 Re-tender]         │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: RFQ Comparison screenshot]
Caption: RFQ Quotation Comparison with AI Price Benchmarking
```

---

## 4. PURCHASE ORDER PROCESSING

### 4.1 Purchase Order Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📋 PURCHASE ORDERS                                               [New PO] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PO STATUS OVERVIEW                                                         │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ DRAFT            │  │ PENDING          │  │ APPROVED         │         │
│  │      5           │  │      8           │  │      12          │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ ORDERED          │  │ PARTIALLY        │  │ COMPLETED        │         │
│  │      23          │  │      6           │  │      145         │         │
│  │                  │  │      RECEIVED    │  │                  │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  RECENT PURCHASE ORDERS                                                     │
│  ┌────────────┬──────────────┬──────────────┬──────────────┬──────────────┐│
│  │ PO Number  │ Vendor       │ Amount       │ Status       │ Delivery     ││
│  ├────────────┼──────────────┼──────────────┼──────────────┼──────────────┤│
│  │ PO-2026-089│ TechCorp     │ RM 12,500    │ 🟢 Ordered   │ 05 Feb 2026  ││
│  │ PO-2026-088│ AutoParts KL │ RM 45,000    │ 🟡 Partial   │ 10 Feb 2026  ││
│  │ PO-2026-087│ Global Tire  │ RM 8,900     │ 🟢 Received  │ 02 Feb 2026  ││
│  │ PO-2026-086│ TechCorp     │ RM 125,000   │ 🟢 Completed │ 28 Jan 2026  ││
│  └────────────┴──────────────┴──────────────┴──────────────┴──────────────┘│
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: PO Dashboard screenshot]
Caption: Purchase Order Status Dashboard
```

---

## 5. GOODS RECEIPT & 3-WAY MATCHING

### 5.1 Three-Way Matching

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  ✅ 3-WAY MATCHING: INV-TC-2026-001234                            [Post]   │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  DOCUMENTS TO MATCH                                                         │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  📄 PURCHASE ORDER                      ✅ MATCHED                  │  │
│  │  PO-2026-089 | TechCorp Sdn Bhd                                     │  │
│  │  Date: 28 Jan 2026 | Status: Completed                              │  │
│  │  ┌─────────────────┬─────────────────┬─────────────────┐            │  │
│  │  │ Item            │ Qty Ordered     │ Unit Price      │            │  │
│  │  ├─────────────────┼─────────────────┼─────────────────┤            │  │
│  │  │ Brake Pads      │ 10 sets         │ RM 450.00       │            │  │
│  │  │ Engine Oil      │ 200L            │ RM 29.00        │            │  │
│  │  └─────────────────┴─────────────────┴─────────────────┘            │  │
│  │  PO Total: RM 10,300                                                │  │
│  │                                                                      │  │
│  │  ─────────────────────────────────────────────────────────────────  │  │
│  │                                                                      │  │
│  │  📦 GOODS RECEIPT NOTE                  ✅ MATCHED                  │  │
│  │  GRN-2026-0567 | Received: 30 Jan 2026                              │  │
│  │  Received By: Encik Kumar                                           │  │
│  │  ┌─────────────────┬─────────────────┬─────────────────┐            │  │
│  │  │ Item            │ Qty Received    │ Condition       │            │  │
│  │  ├─────────────────┼─────────────────┼─────────────────┤            │  │
│  │  │ Brake Pads      │ 10 sets         │ Good            │            │  │
│  │  │ Engine Oil      │ 200L            │ Good            │            │  │
│  │  └─────────────────┴─────────────────┴─────────────────┘            │  │
│  │                                                                      │  │
│  │  ─────────────────────────────────────────────────────────────────  │  │
│  │                                                                      │  │
│  │  🧾 SUPPLIER INVOICE                    ✅ MATCHED                  │  │
│  │  INV-TC-2026-001234 | Date: 31 Jan 2026                             │  │
│  │  ┌─────────────────┬─────────────────┬─────────────────┐            │  │
│  │  │ Item            │ Qty Invoiced    │ Unit Price      │            │  │
│  │  ├─────────────────┼─────────────────┼─────────────────┤            │  │
│  │  │ Brake Pads      │ 10 sets         │ RM 450.00       │            │  │
│  │  │ Engine Oil      │ 200L            │ RM 29.00        │            │  │
│  │  └─────────────────┴─────────────────┴─────────────────┘            │  │
│  │  Invoice Total: RM 10,300                                           │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  MATCHING RESULT                                                            │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  PO Quantity vs GRN:    ✅ 100% Match (10 = 10, 200 = 200)          │  │
│  │  PO Price vs Invoice:   ✅ 100% Match (RM 450 = RM 450)             │  │
│  │  PO Total vs Invoice:   ✅ 100% Match (RM 10,300 = RM 10,300)       │  │
│  │                                                                      │  │
│  │  Status: ✅ FULLY MATCHED - Ready for Payment Processing            │  │
│  │                                                                      │  │
│  │  Variance: RM 0.00 (0%)                                             │  │
│  │  Within Tolerance: ✅ Yes (±2% qty, ±5% price allowed)              │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [✅ Post to FMS]  [📝 Add Notes]  [📧 Query Vendor]                        │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: 3-Way Matching screenshot]
Caption: Automated Three-Way Matching with Full Validation
```

---

## 6. PROCUREMENT ANALYTICS

### 6.1 Spend Analysis Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📊 PROCUREMENT ANALYTICS                                         [Export] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  SPEND BY CATEGORY (YTD 2026)                                               │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Vehicle Parts & Maintenance  ████████████████████████░░░░  RM 1.8M │  │
│  │  Fuel & Lubricants            ██████████████░░░░░░░░░░░░░░  RM 1.2M │  │
│  │  IT Equipment & Software      ██████░░░░░░░░░░░░░░░░░░░░░░  RM 450K │  │
│  │  Office Supplies              ███░░░░░░░░░░░░░░░░░░░░░░░░░  RM 180K │  │
│  │  Professional Services        ██░░░░░░░░░░░░░░░░░░░░░░░░░░  RM 120K │  │
│  │                                                                      │  │
│  │  Total Spend: RM 3.75M                                              │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  TOP VENDORS BY SPEND                                                       │
│  ┌──────────────┬──────────────┬──────────────┬──────────────────────────┐ │
│  │ Vendor       │ YTD Spend    │ % of Total   │ Trend                    │ │
│  ├──────────────┼──────────────┼──────────────┼──────────────────────────┤ │
│  │ TechCorp     │ RM 890,000   │ 24%          │ ↑ 15% vs last year       │ │
│  │ Petronas     │ RM 720,000   │ 19%          │ → Stable                 │ │
│  │ AutoParts KL │ RM 450,000   │ 12%          │ ↑ 8% vs last year        │ │
│  │ Dell Malaysia│ RM 280,000   │ 7%           │ ↓ 5% vs last year        │ │
│  │ Others       │ RM 1,410,000 │ 38%          │ Mixed                    │ │
│  └──────────────┴──────────────┴──────────────┴──────────────────────────┘ │
│                                                                             │
│  🧠 AI INSIGHTS:                                                            │
│  • Maverick spending detected: RM 45,000 in non-contract purchases          │
│  • Consolidation opportunity: 3 vendors for office supplies → save 12%      │
│  • Contract renewal required: Dell enterprise agreement expires in 60 days  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Procurement Analytics screenshot]
Caption: Spend Analysis with AI-Powered Insights
```

---

## 7. BUDGET CONTROL

### 7.1 Budget Tracking

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  💰 BUDGET CONTROL: OPS-2026-MAINT                               [Details] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  BUDGET SUMMARY                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Budget Code:      OPS-2026-MAINT                                   │  │
│  │  Description:      Operations - Maintenance & Repairs               │  │
│  │  Department:       Operations                                       │  │
│  │  Annual Budget:    RM 500,000                                       │  │
│  │  Period:           01 Jan 2026 - 31 Dec 2026                        │  │
│  │  Budget Owner:     Ahmad Khalid                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  BUDGET UTILIZATION                                                         │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Budget Status: 31 Jan 2026                                         │  │
│  │                                                                      │  │
│  │  Total Budget:        RM 500,000                                    │  │
│  │  Committed (POs):     RM 125,000  ████████░░░░░░░░░░  25%           │  │
│  │  Actual Spent:        RM 45,000   ███░░░░░░░░░░░░░░░   9%           │  │
│  │  Available:           RM 330,000  ██████████████████  66%           │  │
│  │                                                                      │  │
│  │  ████████████████████████████████████████████████████████████████   │  │
│  │  Spent      Committed      Available                               │  │
│  │                                                                      │  │
│  │  🟢 Status: Healthy - On track for annual budget                   │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  MONTHLY BREAKDOWN                                                          │
│  ┌──────────┬──────────────┬──────────────┬──────────────┬──────────────┐ │
│  │ Month    │ Budget       │ Spent        │ Variance     │ Status       │ │
│  ├──────────┼──────────────┼──────────────┼──────────────┼──────────────┤ │
│  │ Jan      │ RM 41,667    │ RM 45,000    │ -RM 3,333    │ 🟡 Over      │ │
│  │ Feb      │ RM 41,667    │ RM 0         │ +RM 41,667   │ 🟢 Planned   │ │
│  │ Mar      │ RM 41,667    │ RM 0         │ +RM 41,667   │ 🟢 Planned   │ │
│  │ Q2-Q4    │ RM 375,000   │ TBD          │ TBD          │ ⏳ Future    │ │
│  └──────────┴──────────────┴──────────────┴──────────────┴──────────────┘ │
│                                                                             │
│  🧠 AI FORECAST: Based on historical patterns and pipeline requisitions,    │
│  projected year-end spend: RM 485,000 (3% under budget)                     │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Budget Control screenshot]
Caption: Real-time Budget Tracking with AI Forecasting
```

---

## 8. AI PROCUREMENT INTELLIGENCE

### 8.1 Fraud Detection & Anomaly Alert

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🚨 AI PROCUREMENT ALERTS                                        [Review] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  🔔 ACTIVE ALERTS REQUIRING ATTENTION                                       │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  🔴 HIGH PRIORITY - Potential Split Purchase                         │  │
│  │                                                                      │  │
│  │  Two purchase requisitions detected from same requestor within 24h:   │  │
│  │  • PR-2026-085: RM 9,500 (just below RM 10,000 approval limit)       │  │
│  │  • PR-2026-086: RM 9,800 (same vendor, similar items)                │  │
│  │                                                                      │  │
│  │  Combined value: RM 19,300 (exceeds requestor's approval authority)  │  │
│  │  Pattern match: 87% similar to known circumvention patterns          │  │
│  │                                                                      │  │
│  │  [📋 Review PRs]  [✅ Dismiss]  [📝 Add Comment]                     │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  🟡 MEDIUM PRIORITY - Unusual Vendor Activity                        │  │
│  │                                                                      │  │
│  │  Vendor: NewSupply Sdn Bhd (registered 2 weeks ago)                  │  │
│  │  Activity: Received 3 POs totaling RM 75,000 in first month          │  │
│  │                                                                      │  │
│  │  Risk factors:                                                        │  │
│  │  • New vendor with high transaction volume                            │  │
│  │  • No historical performance data                                     │  │
│  │  • Address matches residential location                               │  │
│  │                                                                      │  │
│  │  [🔍 Investigate]  [⚠️ Flag for Audit]  [✅ Clear]                   │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  🟢 INFORMATION - Maverick Spending Detected                         │  │
│  │                                                                      │  │
│  │  Branch: Port Klang purchased RM 8,500 of printer toner from         │  │
│  │  non-contract vendor (Staples) instead of preferred vendor           │  │
│  │  (TechCorp with 15% volume discount).                                │  │
│  │                                                                      │  │
│  │  Potential savings missed: RM 1,275                                   │  │
│  │                                                                      │  │
│  │  [📧 Notify Branch]  [📊 View Report]                                │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  AI PROTECTION SUMMARY (Last 30 Days)                                       │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Alerts Generated:        12                                         │  │
│  │  High Priority:           2                                          │  │
│  │  Medium Priority:         4                                          │  │
│  │  Informational:           6                                          │  │
│  │  Potential Fraud Prevented: RM 45,000                                │  │
│  │  Contract Compliance Improved: 8%                                    │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: AI Procurement Intelligence screenshot]
Caption: AI-Powered Fraud Detection and Compliance Monitoring
```

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
