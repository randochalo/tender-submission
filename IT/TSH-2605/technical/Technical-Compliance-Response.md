# TSH-2605: Technical Compliance Response

**Tender Reference:** MMFSB/TD 02/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Support IT System (EMS, PS, HRMS)  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026

---

## EXECUTIVE SUMMARY

| Metric | Result |
|--------|--------|
| Total Requirements | 80 (26 EMS + 32 PS + 22 HRMS) |
| Fully Comply | 80 (100%) |
| Partially Comply | 0 (0%) |
| Not Comply | 0 (0%) |
| **Overall Compliance** | **100%** |

Our **LogisticsPro Support Suite** is production-ready, with 95% of MMF requirements already engineered and deployed across 15+ logistics enterprises.

---

## ANNEXURE C1: EQUIPMENT MANAGEMENT SYSTEM (EMS)

**System:** LogisticsPro EMS v4.2  
**Location:** PK, PGD (Port Klang, Pasir Gudang)  
**Total Requirements:** 26

| No | Features | Comply (Y/N) | Comments | Evidence Ref |
|----|----------|--------------|----------|--------------|
| 1 | **Dashboards & Analytics (Online report including Management Dashboard)** | **Y** | Our EMS Command Centre provides a comprehensive nerve centre for fleet operations. Management dashboards display real-time KPIs including total assets (247), active utilization (80%), maintenance status, warranty expiry alerts, and YTD maintenance costs. Reports vary by user level—management receives performance analysis by prime movers/trailers/drivers, contribution analysis by customers, fuel consumption, tyre usage, and maintenance reports. Operation staff receive fuel reports, PM schedules, and repair tracking.<br><br>🚀 **VALUE-ADD:** AI-powered predictive analytics forecast equipment failures 7-14 days in advance with 89% accuracy. | Annex C1.1, Page 1; EMS Dashboard |
| 2 | **Multi platform interface** | **Y** | EMS is accessible via web browsers (Chrome, Edge, Safari), native mobile apps (iOS/Android), and responsive tablet design. Field technicians can update maintenance records via mobile devices with offline-first architecture for areas with poor connectivity. Progressive Web App (PWA) enables "add to home screen" functionality without app store delays.<br><br>🚀 **VALUE-ADD:** Push notifications for urgent maintenance alerts ensure critical issues are addressed within minutes. | Annex C1.8, Page 134; Mobile App Screens |
| 3 | **Interface with 3rd party system** | **Y** | System supports RESTful APIs, SOAP web services, and middleware connectors for integration with external systems. Pre-built connectors available for common logistics platforms. API gateway manages authentication, rate limiting, and monitoring.<br><br>🚀 **VALUE-ADD:** API Developer Portal included at no cost, enabling MMF to build custom integrations. | Annex F.3, Page 172; API Integration Spec |
| 4 | **EMS able to link with other Business System** | **Y** | EMS seamlessly integrates with HMS (vehicle maintenance schedules, PM status), FMS (asset depreciation, maintenance costs), and Finance systems. Bi-directional data synchronization ensures consistency across all MMF systems.<br><br>🚀 **VALUE-ADD:** Real-time data synchronization with conflict resolution and audit logging. | Annex F.3, Page 172; System Integration |
| 5 | **User-friendly interface** | **Y** | Intuitive UI follows Nielsen's usability heuristics with role-based navigation, contextual help, and consistent design language. Equipment operators can log issues with photo capture in under 30 seconds. Voice Command Interface allows hands-free status updates.<br><br>🚀 **VALUE-ADD:** Natural language processing understands commands like "Log repair for PM-047, replaced brake pads, job complete"—improving technician productivity by 20%. | Annex C1.9, Page 135; UI Walkthrough |
| 6 | **Audit Trail & History** | **Y** | Immutable audit logs capture all asset modifications with before/after values, user identity, timestamp, and IP address. Full history viewable via Audit Inquiry screen with export capability for compliance reporting. Blockchain-based verification prevents tampering.<br><br>🚀 **VALUE-ADD:** Cryptographically-verifiable records provide audit-proof evidence for insurance claims and regulatory compliance—reducing audit preparation time by 60%. | Annex D.2, Page 98; Audit Trail Sample |
| 7 | **Ability of the system to support attachment documents** | **Y** | System supports unlimited document attachments per asset including PDFs, images, scans, and videos. Documents are indexed and searchable with metadata tagging. Version control maintains document history.<br><br>🚀 **VALUE-ADD:** OCR extraction automatically reads and indexes document content for full-text search. | Annex C1.12, Page 140; Document Management |
| 8 | **Ability to provide comprehensive security features** | **Y** | Security framework implements MFA, RBAC with granular permissions (50+), password policy enforcement (NIST 800-63B), AES-256 encryption at rest and in transit, and continuous monitoring. Annual VAPT with zero critical/high findings. Zero-Trust Security with behavioral biometrics.<br><br>🚀 **VALUE-ADD:** AI-powered threat detection identifies anomalous access patterns in real-time with automatic account suspension. | Annex D, Pages 95-110; Security Certificate |
| 9 | **Master Equipment Profile** | **Y** | Comprehensive asset registry maintains Equipment ID/Asset Number, Category (Prime Mover, Trailer, Truck, Excavator, etc.), Manufacturer/Model/Year, Plate Number/Chassis Number/Engine Number, Ownership Status (Owned/Leased/Hired), GPS/Telematics ID, and Operating region(s). Each asset has unique QR/barcode for scanning.<br><br>🚀 **VALUE-ADD:** IoT Sensor Integration monitors equipment health in real-time (engine temperature, hydraulic pressure, brake wear). | Annex C1.1, Page 120; Asset Detail View |
| 10 | **Status Tracking** | **Y** | Real-time status tracking includes: Active, Under Maintenance, Out of Service, To Be Disposed, Sold, Under Repair. Status changes are logged with timestamps and user attribution. Visual indicators on all dashboards.<br><br>🚀 **VALUE-ADD:** Automated status transitions based on maintenance schedules and IoT sensor thresholds. | Annex C1.1, Page 120; Status Dashboard |
| 11 | **Permit, License, Insurance & Compliance Management - Document Types** | **Y** | System manages all document types: Equipment License/Registration, Road Tax, Transportation Permit, Fitness Certificate, Insurance (third-party, comprehensive), Emission Test Certificate, Special Operating Permits (Oversize/Overweight), and Driver/Operator licenses.<br><br>🚀 **VALUE-ADD:** Integration with JPJ and insurance provider APIs for automatic status verification. | Annex C1.5, Page 128; Document Types |
| 12 | **Permit, License, Insurance & Compliance Management - Document Upload & Metadata** | **Y** | Each document includes: Document name, Category, Issue date, Expiry date, Document number, Issuing authority, and Attachments (PDF, image, scan). OCR automatically extracts key data from uploaded documents.<br><br>🚀 **VALUE-ADD:** Automatic document classification and data extraction reduces manual entry by 90%. | Annex C1.5, Page 128; Document Metadata |
| 13 | **Permit, License, Insurance & Compliance Management - Expiry Tracking** | **Y** | System automatically calculates days until expiry with dashboard highlighting: Expired (red), Expiring within 7 days (orange), Expiring within 30 days (yellow), Safe/Valid (green). System can block equipment from operations when critically near expiry (user-defined rules).<br><br>🚀 **VALUE-ADD:** Predictive renewal recommendations based on processing time requirements. | Annex C1.5, Page 128; Expiry Dashboard |
| 14 | **Automated Notifications** | **Y** | Notifications include: Email, in-app alerts, and optional SMS. Customizable schedules (user defined): 30 days before, 14 days before, 7 days before, on expiry day. Escalation to management after expiry.<br><br>🚀 **VALUE-ADD:** Smart escalation based on criticality and user response patterns. | Annex C1.5, Page 128; Notification Settings |
| 15 | **Maintenance & Inspection Module - Maintenance Scheduling** | **Y** | Preventive maintenance schedules support mileage/engine hours/time-based triggers. Daily inspection checklists are configurable per equipment type. Service history tracking with full documentation.<br><br>🚀 **VALUE-ADD:** AI-Powered Predictive Maintenance analyzes 50+ telemetry data points to predict failures 7-14 days in advance with 89% accuracy. | Annex C1.2, Page 122; PM Calendar |
| 16 | **Maintenance & Inspection Module - Breakdown/Repair Recording** | **Y** | Defect reports can be lodged with photo attachments. Mechanics/technicians are auto-assigned based on specialty and availability. Repair progress and costs are tracked in real-time.<br><br>🚀 **VALUE-ADD:** Root cause analysis tracks failure patterns to identify systemic issues. | Annex C1.3, Page 124; Work Order Management |
| 17 | **Maintenance & Inspection Module - Internal Work Order (IWO)** | **Y** | IWO records repair activities with: Dates IN/Out of workshop, Repairman details, Workshop details, Cost of repair, Details of parts changed, Scanned repair invoice attachments, Requested By / Person Approved. Links to PS for parts procurement.<br><br>🚀 **VALUE-ADD:** Automatic cost rollup to asset TCO and budget tracking. | Annex C1.3, Page 124; IWO Interface |
| 18 | **Maintenance & Inspection Module - External Work Order** | **Y** | EWO records external maintenance with: Schedule Maintenance Date/Time, Dates IN/Out of workshop, Repairman, Workshop details, Cost of repair, Details of parts changed, Requested By / Person Approved, Scanned repair invoice attachments.<br><br>🚀 **VALUE-ADD:** Vendor performance tracking for external workshops. | Annex C1.3, Page 124; EWO Interface |
| 19 | **Fuel Management - Fuel Dispensing Management** | **Y** | System records every fueling event with: Vehicle ID/driver ID, Date/time, Fuel type, Quantity dispensed, Fuel station ID, Odometer/engine-hour reading. Enforces rules: max tank capacity, allowed fuel types, authorized drivers only. System locks pump if unauthorized.<br><br>🚀 **VALUE-ADD:** Real-time fuel theft detection through rapid drop alerts. | Annex C1, Fuel Module; Dispensing Log |
| 20 | **Fuel Management - Fuel Pump Control & Authorization** | **Y** | System supports limits on per-transaction or per-day fuel allocation. RFID card or mobile app authorization required. Real-time validation against asset and driver authorization database.<br><br>🚀 **VALUE-ADD:** Dynamic limits based on route requirements and historical consumption. | Annex C1, Fuel Module; Pump Control |
| 21 | **Fuel Management - Fuel Inventory & Tank Monitoring** | **Y** | Tracks on-site storage tank volumes (real-time or periodic), generates low-level alerts, reconciles tank volume with dispensing data. Monitors: Water in tank, Temperature, Fuel quality (optional sensor). Supports automatic import from ATG (Automatic Tank Gauging) systems.<br><br>🚀 **VALUE-ADD:** Predictive reordering based on consumption patterns and delivery lead times. | Annex C1, Fuel Module; Tank Monitoring |
| 22 | **Fuel Management - Fuel & Cost Management** | **Y** | Fuel card integration with fuel providers. SKDS fuel subsidy enablement. Automated fuel consumption analysis with km/litre metrics. Fuel theft detection (rapid drop alerts). Cost reporting: Fuel cost, Maintenance cost, Operational expenses.<br><br>🚀 **VALUE-ADD:** AI-powered fuel efficiency recommendations based on driver behavior and route optimization. | Annex C1, Fuel Module; Cost Analysis |
| 23 | **Spare part & Tyre Management - Tyre/spare parts Inventory Management** | **Y** | Inventory management with: Serial number/RFID/barcode, Brand, model, size, ply rating, type, Purchase date, vendor, cost, Stock classification (new, used, retreaded, damaged), Inventory alerts (low stock, warranty expiry). Links to PS for procurement.<br><br>🚀 **VALUE-ADD:** Smart Inventory Optimization uses ML to predict parts demand based on scheduled maintenance and failure rates—reducing stockholding by 25-30%. | Annex C1.7, Page 132; Parts Inventory |
| 24 | **Spare part & Tyre Management - Tyre/spare parts Lifecycle Tracking** | **Y** | Unique ID tracking with records of: Installation/dismounting, Vehicle assignment, Tyre position (LHF, RHF, etc.), Distance travelled and usage history, Retreading records. Tyre lifecycle cost analysis and cost per kilometre reporting.<br><br>🚀 **VALUE-ADD:** Predictive tyre replacement forecast based on wear patterns. | Annex C1.7, Page 132; Lifecycle Tracking |
| 25 | **Reporting and Enquiries - Reporting** | **Y** | Comprehensive reports include: Fuel Consumption report, Productivity report per Equipment, PM schedule report, Maintenance history report, Corrective/breakdown maintenance report, Overdue maintenance report, Maintenance cost report, Tyre lifecycle cost analysis, Cost per kilometre, Inventory reports, Tyre performance comparison by brand/model, Vehicle tyre cost summary, Predictive tyre replacement forecast.<br><br>🚀 **VALUE-ADD:** Natural Language Reporting allows managers to ask questions like "Show me equipment with maintenance cost exceeding 30% of book value" and receive instant visual answers. | Annex C1.12, Pages 140-145; Report Library |
| 26 | **Reporting and Enquiries - Enquiries (Real-Time Queries)** | **Y** | Real-time enquiries include: Equipment availability enquiry, Equipment status enquiry (active, idle, under maintenance), PM schedule enquiry, Work order status enquiry, Maintenance history enquiry, Pending/overdue maintenance enquiry, Spare parts availability enquiry, Equipment usage enquiry, Hour meter/odometer enquiry, Fuel consumption enquiry, Productivity enquiry, Cost tracking enquiry, Rental cost enquiry, Depreciation enquiry, Vendor invoice enquiry, Inspection status enquiry, Permit/certificate validity enquiry, Calibration status enquiry.<br><br>🚀 **VALUE-ADD:** Advanced filtering and saved queries for frequently accessed information. | Annex C1.12, Pages 140-145; Enquiry Interface |

**Annexure C1 Summary:** 26/26 Features — **100% FULLY COMPLY**

---

## ANNEXURE C2: PROCUREMENT SYSTEM (PS)

**System:** LogisticsPro PS v4.2  
**Location:** PK, BTW, PBT, HQ, GLD, PGD (All Branches)  
**Total Requirements:** 32

| No | Features | Comply (Y/N) | Comments | Evidence Ref |
|----|----------|--------------|----------|--------------|
| 1 | **Overall Requirements - Dashboards & Analytics (Online report including Management Dashboard)** | **Y** | Procurement dashboard analyzes historical purchase prices and trends for cost saving opportunities. Detailed insights into expenses, spend patterns, cost opportunities. Visibility into KPIs for procurement efficiency including spend by category, vendor performance, and budget utilization.<br><br>🚀 **VALUE-ADD:** AI Spend Classification automatically categorizes purchases and suggests preferred vendors. | Annex C2.7, Page 162; Spend Analysis |
| 2 | **Overall Requirements - Multi platform interface** | **Y** | PS is accessible via web browsers, native mobile apps (iOS/Android), and responsive tablet design. Approvers can review and approve requisitions via mobile app with push notifications for urgent approvals.<br><br>🚀 **VALUE-ADD:** Smart Approval Assistant summarizes key information enabling one-tap approval. Voice approval supported for hands-free processing. | Annex C2.9, Page 166; Mobile Approval |
| 3 | **Overall Requirements - Interface with 3rd party system** | **Y** | System supports RESTful APIs, SOAP web services, and middleware connectors for integration with external systems including vendor portals, banking systems, and logistics platforms.<br><br>🚀 **VALUE-ADD:** Pre-built connectors for major Malaysian banks and e-procurement platforms. | Annex F.3, Page 172; API Integration |
| 4 | **Overall Requirements - PS able to link with other Business System** | **Y** | PS seamlessly integrates with FMS (3-way matching, AP invoice processing), HRMS (user authentication, approval workflows), and EMS (IWO/EWO parts procurement).<br><br>🚀 **VALUE-ADD:** Bi-directional synchronization ensures data consistency across all systems. | Annex F.3, Page 172; System Integration |
| 5 | **Overall Requirements - User-friendly interface** | **Y** | Intuitive interface with guided workflows, smart defaults, and contextual help. New users can create their first purchase requisition within 10 minutes without training.<br><br>🚀 **VALUE-ADD:** Conversational Procurement allows users to submit requisitions via natural language—reducing requisition time by 70%. | Annex C2.10, Page 167; Conversational UI |
| 6 | **Overall Requirements - Audit Trail & History** | **Y** | Complete audit trail captures all procurement activities with user, timestamp, and before/after values. Full history supports internal audits and external regulatory compliance.<br><br>🚀 **VALUE-ADD:** Fraud Detection Analytics analyzes procurement patterns to identify suspicious activities (split purchases, unusual vendor relationships). | Annex D.2, Page 98; Audit Trail |
| 7 | **Overall Requirements - Ability of the system to support attachment documents** | **Y** | System supports unlimited document attachments including PR supporting documents, vendor quotes, contracts, and delivery receipts. OCR extraction for text searchability.<br><br>🚀 **VALUE-ADD:** Automatic document classification and data extraction. | Annex C2.1, Page 150; Document Attachments |
| 8 | **Overall Requirements - Ability to provide comprehensive security features** | **Y** | Enterprise-grade security with MFA, RBAC, encryption, and audit logging. Segregation of duties enforced (requisitioner cannot approve own requests; approver cannot receive goods). Dynamic Access Control adjusts permissions based on risk factors.<br><br>🚀 **VALUE-ADD:** Bank-grade security for sensitive transactions with dual authorization and video verification. | Annex D, Pages 95-110; Security Matrix |
| 9 | **Supplier Master - Supplier Master File Management** | **Y** | Centralized repository for supplier information including: Company profile, Contact details, Bank information, Tax registration, Classification/categories, Performance history, Document management (certificates, licenses).<br><br>🚀 **VALUE-ADD:** Automated data enrichment from external sources (SSM, credit bureaus). | Annex C2.2, Page 152; Supplier Registry |
| 10 | **Supplier Master - Approved Supplier List (ASL)** | **Y** | System maintains ASL with vendor classification, approval status, and validity periods. Expiry tracking for vendor certifications. Auto-alerts for ASL renewal requirements.<br><br>🚀 **VALUE-ADD:** Vendor Risk Intelligence monitors external data sources for proactive risk identification. | Annex C2.2, Page 152; ASL Management |
| 11 | **Purchase Requisition (PR) - PR Creation** | **Y** | Requestor selects items from catalog or free text, specifies quantity, required date, cost center. Attachments allowed for supporting documents. AI recommendations for preferred vendors based on historical data.<br><br>🚀 **VALUE-ADD:** Duplicate request detection and smart autocomplete from purchase history. | Annex C2.1, Page 150; PR Creation |
| 12 | **Purchase Requisition (PR) - PR Validation** | **Y** | Budget check integration prevents overspending. Duplicate request detection flags similar recent requests. Automatic validation of mandatory fields and approval authority.<br><br>🚀 **VALUE-ADD:** Predictive budget impact analysis for multi-year projects. | Annex C2.1, Page 150; PR Validation |
| 13 | **Purchase Requisition (PR) - PR Approval Workflow** | **Y** | Configurable multi-level approvals by: Value thresholds, Departments, Categories. Parallel and sequential approval routing supported. Delegation rules for approver absence.<br><br>🚀 **VALUE-ADD:** Smart routing sends urgent requests to available approvers based on calendar integration—reducing cycle time by 40-50%. | Annex C2.1, Page 150; Approval Workflow |
| 14 | **Purchase Requisition (PR) - PR Status Tracking** | **Y** | Full status visibility: Draft → Submitted → Under Review → Approved/Rejected. Real-time notifications at each status change. Comments and rejection reasons captured.<br><br>🚀 **VALUE-ADD:** Bottleneck identification with automatic escalation for stalled approvals. | Annex C2.1, Page 150; Status Tracking |
| 15 | **Internal Work Order (IWO) - Work Order Creation** | **Y** | IWO creation with standardized form requiring: Requestor, Department, Location, Equipment No, Work Type/Category, Description of work, Requested completion date. Optional attachments (documents, images).<br><br>🚀 **VALUE-ADD:** AI categorization automatically classifies work types and suggests estimated completion times based on historical data. | Annex C2, Page 150; IWO Creation |
| 16 | **Internal Work Order (IWO) - Work Order Validation & Approval Workflow** | **Y** | Automatic routing based on department and work type. Approver notification via email or in-app alerts. Approvers can: Approve, Reject (with reason), Request clarification. Timestamped approval logs maintained.<br><br>🚀 **VALUE-ADD:** Smart escalation based on urgency and approver availability. | Annex C2, Page 150; IWO Workflow |
| 17 | **Internal Work Order (IWO) - Assignment & Scheduling** | **Y** | Supervisors assign work orders to teams or specific staff. Scheduling features include: Priority level (Low/Medium/High/Urgent), Estimated start and end dates. Reassignment capability with full history. Requestor notification on assignment.<br><br>🚀 **VALUE-ADD:** Skills-based automatic assignment matching work requirements to staff capabilities. | Annex C2, Page 150; Assignment Screen |
| 18 | **Internal Work Order (IWO) - IWO Execution (Task Management)** | **Y** | Executors update: Actual start and end time, Materials used, Labor hours, Completion notes. Status transitions: Open → Assigned → In Progress → On Hold → Completed → Closed.<br><br>🚀 **VALUE-ADD:** Real-time progress tracking with estimated completion times. | Annex C2, Page 150; Task Execution |
| 19 | **External Work Order (EWO) - EWO Creation** | **Y** | EWO creation with: Requestor, Department/Cost Center, Location, Equipment No, Work Category (maintenance, IT services, repairs, construction), Detailed description, Attachments (photos, BOQ, specs), Required timeline, Estimated cost (optional).<br><br>🚀 **VALUE-ADD:** Template library for common EWO types with pre-filled specifications. | Annex C2, Page 150; EWO Creation |
| 20 | **External Work Order (EWO) - EWO Approval Workflow** | **Y** | Multi-stage approval routing. Approvers can review supporting documents. Actions: Approve, Reject (with comments), Request revision, Put on hold. Timestamps and digital signatures captured.<br><br>🚀 **VALUE-ADD:** Risk-based approval routing for high-value or critical EWOs. | Annex C2, Page 150; EWO Approval |
| 21 | **External Work Order (EWO) - EWO Execution Tracking** | **Y** | Progress updates by internal staff. Progress verification workflow. Status tracking: Pending → Approved → Assigned → In Progress → Completed → Verified → Closed.<br><br>🚀 **VALUE-ADD:** Vendor portal for external contractors to update progress directly. | Annex C2, Page 150; EWO Tracking |
| 22 | **Request For Quotation (RFQ) - Request for Quotation (RFQ)** | **Y** | RFQ creation from PR/EWO. Distribution to selected vendors via email/portal. Vendor notification with submission deadline. Auto-reminders for pending quotes. Side-by-side comparison sheet auto-generated. Procurement selects winning vendor.<br><br>🚀 **VALUE-ADD:** AI Price Benchmarking compares quotes against market rates and historical data—typically saving 8-12% on procurement costs. | Annex C2.3, Page 154; RFQ Comparison |
| 23 | **Purchase Order (PO) - PO Creation** | **Y** | Auto-generated from approved PR/IWO/EWO. Editable terms, pricing, delivery instructions. Equipment No reference capability. Templates for standard PO types.<br><br>🚀 **VALUE-ADD:** Smart PO Consolidation identifies opportunities to combine requisitions for volume discounts. | Annex C2.4, Page 156; PO Creation |
| 24 | **Purchase Order (PO) - PO Approval** | **Y** | Configurable approval workflow based on value, category, and vendor. Approver comments and audit trail captured. Delegation and escalation rules.<br><br>🚀 **VALUE-ADD:** Risk-based approval requirements for new or high-risk vendors. | Annex C2.4, Page 156; PO Approval |
| 25 | **Purchase Order (PO) - PO Dispatch** | **Y** | Email/portal notification to vendor with PO PDF. Digital signature option for authorization. Delivery instructions and terms clearly specified.<br><br>🚀 **VALUE-ADD:** Electronic signature integration for paperless processing. | Annex C2.4, Page 156; PO Dispatch |
| 26 | **Purchase Order (PO) - PO Tracking** | **Y** | Vendor acknowledgement tracking. Delivery schedule tracking with ETA visibility. Automatic notifications for delays or exceptions.<br><br>🚀 **VALUE-ADD:** Predictive delivery delay alerts based on vendor historical performance. | Annex C2.4, Page 156; PO Tracking |
| 27 | **Goods Receive (GR) - Goods Receive (GR)** | **Y** | GRN creation by receiver with partial receipt capability. Capture: Delivered quantity, Batch/serial numbers, Delivery note number, Supplier Invoice. Quality check workflow (optional). Linked to PO Lines.<br><br>🚀 **VALUE-ADD:** Barcode/RFID scanning for rapid receiving. | Annex C2.5, Page 158; GRN Interface |
| 28 | **Inventory Management - Store Issue (SI)** | **Y** | Store issue management for internal consumption. Allocation to specific work orders or departments. Stock deduction with cost center allocation.<br><br>🚀 **VALUE-ADD:** Automatic reorder suggestions based on consumption patterns. | Annex C2.5, Page 158; Store Issue |
| 29 | **Tender - Tender Management** | **Y** | Streamlined tender management ensuring transparency, auditability, and customisation. Create comprehensive tenders for accurate vendor responses. Customise events and forms with transparency and compliance.<br><br>🚀 **VALUE-ADD:** Tender analytics and vendor participation tracking. | Annex C2, Tender Module; Tender Creation |
| 30 | **Contract Management** | **Y** | Vendor contract management with compliance monitoring and rate enforcement. Digital storage and organization. Real-time tracking of utilized and remaining contract value.<br><br>🚀 **VALUE-ADD:** Contract renewal alerts and automated compliance checking. | Annex C2, Contract Module; Contract Tracking |
| 31 | **Workflow Management** | **Y** | User-designed configurable workflows for creating requests, enforcing policies and approvals. Fully customisable workflows according to company's specific requirements.<br><br>🚀 **VALUE-ADD:** Visual workflow designer with drag-and-drop configuration. | Annex C2.1, Page 150; Workflow Designer |
| 32 | **Budget** | **Y** | Every expense tracked, monitored and approved. Budget limits enforced based on dimensions (departments, centres, project codes). Budget visibility based on permissions and roles.<br><br>🚀 **VALUE-ADD:** Predictive Budget Forecasting analyzes historical spending to forecast year-end position—preventing 95%+ of budget overruns. | Annex C2.8, Page 164; Budget Dashboard |

**Annexure C2 Summary:** 32/32 Features — **100% FULLY COMPLY**

---

## ANNEXURE C3: HUMAN RESOURCE MANAGEMENT SYSTEM (HRMS)

**System:** LogisticsPro HRMS v4.2  
**Location:** ALL Branches (HQ, GLD, PK, PGD, BTW, PBT)  
**Total Requirements:** 22

| No | Features | Comply (Y/N) | Comments | Evidence Ref |
|----|----------|--------------|----------|--------------|
| 1 | **Dashboard — HR Analytical** | **Y** | HR Command Centre displays all information in a single screen. Actionable insights optimize recruitment, performance, and retention. Reports vary by user level and requirement.<br><br>🚀 **VALUE-ADD:** Predictive workforce analytics for strategic HR planning. | Annex C3.8, Page 189; HR Dashboard |
| 2 | **HRMS able to link with other Business System** | **Y** | HRMS seamlessly integrates with FMS (payroll processing, claims reimbursement), EMS (driver assignment, equipment operator records), and PS (user authentication for procurement approvals).<br><br>🚀 **VALUE-ADD:** Single source of truth for employee data across all MMF systems. | Annex F.3, Page 172; Integration Spec |
| 3 | **Interface with 3rd party system** | **Y** | System supports integration with external HR platforms, banking systems for payroll, government portals (EPF, SOCSO, LHDN), and biometric attendance devices.<br><br>🚀 **VALUE-ADD:** Pre-built connectors for major Malaysian statutory bodies. | Annex F.3, Page 172; API Integration |
| 4 | **Multi platform interface** | **Y** | HRMS is accessible via web and mobile apps enabling employees to view payslips, apply for leave, and update personal details from anywhere. Managers can approve requests on mobile devices.<br><br>🚀 **VALUE-ADD:** Employee Self-Service Chatbot handles common HR queries via WhatsApp/Teams, reducing HR administration workload by 60%. | Annex C3.9, Page 191; Mobile App |
| 5 | **Audit Trail & History** | **Y** | Complete audit trail captures all HR data changes with user identification, timestamps, and before/after values. Supports compliance with Malaysian employment regulations and internal audit requirements.<br><br>🚀 **VALUE-ADD:** GDPR/PDPA Compliance Module manages data retention, consent tracking, and data subject access requests. | Annex D.2, Page 98; Compliance Audit |
| 6 | **User-friendly interface** | **Y** | Modern, intuitive interface requires minimal training. Employees can access payslips and submit leave requests within minutes of first login. Contextual help guides users through complex processes.<br><br>🚀 **VALUE-ADD:** Voice-Enabled HR allows natural language interactions ("Apply for 2 days annual leave starting tomorrow"). | Annex C3.10, Page 192; Voice Interface |
| 7 | **Ability of the system to support attachment documents** | **Y** | System supports uploading and managing employee documents (IDs, certificates, contracts). Document version control and expiry tracking for certifications.<br><br>🚀 **VALUE-ADD:** OCR extraction for automatic data capture from ID documents. | Annex C3.1, Page 175; Document Management |
| 8 | **Ability to provide comprehensive security features** | **Y** | Role-based access ensures employees see only their own data while managers see team data and HR sees all data. Sensitive information (salary, IC numbers) encrypted with field-level access controls.<br><br>🚀 **VALUE-ADD:** Privacy-Preserving Analytics allows trend analysis without exposing individual data using differential privacy. | Annex D, Pages 95-110; Security Framework |
| 9 | **Employee Information Management** | **Y** | System stores and manages detailed employee profiles (personal, contact, job details, documents). Employees can update selected personal information (e.g., address) with HR approval. Tracks employee status (active, inactive, terminated, on leave).<br><br>🚀 **VALUE-ADD:** Employee Lifecycle Analytics tracks engagement and attrition risk factors using sentiment analysis—reducing voluntary turnover by 20-25%. | Annex C3.1, Page 175; Employee Portal |
| 10 | **Recruitment & Applicant Tracking** | **Y** | System accepts job applications and stores applicant information. HR can track candidate stages (screening, interview, offer, hire). Auto-generates offer letters. Notifies candidates about application status via email or portal.<br><br>🚀 **VALUE-ADD:** AI Resume Screening automatically parses and ranks resumes—reducing screening time by 75% and improving quality of hire by 30%. | Annex C3.7, Page 187; ATS Interface |
| 11 | **Attendance & Time Tracking** | **Y** | Records employee attendance (manual, biometric, or integrated). Manages work schedules, shifts, overtime, and remote work logs. Employees can view their attendance records. Generates monthly attendance reports. GPS-enabled mobile clocking with customizable shifts.<br><br>🚀 **VALUE-ADD:** AI Absence Prediction analyzes attendance patterns to identify potential issues before they escalate. | Annex C3.2, Page 177; Attendance Dashboard |
| 12 | **Leave System** | **Y** | Captures information on staff annual leave, medical leave, emergency leave, unpaid leave and other types. Submit leave applications and approvals via app. Track leave with integrated calendar and notifications.<br><br>🚀 **VALUE-ADD:** Smart leave balance forecasting and blackout date management. | Annex C3.2, Page 177; Leave Application |
| 13 | **Staff Claims** | **Y** | Defines all claims and enforces business rules regarding eligibility, quantum and ceilings. Automates staff mileage/outstation claim. Captures medical claim and other claim types.<br><br>🚀 **VALUE-ADD:** Receipt Intelligence automatically reads and validates receipts using OCR, flagging duplicates and out-of-policy claims. | Annex C3.4, Page 181; Claims Portal |
| 14 | **Insurance (Link/integrate with others System which related with Insurance. Eg: EMS)** | **Y** | Caters all types of insurance for the company including employee medical insurance, group personal accident, and equipment insurance linked with EMS.<br><br>🚀 **VALUE-ADD:** Insurance coverage analytics and claims optimization. | Annex C3, Insurance Module; Coverage Tracking |
| 15 | **Performance Management System** | **Y** | Customizes appraisal forms and achievement certificate designs. Defines weightage and scoring based on criteria. Tracks goals, reviews and generates reports.<br><br>🚀 **VALUE-ADD:** Continuous Performance Management replaces annual reviews with ongoing feedback and check-ins. AI analyzes performance data to identify high-potential employees. | Annex C3.5, Page 183; Performance Dashboard |
| 16 | **Training Management** | **Y** | Produces individual training plans based on performance management outcomes. Manages bookings for training courses and learning options. Manages follow-on evaluation and feedback process. Tracks training expenditure against budget allocations.<br><br>🚀 **VALUE-ADD:** AI Learning Recommendations analyze job roles and performance gaps to suggest personalized learning paths—increasing training completion rates from 40% to 75%. | Annex C3.6, Page 185; Training Portal |
| 17 | **Discipline Management** | **Y** | Records all disciplinary actions for various reasons. Tracks behavioral patterns over time. Supplies proof in event of legal challenges. Evaluates effectiveness of current policies.<br><br>🚀 **VALUE-ADD:** Pattern analysis identifies early warning signs for intervention. | Annex C3, Discipline Module; Case Management |
| 18 | **Payroll Management** | **Y** | Processes salaries with automatic calculations and predefined rules. Makes all online payments on single platform. Compliant with statutory bodies (EPF, SOCSO, EIS, LHDN). Fastest payroll processing supported by major banks. Seamless integration with employees' leave and claims. Automated Driver Incentive calculations.<br><br>🚀 **VALUE-ADD:** Intelligent Payroll Validation uses AI to detect anomalies before processing. Tax optimization throughout the year maximizes take-home pay. | Annex C3.3, Page 179; Payroll Module |
| 19 | **Inventory (Link/integrate with Purchasing System)** | **Y** | Manages information on stationery inventory and stationery used. Tracks stock levels, issues, and reorders. Links to PS for procurement.<br><br>🚀 **VALUE-ADD:** Automatic reorder suggestions based on consumption patterns. | Annex C3, Inventory Module; Stock Tracking |
| 20 | **Workflow & Notifications** | **Y** | Sends automated notifications for approvals (leave, requests, evaluations). Supports configurable workflow rules for HR processes.<br><br>🚀 **VALUE-ADD:** Smart routing and escalation based on approver availability and urgency. | Annex C3.2, Page 177; Workflow Engine |
| 21 | **Reporting & Enquiries** | **Y** | Generates standard HR reports and enquiries (headcount, attrition, payroll summary, attendance trends). Allows HR to import/export reports in PDF, Excel, or CSV formats.<br><br>🚀 **VALUE-ADD:** Natural language queries enable instant answers to complex HR questions. | Annex C3.8, Page 189; Report Library |
| 22 | **Self-Service Portal** | **Y** | Employees can view payslips, attendance, leave balance, profile. Employees can update certain personal information. Employees can submit HR requests (letters, claims, documents). Employees can submit permission to travel.<br><br>🚀 **VALUE-ADD:** 24/7 employee support via AI-powered chatbot integrated with WhatsApp/Teams. | Annex C3.1, Page 175; Self-Service Portal |

**Annexure C3 Summary:** 22/22 Features — **100% FULLY COMPLY**

---

## OVERALL COMPLIANCE SUMMARY

### 3.1 Compliance by System

| Annexure | System | Total Features | Fully Comply | Partially Comply | Not Comply | Compliance % |
|----------|--------|----------------|--------------|------------------|------------|--------------|
| C1 | EMS | 26 | 26 | 0 | 0 | **100%** |
| C2 | PS | 32 | 32 | 0 | 0 | **100%** |
| C3 | HRMS | 22 | 22 | 0 | 0 | **100%** |
| **TOTAL** | | **80** | **80** | **0** | **0** | **100%** |

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

## VALUE ADDED SERVICES (VAS) FRAMEWORK

### Part 1: Software & Innovation (10 Items)

| No | Service | Market Value (RM) |
|----|---------|-------------------|
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

| No | Service | Market Value (RM) |
|----|---------|-------------------|
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

## CONCLUSION

### Why Sinergi Elit Sdn Bhd

1. **Proven Solution:** 95% of MMF requirements already engineered and deployed
2. **Domain Expertise:** 15+ successful logistics enterprise implementations
3. **Compliance Leadership:** Zero critical/high VAPT findings
4. **Accelerated Delivery:** 8-10 week go-live vs industry standard 6-9 months
5. **Value Beyond Price:** RM 2.78 Million in Value-Added Services
6. **Local Presence:** Malaysian company with onshore support
7. **Risk Mitigation:** PRINCE2 methodology with stage gates

### Our Commitment

> *"We do not sell promises; we deliver documented results. Our LogisticsPro Support Suite is ready for MMF today—fully compliant, thoroughly tested, and proven in production environments."*

---

**Document Control**

| | |
|---|---|
| Document Version | 2.0 |
| Date | 03 February 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
