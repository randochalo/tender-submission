# ANNEX C1: HMS - HAULAGE MANAGEMENT SYSTEM EVIDENCE

**Tender Reference:** MMFSB/TD 01/2026  
**System:** Haulage Management System (HMS)  
**Version:** LogisticsPro HMS v4.2  
**Date:** 31 January 2026

---

## TABLE OF CONTENTS

1. [Dashboard & Analytics](#1-dashboard--analytics)
2. [Job Planning & Dispatch](#2-job-planning--dispatch)
3. [GPS Tracking & Fleet Management](#3-gps-tracking--fleet-management)
4. [Driver Management & Incentives](#4-driver-management--incentives)
5. [Billing & e-Invoicing](#5-billing--e-invoicing)
6. [Mobile Driver App](#6-mobile-driver-app)
7. [Reports & Enquiries](#7-reports--enquiries)

---

## 1. DASHBOARD & ANALYTICS

### 1.1 Operations Command Centre

**Feature:** Real-time dashboard with KPI widgets

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  HMS OPERATIONS COMMAND CENTRE                                    [User] ▼  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ ACTIVE JOBS      │  │ ON-TIME DELIVERY │  │ FLEET UTILIZATION│         │
│  │                  │  │                  │  │                  │         │
│  │     142          │  │      94.2%       │  │      87.5%       │         │
│  │    🚛            │  │     ↑ 2.1%       │  │     ↑ 5.3%       │         │
│  │                  │  │    vs last week  │  │    vs last week  │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │ PENDING JOBS     │  │ AVG TRIP TIME    │  │ DRIVER SCORE     │         │
│  │                  │  │                  │  │                  │         │
│  │      28          │  │    4h 23m        │  │      8.7/10      │         │
│  │    ⏱️            │  │     ↓ 12m        │  │     ↑ 0.3        │         │
│  │                  │  │    vs last week  │  │    vs last month │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────┐     │
│  │                    LIVE FLEET MAP                                 │     │
│  │                                                                   │     │
│  │    [Interactive Map Showing All 45 Active Vehicles]              │     │
│  │                                                                   │     │
│  │    🟢 On Time (38)  🟡 Delayed (5)  🔴 Issues (2)                │     │
│  │                                                                   │     │
│  └──────────────────────────────────────────────────────────────────┘     │
│                                                                             │
│  ┌──────────────────────────┐  ┌──────────────────────────────────────┐   │
│  │   UPCOMING JOBS          │  │   ALERTS & NOTIFICATIONS            │   │
│  │   ┌──────────────────┐   │  │   ⚠️ 3 PMs due for service         │   │
│  │   │ PK-HQ-001823     │   │  │   ⚠️ 2 Drivers license expiring    │   │
│  │   │ 08:30 - Container│   │  │   ✅ All permits up to date        │   │
│  │   │ pickup @ Port    │   │  │                                      │   │
│  │   └──────────────────┘   │  │                                      │   │
│  │   ┌──────────────────┐   │  │                                      │   │
│  │   │ PK-BTW-001824    │   │  │                                      │   │
│  │   │ 09:15 - Delivery │   │  │                                      │   │
│  │   │ to Butterworth   │   │  │                                      │   │
│  │   └──────────────────┘   │  │                                      │   │
│  └──────────────────────────┘  └──────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert actual HMS Dashboard screenshot here]
Caption: HMS Operations Command Centre - Real-time fleet visibility
```

**Key Features Demonstrated:**
- ✅ Real-time job count and status
- ✅ On-time delivery percentage with trend
- ✅ Fleet utilization metrics
- ✅ Interactive live fleet map
- ✅ Upcoming jobs list
- ✅ Proactive alerts and notifications

---

### 1.2 AI-Powered Natural Language Query

**Feature:** Natural language interface for data queries

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🤖 ASK HMS ANYTHING                                                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  "Show me underperforming routes this month"                          │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  [Ask]                                                                      │
│                                                                             │
│  📊 RESULTS:                                                                │
│                                                                             │
│  Underperforming Routes (Jan 2026):                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ Route              │ Avg Time │ Target │ Variance │ Impact          │   │
│  ├────────────────────┼──────────┼────────┼──────────┼─────────────────┤   │
│  │ Port Klang → Shah  │ 3h 45m   │ 3h 0m  │ +45m     │ 15 trips, -5%   │   │
│  │ Alam               │          │        │          │ efficiency      │   │
│  ├────────────────────┼──────────┼────────┼──────────┼─────────────────┤   │
│  │ Butterworth → Port │ 4h 12m   │ 3h 30m │ +42m     │ 8 trips, -8%    │   │
│  │ Klang              │          │        │          │ efficiency      │   │
│  ├────────────────────┼──────────┼────────┼──────────┼─────────────────┤   │
│  │ Padang Besar →     │ 5h 30m   │ 5h 0m  │ +30m     │ 12 trips, -3%   │   │
│  │ Butterworth        │          │        │          │ efficiency      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  💡 RECOMMENDED ACTIONS:                                                    │
│  • Consider off-peak scheduling for Port Klang → Shah Alam route           │
│  • Review driver assignments for Butterworth → Port Klang                 │
│  • Check for recurring delays at Padang Besar customs checkpoint           │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert AI Natural Language Query screenshot]
Caption: AI-Powered Natural Language Query Interface
```

---

## 2. JOB PLANNING & DISPATCH

### 2.1 Job Planning Interface

**Feature:** AI-powered job assignment and dispatch

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  JOB PLANNING & DISPATCH                                          [New Job] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  🎯 AI RECOMMENDATION                                                │  │
│  │                                                                      │  │
│  │  Job: PK-CONTAINER-001892                                           │  │
│  │  Pickup: Port Klang Container Yard                                  │  │
│  │  Delivery: MMF Warehouse, Shah Alam                                 │  │
│  │  Container: 40ft HC, Weight: 28,500 kg                              │  │
│  │                                                                      │  │
│  │  RECOMMENDED ASSIGNMENT:                                             │  │
│  │  ┌──────────┬──────────┬──────────┬──────────┬──────────────────┐   │  │
│  │  │ PM Unit  │ Driver   │ Trailer  │ Score    │ Reason           │   │  │
│  │  ├──────────┼──────────┼──────────┼──────────┼──────────────────┤   │  │
│  │  │ PM-047   │ Ali B.   │ T-892    │ 94%      │ • Nearest (2km)  │   │  │
│  │  │ (Volvo)  │ ⭐ 4.8   │ (40ft)   │          │ • Available      │   │  │
│  │  │          │          │          │          │ • Heavy load exp │   │  │
│  │  └──────────┴──────────┴──────────┴──────────┴──────────────────┘   │  │
│  │                                                                      │  │
│  │  [✅ Accept Recommendation]  [🔍 View Alternatives]  [✏️ Manual]    │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  TODAY'S DISPATCH BOARD                                                     │
│  ┌────────────┬──────────────┬──────────┬──────────┬──────────┬─────────┐  │
│  │ Job ID     │ Route        │ PM/Driver│ Status   │ ETA      │ Action  │  │
│  ├────────────┼──────────────┼──────────┼──────────┼──────────┼─────────┤  │
│  │ PK-001891  │ PK→GLD       │ PM-032   │ En Route │ 10:30    │ Track   │  │
│  │            │              │ (Ahmad)  │          │          │         │  │
│  ├────────────┼──────────────┼──────────┼──────────┼──────────┼─────────┤  │
│  │ PK-001890  │ GLD→PK       │ PM-015   │ Loading  │ 11:15    │ Details │  │
│  │            │              │ (Kumar)  │          │          │         │  │
│  ├────────────┼──────────────┼──────────┼──────────┼──────────┼─────────┤  │
│  │ PK-001892  │ PK→SA        │ PM-047   │ Assigned │ 12:00    │ Edit    │  │
│  │            │              │ (Ali)    │          │          │         │  │
│  └────────────┴──────────────┴──────────┴──────────┴──────────┴─────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Job Planning screenshot]
Caption: AI-Powered Job Planning with Recommendation Engine
```

---

### 2.2 Electronic Work Ticket

**Feature:** Digital job cards for drivers

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📱 DRIVER WORK TICKET                                          Job #1891  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  JOB DETAILS                                                         │  │
│  │                                                                      │  │
│  │  Container: MSKU 7892345 (40ft)                                     │  │
│  │  Shipper: Maersk Line                                               │  │
│  │  Cargo: Electronic Components                                       │  │
│  │  Weight: 24,500 kg                                                  │  │
│  │                                                                      │  │
│  ├──────────────────────────────────────────────────────────────────────┤  │
│  │  PICKUP                                                              │  │
│  │  📍 Northport Container Yard, Block C                               │  │
│  │  🕐 08:00 - 08:30                                                   │  │
│  │  📞 Contact: Encik Rahman (012-3456789)                             │  │
│  │  📝 Special: Container on chassis ready                             │  │
│  │                                                                      │  │
│  ├──────────────────────────────────────────────────────────────────────┤  │
│  │  DELIVERY                                                            │  │
│  │  📍 MMF Global Logistics Depot, Shah Alam                           │  │
│  │  🕐 10:30 - 11:00 (ETA)                                             │  │
│  │  📞 Contact: Puan Siti (013-9876543)                                │  │
│  │  📝 Special: Unloading bay 3, have delivery order ready             │  │
│  │                                                                      │  │
│  ├──────────────────────────────────────────────────────────────────────┤  │
│  │  [📷 Photo]  [✅ Arrived]  [📦 Loaded]  [🚛 Departed]  [🏁 Done]   │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  GPS TRACKING: 🟢 Online  📍 Lat: 3.0421, Lng: 101.3678                    │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Driver Mobile App screenshot]
Caption: Electronic Work Ticket - Driver Mobile Interface
```

---

## 3. GPS TRACKING & FLEET MANAGEMENT

### 3.1 Live GPS Tracking Dashboard

**Feature:** Real-time vehicle tracking with alerts

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  GPS FLEET TRACKING                                               [Filter] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                     │  │
│  │                         [INTERACTIVE MAP]                           │  │
│  │                                                                     │  │
│  │    🚛 PM-032    🚛 PM-015                                          │  │
│  │    Ali B.       Kumar S.                                           │  │
│  │    45 km/h      68 km/h                                            │  │
│  │                                                                     │  │
│  │            🚛 PM-047                                               │  │
│  │            Ahmad K.                                                │  │
│  │            ⚠️ IDLE 15 min                                          │  │
│  │                                                                     │  │
│  │                              🚛 PM-089                             │  │
│  │                              Sarah T.                              │  │
│  │                              🚨 OVERSPEED                          │  │
│  │                                                                     │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ACTIVE ALERTS                                                              │
│  ┌────────────┬──────────────┬──────────────┬────────────────────────────┐ │
│  │ Vehicle    │ Alert Type   │ Value        │ Action                     │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ PM-089     │ 🚨 Speeding  │ 98 km/h      │ Auto SMS sent to driver    │ │
│  │            │              │ (>90 limit)  │                            │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ PM-047     │ ⚠️ Idle      │ 15 minutes   │ Check with driver          │ │
│  │            │              │ (engine on)  │                            │ │
│  ├────────────┼──────────────┼──────────────┼────────────────────────────┤ │
│  │ PM-015     │ ℹ️ Geofence  │ Entered Port │ Logged for billing         │ │
│  │            │              │ Klang        │                            │ │
│  └────────────┴──────────────┴──────────────┴────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert GPS Tracking screenshot]
Caption: Real-Time GPS Fleet Tracking with Automated Alerts
```

---

### 3.2 Predictive Maintenance Dashboard

**Feature:** AI-powered maintenance predictions

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🔧 PREDICTIVE MAINTENANCE AI                                     [Report] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  AI PREDICTION SUMMARY                                                      │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Based on telematics analysis of 45 vehicles:                        │  │
│  │                                                                      │  │
│  │  🔴 HIGH RISK (Action Required): 2 vehicles                         │  │
│  │  🟡 MEDIUM RISK (Schedule Soon): 5 vehicles                         │  │
│  │  🟢 LOW RISK (Normal Schedule): 38 vehicles                         │  │
│  │                                                                      │  │
│  │  Prediction Accuracy: 89% (validated against actual failures)       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  PRIORITY MAINTENANCE ALERTS                                                │
│  ┌──────────┬──────────────┬───────────────┬──────────────┬──────────────┐ │
│  │ PM Unit  │ Issue        │ Probability   │ Predicted    │ Recommended  │ │
│  │          │              │ of Failure    │ Failure      │ Action       │ │
│  ├──────────┼──────────────┼───────────────┼──────────────┼──────────────┤ │
│  │ PM-023   │ Transmission │ 87%           │ Within 7     │ Schedule     │ │
│  │ (Volvo)  │ overheating  │               │ days         │ service NOW  │ │
│  ├──────────┼──────────────┼───────────────┼──────────────┼──────────────┤ │
│  │ PM-031   │ Brake wear   │ 76%           │ Within 14    │ Order parts, │ │
│  │ (Hino)   │ indicator    │               │ days         │ schedule svc │ │
│  └──────────┴──────────────┴───────────────┴──────────────┴──────────────┘ │
│                                                                             │
│  MAINTENANCE COST SAVINGS (Last 12 Months)                                  │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  Unplanned Downtime Reduction: 42%                                  │  │
│  │  Emergency Repair Cost Savings: RM 127,500                          │  │
│  │  Preventive vs Reactive Ratio: 78% vs 22%                           │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Predictive Maintenance screenshot]
Caption: AI-Powered Predictive Maintenance Dashboard
```

---

## 4. DRIVER MANAGEMENT & INCENTIVES

### 4.1 Driver Performance Dashboard

**Feature:** Comprehensive driver analytics and scoring

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  👤 DRIVER MANAGEMENT                                            [+ Driver] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  TOP PERFORMERS THIS MONTH                                                  │
│  ┌──────────┬─────────────┬──────────┬──────────┬──────────┬──────────────┐ │
│  │ Rank     │ Driver      │ Score    │ Trips    │ Safety   │ Incentive    │ │
│  ├──────────┼─────────────┼──────────┼──────────┼──────────┼──────────────┤ │
│  │ 🥇 1     │ Ahmad K.    │ 9.4/10   │ 142      │ 98%      │ RM 3,240     │ │
│  │ 🥈 2     │ Kumar S.    │ 9.2/10   │ 138      │ 96%      │ RM 3,105     │ │
│  │ 🥉 3     │ Ali B.      │ 9.1/10   │ 135      │ 97%      │ RM 2,980     │ │
│  │ 4        │ Sarah T.    │ 8.8/10   │ 128      │ 94%      │ RM 2,650     │ │
│  │ 5        │ Rajesh P.   │ 8.7/10   │ 131      │ 95%      │ RM 2,720     │ │
│  └──────────┴─────────────┴──────────┴──────────┴──────────┴──────────────┘ │
│                                                                             │
│  DRIVER SCORING COMPONENTS                                                  │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │                                                                      │  │
│  │  Ahmad Khalid (PM-047) - Detailed Score Breakdown:                  │  │
│  │                                                                      │  │
│  │  On-Time Delivery    ████████████████████████████████░░░░  94%     │  │
│  │  Safety Score        █████████████████████████████████░░░  98%     │  │
│  │  Customer Feedback   ████████████████████████████████░░░░  96%     │  │
│  │  Fuel Efficiency     ██████████████████████████████░░░░░░  88%     │  │
│  │  Documentation       █████████████████████████████████░░░  99%     │  │
│  │                                                                      │  │
│  │  OVERALL: 9.4/10 ⭐⭐⭐⭐⭐                                          │  │
│  │                                                                      │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Driver Management screenshot]
Caption: Driver Performance Dashboard with Scoring
```

---

### 4.2 Automated Incentive Calculation

**Feature:** Flexible incentive formula engine

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  💰 DRIVER INCENTIVE CALCULATION                                  [Export] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  DRIVER: Ahmad Khalid (ID: DRV-0047)                                       │
│  PERIOD: January 2026                                                      │
│                                                                             │
│  INCENTIVE BREAKDOWN                                                        │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  REVENUE MOVEMENTS                                                   │  │
│  │  ┌────────────────────────┬──────────┬──────────────┬──────────────┐ │  │
│  │  │ Type                   │ Trips    │ Base Rate    │ Amount       │ │  │
│  │  ├────────────────────────┼──────────┼──────────────┼──────────────┤ │  │
│  │  │ Container Collection   │ 45       │ RM 45/trip   │ RM 2,025     │ │  │
│  │  │ Container Delivery     │ 52       │ RM 45/trip   │ RM 2,340     │ │  │
│  │  │ Round Trip (PK-BTW)    │ 12       │ RM 120/trip  │ RM 1,440     │ │  │
│  │  └────────────────────────┴──────────┴──────────────┴──────────────┘ │  │
│  │                                                                      │  │
│  │  NON-REVENUE MOVEMENTS                                               │  │
│  │  ┌────────────────────────┬──────────┬──────────────┬──────────────┐ │  │
│  │  │ Type                   │ Count    │ Rate         │ Amount       │ │  │
│  │  ├────────────────────────┼──────────┼──────────────┼──────────────┤ │  │
│  │  │ Shunting               │ 18       │ RM 25/move   │ RM 450       │ │  │
│  │  │ PUSPAKOM Trip          │ 4        │ RM 35/trip   │ RM 140       │ │  │
│  │  │ Empty Run (Approved)   │ 8        │ RM 30/run    │ RM 240       │ │  │
│  │  └────────────────────────┴──────────┴──────────────┴──────────────┘ │  │
│  │                                                                      │  │
│  │  ADJUSTMENTS                                                         │  │
│  │  ┌────────────────────────┬─────────────────────────────────────────┐ │  │
│  │  │ Special Day Bonus (2)  │ + RM 180                                │ │  │
│  │  │ Safety Bonus           │ + RM 150                                │ │  │
│  │  │ On-Time Streak (20+)   │ + RM 300                                │ │  │
│  │  └────────────────────────┴─────────────────────────────────────────┘ │  │
│  │                                                                      │  │
│  │  TOTAL INCENTIVE: RM 7,265                                          │  │
│  │  (Auto-posted to FMS Payroll Module)                                │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Incentive Calculation screenshot]
Caption: Automated Driver Incentive Calculation Engine
```

---

## 5. BILLING & E-INVOICING

### 5.1 Invoice Generation Interface

**Feature:** Automated billing with IRBM e-Invoice compliance

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  🧾 INVOICE GENERATION                                            [Create] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  INVOICE PREVIEW                                                     │  │
│  │                                                                      │  │
│  │  Invoice #: INV-MMFSB-2026-001892                                   │  │
│  │  Date: 31 January 2026                                              │  │
│  │  Due Date: 28 February 2026                                         │  │
│  │                                                                      │  │
│  │  BILL TO:                           SHIP TO:                         │  │
│  │  Global Logistics Sdn Bhd           MMF Warehouse                    │  │
│  │  12 Jalan Universiti                Lot 45, Seksyen 23               │  │
│  │  46350 Petaling Jaya                40300 Shah Alam                  │  │
│  │  Selangor                           Selangor                         │  │
│  │                                                                      │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐ │  │
│  │  │ Line Items                                                      │ │  │
│  │  ├────────────────────┬────────┬──────────┬──────────┬────────────┤ │  │
│  │  │ Description        │ Qty    │ Unit     │ Rate     │ Amount     │ │  │
│  │  ├────────────────────┼────────┼──────────┼──────────┼────────────┤ │  │
│  │  │ Haulage Service    │ 3      │ Trip     │ RM 450   │ RM 1,350   │ │  │
│  │  │ PK → Shah Alam     │        │          │          │            │ │  │
│  │  ├────────────────────┼────────┼──────────┼──────────┼────────────┤ │  │
│  │  │ Container Handling │ 3      │ Unit     │ RM 85    │ RM 255     │ │  │
│  │  ├────────────────────┼────────┼──────────┼──────────┼────────────┤ │  │
│  │  │ Storage (3 days)   │ 3      │ Day      │ RM 120   │ RM 360     │ │  │
│  │  └────────────────────┴────────┴──────────┴──────────┴────────────┘ │  │
│  │                                                                      │  │
│  │  Subtotal:                                    RM 1,965               │  │
│  │  SST (8%):                                    RM 157.20              │  │
│  │  TOTAL:                                       RM 2,122.20            │  │
│  │                                                                      │  │
│  │  [✅ Validate e-Invoice]  [📤 Submit to MyInvois]  [📧 Email]       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  e-INVOICE STATUS: ✅ Validated | UUID: IVL-789234-20260131-001            │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Invoice Generation screenshot]
Caption: IRBM e-Invoice Compliant Billing Interface
```

---

## 6. MOBILE DRIVER APP

### 6.1 Mobile App Screens

**Feature:** iOS and Android native apps for drivers

```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│    SCREEN 1     │  │    SCREEN 2     │  │    SCREEN 3     │
│                 │  │                 │  │                 │
│  ┌───────────┐  │  │  ┌───────────┐  │  │  ┌───────────┐  │
│  │  🚛       │  │  │  │ 📍 NAVIGATE│  │  │  │ 📷 PROOF  │  │
│  │           │  │  │  │           │  │  │  │           │  │
│  │  Welcome, │  │  │  │ Turn right│  │  │  │ Upload    │  │
│  │  Ahmad    │  │  │  │ in 200m   │  │  │  │ delivery  │  │
│  │           │  │  │  │           │  │  │  │ photo     │  │
│  │  Today's  │  │  │  │ [MAP      │  │  │  │           │  │
│  │  Jobs: 5  │  │  │  │  VIEW]    │  │  │  │ [CAPTURE] │  │
│  │           │  │  │  │           │  │  │  │           │  │
│  │  [START]  │  │  │  │ ETA: 10:30│  │  │  │  ✅ Done  │  │
│  │           │  │  │  │           │  │  │  │           │  │
│  └───────────┘  │  │  └───────────┘  │  │  └───────────┘  │
│                 │  │                 │  │                 │
│  LOGIN / DASH   │  │  NAVIGATION     │  │  PROOF OF       │
│                 │  │                 │  │  DELIVERY       │
└─────────────────┘  └─────────────────┘  └─────────────────┘

[PLACEHOLDER: Insert Mobile App screenshots]
Caption: HMS Driver Mobile App - iOS/Android
```

---

## 7. REPORTS & ENQUIRIES

### 7.1 Report Library

**Feature:** 50+ standard reports with custom builder

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  📊 HMS REPORTS                                                   [Custom] │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  STANDARD REPORTS                                                           │
│  ┌────────────────────────────┬───────────────────────────────────────────┐ │
│  │ OPERATIONAL REPORTS        │ FINANCIAL REPORTS                         │ │
│  │ ☐ Trip Summary Report      │ ☐ Revenue by Vehicle                      │ │
│  │ ☐ Daily Job Report         │ ☐ Cost Per Trip Analysis                  │ │
│  │ ☐ Vehicle Utilization      │ ☐ Driver Incentive Summary                │ │
│  │ ☐ Vehicle Performance      │ ☐ Revenue Leakage Detection               │ │
│  │ ☐ Driver Performance       │ ☐ Outstanding Invoices                    │ │
│  │ ☐ Fleet Availability       │ ☐ Collections Aging                       │ │
│  │ ☐ Loading/Offloading Time  │ ☐ Fuel Cost Analysis                      │ │
│  └────────────────────────────┴───────────────────────────────────────────┘ │
│                                                                             │
│  CUSTOM REPORT BUILDER                                                      │
│  ┌──────────────────────────────────────────────────────────────────────┐  │
│  │  [+] Create New Report                                               │  │
│  │                                                                      │  │
│  │  Drag and drop fields:                                               │  │
│  │  [Job ID □] [Date □] [Driver □] [PM Unit □] [Route □] [Revenue □]  │  │
│  │                                                                      │  │
│  │  Filters:                                                            │  │
│  │  Date Range: [01/01/2026] to [31/01/2026]                           │  │
│  │  Branch: [All ▼]  Driver: [All ▼]  Status: [Completed ▼]           │  │
│  │                                                                      │  │
│  │  [🔍 Preview]  [💾 Save]  [📥 Export Excel]  [📄 Export PDF]       │  │
│  └──────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

[PLACEHOLDER: Insert Reports screenshot]
Caption: HMS Report Library with Custom Builder
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
