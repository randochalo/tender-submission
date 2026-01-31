# ANNEX G: USER ACCEPTANCE TEST (UAT) SCRIPTS

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** LogisticsPro Enterprise Suite v4.2  
**Date:** 31 January 2026  
**Test Phase:** User Acceptance Testing (UAT)

---

## TABLE OF CONTENTS

1. [UAT Overview](#1-uat-overview)
2. [HMS Test Scripts (19 Test Cases)](#2-hms-test-scripts)
3. [FFS Test Scripts (21 Test Cases)](#3-ffs-test-scripts)
4. [WMS Test Scripts (27 Test Cases)](#4-wms-test-scripts)
5. [TMS Test Scripts (25 Test Cases)](#5-tms-test-scripts)
6. [FMS Test Scripts (37 Test Cases)](#6-fms-test-scripts)
7. [Integration Test Scripts](#7-integration-test-scripts)
8. [UAT Execution Plan](#8-uat-execution-plan)

---

## 1. UAT OVERVIEW

### 1.1 UAT Objectives

| Objective | Description |
|-----------|-------------|
| **Validate Requirements** | Verify all 129 requirements function as specified |
| **User Validation** | Confirm system meets end-user operational needs |
| **Integration Testing** | Validate inter-module data flow and processes |
| **Performance Check** | Ensure system performs under realistic load |
| **Acceptance Sign-off** | Obtain formal acceptance from MMF stakeholders |

### 1.2 Test Environment

| Component | Specification |
|-----------|---------------|
| **Environment** | UAT - Staging (uat.logisticspro.com) |
| **Database** | UAT Database (refreshed from production sample) |
| **Integration** | Connected to test sandboxes (MyInvois sandbox, MyGBS test) |
| **Data** | Anonymized production data (6 months history) |
| **Access** | 25 test user accounts provisioned |

### 1.3 Test Case Summary

| System | Requirements | Test Cases | Priority |
|--------|--------------|------------|----------|
| HMS | 19 | 45 | High |
| FFS | 21 | 52 | High |
| WMS | 27 | 68 | High |
| TMS | 25 | 61 | High |
| FMS | 37 | 89 | High |
| **Integration** | - | 25 | Critical |
| **TOTAL** | **129** | **340** | - |

---

## 2. HMS TEST SCRIPTS

### TC-HMS-001: Dashboards & Analytics

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-001 |
| **Requirement Ref** | C1-1 |
| **Feature** | Dashboards & Analytics |
| **Priority** | High |

**Test Scenario:**
Verify Operations Command Centre displays real-time KPIs and allows interactive drill-down.

**Preconditions:**
- User logged in with Operations Manager role
- Active jobs exist in system (minimum 10)
- Historical data available (minimum 30 days)

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to HMS Dashboard | Dashboard loads within 3 seconds | ⬜ |
| 2 | Verify Active Jobs widget displays current count | Count matches database query | ⬜ |
| 3 | Verify On-Time Delivery percentage | Percentage calculated correctly | ⬜ |
| 4 | Verify Fleet Utilization gauge | Gauge shows percentage with color coding | ⬜ |
| 5 | Click on Live Fleet Map | Map displays with vehicle markers | ⬜ |
| 6 | Click on a vehicle marker | Vehicle details popup appears | ⬜ |
| 7 | Click on Upcoming Jobs list | List displays jobs sorted by time | ⬜ |
| 8 | Verify Alerts panel displays warnings | Any active alerts shown with icons | ⬜ |
| 9 | Refresh page after 5 minutes | All metrics updated automatically | ⬜ |
| 10 | Test responsiveness on different screen sizes | Layout adjusts correctly | ⬜ |

**Expected Results:**
- All KPIs display accurately
- Map is interactive and responsive
- Data refreshes automatically
- UI is responsive across devices

**Pass Criteria:**
All steps execute without errors and data displays correctly.

---

### TC-HMS-002: AI Natural Language Query

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-002 |
| **Requirement Ref** | C1-1-Enh |
| **Feature** | AI-Powered Natural Language Query |
| **Priority** | Medium |

**Test Scenario:**
Verify AI understands natural language queries and returns relevant data visualizations.

**Preconditions:**
- Dashboard module accessible
- Minimum 100 historical trips in database

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click on "Ask HMS Anything" input | Input field activates | ⬜ |
| 2 | Type "Show me underperforming routes this month" | AI processes query | ⬜ |
| 3 | Submit query | Results display within 5 seconds | ⬜ |
| 4 | Verify route performance table appears | Table shows routes with variance | ⬜ |
| 5 | Type "Compare fuel efficiency across branches" | New results display | ⬜ |
| 6 | Verify comparison chart appears | Bar chart with branch comparison | ⬜ |
| 7 | Type "What is the average trip time for Port Klang to Shah Alam" | Specific metric returned | ⬜ |
| 8 | Verify metric accuracy | Matches calculated average | ⬜ |
| 9 | Test ambiguous query handling | AI asks for clarification | ⬜ |
| 10 | Test unsupported query | Friendly error message displayed | ⬜ |

**Pass Criteria:**
AI correctly interprets 80%+ of test queries.

---

### TC-HMS-003: Multi-Platform Interface

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-003 |
| **Requirement Ref** | C1-2 |
| **Feature** | Multi-Platform Interface |
| **Priority** | High |

**Test Scenario:**
Verify system functions across desktop, tablet, and mobile devices.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Access HMS via Chrome on Desktop | System loads correctly | ⬜ |
| 2 | Access HMS via Safari on Mac | System loads correctly | ⬜ |
| 3 | Access HMS via Edge on Windows | System loads correctly | ⬜ |
| 4 | Access HMS on iPad (Portrait) | Responsive layout activates | ⬜ |
| 5 | Access HMS on iPad (Landscape) | Layout adjusts for width | ⬜ |
| 6 | Access HMS on Android tablet | System loads and functions | ⬜ |
| 7 | Test touch interactions on tablet | Touch gestures work | ⬜ |
| 8 | Verify all menus accessible on mobile | Hamburger menu functions | ⬜ |
| 9 | Test form inputs on mobile | Keyboard types appropriate | ⬜ |
| 10 | Verify data syncs across devices | Changes reflect on all devices | ⬜ |

**Pass Criteria:**
System is fully functional on all tested platforms.

---

### TC-HMS-004: GPS Tracking Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-004 |
| **Requirement Ref** | C1-17 |
| **Feature** | Automated Prime Mover Tracking via GPS |
| **Priority** | High |

**Test Scenario:**
Verify real-time GPS tracking, speed monitoring, idle detection, and alerts.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Open GPS Fleet Tracking page | Map loads with vehicle icons | ⬜ |
| 2 | Verify vehicle positions update | Locations refresh every 30s | ⬜ |
| 3 | Click on vehicle PM-047 | Vehicle details panel opens | ⬜ |
| 4 | Verify speed display | Speed matches GPS data | ⬜ |
| 5 | Simulate speed >90 km/h | Overspeed alert triggers | ⬜ |
| 6 | Verify SMS/email sent to driver | Notification logged | ⬜ |
| 7 | Simulate idle condition (engine on, no movement) | Idle alert triggers after threshold | ⬜ |
| 8 | Test geofence entry/exit | Alert generated on boundary crossing | ⬜ |
| 9 | View route history for PM-047 | Historical path displayed | ⬜ |
| 10 | Export GPS data | CSV/Excel file generated | ⬜ |

**Pass Criteria:**
All GPS functions work with <5 second latency.

---

### TC-HMS-005: Driver Incentive Calculation

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-005 |
| **Requirement Ref** | C1-18 |
| **Feature** | Automated Driver Incentive |
| **Priority** | High |

**Test Scenario:**
Verify automated incentive calculation with multiple formula support.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to Driver Incentive module | Module loads | ⬜ |
| 2 | Select driver Ahmad Khalid | Driver profile displays | ⬜ |
| 3 | Select period: January 2026 | Period data loads | ⬜ |
| 4 | Verify container collection trips counted | 45 trips × RM 45 = RM 2,025 | ⬜ |
| 5 | Verify container delivery trips counted | 52 trips × RM 45 = RM 2,340 | ⬜ |
| 6 | Verify round trips calculated | 12 trips × RM 120 = RM 1,440 | ⬜ |
| 7 | Verify non-revenue movements counted | Shunting: 18 × RM 25 = RM 450 | ⬜ |
| 8 | Verify special day bonuses applied | Bonus amounts added | ⬜ |
| 9 | Verify total incentive calculation | Sum of all components correct | ⬜ |
| 10 | Verify auto-post to FMS Payroll | Payroll record created | ⬜ |
| 11 | Generate incentive report | PDF report generated | ⬜ |

**Expected Calculation:**
- Revenue Trips: RM 5,805
- Non-Revenue: RM 590
- Bonuses: RM 630
- **Total: RM 7,025**

**Pass Criteria:**
Calculated incentive matches expected amount exactly.

---

### TC-HMS-006: Credit & Collections Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-006 |
| **Requirement Ref** | C1-7, C1-8 |
| **Feature** | Credit Control & Automated Locking |
| **Priority** | High |

**Test Scenario:**
Verify credit limit enforcement and automated locking for overdue customers.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create customer with RM 100,000 credit limit | Customer created successfully | ⬜ |
| 2 | Record invoices totaling RM 80,000 | Balance shows RM 80,000 | ⬜ |
| 3 | Attempt job for RM 25,000 | Warning: Credit limit exceeded | ⬜ |
| 4 | Verify system blocks job creation | Block message displayed | ⬜ |
| 5 | Process payment of RM 30,000 | Balance reduces to RM 50,000 | ⬜ |
| 6 | Attempt job for RM 25,000 | Job created successfully | ⬜ |
| 7 | Simulate overdue by 60 days | Account flagged as overdue | ⬜ |
| 8 | Attempt new job | System blocks with overdue message | ⬜ |
| 9 | Test override with manager approval | Override workflow triggered | ⬜ |
| 10 | Verify audit trail of override | Log entry created | ⬜ |
| 11 | Generate aging report | Report shows accurate aging buckets | ⬜ |

**Pass Criteria:**
Credit controls enforced accurately with proper audit trails.

---

### TC-HMS-007: IRBM e-Invoicing

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-007 |
| **Requirement Ref** | C1-6 |
| **Feature** | Automated Invoice & e-Invoicing |
| **Priority** | Critical |

**Test Scenario:**
Verify automated invoice generation and IRBM MyInvois submission.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Complete haulage job | Job status: Completed | ⬜ |
| 2 | Trigger billing | Invoice auto-generated | ⬜ |
| 3 | Verify invoice calculations | Subtotal + SST = Total | ⬜ |
| 4 | Click "Validate for MyInvois" | Validation runs | ⬜ |
| 5 | Verify TIN format validated | Validation passed | ⬜ |
| 6 | Verify SST registration checked | Status: Active | ⬜ |
| 7 | Click "Submit to MyInvois" | Submission sent | ⬜ |
| 8 | Receive IRBM response | UUID assigned | ⬜ |
| 9 | Verify QR code generated | QR code displayed on invoice | ⬜ |
| 10 | Email invoice to customer | Email sent with PDF attachment | ⬜ |
| 11 | Verify invoice status updated | Status: Submitted to IRBM | ⬜ |

**Pass Criteria:**
e-Invoice accepted by IRBM MyInvois with valid UUID.

---

### TC-HMS-008: Job Planning with AI

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-008 |
| **Requirement Ref** | C1-15 |
| **Feature** | Job Planning/PM Assignment |
| **Priority** | High |

**Test Scenario:**
Verify AI-powered job assignment with optimization.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create new job: PK → Shah Alam | Job creation form opens | ⬜ |
| 2 | Enter container details (40ft, 25,000kg) | Details saved | ⬜ |
| 3 | Click "Get AI Recommendation" | AI analyzes options | ⬜ |
| 4 | Verify PM recommendation appears | Recommended PM listed with score | ⬜ |
| 5 | Verify driver assignment | Driver matched to PM | ⬜ |
| 6 | Review recommendation reasoning | Factors listed (proximity, availability) | ⬜ |
| 7 | Accept AI recommendation | Job assigned to recommended PM | ⬜ |
| 8 | Test manual override | Alternative PMs listed | ⬜ |
| 9 | Reschedule job | New time slot options shown | ⬜ |
| 10 | Transfer trip to backup team | Trip reassigned successfully | ⬜ |

**Pass Criteria:**
AI recommendations are logical and can be overridden.

---

### TC-HMS-009: Electronic Work Ticket

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-009 |
| **Requirement Ref** | C1-14 |
| **Feature** | Electronic Work Ticket |
| **Priority** | High |

**Test Scenario:**
Verify digital job cards on driver mobile app.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Driver login to mobile app | App authenticates | ⬜ |
| 2 | View today's assigned jobs | Job list displays | ⬜ |
| 3 | Select job PK-001892 | Work ticket opens | ⬜ |
| 4 | Verify job details displayed | Container, pickup, delivery shown | ⬜ |
| 5 | Click "Arrived at Pickup" | Status updates, timestamp recorded | ⬜ |
| 6 | Click "Loaded" | Status updates, photo option shown | ⬜ |
| 7 | Upload container photo | Photo attached to job record | ⬜ |
| 8 | Click "Departed" | GPS location recorded | ⬜ |
| 9 | Navigate to delivery | GPS directions displayed | ⬜ |
| 10 | Click "Delivered" + capture signature | POD completed | ⬜ |
| 11 | Verify timestamp and location | Data accurate | ⬜ |

**Pass Criteria:**
All status updates recorded with timestamp and GPS.

---

### TC-HMS-010: Predictive Maintenance AI

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HMS-010 |
| **Requirement Ref** | C1-17-Enh |
| **Feature** | Predictive Maintenance AI |
| **Priority** | Medium |

**Test Scenario:**
Verify AI predicts vehicle maintenance needs based on telematics.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to Predictive Maintenance dashboard | Dashboard loads | ⬜ |
| 2 | View AI prediction summary | Risk categories displayed | ⬜ |
| 3 | Click on HIGH RISK vehicle | Vehicle details shown | ⬜ |
| 4 | Review predicted issue | Issue type and probability shown | ⬜ |
| 5 | Verify predicted failure timeframe | Days until predicted failure | ⬜ |
| 6 | View recommended action | Maintenance action listed | ⬜ |
| 7 | Click "Schedule Service" | Service booking form opens | ⬜ |
| 8 | View maintenance cost savings | Historical savings displayed | ⬜ |
| 9 | Export maintenance schedule | Excel file generated | ⬜ |

**Pass Criteria:**
AI predictions are actionable and include confidence scores.

---

## 3. FFS TEST SCRIPTS

### TC-FFS-001: Shipment Exception Prediction AI

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FFS-001 |
| **Requirement Ref** | C2-1-Enh |
| **Feature** | Shipment Exception Prediction |
| **Priority** | Medium |

**Test Scenario:**
Verify AI predicts shipment delays before they occur.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to FFS Command Centre | Dashboard loads | ⬜ |
| 2 | View AI Insights panel | Active predictions displayed | ⬜ |
| 3 | Click on delay risk alert | Shipment details shown | ⬜ |
| 4 | View predicted delay duration | Hours of delay shown | ⬜ |
| 5 | View confidence percentage | 87% confidence displayed | ⬜ |
| 6 | View predicted reason | "Port congestion" or similar | ⬜ |
| 7 | Click proactive notification | Customer notification drafted | ⬜ |
| 8 | Send delay notification | Email/SMS sent to customer | ⬜ |
| 9 | View prediction accuracy history | Historical accuracy stats shown | ⬜ |

**Pass Criteria:**
AI predicts delays with >80% accuracy.

---

### TC-FFS-002: BL Auto-Generation with Blockchain

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FFS-002 |
| **Requirement Ref** | C2-17, C2-17-Enh |
| **Feature** | Bill of Lading Generation + Blockchain Verification |
| **Priority** | High |

**Test Scenario:**
Verify automated BL generation with blockchain document verification.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create new shipment booking | Booking saved | ⬜ |
| 2 | Enter shipper/consignee details | Details validated | ⬜ |
| 3 | Enter cargo details | Auto-populated from booking | ⬜ |
| 4 | Click "Generate BL" | BL draft created | ⬜ |
| 5 | Review BL content | All fields accurate | ⬜ |
| 6 | Click "Digital Sign" | Signature applied | ⬜ |
| 7 | Submit to blockchain | Transaction submitted | ⬜ |
| 8 | Receive blockchain confirmation | Block number assigned | ⬜ |
| 9 | Verify QR code generated | QR code contains hash | ⬜ |
| 10 | Scan QR code with verifier | Document authenticity confirmed | ⬜ |
| 11 | Email BL to customer | PDF with QR code sent | ⬜ |

**Pass Criteria:**
BL generated and blockchain verification successful.

---

### TC-FFS-003: MyGBS Customs Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FFS-003 |
| **Requirement Ref** | C2-3, C2-17 |
| **Feature** | MyGBS Customs Declaration |
| **Priority** | Critical |

**Test Scenario:**
Verify automated customs declaration submission and status tracking.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create import shipment | Shipment created | ⬜ |
| 2 | Click "Submit K1 Declaration" | Declaration form opens | ⬜ |
| 3 | Verify HS code lookup | Auto-suggestion works | ⬜ |
| 4 | Enter cargo value and weight | Calculations auto-updated | ┮ |
| 5 | Submit to MyGBS | API call initiated | ⬜ |
| 6 | Receive customs reference | K1-2026-XXXXX assigned | ⬜ |
| 7 | Check declaration status | Status: Submitted | ⬜ |
| 8 | Auto-refresh status | Status updates to "Verified" | ⬜ |
| 9 | View duty calculation | Import duty displayed | ⬜ |
| 10 | Receive customs clearance | Status: Cleared | ⬜ |
| 11 | View complete audit trail | All status changes logged | ⬜ |

**Pass Criteria:**
Declaration submitted and cleared through MyGBS.

---

### TC-FFS-004: Revenue Intelligence Module

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FFS-004 |
| **Requirement Ref** | C2-1-Enh |
| **Feature** | Revenue Intelligence & Cross-sell |
| **Priority** | Medium |

**Test Scenario:**
Verify AI identifies revenue opportunities and cross-sell recommendations.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to Revenue Intelligence dashboard | Dashboard loads | ⬜ |
| 2 | View "At-Risk Customers" section | Declining customers listed | ⬜ |
| 3 | Click on customer with 23% decline | Customer details shown | ⬜ |
| 4 | View recommended action | "Proactive outreach" suggested | ⬜ |
| 5 | View cross-sell opportunities | 34 customers identified | ⬜ |
| 6 | Click opportunity | Revenue potential: RM 450K | ⬜ |
| 7 | Generate customer proposal | Proposal template auto-filled | ⬜ |
| 8 | View margin alerts | China lane margin drop flagged | ⬜ |
| 9 | View recommended rate adjustment | Suggested surcharge shown | ⬜ |

**Pass Criteria:**
AI insights are actionable and specific.

---

## 4. WMS TEST SCRIPTS

### TC-WMS-001: Digital Twin Visualization

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-WMS-001 |
| **Requirement Ref** | C3-1-Enh |
| **Feature** | Warehouse Digital Twin |
| **Priority** | Medium |

**Test Scenario:**
Verify 3D warehouse visualization with real-time data.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to WMS Control Tower | Dashboard loads | ⬜ |
| 2 | Click "3D Warehouse View" | Digital twin loads | ⬜ |
| 3 | Rotate view | 3D model rotates smoothly | ⬜ |
| 4 | Zoom to Zone 2 | Zone details visible | ⬜ |
| 5 | View occupancy by color | Full slots dark, empty light | ⬜ |
| 6 | View active pickers | 3 pickers shown in Zone 2 | ⬜ |
| 7 | View dock status | Dock 4: Loading displayed | ⬜ |
| 8 | Click on location Z2-A-05-02 | Inventory details popup | ⬜ |
| 9 | Run "What-if" scenario | Scenario modeling panel opens | ⬜ |
| 10 | Add 20% SKUs to Zone 2 | Efficiency prediction shown | ⬜ |

**Pass Criteria:**
3D visualization is interactive and data-accurate.

---

### TC-WMS-002: AI Slotting Optimizer

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-WMS-002 |
| **Requirement Ref** | C3-17, C3-17-Enh |
| **Feature** | AI Put-away Optimization |
| **Priority** | High |

**Test Scenario:**
Verify AI recommends optimal storage locations.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create goods receipt for SKU-789234 | ASN line created | ⬜ |
| 2 | Verify item velocity data | 42 picks/week displayed | ⬜ |
| 3 | Click "Get AI Recommendation" | AI analyzes | ⬜ |
| 4 | View recommended location | Z2-A-05-04 recommended | ⬜ |
| 5 | Review optimization factors | 4 factors listed | ⬜ |
| 6 | Verify reasoning | "Closest to packing station" | ⬜ |
| 7 | View travel distance savings | 45m saved vs alternative | ⬜ |
| 8 | Accept recommendation | Location assigned | ⬜ |
| 9 | Test manual override | Manual selection allowed | ⬜ |
| 10 | Complete put-away | Stock updated in location | ⬜ |

**Pass Criteria:**
AI recommendations improve efficiency by 20%+.

---

### TC-WMS-003: Pick Path Optimization

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-WMS-003 |
| **Requirement Ref** | C3-19 |
| **Feature** | Order Picking with Path Optimization |
| **Priority** | High |

**Test Scenario:**
Verify AI optimizes pick sequence to minimize travel distance.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create pick wave with 10 orders | Wave created | ⬜ |
| 2 | Click "Optimize Pick Path" | AI calculates | ⬜ |
| 3 | View optimized sequence | Items ordered by location | ⬜ |
| 4 | View total travel distance | 350m shown | ⬜ |
| 5 | View unoptimized comparison | 520m (33% savings) | ⬜ |
| 6 | Assign picker Ahmad | Pick list sent to RF scanner | ⬜ |
| 7 | Picker scans first location | Correct item confirmed | ⬜ |
| 8 | Follow pick sequence | Sequential locations logical | ⬜ |
| 9 | Complete all picks | 99.9% accuracy achieved | ⬜ |
| 10 | View productivity report | Picks/hour calculated | ⬜ |

**Pass Criteria:**
Pick path optimized with measurable travel reduction.

---

### TC-WMS-004: RFID Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-WMS-004 |
| **Requirement Ref** | C3-12 |
| **Feature** | RFID Scanning & Tracking |
| **Priority** | High |

**Test Scenario:**
Verify RFID tag reading for inventory operations.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Connect RFID scanner | Device connected | ⬜ |
| 2 | Scan inbound pallet | EPC code captured | ⬜ |
| 3 | Verify item details | SKU-789234 displayed | ⬜ |
| 4 | Scan put-away location | Location confirmed | ⬜ |
| 5 | Complete put-away | Stock updated | ⬜ |
| 6 | Use batch scan mode | 45 items detected | ⬜ |
| 7 | Review scan results | 44 success, 1 duplicate | ⬜ |
| 8 | Handle duplicate read | System resolves conflict | ⬜ |
| 9 | View RFID transaction log | All scans logged | ⬜ |
| 10 | Run inventory cycle count | Count matches system | ⬜ |

**Pass Criteria:**
RFID scanning 99%+ accurate with <2 second read time.

---

## 5. TMS TEST SCRIPTS

### TC-TMS-001: Yard Slotting AI

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-TMS-001 |
| **Requirement Ref** | C4-16, C4-16-Enh |
| **Feature** | AI Container Slotting |
| **Priority** | High |

**Test Scenario:**
Verify AI recommends optimal yard positions for containers.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Gate-in container MSKU 7892345 | Container recorded | ⬜ |
| 2 | Click "Get AI Recommendation" | AI analyzes | ⬜ |
| 3 | View recommended block/row/slot | Block C-08-04 (94% confidence) | ⬜ |
| 4 | Review optimization factors | Dwell time, vessel schedule, weight | ⬜ |
| 5 | View rehandle savings | 1 rehandle saved | ⬜ |
| 6 | View yard travel reduction | 45m reduced | ⬜ |
| 7 | Accept recommendation | Slot assigned | ⬜ |
| 8 | View alternative locations | 2 alternatives shown | ⬜ |
| 9 | Test manual override | Manual selection allowed | ⬜ |
| 10 | Complete stacking | Container position updated | ⬜ |

**Pass Criteria:**
AI slotting reduces rehandles by 25%+.

---

### TC-TMS-002: Gate Operations Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-TMS-002 |
| **Requirement Ref** | C4-19 |
| **Feature** | Gate-In with Weighbridge & Customs |
| **Priority** | High |

**Test Scenario:**
Verify integrated gate processing with weighbridge and customs.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Truck PM-047 arrives at gate | License plate recognized | ⬜ |
| 2 | Enter container number | MSKU 7892345 validated | ⬜ |
| 3 | Capture gross weight from weighbridge | 32,450 kg auto-captured | ⬜ |
| 4 | System calculates net weight | 24,500 kg displayed | ⬜ |
| 5 | Verify weight matches booking | Match confirmed | ⬜ |
| 6 | Query MyGBS customs status | K1-2026-001892: Cleared | ⬜ |
| 7 | Verify customs permission | Import allowed | ⬜ |
| 8 | Capture gate-in photo | Photo saved | ⬜ |
| 9 | Print gate pass | Gate pass generated | ⬜ |
| 10 | Complete gate-in | Container in system | ⬜ |

**Pass Criteria:**
Gate-in completed with all validations passed.

---

### TC-TMS-003: APAD Compliance

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-TMS-003 |
| **Requirement Ref** | C4-23 |
| **Feature** | APAD Requirements - TAT Tracking |
| **Priority** | Critical |

**Test Scenario:**
Verify APAD compliance with turnaround time tracking.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Haulier books appointment online | Booking confirmed | ⬜ |
| 2 | Verify 48-hour validation | Booking >48h before vessel: Accepted | ⬜ |
| 3 | Test <48h booking rejection | System rejects with message | ⬜ |
| 4 | Truck arrives at gate | Arrival time recorded | ⬜ |
| 5 | Process container pickup | Status updated | ⬜ |
| 6 | Truck exits gate | Exit time recorded | ⬜ |
| 7 | Calculate TAT | 18.5 minutes displayed | ⬜ |
| 8 | View TAT dashboard | Real-time TAT metrics shown | ⬜ |
| 9 | Compare to target | <30 min target: PASS | ⬜ |
| 10 | Generate APAD compliance report | Report shows 100% compliance | ⬜ |

**Pass Criteria:**
Average TAT <30 minutes with full tracking.

---

## 6. FMS TEST SCRIPTS

### TC-FMS-001: AI Cash Flow Forecasting

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FMS-001 |
| **Requirement Ref** | C5-1, C5-1-Enh |
| **Feature** | AI-Powered Cash Flow Forecasting |
| **Priority** | Medium |

**Test Scenario:**
Verify AI predicts cash flow 90 days forward.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to Finance Dashboard | Dashboard loads | ⬜ |
| 2 | View Cash Flow Forecast widget | 90-day forecast displayed | ⬜ |
| 3 | View predicted inflow | RM 12.4M predicted | ⬜ |
| 4 | View predicted outflow | RM 8.9M predicted | ⬜ |
| 5 | View net position | RM 3.5M positive | ⬜ |
| 6 | View confidence level | 94% confidence shown | ⬜ |
| 7 | Drill down to month 2 | February forecast shown | ⬜ |
| 8 | View by customer | Top payers listed | ⬜ |
| 9 | Export forecast | Excel file generated | ⬜ |

**Pass Criteria:**
Forecast generated with confidence scoring.

---

### TC-FMS-002: 3-Way Matching

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FMS-002 |
| **Requirement Ref** | C5-19 |
| **Feature** | AP Invoice 3-Way Matching |
| **Priority** | High |

**Test Scenario:**
Verify automatic matching of invoice with PO and GRN.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create PO for 10 laptops | PO-MMFSB-2026-001234 created | ⬜ |
| 2 | Receive goods (GRN) | GRN-2026-000567: 10 units | ⬜ |
| 3 | Receive vendor invoice | INV-TC-2026-001234: 10 × RM 4,560 | ⬜ |
| 4 | System auto-matches | Match indicators shown | ⬜ |
| 5 | Verify PO match | ✅ Qty: 10 = 10 | ⬜ |
| 6 | Verify GRN match | ✅ Received: 10 = 10 | ⬜ |
| 7 | Verify price match | ✅ RM 4,560 = RM 4,560 | ⬜ |
| 8 | Verify total match | ✅ RM 45,600 = RM 45,600 | ⬜ |
| 9 | Route for approval | Approval workflow triggered | ⬜ |
| 10 | Post to GL | Journal entry created | ⬜ |

**Pass Criteria:**
All three documents match with 100% accuracy.

---

### TC-FMS-003: MyInvois e-Invoice Submission

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FMS-003 |
| **Requirement Ref** | C5-6, C5-14 |
| **Feature** | IRBM e-Invoice Integration |
| **Priority** | Critical |

**Test Scenario:**
Verify end-to-end e-invoice submission to IRBM.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Generate customer invoice | Invoice INV-001892 created | ⬜ |
| 2 | Click "Validate for MyInvois" | Validation starts | ⬜ |
| 3 | Verify TIN format | ✅ Valid | ⬜ |
| 4 | Verify SST registration | ✅ Active | ⬜ |
| 5 | Verify invoice format | ✅ Compliant | ⬜ |
| 6 | Verify tax calculation | ✅ SST 8% correct | ⬜ |
| 7 | Submit to MyInvois | API call successful | ⬜ |
| 8 | Receive UUID | IVL-789234-20260131-001892 | ⬜ |
| 9 | Verify QR code generated | QR code displayed | ⬜ |
| 10 | Validate QR with IRBM verifier | Document valid | ⬜ |
| 11 | Email to customer | PDF with QR sent | ⬜ |

**Pass Criteria:**
e-Invoice validated and accepted by IRBM.

---

### TC-FMS-004: AI Credit Scoring

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FMS-004 |
| **Requirement Ref** | C5-6, C5-6-Enh |
| **Feature** | AI-Based Credit Scoring |
| **Priority** | Medium |

**Test Scenario:**
Verify AI recommends optimal credit limits based on customer data.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to customer ABC Logistics | Customer profile open | ⬜ |
| 2 | View current credit limit | RM 500,000 | ⬜ |
| 3 | View AI Credit Score | 78/100 displayed | ⬜ |
| 4 | View recommended limit | RM 600,000 suggested | ⬜ |
| 5 | View risk level | Low-Medium | ⬜ |
| 6 | View score breakdown | 5 factors listed | ⬜ |
| 7 | View payment history analysis | 87% on-time rate | ⬜ |
| 8 | Adjust credit limit | New limit approved | ⬜ |
| 9 | Verify automatic enforcement | New limit active | ⬜ |

**Pass Criteria:**
AI score accurate with actionable recommendations.

---

### TC-FMS-005: Fixed Asset Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-FMS-005 |
| **Requirement Ref** | C5-25 to C5-32 |
| **Feature** | Fixed Asset Lifecycle Management |
| **Priority** | High |

**Test Scenario:**
Verify complete asset lifecycle from acquisition to disposal.

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create new asset PM-100 | Asset registered | ⬜ |
| 2 | Enter acquisition cost | RM 580,000 | ⬜ |
| 3 | Set depreciation method | Straight line, 8 years | ⬜ |
| 4 | Calculate monthly depreciation | RM 6,041.67/month | ⬜ |
| 5 | View depreciation schedule | 8-year schedule displayed | ⬜ |
| 6 | Record maintenance | Service cost RM 4,500 | ⬜ |
| 7 | Transfer asset to Butterworth | Transfer recorded | ⬜ |
| 8 | Revalue asset upward | New value RM 600,000 | ⬜ |
| 9 | Recalculate depreciation | New monthly amount calculated | ⬜ |
| 10 | Dispose of asset | Gain/loss calculated | ⬜ |
| 11 | View asset history | Complete audit trail shown | ⬜ |

**Pass Criteria:**
All asset transactions processed with proper GL impact.

---

## 7. INTEGRATION TEST SCRIPTS

### TC-INT-001: HMS to FMS Billing Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-INT-001 |
| **Feature** | End-to-end Job to Invoice |
| **Priority** | Critical |

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | HMS | Create job PK→SA | Job created | ⬜ |
| 2 | HMS | Assign PM-047 | Job assigned | ⬜ |
| 3 | Mobile | Driver starts job | Status: In Progress | ⬜ |
| 4 | Mobile | Driver completes delivery | Status: Completed | ⬜ |
| 5 | HMS | Job auto-completes | Completion logged | ⬜ |
| 6 | HMS→FMS | Billing trigger fired | Invoice request sent | ⬜ |
| 7 | FMS | Invoice auto-generated | INV-001892 created | ⬜ |
| 8 | FMS | Amount calculated correctly | RM 2,122.20 | ⬜ |
| 9 | FMS | Submit to MyInvois | UUID received | ⬜ |
| 10 | FMS | Update AR | Balance increased | ⬜ |
| 11 | HMS | Job marked as invoiced | Status updated | ⬜ |

**Pass Criteria:**
Complete flow executed without manual intervention.

---

### TC-INT-002: FFS to HMS Shipment Handover

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-INT-002 |
| **Feature** | Freight to Haulage Coordination |
| **Priority** | High |

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | FFS | Create import shipment | Shipment created | ⬜ |
| 2 | FFS | Container arrives Port Klang | Arrival logged | ⬜ |
| 3 | FFS→HMS | Haulage request triggered | Job request sent | ⬜ |
| 4 | HMS | Job automatically created | Job in queue | ⬜ |
| 5 | HMS | Assign nearest PM | PM-047 assigned | ⬜ |
| 6 | HMS | Execute haulage | Container delivered | ⬜ |
| 7 | HMS→FFS | Delivery confirmation sent | Status updated | ⬜ |
| 8 | FFS | Shipment status: Delivered | Complete | ⬜ |

**Pass Criteria:**
Seamless handover between FFS and HMS.

---

### TC-INT-003: WMS to TMS Container Receipt

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-INT-003 |
| **Feature** | Warehouse to Terminal Coordination |
| **Priority** | High |

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | TMS | Container at terminal | Ready for pickup | ⬜ |
| 2 | WMS | Create inbound order | ASN created | ⬜ |
| 3 | TMS→HMS | Haulage to warehouse | Job executed | ⬜ |
| 4 | WMS | Container arrives | Gate-in recorded | ⬜ |
| 5 | WMS | Unload and put-away | Inventory updated | ⬜ |
| 6 | WMS→TMS | Receipt confirmation sent | TMS updated | ⬜ |
| 7 | TMS | Container marked delivered | Status sync complete | ⬜ |

**Pass Criteria:**
Container flow tracked across TMS→HMS→WMS.

---

## 8. UAT EXECUTION PLAN

### 8.1 Test Schedule

| Phase | Duration | Activities |
|-------|----------|------------|
| **Phase 1: System Setup** | Day 1 | Environment validation, data loading |
| **Phase 2: Module Testing** | Days 2-6 | HMS, FFS, WMS, TMS, FMS parallel testing |
| **Phase 3: Integration Testing** | Days 7-8 | End-to-end workflows |
| **Phase 4: Regression Testing** | Day 9 | Re-test defects, verify fixes |
| **Phase 5: Sign-off** | Day 10 | Final acceptance, sign-off |

### 8.2 Entry Criteria

- [ ] All systems deployed to UAT environment
- [ ] Test data loaded (6 months historical)
- [ ] All user accounts provisioned
- [ ] Integration sandboxes configured
- [ ] Test cases reviewed and approved by MMF

### 8.3 Exit Criteria

- [ ] 100% of Critical test cases passed
- [ ] 95% of High priority test cases passed
- [ ] 90% of Medium priority test cases passed
- [ ] All Critical defects resolved
- [ ] MMF Business Sign-off obtained

### 8.4 Defect Severity

| Severity | Definition | Response Time |
|----------|------------|---------------|
| **Critical** | System crash, data loss, security breach | 4 hours |
| **High** | Major feature not working, workaround difficult | 24 hours |
| **Medium** | Feature partially working, workaround available | 72 hours |
| **Low** | Cosmetic issues, minor inconveniences | Next release |

### 8.5 UAT Sign-off Template

```
┌─────────────────────────────────────────────────────────────────────┐
│           UAT COMPLETION SIGN-OFF                                    │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  Tender Reference: MMFSB/TD 01/2026                                 │
│  System: LogisticsPro Enterprise Suite v4.2                         │
│  UAT Period: [Start Date] to [End Date]                             │
│                                                                      │
│  TEST SUMMARY:                                                       │
│  ┌──────────────────┬──────────┬──────────┬──────────┐              │
│  │ Category         │ Planned  │ Executed │ Passed   │              │
│  ├──────────────────┼──────────┼──────────┼──────────┤              │
│  │ HMS Tests        │ 45       │          │          │              │
│  │ FFS Tests        │ 52       │          │          │              │
│  │ WMS Tests        │ 68       │          │          │              │
│  │ TMS Tests        │ 61       │          │          │              │
│  │ FMS Tests        │ 89       │          │          │              │
│  │ Integration      │ 25       │          │          │              │
│  ├──────────────────┼──────────┼──────────┼──────────┤              │
│  │ TOTAL            │ 340      │          │          │              │
│  └──────────────────┴──────────┴──────────┴──────────┘              │
│                                                                      │
│  DEFECT SUMMARY:                                                     │
│  - Critical: ___ Open / ___ Resolved                                 │
│  - High:     ___ Open / ___ Resolved                                 │
│  - Medium:   ___ Open / ___ Resolved                                 │
│  - Low:      ___ Open / ___ Resolved                                 │
│                                                                      │
│  ACCEPTANCE DECISION:                                                │
│  ☐ ACCEPT - System ready for production deployment                   │
│  ☐ CONDITIONAL ACCEPT - Minor issues to be resolved post-go-live    │
│  ☐ REJECT - Critical issues must be resolved before deployment      │
│                                                                      │
│  SIGNATURES:                                                         │
│                                                                      │
│  MMF Project Manager: ___________________ Date: ____________         │
│                                                                      │
│  MMF IT Lead:         ___________________ Date: ____________         │
│                                                                      │
│  MMF Finance Lead:    ___________________ Date: ____________         │
│                                                                      │
│  SESB Project Manager: __________________ Date: ____________         │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
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
| Total Test Cases | 340 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
