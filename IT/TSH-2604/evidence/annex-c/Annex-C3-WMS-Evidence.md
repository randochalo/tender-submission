# ANNEX C3: WMS - WAREHOUSE MANAGEMENT SYSTEM EVIDENCE

**Tender Reference:** MMFSB/TD 01/2026  
**System:** Warehouse Management System (WMS)  
**Version:** LogisticsPro WMS v4.2  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Warehouse Control Tower](#1-warehouse-control-tower)
2. [Inventory Management](#2-inventory-management)
3. [Receiving & Put-away](#3-receiving--put-away)
4. [Picking & Packing](#4-picking--packing)
5. [Digital Twin & Yard Map](#5-digital-twin--yard-map)
6. [RFID & Barcode Integration](#6-rfid--barcode-integration)
7. [Warehouse Reports](#7-warehouse-reports)

---

## 1. WAREHOUSE CONTROL TOWER

### 1.1 WMS Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  WMS CONTROL TOWER                                                [User] ▼  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ INVENTORY        │  │ SPACE UTILIZATION│  │ ORDERS TODAY     │         │
│  │ ACCURACY         │  │                  │  │                  │         │
│  │                  │  │                  │  │                  │         │
│  │     99.7%        │  │      87.3%       │  │     142          │         │
│  │    ✅            │  │    ↑ 3.2%        │  │    128 shipped   │         │
│  │    Target: 99.5% │  │    vs last week  │  │    14 pending    │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                    WAREHOUSE DIGITAL TWIN                           │  │
│  │                                                                     │  │
│  │    ┌───────────────────────────────────────────────────────────┐   │  │
│  │    │  [3D VISUALIZATION OF WAREHOUSE WITH REAL-TIME DATA]      │   │  │
│  │    │                                                           │   │  │
│  │    │   Z1    Z2    Z3    Z4    Z5    Z6                       │   │  │
│  │    │  ┌───┐ ┌───┐ ┌───┐ ┌───┐ ┌───┐ ┌───┐                    │   │  │
│  │    │  │███│ │░░░│ │███│ │███│ │░░░│ │███│  ███ = Full        │   │  │
│  │    │  │███│ │░░░│ │███│ │███│ │░░░│ │███│  ░░░ = Available   │   │  │
│  │    │  └───┘ └───┘ └───┘ └───┘ └───┘ └───┘                    │   │  │
│  │    │                                                           │   │  │
│  │    │  🏃 3 active pickers in Zone 2                            │   │  │
│  │    │  🚛 Dock 4: Loading in progress                           │   │  │
│  │    │  ⚠️ Zone 5: Low stock alert for SKU-789234                │   │  │
│  │    │                                                           │   │  │
│  │    └───────────────────────────────────────────────────────────┘   │  │
│  │                                                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  OPERATIONAL ALERTS                                                         │
│  ┌────────────┬──────────────┬──────────────┬────────────────────────────┐ │
│  │ Alert      │ Location     │ Priority     │ Action                     │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ Low Stock  │ Zone 5-B-12  │ 🔴 High      │ Reorder triggered          │ │
│  │ Overdue Put│ Zone 3-C-08  │ 🟡 Medium    │ Assign to picker           │ │
│  │ Damaged    │ Receiving    │ 🟡 Medium    │ QC inspection required     │ │
│  └────────────┴──────────────┴──────────────┴────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: WMS Dashboard screenshot]
Caption: WMS Control Tower with Digital Twin Visualization
```

---

## 2. INVENTORY MANAGEMENT

### 2.1 Inventory Detail View

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📦 INVENTORY: SKU-789234 - Computer Parts                    [Adjust] [📤]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  PRODUCT INFORMATION                                                 │  │
│  │                                                                      │  │
│  │  SKU: SKU-789234                                                    │  │
│  │  Description: Dell Laptop Motherboard XPS15                         │  │
│  │  Category: Electronics > Computer Parts                             │  │
│  │  UOM: PCS                                                           │  │
│  │  Dimensions: 35cm x 25cm x 5cm                                      │  │
│  │  Weight: 850g                                                       │  │
│  │  Hazardous: No                                                      │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  STOCK LEVELS                                                               │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Total Stock: 1,245 PCS                                             │  │
│  │                                                                      │  │
│  │  Available:     ████████████████████████████████░░░░  892 (72%)     │  │
│  │  Allocated:     ██████████░░░░░░░░░░░░░░░░░░░░░░░░░░  298 (24%)     │  │
│  │  Quarantine:    ██░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   45 (4%)      │  │
│  │  Damaged:       ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░    0 (0%)      │  │
│  │  On Hold:       ████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   10 (1%)      │  │
│  │                                                                      │  │
│  │  Reorder Point: 500 PCS    Reorder Qty: 1,000 PCS                   │  │
│  │  Status: ✅ Above Reorder Point                                     │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  STOCK LOCATIONS                                                            │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────┐ │
│  │ Location     │ Zone         │ Qty          │ Status       │ Last Move│ │
│  ├──────────────┼──────────────┼──────────────┼──────────────┼──────────┤ │
│  │ Z2-A-05-02   │ Fast Moving  │ 350          │ Available    │ 2h ago   │ │
│  │ Z2-A-05-03   │ Fast Moving  │ 350          │ Available    │ 2h ago   │ │
│  │ Z3-B-12-08   │ Bulk Storage │ 500          │ Available    │ 1d ago   │ │
│  │ Z5-C-03-01   │ Quarantine   │ 45           │ QC Hold      │ 3h ago   │ │
│  └──────────────┴──────────────┴──────────────┴──────────────┴──────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Inventory Detail screenshot]
Caption: Real-time Inventory Tracking with Status Breakdown
```

---

## 3. RECEIVING & PUT-AWAY

### 3.1 Goods Receipt Process

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📥 GOODS RECEIPT: GRN-2026-001892                                [Print]  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ASN INFORMATION                                                            │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  ASN Number: ASN-TechCorp-2026-001234                               │  │
│  │  Supplier: TechCorp Sdn Bhd                                         │  │
│  │  Expected: 500 CTNS Computer Parts                                  │  │
│  │  Status: 🟡 Partially Received (350/500)                            │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  RECEIPT DETAILS                                                            │
│  ┌──────────────┬──────────────┬──────────────┬──────────────┬──────────┐ │
│  │ SKU          │ Description  │ Exp. Qty     │ Rec. Qty     │ Status   │ │
│  ├──────────────┼──────────────┼──────────────┼──────────────┼──────────┤ │
│  │ SKU-789234   │ Motherboard  │ 200          │ 200 ✅       │ Match    │ │
│  │ SKU-789235   │ RAM 16GB     │ 150          │ 150 ✅       │ Match    │ │
│  │ SKU-789236   │ SSD 512GB    │ 150          │ 0 ⚠️         │ Shortage │ │
│  └──────────────┴──────────────┴──────────────┴──────────────┴──────────┘ │
│                                                                             │
│  AI PUT-AWAY RECOMMENDATION                                                 │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  🧠 AI SLOT OPTIMIZER                                               │  │
│  │                                                                      │  │
│  │  For SKU-789234 (Motherboard):                                      │  │
│  │  Recommended Location: Z2-A-05-04 (Fast Moving Zone)                │  │
│  │                                                                      │  │
│  │  Reasoning:                                                         │  │
│  │  • High velocity item (42 picks/week)                               │  │
│  │  • Zone 2 is closest to packing station                             │  │
│  │  • Current slot is 15% faster than alternative                      │  │
│  │  • Compatible with existing stock                                   │  │
│  │                                                                      │  │
│  │  [✅ Accept Recommendation]  [📍 View Alternatives]                  │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [📷 Scan Barcode]  [📍 Start Put-away]  [📝 Add Discrepancy Note]        │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Goods Receipt screenshot]
Caption: Goods Receipt with AI Put-away Recommendation
```

---

## 4. PICKING & PACKING

### 4.1 Pick Wave Management

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🛒 PICK WAVE: WAVE-2026-0131-A                                   [Release] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  WAVE SUMMARY                                                               │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Orders: 25         SKUs: 45          Lines: 89                      │  │
│  │  Priority: High     Zone Coverage: Z2, Z3, Z5                        │  │
│  │  Estimated Duration: 2h 15m                                          │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  AI-OPTIMIZED PICK PATH                                                     │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  🧠 OPTIMIZED PICK SEQUENCE:                                        │  │
│  │                                                                      │  │
│  │  1. Start → Z2-A-05-02 (SKU-789234) x5    [Travel: 0m]             │  │
│  │  2. Z2-A-05-02 → Z2-A-05-03 (SKU-789234) x3  [Travel: 5m]          │  │
│  │  3. Z2-A-08-12 (SKU-789240) x2            [Travel: 45m]            │  │
│  │  4. Z3-B-12-08 (SKU-789251) x4            [Travel: 120m]           │  │
│  │  5. Z5-C-03-01 (SKU-789267) x1            [Travel: 180m]           │  │
│  │                                                                      │  │
│  │  Total Optimized Travel: 350m (vs 520m unoptimized = 33% savings)   │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  PICK TASKS                                                                 │
│  ┌──────────┬──────────────┬──────────┬──────────┬──────────────┬────────┐ │
│  │ Priority │ SKU          │ Location │ Qty      │ Picker       │ Status │ │
│  ├──────────┼──────────────┼──────────┼──────────┼──────────────┼────────┤ │
│  │ 🔴 High  │ SKU-789234   │ Z2-A-05  │ 5        │ Ahmad (RF1)  │ 🟡 Pick│ │
│  │ 🔴 High  │ SKU-789234   │ Z2-A-05  │ 3        │ Ahmad (RF1)  │ ⏳ Wait│ │
│  │ 🟡 Med   │ SKU-789240   │ Z2-A-08  │ 2        │ Kumar (RF2)  │ ⏳ Wait│ │
│  │ 🟢 Low   │ SKU-789251   │ Z3-B-12  │ 4        │ Unassigned   │ ⏳ Wait│ │
│  └──────────┴──────────────┴──────────┴──────────┴──────────────┴────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Pick Wave screenshot]
Caption: AI-Optimized Pick Path with Travel Distance Savings
```

---

## 5. DIGITAL TWIN & YARD MAP

### 5.1 Warehouse Digital Twin

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🏭 WAREHOUSE DIGITAL TWIN                                        [3D View]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  [3D VISUALIZATION - ISO VIEW]                                       │  │
│  │                                                                      │  │
│  │          Z1          Z2          Z3          Z4          Z5          │  │
│  │       ┌──────┐   ┌──────┐   ┌──────┐   ┌──────┐   ┌──────┐        │  │
│  │    A  │██████│   │▓▓▓▓▓▓│   │██████│   │░░░░░░│   │██████│        │  │
│  │       │██████│   │▓▓▓▓▓▓│   │██████│   │░░░░░░│   │██████│        │  │
│  │       │██████│   │▓▓▓▓▓▓│   │██████│   │░░░░░░│   │██████│        │  │
│  │       ├──────┤   ├──────┤   ├──────┤   ├──────┤   ├──────┤        │  │
│  │    B  │██████│   │▓▓▓▓▓▓│   │██████│   │██████│   │░░░░░░│        │  │
│  │       │██████│   │▓▓▓▓▓▓│   │██████│   │██████│   │░░░░░░│        │  │
│  │       ├──────┤   ├──────┤   ├──────┤   ├──────┤   ├──────┤        │  │
│  │    C  │░░░░░░│   │██████│   │▓▓▓▓▓▓│   │██████│   │██████│        │  │
│  │       │░░░░░░│   │██████│   │▓▓▓▓▓▓│   │██████│   │██████│        │  │
│  │       └──────┘   └──────┘   └──────┘   └──────┘   └──────┘        │  │
│  │                                                                      │  │
│  │  Legend: ████ Full (85%+)  ▓▓▓▓ Medium (50-85%)  ░░░░ Available    │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  SCENARIO MODELING                                                          │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  What would happen if we...                                         │  │
│  │                                                                      │  │
│  │  [+] Add 20% more fast-moving SKUs to Zone 2                        │  │
│  │     → Predicted efficiency gain: +12% pick rate                     │  │
│  │     → Space constraint: Zone 2 at 95% capacity                      │  │
│  │                                                                      │  │
│  │  [+] Reorganize Zone 4 for bulk storage                             │  │
│  │     → Space utilization: 73% → 89%                                  │  │
│  │     → Investment required: RM 45,000 (racking)                      │  │
│  │                                                                      │  │
│  │  [+] Implement ABC slotting optimization                            │  │
│  │     → Picking efficiency: +23% improvement                          │  │
│  │     → Implementation time: 2 weeks                                  │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Digital Twin screenshot]
Caption: Warehouse Digital Twin with Scenario Modeling
```

---

## 6. RFID & BARCODE INTEGRATION

### 6.1 RFID Scanning Interface

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📡 RFID SCANNER                                                  [Config]  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  SCANNER STATUS                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Device: Zebra RFID FX9600                                          │  │
│  │  Status: 🟢 Connected                                               │  │
│  │  Signal Strength: ████████████████████████░░░░  87%                 │  │
│  │  Last Scan: 14:32:18                                                │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  RECENT RFID TRANSACTIONS                                                   │
│  ┌────────────┬──────────────┬──────────────┬──────────────┬────────────┐ │
│  │ Time       │ EPC          │ Location     │ Action       │ Status     │ │
│  ├────────────┼──────────────┼──────────────┼──────────────┼────────────┤ │
│  │ 14:32:18   │ EPC-789234   │ Dock 4       │ INBOUND      │ ✅ Valid   │ │
│  │ 14:28:45   │ EPC-789235   │ Z2-A-05-02   │ PUT-AWAY     │ ✅ Valid   │ │
│  │ 14:25:12   │ EPC-789236   │ Z2-A-05-02   │ PUT-AWAY     │ ✅ Valid   │ │
│  │ 14:20:33   │ EPC-789237   │ Pack Station │ PICKED       │ ✅ Valid   │ │
│  └────────────┴──────────────┴──────────────┴──────────────┴────────────┘ │
│                                                                             │
│  BATCH SCAN MODE                                                            │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  📦 Place items in scan zone and press START                        │  │
│  │                                                                      │  │
│  │  [▶️ START SCAN]  [⏹️ STOP]  [🔄 RESET]                              │  │
│  │                                                                      │  │
│  │  Items Detected: 45                                                 │  │
│  │  Scanned Successfully: 44                                           │  │
│  │  Scan Errors: 1 (EPC-789238 - Duplicate read)                       │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: RFID Interface screenshot]
Caption: RFID Integration for Contactless Inventory Tracking
```

---

## 7. WAREHOUSE REPORTS

### 7.1 Inventory Accuracy Report

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📊 INVENTORY ACCURACY REPORT                                     [Export]  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  REPORT PARAMETERS                                                          │
│  Period: January 2026    Warehouse: Port Klang    Cycle Count: Monthly    │
│                                                                             │
│  ACCURACY SUMMARY                                                           │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Overall Accuracy: 99.7%  ████████████████████████████████████████  │  │
│  │  Target: 99.5%          █████████████████████████████████████░░░    │  │
│  │                                                                      │  │
│  │  Total SKUs Counted: 2,456                                          │  │
│  │  Discrepancies Found: 7                                             │  │
│  │  Net Variance Value: RM 12,450 (0.03% of total inventory)           │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  TOP VARIANCES                                                              │
│  ┌────────────┬──────────────┬──────────┬──────────┬──────────┬──────────┐ │
│  │ SKU        │ Description  │ System   │ Physical │ Variance │ Reason   │ │
│  ├────────────┼──────────────┼──────────┼──────────┼──────────┼──────────┤ │
│  │ SKU-789234 │ Motherboard  │ 350      │ 348      │ -2       │ Damaged  │ │
│  │ SKU-789256 │ RAM 32GB     │ 120      │ 125      │ +5       │ Found    │ │
│  │ SKU-789278 │ SSD 1TB      │ 85       │ 84       │ -1       │ Misplace │ │
│  └────────────┴──────────────┴──────────┴──────────┴──────────┴──────────┘ │
│                                                                             │
│  ACCURACY BY ZONE                                                             │
│  ┌────────────┬──────────────┬──────────────┬────────────────────────────┐ │
│  │ Zone       │ SKUs         │ Accuracy     │ Trend                      │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ Zone 2     │ 892          │ 99.9%        │ ↑ +0.2% vs last month      │ │
│  │ Zone 3     │ 756          │ 99.6%        │ → Same                     │ │
│  │ Zone 5     │ 808          │ 99.4%        │ ↓ -0.1% vs last month      │ │
│  └────────────┴──────────────┴──────────────┴────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: WMS Report screenshot]
Caption: Inventory Accuracy Report with Variance Analysis
```

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
