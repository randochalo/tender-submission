# ANNEX C2: FFS - FORWARDING MANAGEMENT SYSTEM EVIDENCE

**Tender Reference:** MMFSB/TD 01/2026  
**System:** Forwarding Management System (FFS)  
**Version:** LogisticsPro FFS v4.2  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Dashboard & Command Centre](#1-dashboard--command-centre)
2. [Shipment Management](#2-shipment-management)
3. [Documentation & BL Generation](#3-documentation--bl-generation)
4. [Customs Integration](#4-customs-integration)
5. [Freight Rate & Quotation](#5-freight-rate--quotation)
6. [EDI Integration](#6-edi-integration)
7. [Reports & Analytics](#7-reports--analytics)

---

## 1. DASHBOARD & COMMAND CENTRE

### 1.1 FFS Command Centre

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  FFS COMMAND CENTRE                                               [User] ▼  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ ACTIVE SHIPMENTS │  │ REVENUE (MTD)    │  │ PENDING CUSTOMS  │         │
│  │                  │  │                  │  │                  │         │
│  │     287          │  │  RM 4.2M         │  │      42          │         │
│  │    🚢            │  │     ↑ 12%        │  │    ⏱️            │         │
│  │                  │  │    vs last month │  │    3 urgent      │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                    SHIPMENT STATUS BREAKDOWN                        │  │
│  │                                                                     │  │
│  │  Booking ████████░░░░░░░░░░  45 (16%)                              │  │
│  │  In Transit ██████████████░░  89 (31%)                              │  │
│  │  Customs ██████░░░░░░░░░░░░░  42 (15%)                              │  │
│  │  At Warehouse ████░░░░░░░░░░  28 (10%)                              │  │
│  │  Delivered ████████████░░░░░  83 (29%)                              │  │
│  │                                                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ALERTS & EXCEPTIONS                                                        │
│  ┌────────────┬──────────────┬──────────────┬────────────────────────────┐ │
│  │ Shipment   │ Alert        │ Predicted    │ AI Confidence              │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ SH-789234  │ ⚠️ Delay Risk│ 2 days late  │ 87% - Port congestion      │ │
│  │ SH-789198  │ ⚠️ Doc Issue │ K3 missing   │ 92% - AI detected pattern  │ │
│  │ SH-789156  │ ℹ️ ETA Change│ New ETA: +1d │ 76% - Vessel rescheduled   │ │
│  └────────────┴──────────────┴──────────────┴────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: FFS Dashboard screenshot]
Caption: FFS Command Centre with AI Exception Prediction
```

---

## 2. SHIPMENT MANAGEMENT

### 2.1 Shipment Lifecycle View

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  SHIPMENT: SH-MMFSB-2026-001892                                  [Edit] [📧]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  SHIPMENT TIMELINE                                                          │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  ✅ Booking Confirmed    ✅ Goods Received    🚢 In Transit         │  │
│  │     15 Jan 2026            18 Jan 2026          20 Jan 2026         │  │
│  │                                                                      │  │
│  │  ⏳ Customs Clearance     ⏳ Delivery                              │  │
│  │     (Pending K1)           (ETA: 25 Jan)                            │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  SHIPMENT DETAILS                                                           │
│  ┌─────────────────────────┐  ┌──────────────────────────────────────────┐ │
│  │  HOUSE BL: HBL-789234   │  │  CONTAINER DETAILS                       │ │
│  │  MASTER BL: MBL-MSCU892 │  │  Container: MSKU 789234-5 (40ft HC)      │ │
│  │  Vessel: MSC OSCAR      │  │  Seal: SL789234                          │ │
│  │  Voyage: 026E           │  │  Weight: 24,500 kg                       │ │
│  │  POL: Port Klang        │  │  Commodity: Electronics                  │ │
│  │  POD: Singapore         │  │  HS Code: 8471.30.1000                   │ │
│  │  ETD: 20 Jan 2026       │  │  Dangerous Goods: No                     │ │
│  │  ETA: 25 Jan 2026       │  │                                          │ │
│  └─────────────────────────┘  └──────────────────────────────────────────┘ │
│                                                                             │
│  PARTIES                                                                    │
│  ┌──────────────────────┐  ┌──────────────────────┐  ┌──────────────────┐ │
│  │ Shipper              │  │ Consignee            │  │ Notify Party     │ │
│  │ TechCorp Sdn Bhd     │  │ Global Electronics   │  │ TechCorp         │ │
│  │ Shah Alam, Malaysia  │  │ Singapore            │  │ Singapore        │ │
│  └──────────────────────┘  └──────────────────────┘  └──────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Shipment Detail screenshot]
Caption: Shipment Lifecycle Management with Timeline View
```

---

## 3. DOCUMENTATION & BL GENERATION

### 3.1 Bill of Lading Generation

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📄 BILL OF LADING GENERATOR                                      [Preview]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  BILL OF LADING                                                      │  │
│  │                                                                      │  │
│  │  BL Number: HBL-SESB-2026-001892                                    │  │
│  │  Date: 18 January 2026                                              │  │
│  │                                                                      │  │
│  │  SHIPPER:                          CONSIGNEE:                        │  │
│  │  TechCorp Sdn Bhd                  Global Electronics Pte Ltd       │  │
│  │  Lot 12, Jalan Teknologi 3         45 Science Park Drive            │  │
│  │  47500 Subang Jaya                 Singapore 118259                 │  │
│  │  Selangor, Malaysia                                                  │  │
│  │                                                                      │  │
│  │  NOTIFY PARTY:                                                       │  │
│  │  Same as Consignee                                                   │  │
│  │                                                                      │  │
│  │  ┌────────────────────────────────────────────────────────────────┐ │  │
│  │  │ DESCRIPTION OF GOODS                                           │ │  │
│  │  ├────────────────────────────────────────────────────────────────┤ │  │
│  │  │ Container No: MSKU 789234-5                                    │ │  │
│  │  │ Seal No: SL789234                                              │ │  │
│  │  │                                                                │ │  │
│  │  │ 500 CTNS COMPUTER PARTS                                        │ │  │
│  │  │ HS CODE: 8471.30.1000                                          │ │  │
│  │  │                                                                │ │  │
│  │  │ GROSS WEIGHT: 24,500 KGS                                       │ │  │
│  │  │ MEASUREMENT: 65.5 CBM                                          │ │  │
│  │  └────────────────────────────────────────────────────────────────┘ │  │
│  │                                                                      │  │
│  │  Place of Receipt: Port Klang                                       │  │
│  │  Port of Loading: Port Klang                                        │  │
│  │  Port of Discharge: Singapore                                       │  │
│  │  Place of Delivery: Singapore                                       │  │
│  │                                                                      │  │
│  │  Freight Terms: PREPAID                                             │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [✏️ Edit]  [🖊️ Digital Sign]  [📤 Submit to Blockchain]  [📧 Email]      │
│                                                                             │
│  Blockchain Verification: ✅ Document hash recorded at Block #7823451      │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: BL Generation screenshot]
Caption: Automated Bill of Lading with Blockchain Verification
```

---

## 4. CUSTOMS INTEGRATION

### 4.1 MyGBS (uCustoms) Integration

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🛃 CUSTOMS CLEARANCE - MyGBS                                      [Refresh]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  DECLARATION STATUS                                                  │  │
│  │                                                                      │  │
│  │  Customs Ref: K1-2026-001892-45                                     │  │
│  │  Status: 🟡 PENDING INSPECTION                                       │  │
│  │  Last Updated: 22 Jan 2026 14:32:18                                 │  │
│  │                                                                      │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐ │  │
│  │  │ TIMELINE:                                                       │ │  │
│  │  ├─────────────────────────────────────────────────────────────────┤ │  │
│  │  │ ✅ Declaration Submitted       20 Jan 2026 09:15               │ │  │
│  │  │ ✅ Document Verified           20 Jan 2026 11:30               │ │  │
│  │  │ ✅ Duty Calculated             20 Jan 2026 11:45               │ │  │
│  │  │ ✅ Duty Paid                   20 Jan 2026 14:00               │ │  │
│  │  │ ⏳ Physical Inspection         (Pending)                        │ │  │
│  │  │ ⏳ Release Approval            (Pending)                        │ │  │
│  │  └─────────────────────────────────────────────────────────────────┘ │  │
│  │                                                                      │  │
│  │  [📤 Resubmit Documents]  [💬 Message Customs]  [📞 Escalate]       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ASSOCIATED DOCUMENTS                                                       │
│  ┌──────────────┬──────────────┬──────────────┬──────────────────────────┐ │
│  │ Document     │ Status       │ Customs Ref  │ Action                   │ │
│  ├──────────────┼──────────────┼──────────────┼──────────────────────────┤ │
│  │ K1 Form      │ ✅ Approved  │ K1-2026-001  │ View                     │ │
│  │ Invoice      │ ✅ Approved  │ K1-2026-001  │ View                     │ │
│  │ Packing List │ ✅ Approved  │ K1-2026-001  │ View                     │ │
│  │ COO          │ ⚠️ Query     │ K1-2026-001  │ Respond                  │ │
│  └──────────────┴──────────────┴──────────────┴──────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Customs Integration screenshot]
Caption: Real-time MyGBS Customs Status Integration
```

---

## 5. FREIGHT RATE & QUOTATION

### 5.1 Automated Quotation Engine

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  💰 FREIGHT QUOTATION                                            [History] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  QUOTATION REQUEST                                                   │  │
│  │                                                                      │  │
│  │  Customer: Global Logistics Sdn Bhd                                 │  │
│  │  Route: Port Klang → Singapore                                      │  │
│  │  Mode: Sea Freight (FCL)                                            │  │
│  │  Container: 40ft HC                                                 │  │
│  │  Cargo: Electronics (Non-DG)                                        │  │
│  │  Weight: 24,500 kg                                                  │  │
│  │                                                                      │  │
│  │  [🔍 Get Instant Quote]                                             │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  AI-GENERATED QUOTATION OPTIONS                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  OPTION 1: ECONOMY (Recommended)                                    │  │
│  │  ┌────────────┬────────────┬────────────┬──────────┬──────────────┐ │  │
│  │  │ Carrier    │ Transit    │ Rate       │ Total    │ Valid Until  │ │  │
│  │  ├────────────┼────────────┼────────────┼──────────┼──────────────┤ │  │
│  │  │ MSC        │ 5 days     │ RM 1,850   │ RM 2,405 │ 15 Feb 2026  │ │  │
│  │  └────────────┴────────────┴────────────┴──────────┴──────────────┘ │  │
│  │  [✅ Select This Option]                                            │  │
│  │                                                                      │  │
│  │  OPTION 2: PREMIUM                                                  │  │
│  │  ┌────────────┬────────────┬────────────┬──────────┬──────────────┐ │  │
│  │  │ Carrier    │ Transit    │ Rate       │ Total    │ Valid Until  │ │  │
│  │  ├────────────┼────────────┼────────────┼──────────┼──────────────┤ │  │
│  │  │ Maersk     │ 3 days     │ RM 2,450   │ RM 3,185 │ 15 Feb 2026  │ │  │
│  │  └────────────┴────────────┴────────────┴──────────┴──────────────┘ │  │
│  │  [✅ Select This Option]                                            │  │
│  │                                                                      │  │
│  │  💡 AI RECOMMENDATION: Based on customer's history (12 shipments    │  │
│  │     with MSC, on-time preference), Option 1 is 94% likely to be     │  │
│  │     accepted while maximizing margin by 8.5%.                       │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Quotation Engine screenshot]
Caption: AI-Powered Freight Quotation with Rate Comparison
```

---

## 6. EDI INTEGRATION

### 6.1 EDI Message Monitor

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📡 EDI MESSAGE MONITOR                                          [Settings]│
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  EDI TRAFFIC (Last 24 Hours)                                                │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Messages In: 1,247    Messages Out: 892    Success Rate: 99.8%     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  RECENT TRANSACTIONS                                                        │
│  ┌────────────┬────────────┬──────────────┬──────────────┬──────────────┐ │
│  │ Time       │ Partner    │ Message Type │ Status       │ Ref          │ │
│  ├────────────┼────────────┼──────────────┼──────────────┼──────────────┤ │
│  │ 14:32:18   │ Maersk     │ BOOKING      │ ✅ Accepted  │ BKG-789234   │ │
│  │ 14:28:45   │ MSC        │ COPARN       │ ✅ Processed │ COP-892345   │ │
│  │ 14:15:22   │ Port Klang │ CODECO       │ ✅ Received  │ CDE-456789   │ │
│  │ 14:10:08   │ MyGBS      │ CUSDEC       │ ✅ Validated │ K1-789234    │ │
│  │ 13:58:33   │ Customer A │ IFTMIN       │ ✅ Processed │ IFT-123456   │ │
│  └────────────┴────────────┴──────────────┴──────────────┴──────────────┘ │
│                                                                             │
│  EDI PARTNERS                                                               │
│  ┌────────────────┬────────────────┬────────────────┬──────────────────┐   │
│  │ Partner        │ Standard       │ Connection     │ Status           │   │
│  ├────────────────┼────────────────┼────────────────┼──────────────────┤   │
│  │ Maersk Line    │ EDIFACT        │ API + SFTP     │ 🟢 Active        │   │
│  │ MSC            │ EDIFACT        │ API            │ 🟢 Active        │   │
│  │ CMA CGM        │ XML API        │ REST           │ 🟢 Active        │   │
│  │ Port Klang PCS │ Custom XML     │ SFTP           │ 🟢 Active        │   │
│  │ MyGBS          │ SOAP           │ Web Service    │ 🟢 Active        │   │
│  └────────────────┴────────────────┴────────────────┴──────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: EDI Monitor screenshot]
Caption: Real-time EDI Transaction Monitoring
```

---

## 7. REPORTS & ANALYTICS

### 7.1 Revenue Intelligence Dashboard

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📊 REVENUE INTELLIGENCE                                          [Export] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  REVENUE BY TRADE LANE (YTD 2026)                                           │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                     │  │
│  │  Port Klang → Singapore    ████████████████████████░░░░  RM 12.4M  │  │
│  │  Port Klang → China        ████████████████░░░░░░░░░░░░  RM 8.2M   │  │
│  │  Port Klang → Australia    ██████████░░░░░░░░░░░░░░░░░░  RM 5.1M   │  │
│  │  Port Klang → Europe       ████████░░░░░░░░░░░░░░░░░░░░  RM 4.3M   │  │
│  │  Others                    ████░░░░░░░░░░░░░░░░░░░░░░░░  RM 2.1M   │  │
│  │                                                                     │  │
│  │  TOTAL: RM 32.1M (+15% vs 2025)                                    │  │
│  │                                                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  💡 AI INSIGHTS                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  🔍 Revenue Opportunity Detected:                                   │  │
│  │  Customer "TechCorp Sdn Bhd" has reduced shipments by 23%           │  │
│  │  compared to Q4 2025. Consider proactive outreach.                  │  │
│  │                                                                      │  │
│  │  💰 Cross-sell Opportunity:                                         │  │
│  │  34 customers using only sea freight could benefit from             │  │
│  │  air freight for urgent shipments. Potential revenue: RM 450K       │  │
│  │                                                                      │  │
│  │  ⚠️ Margin Alert:                                                   │  │
│  │  China lane margins dropped 4.2% due to rate increases.             │  │
│  │  Recommend rate renegotiation or surcharges.                        │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Revenue Intelligence screenshot]
Caption: AI-Powered Revenue Intelligence with Opportunity Detection
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
