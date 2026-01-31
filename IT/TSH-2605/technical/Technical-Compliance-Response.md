# TSH-2605: Technical Compliance Response

**Tender Reference:** MMFSB/TD 02/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Support IT System (EMS, PS, HRMS)  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026

---

## EXECUTIVE GUIDE TO EVIDENCE

| What You Need | Where to Find It | Section |
|---------------|------------------|---------|
| System Architecture Overview | Annex A - Technical Architecture | Page 15 |
| Compliance Proof by System | Annex C1-C3 - Compliance Matrices | Page 25 |
| Security & VAPT Certification | Annex D - Security Assessment | Page 95 |
| Live System Screenshots | Annex E - System Evidence | Page 120 |
| API Integration Specs | Annex F - Integration Guide | Page 165 |
| UAT Test Scripts | Annex G - Testing Documentation | Page 200 |
| PRINCE2 Project Plan | Annex H - Project Methodology | Page 250 |
| 10+10 VAS Framework | Section 7 - Value Added Services | Page 12 |

---

## OUR VALUE PROPOSITION

### The Accelerated Baseline Advantage

Our **LogisticsPro Support Suite** is **production-ready today**, not a promise for tomorrow:

| Metric | Our Solution | Industry Standard |
|--------|--------------|-------------------|
| Pre-built Functionality | 95% of MMF requirements | 40-60% |
| Go-Live Timeline | 8-10 weeks | 6-9 months |
| Successful Deployments | 15+ logistics enterprises | N/A |
| UAT Pass Rate | 98%+ first attempt | 60-70% |

### Risk Mitigation

- ✅ **Zero High/Critical VAPT findings** — CREST-accredited penetration test completed (Annex D)
- ✅ **PRINCE2 methodology** — Stage gates for MMF control at each phase
- ✅ **99.9% uptime SLA** — Awan Kita sovereign cloud infrastructure
- ✅ **Awan Kita Compliant** — Data residency in Malaysia with local encryption keys

### Value Beyond Price

**RM 2.5 Million** in Value-Added Services included at **NO ADDITIONAL COST** (see Section 7).

---

## 1. SCOPE & TRACEABILITY MATRIX

### 1.1 System Coverage

| System | Annexure | Locations | Features | Status |
|--------|----------|-----------|----------|--------|
| Equipment Management System (EMS) | C1 | ALL Branches | 12 | ✅ FULLY COMPLY |
| Procurement System (PS) | C2 | ALL Branches | 13 | ✅ FULLY COMPLY |
| HR Management System (HRMS) | C3 | ALL Branches | 12 | ✅ FULLY COMPLY |
| **TOTAL** | | **6 Branches** | **37** | **✅ 100%** |

### 1.2 Branch Deployment Matrix

| Branch | EMS | PS | HRMS |
|--------|-----|-----|------|
| Headquarters (HQ) | ✅ | ✅ | ✅ |
| Global Logistics Dept (GLD) | ✅ | ✅ | ✅ |
| Port Klang (PK) | ✅ | ✅ | ✅ |
| Pasir Gudang (PGD) | ✅ | ✅ | ✅ |
| Butterworth (BTW) | ✅ | ✅ | ✅ |
| Padang Besar | ✅ | ✅ | ✅ |

### 1.3 Integration with TSH-2604 Systems

| TSH-2604 System | Integration Point | Data Exchange |
|-----------------|-------------------|---------------|
| **HMS** | EMS ↔ HMS | Vehicle maintenance schedules, PM status |
| **FMS** | EMS ↔ FMS | Asset depreciation, maintenance costs |
| **FMS** | PS ↔ FMS | 3-way matching, AP invoice processing |
| **FMS** | HRMS ↔ FMS | Payroll processing, claims reimbursement |
| **All** | HRMS ↔ All | User authentication, role-based access |

---

## 2. COMPLIANCE-PLUS RESPONSE

### Compliance Philosophy

For every requirement, we provide:
1. **FULLY COMPLY** declaration — Never just "Yes"
2. **2-Sentence Technical Justification** — Specific functionality explanation
3. **Evidence Cross-Reference** — Link to Annex/Section/Page
4. **🚀 Value-Add Enhancement** — Beyond baseline capability

---

## ANNEXURE C1: EQUIPMENT MANAGEMENT SYSTEM (EMS)

**Location:** ALL Branches  
**System Version:** LogisticsPro EMS v4.2  
**Asset Types:** Prime Movers, Trailers, Forklifts, Cranes, Container Handling Equipment

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Asset Register & Tracking** | **FULLY COMPLY** | Our EMS maintains a comprehensive centralized asset registry with unique asset IDs, QR/barcode tagging, and RFID support for all MMF equipment. Real-time location tracking shows current assignment, status, and custody chain for each asset across all 6 branches.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Beyond basic tracking, we provide **IoT Sensor Integration** that monitors equipment health in real-time (engine temperature, hydraulic pressure, brake wear). Our **Asset Performance Scoring** algorithm analyzes utilization patterns to recommend optimal fleet sizing—typically identifying 10-15% overcapacity that can be redeployed or retired. | Annex C1.1, Page 120; IoT Dashboard |
| 2. | **Maintenance Scheduling** | **FULLY COMPLY** | The Preventive Maintenance Module supports time-based (calendar) and usage-based (hour/mileage/km) scheduling with automatic work order generation. Maintenance calendars provide visibility across all assets with drag-and-drop rescheduling and resource allocation.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI-Powered Predictive Maintenance** analyzes 50+ telemetry data points to predict failures 7-14 days in advance with 89% accuracy. This shifts maintenance from reactive/fix to predictive/prevent, reducing unexpected breakdowns by 40% and extending asset lifespan by 15-20%. | Annex C1.2, Page 122; PM Calendar |
| 3. | **Repair History & Costs** | **FULLY COMPLY** | Complete repair history tracks all maintenance activities, parts replaced, labor hours, and costs with full audit trail. Cost analysis reports show total cost of ownership (TCO) per asset, enabling data-driven replacement decisions based on maintenance cost trends.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Total Cost of Ownership Analytics** provides 5-year TCO projections considering depreciation, maintenance, fuel, insurance, and downtime costs. The system automatically flags assets approaching the "replace vs repair" crossover point, typically saving 15-20% on lifecycle costs. | Annex C1.3, Page 124; Cost Analysis |
| 4. | **Asset Depreciation Tracking** | **FULLY COMPLY** | Depreciation engine supports multiple methods (straight-line, declining balance, sum-of-years) with automatic monthly calculations. Asset values are automatically posted to FMS General Ledger ensuring financial reporting accuracy.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Tax Optimization Engine** automatically determines the most tax-efficient depreciation method and timing to maximize capital allowances while ensuring MFRS compliance. For MMF's fleet, this typically defers RM 200K-300K in tax liabilities annually. | Annex C1.4, Page 126; Depreciation Report |
| 5. | **Warranty Management** | **FULLY COMPLY** | Warranty tracker maintains all warranty information with automated alerts at 90/60/30 days before expiry. Warranty claims history is logged with claim status and reimbursement tracking.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Warranty Intelligence** module analyzes warranty claim patterns across similar assets to identify manufacturer defects early. It also tracks extended warranty options with ROI calculations—typically saving 8-12% on warranty costs through optimized coverage decisions. | Annex C1.5, Page 128; Warranty Dashboard |
| 6. | **Equipment Utilization Reports** | **FULLY COMPLY** | Utilization tracking monitors operating hours, idle time, and productivity metrics per asset. Reports identify underutilized assets and peak demand periods to support capacity planning and resource allocation decisions.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Fleet Right-Sizing Analytics** uses utilization patterns to recommend optimal fleet composition. The system identifies opportunities for asset sharing between branches and predicts future capacity needs based on business growth—typically uncovering 15-20% efficiency gains. | Annex C1.6, Page 130; Utilization Heat Map |
| 7. | **Spare Parts Inventory** | **FULLY COMPLY** | Spare parts module manages inventory with reorder level alerts, ABC classification, and automatic reorder suggestions. Parts usage is tracked against specific assets enabling failure pattern analysis.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Smart Inventory Optimization** uses machine learning to predict parts demand based on scheduled maintenance, seasonal patterns, and failure rates. This reduces parts stockholding by 25-30% while maintaining 99%+ parts availability—freeing up RM 150K-200K in working capital. | Annex C1.7, Page 132; Parts Inventory |
| 8. | **Multi platform interface** | **FULLY COMPLY** | EMS is accessible via web browsers (Chrome, Edge, Safari), native mobile apps (iOS/Android), and responsive design for tablets. Field technicians can update maintenance records via mobile devices even in areas with poor connectivity using offline-first architecture.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Progressive Web App (PWA)** enables "add to home screen" functionality without app store approval delays. Technicians receive push notifications for urgent maintenance alerts even when not actively using the app—ensuring critical issues are addressed within minutes. | Annex C1.8, Page 134; Mobile App Screens |
| 9. | **User-friendly interface** | **FULLY COMPLY** | Intuitive UI follows Nielsen's usability heuristics with role-based navigation, contextual help, and consistent design language. Equipment operators can log issues with photo capture in under 30 seconds.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Voice Command Interface** allows technicians to update maintenance status hands-free while working on equipment. Natural language processing understands commands like "Log repair for PM-047, replaced brake pads, job complete"—improving technician productivity by 20%. | Annex C1.9, Page 135; UI Walkthrough |
| 10. | **Audit Trail & History** | **FULLY COMPLY** | Immutable audit logs capture all asset modifications with before/after values, user identity, timestamp, and IP address. Full history viewable via Audit Inquiry screen with export capability for compliance reporting.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Blockchain-Based Audit Trail** creates cryptographically-verifiable records that prevent tampering even by database administrators. This provides audit-proof evidence for insurance claims, warranty disputes, and regulatory compliance—reducing audit preparation time by 60%. | Annex D.2, Page 98; Audit Trail Sample |
| 11. | **Comprehensive security features** | **FULLY COMPLY** | Security framework implements MFA, RBAC with granular permissions (50+), password policy enforcement (NIST 800-63B), AES-256 encryption, and continuous monitoring. Annual VAPT with zero critical/high findings.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** We implement **Zero-Trust Security** with behavioral biometrics that continuously authenticate users based on typing patterns and device posture. AI-powered threat detection identifies anomalous access patterns in real-time with automatic account suspension. | Annex D, Pages 95-110; Security Certificate |
| 12. | **Reporting and Enquiries** | **FULLY COMPLY** | Comprehensive report library includes asset listings, maintenance schedules, repair history, cost analysis, depreciation, warranty status, and utilization reports. Ad-hoc query builder enables custom analysis without IT assistance.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Natural Language Reporting** allows managers to ask questions like "Show me equipment with maintenance cost exceeding 30% of book value" and receive instant visual answers. Predictive analytics forecast which assets will need major repairs in the next quarter. | Annex C1.12, Pages 140-145; Report Library |

**Annexure C1 Summary:** 12/12 Features — **100% FULLY COMPLY**

---

## ANNEXURE C2: PROCUREMENT SYSTEM (PS)

**Location:** ALL Branches  
**System Version:** LogisticsPro PS v4.2  
**Procurement Types:** Direct Purchase, RFQ, Tender, Framework Agreements

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Purchase Requisition Workflow** | **FULLY COMPLY** | Online PR module supports multi-level approval workflows with configurable rules based on amount, category, and department. Budget checking during requisition prevents overspend with real-time visibility into remaining budgets.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Spend Classification** automatically categorizes purchase requests and suggests preferred vendors based on historical performance and pricing. Smart routing sends urgent requests to available approvers based on calendar integration—reducing approval cycle time by 40-50%. | Annex C2.1, Page 150; PR Workflow |
| 2. | **Vendor Management and Evaluation** | **FULLY COMPLY** | Comprehensive vendor registry with profile management, classification, and performance tracking. Vendor scorecards track delivery performance, quality metrics, and price competitiveness with automated rating calculations.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Vendor Risk Intelligence** monitors external data sources (news, financial reports, court records) to identify vendor risks proactively. The system also benchmarks MMF's vendor performance against industry peers using anonymized data—identifying opportunities to negotiate better terms. | Annex C2.2, Page 152; Vendor Scorecard |
| 3. | **Quotation Management** | **FULLY COMPLY** | RFQ module enables creation, distribution, and comparison of vendor quotations with side-by-side analysis. Historical pricing data provides context for evaluating current quotes and identifying price trends.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Price Benchmarking** compares received quotes against market rates, historical MMF purchases, and industry benchmarks. The system flags quotes significantly above or below market rates and suggests target prices based on predictive analytics—typically saving 8-12% on procurement costs. | Annex C2.3, Page 154; RFQ Comparison |
| 4. | **Purchase Order Processing** | **FULLY COMPLY** | Automated PO generation from approved requisitions with configurable templates and approval workflows. PO tracking provides real-time status visibility with automatic notifications for delays or exceptions.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Smart PO Consolidation** identifies opportunities to combine multiple requisitions into single POs to leverage volume discounts. The system also predicts delivery delays based on vendor historical performance and automatically suggests alternative suppliers—reducing stockout risk by 35%. | Annex C2.4, Page 156; PO Dashboard |
| 5. | **Goods Receipt and Inspection** | **FULLY COMPLY** | GRN module supports receiving with barcode/RFID scanning, quality inspection recording, and acceptance/rejection workflows. Integration with WMS automatically updates inventory upon goods receipt.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Quality Prediction** analyzes vendor historical quality data to predict likelihood of defects in incoming shipments. High-risk shipments are flagged for enhanced inspection while trusted vendors can be fast-tracked—reducing inspection workload by 30% without compromising quality. | Annex C2.5, Page 158; GRN Interface |
| 6. | **Three-Way Matching (PO-GRN-Invoice)** | **FULLY COMPLY** | Automated three-way matching validates invoice against PO and GRN with configurable tolerance levels (e.g., ±2% quantity, ±5% price). Discrepancies trigger approval workflows with variance justification.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Intelligent Matching Engine** uses AI to match invoices even with incomplete references or minor discrepancies (e.g., different unit of measure). The system handles 85%+ of invoices automatically, reducing accounts payable processing time from days to hours and virtually eliminating duplicate payments. | Annex C2.6, Page 160; 3-Way Matching |
| 7. | **Procurement Analytics** | **FULLY COMPLY** | Analytics dashboard provides spending analysis by category, vendor, department with drill-down capability. Purchase trend reports and vendor performance scorecards support strategic sourcing decisions.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Procurement Intelligence** identifies maverick spending (off-contract purchases) and consolidation opportunities. The system tracks realized savings against negotiated contracts and provides early warning of contract expiries—typically recovering 10-15% in leakage savings. | Annex C2.7, Page 162; Spend Analysis |
| 8. | **Budget Control and Tracking** | **FULLY COMPLY** | Budget allocation by department/category with real-time checking during requisition. Budget utilization tracking provides visibility into committed vs actual spend with overspend alerts.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Predictive Budget Forecasting** analyzes historical spending patterns and pipeline requisitions to forecast year-end position. The system alerts budget holders when forecasts indicate potential overspend, enabling proactive adjustments—preventing 95%+ of budget overruns. | Annex C2.8, Page 164; Budget Dashboard |
| 9. | **Multi platform interface** | **FULLY COMPLY** | PS is accessible across desktop, tablet, and mobile devices with responsive design. Approvers can review and approve requisitions via mobile app with push notifications for urgent approvals.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Smart Approval Assistant** summarizes key information for approvers ("RM 25,000 server purchase from TechCorp—within budget, preferred vendor, urgent for project X") enabling one-tap approval. Voice approval is supported for hands-free processing while driving or in the field. | Annex C2.9, Page 166; Mobile Approval |
| 10. | **User-friendly interface** | **FULLY COMPLY** | Intuitive interface with guided workflows, smart defaults, and contextual help. New users can create their first purchase requisition within 10 minutes without training.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Conversational Procurement** allows users to submit requisitions via natural language ("I need 10 boxes of A4 paper for Port Klang office") which the AI converts to structured requisitions with suggested vendors and pricing—reducing requisition time by 70%. | Annex C2.10, Page 167; Conversational UI |
| 11. | **Audit Trail & History** | **FULLY COMPLY** | Complete audit trail captures all procurement activities with user, timestamp, and before/after values. Full history supports internal audits and external regulatory compliance requirements.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Fraud Detection Analytics** analyzes procurement patterns to identify suspicious activities (e.g., split purchases to bypass approval thresholds, unusual vendor relationships). The system automatically flags high-risk transactions for review—protecting against procurement fraud which typically costs organizations 3-5% of spend. | Annex D.2, Page 98; Audit Trail |
| 12. | **Comprehensive security features** | **FULLY COMPLY** | Enterprise-grade security with MFA, RBAC, encryption, and audit logging. Segregation of duties enforced (requisitioner cannot approve their own requests; approver cannot receive goods).<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Dynamic Access Control** adjusts user permissions based on risk factors (location, device, time of day). Sensitive transactions (e.g., vendor bank detail changes) require dual authorization with video verification—providing bank-grade security for financial transactions. | Annex D, Pages 95-110; Security Matrix |
| 13. | **Reporting and Enquiries** | **FULLY COMPLY** | Comprehensive reporting includes PR status, PO tracking, vendor performance, spend analysis, budget utilization, and GRN reports. Custom report builder enables ad-hoc analysis.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Procurement Cockpit** provides executives with real-time visibility into procurement KPIs (spend under management, contract compliance, savings achieved). Natural language queries enable instant answers to questions like "What percentage of spend is with preferred vendors?"—supporting strategic decision-making. | Annex C2.13, Pages 168-172; Report Library |

**Annexure C2 Summary:** 13/13 Features — **100% FULLY COMPLY**

---

## ANNEXURE C3: HUMAN RESOURCE MANAGEMENT SYSTEM (HRMS)

**Location:** ALL Branches  
**System Version:** LogisticsPro HRMS v4.2  
**Employees:** 500+ across 6 branches

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Employee Database Management** | **FULLY COMPLY** | Centralized employee database maintains comprehensive profiles including personal info, employment history, qualifications, and document management. Organization chart module visualizes hierarchy across all branches with drill-down capability.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Employee Lifecycle Analytics** tracks engagement and attrition risk factors using sentiment analysis from performance reviews and pulse surveys. Predictive models identify flight risks 60-90 days in advance, enabling proactive retention interventions—typically reducing voluntary turnover by 20-25%. | Annex C3.1, Page 175; Employee Portal |
| 2. | **Attendance and Leave Management** | **FULLY COMPLY** | Attendance tracking supports multiple clock-in methods (biometric, mobile GPS, web) with automatic overtime calculation. Leave module manages all leave types (annual, medical, unpaid) with balance tracking and approval workflows.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Absence Prediction** analyzes attendance patterns to identify potential issues (e.g., Monday/Friday patterns suggesting disengagement) before they escalate. The system also optimizes shift scheduling based on demand forecasts and employee preferences—improving workforce utilization by 15%. | Annex C3.2, Page 177; Attendance Dashboard |
| 3. | **Payroll Processing** | **FULLY COMPLY** | Monthly payroll calculation supports all statutory requirements (EPF, SOCSO, EIS, PCB) with automatic form generation (EA, CP8D). Integration with FMS ensures accurate financial posting and bank payment file generation.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Intelligent Payroll Validation** uses AI to detect anomalies (unusual overtime, duplicate payments, rate changes) before processing. The system also optimizes tax deductions throughout the year to maximize take-home pay while ensuring compliance—typically saving employees RM 500-1,000 annually in tax optimization. | Annex C3.3, Page 179; Payroll Module |
| 4. | **Claims and Reimbursement** | **FULLY COMPLY** | Online claims module supports multiple claim types (medical, travel, entertainment) with receipt attachment and OCR extraction. Approval workflows route based on amount and claim type with integration to payroll for reimbursement.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Receipt Intelligence** automatically reads and validates receipts using OCR, flagging duplicates and out-of-policy claims. Integration with corporate credit cards enables automatic reconciliation—reducing claims processing time from weeks to 2-3 days and eliminating manual data entry errors. | Annex C3.4, Page 181; Claims Portal |
| 5. | **Performance Appraisal** | **FULLY COMPLY** | Performance module supports goal setting, periodic reviews, and 360-degree feedback with customizable appraisal forms. Historical performance tracking enables trend analysis and succession planning.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Continuous Performance Management** replaces annual reviews with ongoing feedback and check-ins. AI analyzes performance data to identify high-potential employees and skill gaps, automatically recommending training programs—improving employee development effectiveness by 40%. | Annex C3.5, Page 183; Performance Dashboard |
| 6. | **Training Management** | **FULLY COMPLY** | Training module manages needs assessment, course scheduling, attendance tracking, and certification management. Training costs are tracked per employee and department with ROI analysis.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Learning Recommendations** analyze job roles, performance gaps, and career aspirations to suggest personalized learning paths. The system integrates with online learning platforms (LinkedIn Learning, Coursera) for seamless access—typically increasing training completion rates from 40% to 75%. | Annex C3.6, Page 185; Training Portal |
| 7. | **Recruitment Tracking** | **FULLY COMPLY** | Recruitment module manages requisition-to-offer workflow with candidate database, interview scheduling, and offer letter generation. Onboarding checklists ensure new hire readiness.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **AI Resume Screening** automatically parses and ranks resumes against job requirements, reducing screening time by 75%. Predictive analytics identify candidates most likely to accept offers and succeed in roles—improving quality of hire by 30% and reducing time-to-fill by 40%. | Annex C3.7, Page 187; ATS Interface |
| 8. | **HR Analytics and Reporting** | **FULLY COMPLY** | HR dashboard provides headcount, turnover, attendance, and payroll summary reports with drill-down by branch, department, and job level. Standard reports support management and regulatory reporting.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Workforce Intelligence** provides predictive analytics for workforce planning (retirement forecasting, succession gaps, hiring needs). The system benchmarks MMF's HR metrics against industry peers using anonymized data—identifying improvement opportunities in engagement, productivity, and retention. | Annex C3.8, Page 189; HR Analytics |
| 9. | **Multi platform interface** | **FULLY COMPLY** | HRMS is accessible via web and mobile apps enabling employees to view payslips, apply for leave, and update personal details from anywhere. Managers can approve requests and view team information on mobile devices.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Employee Self-Service Chatbot** handles common HR queries ("How much annual leave do I have?", "When is my next pay date?") via WhatsApp/Teams, reducing HR administration workload by 60% while providing instant 24/7 employee support. | Annex C3.9, Page 191; Mobile App |
| 10. | **User-friendly interface** | **FULLY COMPLY** | Modern, intuitive interface requires minimal training. Employees can access payslips and submit leave requests within minutes of first login. Contextual help guides users through complex processes.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Voice-Enabled HR** allows employees to interact with the system using natural language ("Apply for 2 days annual leave starting tomorrow") via mobile or smart speakers. This accessibility feature is particularly valuable for field staff and drivers who may have limited typing ability while on duty. | Annex C3.10, Page 192; Voice Interface |
| 11. | **Audit Trail & History** | **FULLY COMPLY** | Complete audit trail captures all HR data changes with user identification, timestamps, and before/after values. Supports compliance with Malaysian employment regulations and internal audit requirements.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **GDPR/PDPA Compliance Module** automatically manages data retention policies, consent tracking, and data subject access requests. The system flags potential compliance risks (over-retention, unauthorized access) and generates compliance reports—reducing regulatory risk and audit preparation effort. | Annex D.2, Page 98; Compliance Audit |
| 12. | **Comprehensive security features** | **FULLY COMPLY** | Role-based access ensures employees see only their own data while managers see team data and HR sees all data. Sensitive information (salary, IC numbers) is encrypted with field-level access controls.<br><br>**🚀 VALUE-ADD ENHANCEMENT:** Our **Privacy-Preserving Analytics** allows HR to analyze workforce trends without exposing individual data (differential privacy). For example, analyzing gender pay gaps or diversity metrics while mathematically guaranteeing individual privacy—enabling data-driven decisions without compromising employee trust. | Annex D, Pages 95-110; Security Framework |

**Annexure C3 Summary:** 12/12 Features — **100% FULLY COMPLY**

---

## 3. COMPLIANCE SUMMARY

### 3.1 Overall Compliance Matrix

| Annexure | System | Total Features | Fully Comply | Partially Comply | Not Comply | Compliance % |
|----------|--------|----------------|--------------|------------------|------------|--------------|
| C1 | EMS | 12 | 12 | 0 | 0 | **100%** |
| C2 | PS | 13 | 13 | 0 | 0 | **100%** |
| C3 | HRMS | 12 | 12 | 0 | 0 | **100%** |
| **TOTAL** | | **37** | **37** | **0** | **0** | **100%** |

### 3.2 Integration Compliance

| Integration | Status | Evidence |
|-------------|--------|----------|
| EMS ↔ HMS (Vehicle Maintenance) | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| EMS ↔ FMS (Asset Depreciation) | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| PS ↔ FMS (3-Way Matching) | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| HRMS ↔ FMS (Payroll) | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| HRMS ↔ All (User Authentication) | ✅ FULLY COMPLY | Annex F.7, Page 176 |

### 3.3 Security & Compliance Certification

| Requirement | Status | Evidence |
|-------------|--------|----------|
| User Authentication | ✅ FULLY COMPLY | Annex D.1, Page 96 |
| Access Privileges (RBAC) | ✅ FULLY COMPLY | Annex D.3, Page 99 |
| Password Policy Enforcement | ✅ FULLY COMPLY | Annex D.4, Page 100 |
| Encrypted Passwords (AES-256) | ✅ FULLY COMPLY | Annex D.5, Page 101 |
| Security Auditing | ✅ FULLY COMPLY | Annex D.6, Page 102 |
| Data Protection Measures | ✅ FULLY COMPLY | Annex D.7, Page 103 |
| VAPT - Critical Findings | ✅ 0 Found | Annex D.8, Page 104 |
| VAPT - High Findings | ✅ 0 Found | Annex D.8, Page 104 |
| PDPA Compliance | ✅ FULLY COMPLY | Annex C3.11 |

---

## 4. PROJECT MANAGEMENT METHODOLOGY (PRINCE2)

### 4.1 Management Stages

| Stage | Duration | Key Deliverables | Stage Gate |
|-------|----------|------------------|------------|
| **Stage 1: Initiation** | 2 weeks | PID, Risk Register, Project Plan | Go/No-Go Decision |
| **Stage 2: Foundation** | 4 weeks | BRS/URS Sign-off, Technical Architecture | Requirements Freeze |
| **Stage 3: Delivery** | 6 weeks | EMS/PS/HRMS Configured, UAT Scripts | UAT Readiness |
| **Stage 4: Deployment** | 4 weeks | UAT Completion, Training, Go-Live | Production Release |
| **Stage 5: Closure** | 2 weeks | Handover, Warranty Begins, Project Closure | Final Acceptance |

### 4.2 Product-Based Planning

Our Work Breakdown Structure (WBS) follows Product-Based Planning:
- **Specialist Products:** EMS, PS, HRMS modules, integrations, reports
- **Management Products:** Plans, logs, reports, meeting minutes

### 4.3 Quality Register

| Product | Quality Criteria | Quality Method | Reviewer |
|---------|------------------|----------------|----------|
| BRS/URS | Completeness, traceability to SOW | Peer Review + Client Review | Business Analyst + MMF |
| EMS Configuration | Functional accuracy, data integrity | System Testing + User Demo | EMS Team Lead |
| PS Configuration | Workflow accuracy, integration | System Testing + User Demo | PS Team Lead |
| HRMS Configuration | Compliance, payroll accuracy | System Testing + User Demo | HRMS Team Lead |
| UAT Scripts | Coverage of all requirements | Traceability Matrix Check | QA Lead + MMF |

---

## 5. VALUE ADDED SERVICES (VAS) FRAMEWORK

### Part 1: Software & Innovation (10 Items)

| No. | Service | Market Value (RM) |
|-----|---------|-------------------|
| 1.1 | AI Predictive Maintenance for EMS | 250,000 |
| 1.2 | Smart Procurement Analytics | 200,000 |
| 1.3 | HR Predictive Analytics (Attrition) | 180,000 |
| 1.4 | Vendor Risk Intelligence Module | 150,000 |
| 1.5 | Employee Self-Service Chatbot | 120,000 |
| 1.6 | Advanced BI & Reporting Suite | 180,000 |
| 1.7 | Document OCR for Procurement | 100,000 |
| 1.8 | API Developer Portal | 100,000 |
| 1.9 | Data Migration Accelerator | 150,000 |
| 1.10 | Custom Report Development (15) | 120,000 |
| | **PART 1 SUBTOTAL** | **RM 1,550,000** |

### Part 2: Support & Consultative (10 Items)

| No. | Service | Market Value (RM) |
|-----|---------|-------------------|
| 2.1 | Change Management Launch Kit | 100,000 |
| 2.2 | Annual Health Checks (3 years) | 120,000 |
| 2.3 | 24/7 Premium Support (3 years) | 350,000 |
| 2.4 | Quarterly Business Reviews | 80,000 |
| 2.5 | Unlimited User Training | 180,000 |
| 2.6 | Data Quality Assessment | 80,000 |
| 2.7 | Disaster Recovery Drills | 100,000 |
| 2.8 | Process Optimization | 80,000 |
| 2.9 | Knowledge Transfer | 60,000 |
| 2.10 | Strategic HR Analytics | 80,000 |
| | **PART 2 SUBTOTAL** | **RM 1,230,000** |

### TOTAL VAS VALUE: **RM 2,780,000**

---

## 6. CONCLUSION

### 6.1 Summary of Compliance

| Metric | Result |
|--------|--------|
| Total Requirements | 37 |
| Fully Comply | 37 (100%) |
| Partially Comply | 0 (0%) |
| Not Comply | 0 (0%) |
| **Overall Compliance** | **100%** |

### 6.2 Why Sinergi Elit Sdn Bhd

1. **Proven Solution:** 95% of MMF requirements already engineered and deployed
2. **Domain Expertise:** 15+ successful logistics enterprise implementations
3. **Compliance Leadership:** Zero critical/high VAPT findings
4. **Accelerated Delivery:** 8-10 week go-live vs industry standard 6-9 months
5. **Value Beyond Price:** RM 2.78 Million in Value-Added Services
6. **Local Presence:** Malaysian company with onshore support
7. **Risk Mitigation:** PRINCE2 methodology with stage gates

### 6.3 Our Commitment

> *"We do not sell promises; we deliver documented results. Our LogisticsPro Support Suite is ready for MMF today—fully compliant, thoroughly tested, and proven in production environments."*

---

**Document Control**

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
