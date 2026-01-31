# ANNEX G: USER ACCEPTANCE TEST (UAT) SCRIPTS - TSH-2605

**Tender Reference:** MMFSB/TD 02/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Support IT System (EMS, PS, HRMS)  
**Version:** LogisticsPro Enterprise Suite v4.2  
**Date:** 31 January 2026  
**Test Phase:** User Acceptance Testing (UAT)

---

## TABLE OF CONTENTS

1. [UAT Overview](#1-uat-overview)
2. [EMS Test Scripts (12 Test Cases)](#2-ems-test-scripts)
3. [PS Test Scripts (13 Test Cases)](#3-ps-test-scripts)
4. [HRMS Test Scripts (12 Test Cases)](#4-hrms-test-scripts)
5. [Integration Test Scripts](#5-integration-test-scripts)
6. [UAT Execution Plan](#6-uat-execution-plan)

---

## 1. UAT OVERVIEW

### 1.1 UAT Objectives

| Objective | Description |
|-----------|-------------|
| **Validate Requirements** | Verify all 37 requirements function as specified |
| **User Validation** | Confirm system meets end-user operational needs |
| **Integration Testing** | Validate inter-module data flow and processes |
| **Performance Check** | Ensure system performs under realistic load |
| **Acceptance Sign-off** | Obtain formal acceptance from MMF stakeholders |

### 1.2 Test Environment

| Component | Specification |
|-----------|---------------|
| **Environment** | UAT - Staging (uat.logisticspro.com) |
| **Database** | UAT Database (refreshed from production sample) |
| **Integration** | Connected to test sandboxes |
| **Data** | Anonymized production data (6 months history) |
| **Access** | 25 test user accounts provisioned |

### 1.3 Test Case Summary

| System | Requirements | Test Cases | Priority |
|--------|--------------|------------|----------|
| EMS | 12 | 28 | High |
| PS | 13 | 32 | High |
| HRMS | 12 | 30 | High |
| **Integration** | - | 15 | Critical |
| **TOTAL** | **37** | **105** | - |

---

## 2. EMS TEST SCRIPTS

### TC-EMS-001: Asset Register & Tracking

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-001 |
| **Requirement Ref** | C1-1 |
| **Feature** | Asset Register & Tracking |
| **Priority** | High |

**Test Scenario:**
Verify comprehensive asset registry with unique identification and tracking.

**Preconditions:**
- User logged in with Asset Manager role
- Test assets created in system (minimum 10)
- Barcode/RFID scanners available

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to EMS Dashboard | Dashboard loads within 3 seconds | ⬜ |
| 2 | View Total Assets widget | Count matches database query | ⬜ |
| 3 | Click on Asset Register | Asset list displays with filters | ⬜ |
| 4 | Search for asset by ID | Asset details displayed | ⬜ |
| 5 | Search for asset by name | Relevant assets listed | ⬜ |
| 6 | Scan asset barcode/QR code | Asset auto-identified | ⬜ |
| 7 | Update asset location | Location change recorded | ⬜ |
| 8 | View asset movement history | Complete custody chain shown | ⬜ |
| 9 | Export asset register | Excel/PDF generated | ⬜ |
| 10 | Test RFID bulk scanning | Multiple assets scanned simultaneously | ⬜ |

**Pass Criteria:**
All asset tracking functions work accurately with real-time updates.

---

### TC-EMS-002: IoT Sensor Integration

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-002 |
| **Requirement Ref** | C1-1-Enh |
| **Feature** | IoT Sensor Monitoring |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to IoT Dashboard | Real-time sensor data displayed | ⬜ |
| 2 | View engine temperature | Current temp within normal range shown | ⬜ |
| 3 | Check oil pressure | Pressure reading accurate | ⬜ |
| 4 | Monitor brake wear | Percentage displayed with trend | ⬜ |
| 5 | View tire pressure | All tires showing pressure values | ⬜ |
| 6 | Test alert for high temperature | Alert triggered when threshold exceeded | ⬜ |
| 7 | View historical sensor trends | 30-day graph displayed | ⬜ |
| 8 | Export sensor data | CSV file generated | ⬜ |

**Pass Criteria:**
IoT data displays accurately with <30 second refresh rate.

---

### TC-EMS-003: Maintenance Scheduling

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-003 |
| **Requirement Ref** | C1-2 |
| **Feature** | Preventive Maintenance Scheduling |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View Maintenance Calendar | Calendar displays scheduled maintenance | ⬜ |
| 2 | Create new maintenance schedule | Schedule created with reminder | ⬜ |
| 3 | Set time-based trigger | Schedule activates on date | ⬜ |
| 4 | Set usage-based trigger | Schedule activates at km/hours threshold | ⬜ |
| 5 | Receive maintenance alert | Notification sent before due date | ⬜ |
| 6 | Generate work order | WO auto-created from schedule | ⬜ |
| 7 | Assign technician | Technician receives notification | ⬜ |
| 8 | Complete maintenance | Status updated, history recorded | ⬜ |

**Pass Criteria:**
Maintenance schedules trigger correctly and alerts delivered on time.

---

### TC-EMS-004: AI Predictive Maintenance

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-004 |
| **Requirement Ref** | C1-2-Enh |
| **Feature** | AI-Powered Predictive Maintenance |
| **Priority** | Medium |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to Predictive Maintenance | AI dashboard loads | ⬜ |
| 2 | View risk predictions | Assets categorized by risk level | ⬜ |
| 3 | Click on high-risk asset | Detailed prediction shown | ⬜ |
| 4 | View failure probability | Percentage and timeframe displayed | ⬜ |
| 5 | View recommended action | Specific maintenance suggested | ⬜ |
| 6 | Schedule service from prediction | Service appointment created | ⬜ |
| 7 | View cost savings report | Historical savings calculated | ⬜ |
| 8 | Export maintenance forecast | Report generated | ⬜ |

**Pass Criteria:**
AI predictions actionable with confidence scores.

---

### TC-EMS-005: Total Cost of Ownership

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-005 |
| **Requirement Ref** | C1-3 |
| **Feature** | TCO Analysis |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Select asset for TCO analysis | Asset details loaded | ⬜ |
| 2 | View acquisition cost | Original purchase price shown | ⬜ |
| 3 | View accumulated depreciation | Depreciation calculated correctly | ⬜ |
| 4 | View operating costs | Fuel, maintenance, insurance listed | ⬜ |
| 5 | View cost per km | Unit cost calculated | ⬜ |
| 6 | View TCO trend chart | 3-year cost visualization | ⬜ |
| 7 | View AI replacement recommendation | Optimal replacement timing suggested | ⬜ |
| 8 | Export TCO report | PDF generated | ⬜ |

**Pass Criteria:**
TCO calculations accurate with all cost components included.

---

### TC-EMS-006: Depreciation Tracking

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-006 |
| **Requirement Ref** | C1-4 |
| **Feature** | Asset Depreciation |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View asset depreciation schedule | Monthly depreciation shown | ⬜ |
| 2 | Verify straight-line calculation | Amount = (Cost - Salvage) / Life | ⬜ |
| 3 | View accumulated depreciation | Running total correct | ⬜ |
| 4 | View current book value | Cost - Accumulated Dep = Book Value | ⬜ |
| 5 | View depreciation history | All prior months listed | ⬜ |
| 6 | Post monthly depreciation | Journal entry created in FMS | ⬜ |
| 7 | View tax optimization suggestion | Alternative methods compared | ⬜ |
| 8 | Export depreciation report | Report with GL entries | ⬜ |

**Pass Criteria:**
Depreciation calculates correctly and posts to FMS accurately.

---

### TC-EMS-007: Warranty Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-007 |
| **Requirement Ref** | C1-5 |
| **Feature** | Warranty Tracking |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View warranty dashboard | Active/expiring warranties listed | ⬜ |
| 2 | Check 90-day expiry alert | Alert shown for warranty expiring | ⬜ |
| 3 | Check 30-day expiry alert | Urgent alert displayed | ⬜ |
| 4 | View warranty claim history | Past claims listed with status | ⬜ |
| 5 | Submit new warranty claim | Claim created with documentation | ⬜ |
| 6 | Track claim status | Status updates visible | ⬜ |
| 7 | View extended warranty options | Cost-benefit analysis shown | ⬜ |
| 8 | Export warranty register | Report generated | ⬜ |

**Pass Criteria:**
Warranty alerts timely and claim tracking accurate.

---

### TC-EMS-008: Utilization Reports

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-008 |
| **Requirement Ref** | C1-6 |
| **Feature** | Equipment Utilization |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View utilization dashboard | Fleet utilization % displayed | ⬜ |
| 2 | View utilization by asset | Individual asset hours shown | ⬜ |
| 3 | View idle time analysis | Idle vs operating time compared | ⬜ |
| 4 | View top performers | Highest utilization assets listed | ⬜ |
| 5 | View underutilized assets | Low utilization flagged | ⬜ |
| 6 | View AI optimization suggestion | Fleet right-sizing recommended | ⬜ |
| 7 | Export utilization report | Excel report generated | ⬜ |
| 8 | Schedule automated report | Monthly email scheduled | ⬜ |

**Pass Criteria:**
Utilization metrics accurate with actionable insights.

---

### TC-EMS-009: Spare Parts Inventory

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-EMS-009 |
| **Requirement Ref** | C1-7 |
| **Feature** | Parts Inventory Management |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View parts inventory | Stock levels displayed | ⬜ |
| 2 | View low stock alerts | Items below reorder point flagged | ⬜ |
| 3 | View ABC classification | Parts categorized by value/usage | ⬜ |
| 4 | Create purchase requisition | PR auto-generated for low stock | ⬜ |
| 5 | View AI reorder suggestion | Optimal quantity recommended | ⬜ |
| 6 | Record parts usage | Stock reduced, linked to asset | ⬜ |
| 7 | View parts movement history | In/out transactions listed | ⬜ |
| 8 | Export inventory report | Report with valuations | ⬜ |

**Pass Criteria:**
Inventory tracking accurate with automated reorder triggers.

---

## 3. PS TEST SCRIPTS

### TC-PS-001: Purchase Requisition Workflow

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-001 |
| **Requirement Ref** | C2-1 |
| **Feature** | Purchase Requisition |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create new PR | PR form opens | ⬜ |
| 2 | Add line items | Items added with descriptions | ⬜ |
| 3 | Check budget availability | Budget balance displayed | ⬜ |
| 4 | Submit for approval | Workflow triggered | ⬜ |
| 5 | Approver receives notification | Email/app alert sent | ⬜ |
| 6 | Approver reviews PR | Details viewable | ⬜ |
| 7 | Approver approves | Status updated to Approved | ⬜ |
| 8 | Requestor receives confirmation | Notification received | ⬜ |
| 9 | Test rejection flow | Rejection with reason recorded | ⬜ |
| 10 | Test delegation | Auto-routes when approver absent | ⬜ |

**Pass Criteria:**
PR workflow completes within 24 hours for standard approvals.

---

### TC-PS-002: AI Vendor Recommendations

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-002 |
| **Requirement Ref** | C2-1-Enh |
| **Feature** | AI Vendor Suggestions |
| **Priority** | Medium |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create PR for spare parts | AI suggests preferred vendor | ⬜ |
| 2 | View vendor recommendation | Vendor name, price, rating shown | ⬜ |
| 3 | View alternative vendors | 2-3 alternatives listed | ⬜ |
| 4 | Compare vendor prices | Side-by-side comparison | ⬜ |
| 5 | Select AI-recommended vendor | Selection recorded | ⬜ |
| 6 | View savings vs last purchase | Savings amount calculated | ⬜ |
| 7 | Accept recommendation | PR pre-filled with vendor | ⬜ |

**Pass Criteria:**
AI recommendations relevant with measurable savings.

---

### TC-PS-003: Vendor Scorecard

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-003 |
| **Requirement Ref** | C2-2 |
| **Feature** | Vendor Management & Evaluation |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View vendor list | All vendors displayed | ⬜ |
| 2 | Search vendor by name | Vendor found | ⬜ |
| 3 | View vendor profile | Contact, category, status shown | ⬜ |
| 4 | View performance scorecard | Quality, delivery, price scores | ⬜ |
| 5 | View transaction history | Past POs and amounts listed | ⬜ |
| 6 | View vendor trend | Performance over time charted | ⬜ |
| 7 | Update vendor rating | New rating saved | ⬜ |
| 8 | View AI risk assessment | External risk factors flagged | ⬜ |

**Pass Criteria:**
Vendor data comprehensive with accurate performance scoring.

---

### TC-PS-004: RFQ Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-004 |
| **Requirement Ref** | C2-3 |
| **Feature** | Quotation & RFQ |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create new RFQ | RFQ form opens | ⬜ |
| 2 | Add items and quantities | Line items added | ⬜ |
| 3 | Select vendors to invite | Vendor list selected | ⬜ |
| 4 | Send RFQ to vendors | Email notifications sent | ⬜ |
| 5 | Vendor submits quotation | Quote received in system | ⬜ |
| 6 | View quotation comparison | Side-by-side analysis | ⬜ |
| 7 | View AI price benchmarking | Market comparison shown | ⬜ |
| 8 | Select winning vendor | Award decision recorded | ⬜ |
| 9 | Generate PO from RFQ | PO auto-populated | ⬜ |

**Pass Criteria:**
RFQ process streamlined with clear comparison tools.

---

### TC-PS-005: Three-Way Matching

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-005 |
| **Requirement Ref** | C2-6 |
| **Feature** | 3-Way Matching |
| **Priority** | Critical |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create PO | PO issued to vendor | ⬜ |
| 2 | Receive goods via GRN | GRN created, stock updated | ⬜ |
| 3 | Receive vendor invoice | Invoice scanned/uploaded | ⬜ |
| 4 | System auto-matches documents | Match status displayed | ⬜ |
| 5 | Verify PO-GRN match | Quantities match | ⬜ |
| 6 | Verify GRN-Invoice match | Prices match | ⬜ |
| 7 | Approve matched invoice | Ready for payment | ⬜ |
| 8 | Test variance tolerance | Within threshold auto-approved | ⬜ |
| 9 | Test variance exceeded | Routes for approval | ⬜ |
| 10 | Post to FMS | Journal entry created | ⬜ |

**Pass Criteria:**
3-way matching 95%+ automated with accurate exception handling.

---

### TC-PS-006: Procurement Analytics

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-006 |
| **Requirement Ref** | C2-7 |
| **Feature** | Spend Analysis |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|-------- |
| 1 | View spend dashboard | Total spend displayed | ⬜ |
| 2 | View spend by category | Category breakdown shown | ⬜ |
| 3 | View spend by vendor | Top vendors listed | ⬜ |
| 4 | View spend by branch | Branch comparison | ⬜ |
| 5 | View trend analysis | Year-over-year comparison | ⬜ |
| 6 | View AI insights | Maverick spending flagged | ⬜ |
| 7 | View consolidation opportunities | Savings recommendations | ⬜ |
| 8 | Export spend report | Excel/PDF generated | ⬜ |

**Pass Criteria:**
Analytics accurate with actionable business intelligence.

---

### TC-PS-007: Budget Control

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-007 |
| **Requirement Ref** | C2-8 |
| **Feature** | Budget Management |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View budget dashboard | All budgets listed | ⬜ |
| 2 | View budget utilization | Spent vs remaining shown | ⬜ |
| 3 | Test overspend warning | Alert when exceeding budget | ⬜ |
| 4 | View committed vs actual | POs vs payments compared | ⬜ |
| 5 | View AI forecast | Year-end projection | ⬜ |
| 6 | Receive budget alert | Notification when threshold hit | ⬜ |
| 7 | Export budget report | Report with variances | ⬜ |

**Pass Criteria:**
Budget controls prevent overspend with timely alerts.

---

### TC-PS-008: Fraud Detection

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-PS-008 |
| **Requirement Ref** | C2-11-Enh |
| **Feature** | AI Fraud Detection |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View alerts dashboard | Active alerts listed | ⬜ |
| 2 | Review split purchase alert | Suspicious PRs flagged | ⬜ |
| 3 | Review new vendor alert | High-risk vendor flagged | ⬜ |
| 4 | Review maverick spend alert | Off-contract purchase flagged | ⬜ |
| 5 | Investigate alert | Details viewable | ⬜ |
| 6 | Dismiss false positive | Alert marked resolved | ⬜ |
| 7 | Escalate genuine issue | Routed to management | ⬜ |
| 8 | View fraud prevention summary | Protected amount displayed | ⬜ |

**Pass Criteria:**
Fraud alerts accurate with minimal false positives.

---

## 4. HRMS TEST SCRIPTS

### TC-HRMS-001: Employee Database

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-001 |
| **Requirement Ref** | C3-1 |
| **Feature** | Employee Management |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View employee list | All employees displayed | ⬜ |
| 2 | Search by name | Employee found | ⬜ |
| 3 | Search by ID | Employee found | ⬜ |
| 4 | View employee profile | Complete details shown | ⬜ |
| 5 | Update employee info | Changes saved with audit | ⬜ |
| 6 | Upload document | Document attached | ⬜ |
| 7 | View organization chart | Hierarchy displayed | ⬜ |
| 8 | Export employee list | Report generated | ⬜ |

**Pass Criteria:**
Employee data managed securely with full audit trail.

---

### TC-HRMS-002: Employee Self-Service

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-002 |
| **Requirement Ref** | C3-1-Enh |
| **Feature** | ESS Portal |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Login as employee | Dashboard personalized | ⬜ |
| 2 | View leave balance | Accurate balances shown | ⬜ |
| 3 | View payslip | Current and historical payslips | ⬜ |
| 4 | View claims status | Pending/approved claims | ⬜ |
| 5 | Update personal info | Changes saved (pending HR approval) | ⬜ |
| 6 | View performance | Latest review visible | ⬜ |
| 7 | Access via mobile app | Responsive mobile interface | ⬜ |
| 8 | Test chatbot query | Answer provided via WhatsApp | ⬜ |

**Pass Criteria:**
ESS intuitive with 90%+ employee adoption.

---

### TC-HRMS-003: Attendance & Leave

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-003 |
| **Requirement Ref** | C3-2 |
| **Feature** | Attendance Management |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Clock in via biometric | Time recorded | ⬜ |
| 2 | Clock in via mobile GPS | Location verified, time recorded | ⬜ |
| 3 | View attendance record | Daily attendance visible | ⬜ |
| 4 | Apply for leave | Application submitted | ⬜ |
| 5 | Manager receives notification | Alert sent | ⬜ |
| 6 | Manager approves leave | Balance updated | ⬜ |
| 7 | View leave calendar | Approved leave visible | ⬜ |
| 8 | Calculate overtime | OT hours calculated correctly | ⬜ |
| 9 | View AI absence prediction | Pattern analysis shown | ⬜ |

**Pass Criteria:**
Attendance tracking accurate with leave workflow <24h.

---

### TC-HRMS-004: Payroll Processing

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-004 |
| **Requirement Ref** | C3-3 |
| **Feature** | Payroll |
| **Priority** | Critical |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Run payroll pre-calculation | Preview generated | ⬜ |
| 2 | Verify basic salary | Amount correct | ⬜ |
| 3 | Verify allowances | Transport, meal, etc. correct | ⬜ |
| 4 | Verify overtime | OT calculated at correct rates | ⬜ |
| 5 | Verify EPF calculation | Employee 11%, Employer 12% | ⬜ |
| 6 | Verify SOCSO calculation | Correct rates applied | ⬜ |
| 7 | Verify EIS calculation | Correct rates applied | ⬜ |
| 8 | Verify PCB (tax) | Monthly tax deduction correct | ⬜ |
| 9 | Generate bank file | FPX format correct | ⬜ |
| 10 | Post to FMS | Journal entries created | ⬜ |
| 11 | Generate payslips | PDFs distributed | ⬜ |
| 12 | View EA form | Year-end tax form accurate | ⬜ |

**Pass Criteria:**
Payroll 100% accurate with statutory compliance.

---

### TC-HRMS-005: Claims Processing

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-005 |
| **Requirement Ref** | C3-4 |
| **Feature** | Claims & Reimbursement |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Submit medical claim | Claim created | ⬜ |
| 2 | Upload receipt | OCR extracts amount/date | ⬜ |
| 3 | OCR validates receipt | Amount matches entry | ⬜ |
| 4 | Manager approves claim | Status updated | ⬜ |
| 5 | Finance verifies | Ready for payment | ⬜ |
| 6 | Reimburse via payroll | Added to next payslip | ⬜ |
| 7 | View claims history | All claims listed | ⬜ |
| 8 | Test duplicate detection | Alert for duplicate receipt | ⬜ |

**Pass Criteria:**
Claims processed within 5 business days.

---

### TC-HRMS-006: Performance Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-006 |
| **Requirement Ref** | C3-5 |
| **Feature** | Performance Appraisal |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View performance dashboard | Current rating displayed | ⬜ |
| 2 | View goal status | Progress against targets | ⬜ |
| 3 | Manager initiates review | Review form opened | ⬜ |
| 4 | Manager rates competencies | Scores saved | ⬜ |
| 5 | Employee acknowledges | Review confirmed | ⬜ |
| 6 | Set new goals | Goals created for next cycle | ⬜ |
| 7 | View historical performance | Trend over years | ⬜ |
| 8 | 360-degree feedback | Peer feedback collected | ⬜ |

**Pass Criteria:**
Performance process complete with goal tracking.

---

### TC-HRMS-007: Training Management

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-007 |
| **Requirement Ref** | C3-6 |
| **Feature** | Training |
| **Priority** | Medium |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View training dashboard | Completed hours shown | ⬜ |
| 2 | View AI recommendations | Personalized suggestions | ⬜ |
| 3 | Register for course | Enrollment confirmed | ⬜ |
| 4 | Complete online training | Progress tracked | ⬜ |
| 5 | Receive certification | Certificate generated | ⬜ |
| 6 | Manager tracks team training | Team progress visible | ⬜ |
| 7 | View mandatory training | Overdue alerts shown | ⬜ |
| 8 | Export training record | Transcript generated | ⬜ |

**Pass Criteria:**
Training tracking accurate with completion rates >75%.

---

### TC-HRMS-008: Recruitment

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-008 |
| **Requirement Ref** | C3-7 |
| **Feature** | ATS |
| **Priority** | Medium |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create job requisition | Requisition submitted | ⬜ |
| 2 | Post to careers page | Job visible externally | ⬜ |
| 3 | Candidate applies | Application received | ⬜ |
| 4 | AI scores resume | Match percentage shown | ⬜ |
| 5 | Schedule interview | Calendar invite sent | ⬜ |
| 6 | Record interview feedback | Notes saved | ⬜ |
| 7 | Make offer | Offer letter generated | ⬜ |
| 8 | Onboard new hire | Checklist initiated | ⬜ |

**Pass Criteria:**
Recruitment workflow complete with AI screening.

---

### TC-HRMS-009: Predictive HR Analytics

| Field | Details |
|-------|---------|
| **Test Case ID** | TC-HRMS-009 |
| **Requirement Ref** | C3-8-Enh |
| **Feature** | AI Attrition Prediction |
| **Priority** | High |

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View HR analytics dashboard | KPIs displayed | ⬜ |
| 2 | View turnover trend | Monthly turnover charted | ⬜ |
| 3 | View flight risk alerts | High-risk employees flagged | ⬜ |
| 4 | Click on risk alert | Contributing factors shown | ⬜ |
| 5 | View retention recommendations | Actions suggested | ⬜ |
| 6 | Schedule retention meeting | Calendar invite created | ⬜ |
| 7 | View workforce forecast | Headcount projections | ⬜ |
| 8 | Export analytics report | Report generated | ⬜ |

**Pass Criteria:**
Predictions actionable with early warning 60+ days.

---

## 5. INTEGRATION TEST SCRIPTS

### TC-INT-001: EMS to FMS Integration

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | EMS | Record maintenance cost | Cost captured | ⬜ |
| 2 | EMS→FMS | Cost sync triggered | Journal entry created | ⬜ |
| 3 | FMS | Verify GL posting | Expense account debited | ⬜ |
| 4 | EMS | Run depreciation | Depreciation calculated | ⬜ |
| 5 | EMS→FMS | Depreciation posted | GL updated | ⬜ |
| 6 | FMS | Verify balance sheet | Asset values accurate | ⬜ |

**Pass Criteria:**
EMS-FMS data sync real-time with accurate financial posting.

---

### TC-INT-002: PS to FMS Integration

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | PS | Approve matched invoice | Ready for payment | ⬜ |
| 2 | PS→FMS | AP invoice created | Liability recorded | ⬜ |
| 3 | FMS | Verify AP aging | Invoice appears correctly | ⬜ |
| 4 | PS | Record GRN | Inventory updated | ⬜ |
| 5 | PS→FMS | Inventory value posted | Asset account updated | ⬜ |
| 6 | FMS | Verify 3-way match | All documents linked | ⬜ |

**Pass Criteria:**
PS-FMS procurement-to-pay seamless.

---

### TC-INT-003: HRMS to FMS Integration

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | HRMS | Process payroll | Calculations complete | ⬜ |
| 2 | HRMS→FMS | Payroll journal created | Expense recorded | ⬜ |
| 3 | FMS | Verify payroll expense | Salary expense accurate | ⬜ |
| 4 | HRMS | Post EPF/SOCSO | Statutory amounts calculated | ⬜ |
| 5 | HRMS→FMS | Liability entries created | Payables recorded | ⬜ |
| 6 | FMS | Verify liability accounts | Balances correct | ⬜ |

**Pass Criteria:**
HRMS-FMS payroll posting accurate.

---

### TC-INT-004: EMS to HMS Integration

**Test Steps:**

| Step | System | Action | Expected Result | Status |
|------|--------|--------|-----------------|--------|
| 1 | EMS | Flag vehicle for maintenance | Status: Maintenance Due | ⬜ |
| 2 | EMS→HMS | Maintenance alert sent | HMS receives notification | ⬜ |
| 3 | HMS | View PM schedule | Maintenance window blocked | ⬜ |
| 4 | HMS | Complete haulage job | Job status updated | ⬜ |
| 5 | HMS→EMS | Vehicle mileage updated | Odometer sync accurate | ⬜ |
| 6 | EMS | Trigger mileage-based PM | Schedule auto-adjusted | ⬜ |

**Pass Criteria:**
EMS-HMS vehicle status sync real-time.

---

### TC-INT-005: Cross-System User Authentication

**Test Steps:**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Login to HRMS | Authentication successful | ⬜ |
| 2 | Access EMS without re-login | SSO works | ⬜ |
| 3 | Access PS without re-login | SSO works | ⬜ |
| 4 | Verify role permissions | Correct access per role | ⬜ |
| 5 | Password change in HRMS | Synced to all systems | ⬜ |
| 6 | Account lock test | All systems locked | ⬜ |

**Pass Criteria:**
Single sign-on functional across all support systems.

---

## 6. UAT EXECUTION PLAN

### 6.1 Test Schedule

| Phase | Duration | Activities |
|-------|----------|------------|
| **Phase 1: System Setup** | Day 1 | Environment validation, data loading |
| **Phase 2: Module Testing** | Days 2-4 | EMS, PS, HRMS parallel testing |
| **Phase 3: Integration Testing** | Day 5 | End-to-end workflows |
| **Phase 4: Regression Testing** | Day 6 | Re-test defects |
| **Phase 5: Sign-off** | Day 7 | Final acceptance |

### 6.2 Entry Criteria

- [ ] All systems deployed to UAT environment
- [ ] Test data loaded
- [ ] All user accounts provisioned
- [ ] Integration sandboxes configured
- [ ] Test cases reviewed by MMF

### 6.3 Exit Criteria

- [ ] 100% of Critical test cases passed
- [ ] 95% of High priority test cases passed
- [ ] All Critical defects resolved
- [ ] MMF Business Sign-off obtained

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |
| Total Test Cases | 105 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
