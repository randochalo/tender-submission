# TSH-2604: Technical Compliance Response

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Business Operating & Finance IT System  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026

---

## EXECUTIVE GUIDE TO EVIDENCE

| What You Need | Where to Find It | Section |
|---------------|------------------|---------|
| System Architecture Overview | Annex A - Technical Architecture | Page 15 |
| Compliance Proof by System | Annex C1-C5 - Compliance Matrices | Page 25 |
| Security & VAPT Certification | Annex D - Security Assessment | Page 95 |
| Live System Screenshots | Annex E - System Evidence | Page 120 |
| API Integration Specs | Annex F - Integration Guide | Page 165 |
| UAT Test Scripts | Annex G - Testing Documentation | Page 200 |
| PRINCE2 Project Plan | Annex H - Project Methodology | Page 250 |
| 10+10 VAS Framework | Section 7 - Value Added Services | Page 12 |

---

## OUR VALUE PROPOSITION

### The Accelerated Baseline Advantage

Our **LogisticsPro Enterprise Suite** is **production-ready today**, not a promise for tomorrow:

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

**RM 2.8 Million** in Value-Added Services included at **NO ADDITIONAL COST** (see Section 7).

---

## 1. SCOPE & TRACEABILITY MATRIX

### 1.1 System Coverage

| System | Annexure | Locations | Features | Status |
|--------|----------|-----------|----------|--------|
| Haulage Management System (HMS) | C1 | PK, HQ | 19 | ✅ FULLY COMPLY |
| Forwarding Management System (FFS) | C2 | PK, GLD, BTW, PGD | 21 | ✅ FULLY COMPLY |
| Warehouse Management System (WMS) | C3 | PK, HQ | 27 | ✅ FULLY COMPLY |
| Terminal Management System (TMS) | C4 | PK, BTW | 25 | ✅ FULLY COMPLY |
| Finance Management System (FMS) | C5 | ALL Branches | 37 | ✅ FULLY COMPLY |
| **TOTAL** | | **6 Branches** | **129** | **✅ 100%** |

### 1.2 Branch Deployment Matrix

| Branch | HMS | FFS | WMS | TMS | FMS |
|--------|-----|-----|-----|-----|-----|
| Headquarters (HQ) | ✅ | — | ✅ | — | ✅ |
| Global Logistics Dept (GLD) | — | ✅ | — | — | ✅ |
| Port Klang (PK) | ✅ | ✅ | ✅ | ✅ | ✅ |
| Pasir Gudang (PGD) | — | ✅ | — | — | ✅ |
| Butterworth (BTW) | — | ✅ | — | ✅ | ✅ |
| Padang Besar | — | — | — | — | ✅ |

---

## 2. COMPLIANCE-PLUS RESPONSE

### Compliance Philosophy

For every requirement, we provide:
1. **FULLY COMPLY** declaration — Never just "Yes"
2. **2-Sentence Technical Justification** — Specific functionality explanation
3. **Evidence Cross-Reference** — Link to Annex/Section/Page

---

## ANNEXURE C1: HAULAGE MANAGEMENT SYSTEM (HMS)

**Location:** PK, HQ  
**System Version:** LogisticsPro HMS v4.2  
**Deployment Model:** Cloud-native with offline mobile capability

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Dashboards & Analytics** | **FULLY COMPLY** | Our HMS includes a real-time Operations Command Centre with customizable KPI widgets showing fleet utilization, on-time delivery rates, and driver performance metrics. The analytics engine uses predictive algorithms to forecast maintenance needs and optimize route planning based on historical data patterns. | Annex E.1, Pages 120-125; Live Demo Video (QR Code) |
| 2. | **Multi platform interface** | **FULLY COMPLY** | The system architecture follows responsive design principles ensuring seamless functionality across desktop (Windows/macOS), web browsers (Chrome/Edge/Safari), and mobile devices (iOS/Android native apps). All platforms share a unified codebase with real-time synchronization via WebSocket connections. | Annex E.2, Page 126; System Architecture Diagram |
| 3. | **Interface with 3rd party system** | **FULLY COMPLY** | Our Integration Layer supports RESTful APIs, SOAP web services, SFTP, and EDI protocols for connecting with Port Klang Authority, JPJ, Customs (MyGBS), and customer ERP systems. Pre-built connectors available for SAP, Oracle, Microsoft Dynamics, and custom proprietary systems. | Annex F, Pages 165-180; API Documentation |
| 4. | **HMS able to link with other Business/Support system** | **FULLY COMPLY** | Native integration with our FMS, WMS, and TMS modules via enterprise service bus (ESB) architecture enables real-time data exchange between systems. For example, job completion in HMS automatically triggers billing generation in FMS and inventory updates in WMS. | Annex F.3, Page 172; Integration Flow Diagrams |
| 5. | **User-friendly interface** | **FULLY COMPLY** | The UI/UX follows Nielsen's 10 usability heuristics with role-based navigation menus, contextual help tooltips, and consistent design language across all modules. User acceptance testing with 50+ logistics operators achieved 4.7/5.0 satisfaction rating with minimal training required. | Annex E.3, Page 127; UX Research Report |
| 6. | **Automated Invoice & Receipts Generation** | **FULLY COMPLY** | Our Billing Engine supports complex rating scenarios including multi-tier pricing, zone-based tariffs, and conditional surcharges with automated invoice generation via scheduled batch or real-time triggers. Full IRBM e-Invoicing compliance implemented with MyInvois API integration for validation and submission. | Annex E.4, Pages 128-130; e-Invoice Sample |
| 7. | **Credit & Collections Management** | **FULLY COMPLY** | The Credit Control Module enforces customizable credit limits at customer, group, and corporate levels with automated credit checks during job creation. Collection worklists are auto-generated based on aging buckets with configurable dunning letter templates and promise-to-pay tracking. | Annex E.5, Page 131; Credit Workflow Diagram |
| 8. | **Automated Locking for Overdue Customer** | **FULLY COMPLY** | System automatically places credit-hold status on customers exceeding credit limits or payment terms, blocking new job creation while preserving existing operations. Override capability requires dual-authorization from Finance Manager and GM with full audit trail of all override decisions. | Annex E.6, Page 132; Credit Control SOP |
| 9. | **Audit Trail & History** | **FULLY COMPLY** | Immutable audit logs capture all data modifications with before/after values, user identity, timestamp, and IP address stored in tamper-resistant database tables. Full history viewable via Audit Inquiry screen with export capability for compliance reporting and forensic analysis. | Annex D.2, Page 98; Audit Trail Sample |
| 10. | **Ability of the system to support attachment documents** | **FULLY COMPLY** | Document Management System supports unlimited file attachments (up to 50MB per file) in formats including PDF, DOC, XLS, images, and video with OCR indexing for full-text search. Documents are encrypted at rest with access controls tied to user roles and job permissions. | Annex E.7, Page 133; Document Management UI |
| 11. | **Comprehensive security features** | **FULLY COMPLY** | Security framework implements MFA via TOTP/SMS, RBAC with 50+ granular permissions, password policy enforcement (NIST 800-63B), AES-256 encryption, and continuous security monitoring. Annual VAPT by CREST-accredited firm with zero critical/high findings. | Annex D, Pages 95-110; Security Certificate |
| 12. | **Online submission of Request & Tracking** | **FULLY COMPLY** | Customer Portal enables self-service RFD submission with real-time tracking including GPS map view of assigned Prime Mover location. Automated email/SMS/WhatsApp notifications triggered at 12 predefined status points from booking confirmation to delivery completion. | Annex E.8, Page 134; Customer Portal Demo |
| 13. | **Container Tracking** | **FULLY COMPLY** | Mobile Driver App with GPS tracking captures container events (pickup, in-transit, arrived, delivered) with photo proof and digital signature. Real-time tracking data synchronized every 30 seconds via 4G/WiFi with offline mode for areas with poor connectivity. | Annex E.9, Page 135; Driver App Screenshots |
| 14. | **Electronic Work Ticket** | **FULLY COMPLY** | Digital Job Cards auto-populated on driver mobile devices with job details, container info, pickup/delivery addresses, and special instructions. Drivers update job status via one-tap buttons with automated timestamp and geolocation capture for performance tracking. | Annex E.10, Page 136; Work Ticket Flow |
| 15. | **Job Planning/PM, Trailers Assignment** | **FULLY COMPLY** | AI-powered Job Planning Engine optimizes PM and trailer assignments based on proximity, availability, driver hours, and delivery priorities with drag-and-drop manual override. Real-time visibility dashboard shows all active jobs with color-coded status and ETA calculations. | Annex E.11, Page 137; Job Planning UI |
| 16. | **Trailer Monitoring** | **FULLY COMPLY** | Trailer Master maintains comprehensive registry with automatic alerts 30/60/90 days before permit expiry, PUSPAKOM due dates, and insurance renewal. System blocks trailer assignment if any mandatory document is expired or flagged for maintenance. | Annex E.12, Page 138; Trailer Registry |
| 17. | **Automated Prime Mover Tracking via GPS** | **FULLY COMPLY** | GPS integration with Geotab/Wialon provides real-time location tracking, speed monitoring (alerts >90km/h), idle detection (engine on + no movement >10 min), and geofence violations. Historical playback shows complete route history for up to 2 years. | Annex E.13, Page 139; GPS Tracking Dashboard |
| 18. | **Automated Driver incentive** | **FULLY COMPLY** | Incentive Calculation Engine supports unlimited formula configurations including revenue trips, non-revenue movements, special day multipliers, and incremental tier bonuses. Calculated incentives auto-post to FMS Payroll module with detailed breakdown reports for driver transparency. | Annex E.14, Pages 140-142; Incentive Formula Sheet |
| 19. | **Reporting And Enquiries** | **FULLY COMPLY** | Comprehensive report library includes 50+ standard reports covering trips, vehicles, drivers, financials, and fleet operations with customizable filters and export formats (PDF/Excel/CSV). Ad-hoc query builder enables users to create custom reports without IT assistance. | Annex E.15, Pages 143-150; Report Catalogue |

**Annexure C1 Summary:** 19/19 Features — **100% FULLY COMPLY**

---

## ANNEXURE C2: FORWARDING MANAGEMENT SYSTEM (FFS)

**Location:** PK, GLD, BTW, PGD  
**System Version:** LogisticsPro FFS v4.2  
**Trade Lane Coverage:** Import/Export, Cross-trade, Domestic

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Dashboard - Real Time Reporting** | **FULLY COMPLY** | FFS Command Centre provides real-time visibility into all shipments with drill-down capability from summary KPIs to individual job details. Role-based views ensure management sees revenue analytics while operations focuses on pending collections and customs clearances. | Annex E.16, Page 151; FFS Dashboard Video |
| 2. | **Multi platform interface** | **FULLY COMPLY** | Identical multi-platform architecture as HMS with responsive web interface and native mobile apps for field staff. Offline capability allows freight coordinators to update shipment status even in Port Klang areas with limited connectivity. | Annex E.2, Page 126; Platform Matrix |
| 3. | **Interface with 3rd party system** | **FULLY COMPLY** | Pre-built integrations with Port Community System (PCS), uCustoms (MyGBS), shipping lines (Maersk, MSC, CMA CGM), and airline cargo systems. EDI support for ANSI X12 and UN/EDIFACT standards ensures seamless partner communication. | Annex F.4, Page 173; Integration Catalogue |
| 4. | **FFS able to link with other Business System** | **FULLY COMPLY** | Real-time data exchange with HMS for haulage coordination, WMS for warehouse inventory, and FMS for automated billing. Shipment status updates trigger downstream workflows automatically across all linked systems. | Annex F.3, Page 172; System Integration Map |
| 5. | **User-friendly interface** | **FULLY COMPLY** | Workflow-driven interface guides users through shipment lifecycle stages (Booking → Documentation → Customs → Haulage → Delivery) with visual progress indicators. Context-sensitive menus reduce clicks by 60% compared to traditional freight software. | Annex E.17, Page 152; UX Walkthrough |
| 6. | **Automated Invoice & Receipts Generation** | **FULLY COMPLY** | Complex freight billing engine handles multi-currency, multi-party, and multi-leg shipments with automatic cost apportionment and revenue recognition. IRBM e-Invoicing integrated with MyInvois platform for compliance with Malaysian tax regulations. | Annex E.4, Pages 128-130; Freight Invoice Samples |
| 7. | **Credit & Collections Management** | **FULLY COMPLY** | Integrated credit management from HMS shared across FFS with consolidated customer view across all business units. Automated collection workflows trigger based on shipment delivery and agreed payment terms with escalation matrix. | Annex E.5, Page 131; Collections Dashboard |
| 8. | **Automated Locking for Overdue Customer** | **FULLY COMPLY** | Unified credit control across HMS, FFS, WMS, and TMS ensures consistent enforcement of credit holds regardless of which business unit the customer interacts with. Override workflows route to appropriate authority based on credit exposure amount. | Annex E.6, Page 132; Credit Policy Matrix |
| 9. | **Audit Trail & History** | **FULLY COMPLY** | Comprehensive audit logging covers all shipment data changes, document uploads, status transitions, and financial transactions with immutable storage. Complete shipment lifecycle history viewable via single-click Audit Trail button on every job screen. | Annex D.2, Page 98; Shipment Audit Sample |
| 10. | **Ability of the system to support attachment documents** | **FULLY COMPLY** | Document Management supports trade documents including BL, AWB, CO, packing lists, and customs forms with automatic metadata extraction. Version control maintains document history with rollback capability and sharing controls for external parties. | Annex E.7, Page 133; Trade Document Repository |
| 11. | **Comprehensive security features** | **FULLY COMPLY** | Enterprise-grade security with role-based access ensuring forwarders only see their assigned shipments and sensitive commercial data is restricted to authorized personnel. Data encryption, MFA, and session management identical to HMS security framework. | Annex D, Pages 95-110; Security Whitepaper |
| 12. | **Online submission of Request & Tracking** | **FULLY COMPLY** | Customer Self-Service Portal enables online booking requests, document uploads, real-time shipment tracking, and e-billing with 24/7 availability. Automated notifications keep customers informed at every milestone without manual intervention. | Annex E.8, Page 134; Customer Portal Tour |
| 13. | **Job Planning / Tracking** | **FULLY COMPLY** | Visual shipment timeline shows planned vs actual milestones with automatic alerts for delays or deviations. Project management view consolidates multiple related shipments with overall project status and revenue tracking for large contracts. | Annex E.18, Page 153; Shipment Timeline View |
| 14. | **Shipment Tracking** | **FULLY COMPLY** | Multi-modal tracking captures sea freight (vessel/voyage), air freight (flight details), and land transport milestones in unified timeline. Integration with shipping line track-and-trace APIs provides automatic updates without manual data entry. | Annex E.19, Page 154; Multi-modal Tracking |
| 15. | **Job Costing Automation** | **FULLY COMPLY** | Automated cost capture from all sources (haulage, storage, documentation, customs) with real-time P&L visibility per shipment. Cost variance alerts notify management when actual costs exceed estimates by configurable thresholds. | Annex E.20, Page 155; Job Costing Dashboard |
| 16. | **Data Bank** | **FULLY COMPLY** | Comprehensive tender management module tracks all tender submissions with status, win/loss analysis, and document repository. Historical freight rate database with 3-year history enables accurate quotation and margin analysis for new tenders. | Annex E.21, Page 156; Tender Database UI |
| 17. | **Centralized Documentation Management** | **FULLY COMPLY** | Auto-generation of freight documents including BL, AWB, and customs declarations with digital signature capability. Template library supports multiple trade lanes and document types with automatic population from shipment data. | Annex E.22, Page 157; Document Generation Demo |
| 18. | **Freight Rate Sheets and Quotation** | **FULLY COMPLY** | Rate management supports multiple carriers, routes, and cargo types with validity period tracking and automatic expiry alerts. Self-service customer portal provides instant quotations based on predefined rate cards with transportation alternatives. | Annex E.23, Page 158; Rate Management Module |
| 19. | **Reporting and Enquiry** | **FULLY COMPLY** | 40+ standard freight reports covering shipments, documentation, operations, and financials with flexible filtering by date range, branch, customer, and trade lane. Custom report builder enables ad-hoc analysis without technical expertise. | Annex E.24, Pages 159-162; FFS Report Library |
| 20. | **Financial Reports** | **FULLY COMPLY** | Freight-specific financial reports include revenue by trade lane, profitability per customer, agent commission statements, and cost breakdown analysis. Real-time integration with FMS ensures financial data accuracy without manual reconciliation. | Annex E.25, Page 163; Freight Financial Reports |
| 21. | **Enquiries** | **FULLY COMPLY** | Advanced enquiry screens support real-time search by BL number, container number, customer reference, or job ID with cross-module results. Drill-down capability from summary to detailed transaction level with document attachments viewable inline. | Annex E.26, Page 164; Enquiry Interface |

**Annexure C2 Summary:** 21/21 Features — **100% FULLY COMPLY**

---

## ANNEXURE C3: WAREHOUSE MANAGEMENT SYSTEM (WMS)

**Location:** PK, HQ  
**System Version:** LogisticsPro WMS v4.2  
**Warehouse Types:** Bonded, Free Zone, Cold Storage, General

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Dashboards & Analytics** | **FULLY COMPLY** | WMS Control Tower provides real-time warehouse KPIs including inventory accuracy, space utilization, order fulfillment rates, and labor productivity. Predictive analytics forecast inventory levels and suggest optimal reorder points based on demand patterns. | Annex E.27, Page 166; WMS Dashboard Video |
| 2. | **Multi platform interface** | **FULLY COMPLY** | Full-featured web interface for office staff and responsive mobile apps for warehouse floor operations on RF scanners and tablets. Touch-optimized screens for forklift-mounted devices with voice-picking support for hands-free operation. | Annex E.2, Page 126; WMS Device Matrix |
| 3. | **Interface with 3rd party system** | **FULLY COMPLY** | Integration with Port Klang PCS, Customs systems, courier services (DHL, FedEx, Pos Laju), and e-commerce platforms (Shopify, Lazada, Shopee). API gateway supports high-volume transaction processing for 3PL operations. | Annex F.5, Page 174; WMS Integration Specs |
| 4. | **WMS able to link with other Business System** | **FULLY COMPLY** | Seamless integration with HMS for delivery scheduling, FFS for freight coordination, and FMS for automated billing. Inventory reservations from FFS bookings automatically allocate warehouse space and trigger receiving workflows. | Annex F.3, Page 172; WMS Integration Flows |
| 5. | **User-friendly interface** | **FULLY COMPLY** | Warehouse-optimized UI with barcode scanning workflows, color-coded location indicators, and simplified screens for warehouse operators. Supervisor dashboards provide management oversight with exception-based alerts for proactive intervention. | Annex E.28, Page 167; WMS UI Tour |
| 6. | **Automated Invoice & Receipts Generation** | **FULLY COMPLY** | Automated storage billing calculates charges based on occupied space (CBM/sqft), storage duration, and handling activities with configurable rate cards. Full IRBM e-Invoicing support for 3PL customer billing with consolidated or detailed invoice options. | Annex E.4, Pages 128-130; Storage Invoice Samples |
| 7. | **Credit & Collections Management** | **FULLY COMPLY** | Unified credit management across all systems ensures consistent credit control for warehouse customers who also use haulage or freight services. Automated invoicing and collection workflows reduce DSO (Days Sales Outstanding) by average 15 days. | Annex E.5, Page 131; WMS Credit Controls |
| 8. | **Automated Locking for Overdue Customer** | **FULLY COMPLY** | System prevents goods release for customers exceeding credit limits with configurable grace periods and partial payment options. Credit hold visibility across all warehouse operations ensures consistent enforcement. | Annex E.6, Page 132; Release Control SOP |
| 9. | **Audit Trail & History** | **FULLY COMPLY** | Complete inventory transaction history captures every movement, adjustment, and count with user identification and timestamp. Full traceability for compliance with customs regulations and audit requirements with 7-year retention. | Annex D.2, Page 98; Inventory Audit Trail |
| 10. | **Ability of the system to support attachment documents** | **FULLY COMPLY** | Document management for warehouse operations including GRN, delivery orders, customs forms, and damage photos with automatic filing by job number. OCR indexing enables text search within uploaded documents for quick retrieval. | Annex E.7, Page 133; WMS Document Attachments |
| 11. | **Comprehensive security features** | **FULLY COMPLY** | Role-based access ensures warehouse staff only access assigned zones and functions with supervisor approval workflows for sensitive operations. Data security identical to HMS/FFS with encryption, MFA, and comprehensive audit logging. | Annex D, Pages 95-110; WMS Security Config |
| 12. | **Cargo In/Out (barcode/RFID reader)** | **FULLY COMPLY** | Native support for barcode scanners (1D/2D), RFID readers, and mobile computers with automatic device detection and configuration. GS1-128 and SSCC barcode standards supported for standardized labeling and scanning. | Annex E.29, Page 168; Barcode Integration Spec |
| 13. | **Cargo storage and others charges** | **FULLY COMPLY** | Flexible storage charging supports multiple methods (per pallet, per CBM, per weight, per carton) with tiered rates and minimum charges. Storage calculations auto-post to FMS with detailed breakdown by charge type and billing period. | Annex E.30, Page 169; Storage Charge Engine |
| 14. | **System Generate Gate Pass** | **FULLY COMPLY** | Auto-generated gate passes for cargo release with barcode/QR code for scanner validation at exit gates. Digital signature capture on mobile devices provides proof of delivery with automatic email notification to customer. | Annex E.31, Page 170; Gate Pass Sample |
| 15. | **Inventory Management** | **FULLY COMPLY** | Real-time inventory tracking with multiple status types (available, allocated, quarantine, damaged) and full attribute support (lot, serial, batch, expiry). Automated reorder alerts and cycle counting schedules maintain inventory accuracy above 99.5%. | Annex E.32, Page 171; Inventory Management UI |
| 16. | **Receiving & Inbound Processing** | **FULLY COMPLY** | ASN-based receiving with barcode verification against PO quantities and automatic discrepancy reporting. Put-away task generation with location suggestions based on product attributes and warehouse zoning rules. | Annex E.33, Page 172; Receiving Workflow |
| 17. | **Put-Away Management** | **FULLY COMPLY** | Intelligent put-away engine suggests optimal storage locations based on product dimensions, velocity, and storage class with manual override capability. Real-time location updates as tasks are completed via RF scanners. | Annex E.34, Page 173; Put-away Rules Engine |
| 18. | **Storage & Location Management** | **FULLY COMPLY** | Visual warehouse map with configurable zones, aisles, racks, and bins supporting multiple location types (bulk, pick-face, cold storage, hazardous). Location utilization reports identify space optimization opportunities. | Annex E.35, Page 174; Warehouse Map View |
| 19. | **Order Management & Picking** | **FULLY COMPLY** | Advanced picking methods include single order, batch, wave, zone, and cluster picking with optimized pick path algorithms. Barcode verification at pick and pack stages ensures 99.9%+ order accuracy with error alerts. | Annex E.36, Page 175; Picking Optimization Demo |
| 20. | **Packing & Shipping** | **FULLY COMPLY** | Cartonization engine calculates optimal packing configuration with shipping label generation and carrier integration for tracking numbers. Packing list auto-generated with carton-level detail for multi-carton shipments. | Annex E.37, Page 176; Packing Workflow |
| 21. | **Returns (RMA) Management** | **FULLY COMPLY** | Returns processing workflow includes RMA creation, receipt inspection with condition assessment (resellable, damaged, quarantine), and automatic inventory adjustment. Integration with FMS handles credit note generation for customer returns. | Annex E.38, Page 177; Returns Management UI |
| 22. | **Cycle Counting & Physical Inventory** | **FULLY COMPLY** | Flexible cycle counting supports ABC classification, random, and triggered counts with blind count option for audit integrity. Variance reporting with supervisor approval workflow for inventory adjustments with full audit trail. | Annex E.39, Page 178; Cycle Count Module |
| 23. | **Labor & Task Management** | **FULLY COMPLY** | Task assignment engine allocates work based on operator skills, location proximity, and workload balancing with real-time progress tracking. Performance metrics track picks per hour, accuracy rates, and time per task for productivity analysis. | Annex E.40, Page 179; Labor Management Dashboard |
| 24. | **Multi-Warehouse Support** | **FULLY COMPLY** | Single platform manages multiple warehouse facilities with inter-warehouse transfer orders and consolidated inventory visibility across all locations. Branch-specific configurations support different operational requirements per site. | Annex E.41, Page 180; Multi-Warehouse View |
| 25. | **Document Creation** | **FULLY COMPLY** | Auto-generation of warehouse documents including pick lists, packing slips, bill of lading, and shipping labels with customizable templates. Documents support barcode/QR codes for automated processing and tracking. | Annex E.42, Page 181; Document Templates |
| 26. | **Scalability & Flexibility for Future Technology** | **FULLY COMPLY** | Modular architecture supports integration with automation technologies including AGVs, AMRs, voice picking, and RFID without core system changes. Data platform enables AI/ML applications for demand forecasting and optimization. | Annex A, Page 15; Future Tech Roadmap |
| 27. | **Report and Enquiry** | **FULLY COMPLY** | Comprehensive reporting suite includes inventory, inbound/outbound, warehouse operations, financial/billing, and compliance reports with 50+ standard templates. Custom report builder and enquiry screens provide flexible data access without IT dependency. | Annex E.43, Pages 182-188; WMS Report Catalogue |

**Annexure C3 Summary:** 27/27 Features — **100% FULLY COMPLY**

---

## ANNEXURE C4: TERMINAL MANAGEMENT SYSTEM (TMS)

**Location:** PK, BTW  
**System Version:** LogisticsPro TMS v4.2  
**Terminal Types:** Container Yard, ICD, Rail Terminal

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Dashboards & Analytics** | **FULLY COMPLY** | Terminal Operations Dashboard displays real-time yard KPIs including container count by status, gate throughput, yard utilization, and equipment productivity. Visual indicators highlight bottlenecks and exceptions requiring management attention. | Annex E.44, Page 189; TMS Dashboard Video |
| 2. | **Multi platform interface** | **FULLY COMPLY** | Multi-platform support includes desktop for control room staff, tablets for yard supervisors, and mobile devices for gate officers and equipment operators. Touch-optimized interfaces for outdoor use in various lighting conditions. | Annex E.2, Page 126; TMS Platform Matrix |
| 3. | **Interface with 3rd party system** | **FULLY COMPLY** | Extensive integration capabilities with KTMB for rail operations, PPSB (Penang Port) for port terminals, customs (KDM), shipping lines, and haulage companies. EDI and API support for industry-standard message formats including COPARN, CODECO, and COARRI. | Annex F.6, Page 175; TMS Integration Specs |
| 4. | **TMS able to link with other Business System** | **FULLY COMPLY** | Real-time data exchange with HMS for haulier coordination, FFS for freight forwarding, and FMS for billing ensures seamless information flow across all business units. Container status updates propagate automatically to connected systems. | Annex F.3, Page 172; TMS Integration Architecture |
| 5. | **User-friendly interface** | **FULLY COMPLY** | Terminal-optimized UI with visual yard maps, color-coded container status, and simplified data entry screens for high-volume gate operations. Touch-friendly design supports rapid transaction processing during peak hours. | Annex E.45, Page 190; TMS UI Walkthrough |
| 6. | **Automated Invoice & Receipts Generation** | **FULLY COMPLY** | Automated billing for storage, handling, and ancillary charges with configurable rate structures by customer, container type, and service. Full IRBM e-Invoicing compliance with MyInvois integration for Malaysian tax requirements. | Annex E.4, Pages 128-130; Terminal Billing Samples |
| 7. | **Credit & Collections Management** | **FULLY COMPLY** | Integrated credit management ensures container release authorization checks credit status across all MMF systems. Automated invoicing and collection workflows with customized dunning procedures for terminal customers. | Annex E.5, Page 131; Terminal Credit Controls |
| 8. | **Automated Locking for Overdue Customer** | **FULLY COMPLY** | System blocks container release for customers exceeding credit limits with override capability requiring dual authorization. Credit hold status visible across gate operations, customer service, and management dashboards. | Annex E.6, Page 132; Release Authorization Matrix |
| 9. | **Audit Trail & History** | **FULLY COMPLY** | Complete container lifecycle tracking from gate-in to gate-out with every movement, inspection, and transaction logged with user and timestamp. Full audit trail supports compliance requirements and dispute resolution. | Annex D.2, Page 98; Container History Sample |
| 10. | **Ability of the system to support attachment documents** | **FULLY COMPLY** | Document management supports terminal operations including gate passes, damage photos, inspection reports, and customs documentation with automatic linking to container records. High-resolution photo storage for damage claims. | Annex E.7, Page 133; TMS Document Management |
| 11. | **Comprehensive security features** | **FULLY COMPLY** | Enterprise security with role-based access ensuring gate staff, yard operators, and managers have appropriate system capabilities. Data protection identical to other modules with encryption, MFA, and comprehensive security auditing. | Annex D, Pages 95-110; TMS Security Configuration |
| 12. | **Yard Module** | **FULLY COMPLY** | Visual yard management with digital layout showing zones, blocks, rows, and slots with real-time occupancy status. Automatic container slotting optimizes yard space while supporting manual placement for operational needs. | Annex E.46, Page 191; Yard Module Demo |
| 13. | **Container Turn In** | **FULLY COMPLY** | Streamlined gate-in process captures container details via manual entry, EDI, or file upload with automatic validation against bookings. Shipping agent portal allows authorized amendments to booking details with audit trail. | Annex E.47, Page 192; Gate-In Process Flow |
| 14. | **Container Turn Out** | **FULLY COMPLY** | Gate-out processing validates container release against authorized bookings with automatic generation of gate passes and customs clearance checks. Real-time inventory update triggers billing calculation for storage charges. | Annex E.48, Page 193; Gate-Out Process Flow |
| 15. | **Container Tracking** | **FULLY COMPLY** | Real-time container location tracking within the yard with movement history and dwell time calculation. Yard inventory enquiries provide instant visibility of container status, location, and storage duration. | Annex E.49, Page 194; Container Tracking View |
| 16. | **Container Putaway/Stacking** | **FULLY COMPLY** | Intelligent yard slotting algorithm recommends optimal stacking locations based on container attributes, departure schedule, and yard constraints. Digital yard map with mobile device integration for yard crane operators. | Annex E.50, Page 195; Yard Slotting Engine |
| 17. | **Container Damage Repair** | **FULLY COMPLY** | Damage inspection workflow captures damage details with photo documentation and automatic repair estimate generation. M&R tracking monitors repair status with cost accumulation and insurance claim documentation. | Annex E.51, Page 196; Damage Repair Module |
| 18. | **Container Railing** | **FULLY COMPLY** | Rail operations module manages container movements via KTMB with batch upload capability for manifest data. Integration with KTMB systems provides real-time rail schedule visibility and container tracking. | Annex E.52, Page 197; Rail Operations UI |
| 19. | **Gate module** | **FULLY COMPLY** | Integrated gate operations with weighbridge system for weight capture and customs system integration for KDM verification. Automated gate pass validation prevents unauthorized container movements. | Annex E.53, Page 198; Gate Module Integration |
| 20. | **System Generated Gatepass** | **FULLY COMPLY** | Automatic gate pass generation with unique serial numbers, barcode/QR codes, and all required container and customs information. Digital gate pass reduces paperwork and speeds up gate processing. | Annex E.54, Page 199; Gate Pass Sample |
| 21. | **Online Request Submission/Tracking** | **FULLY COMPLY** | Online booking system validates requests against vessel schedules with automatic rejection for requests within 48 hours of closing. Suspended customer/agent blocking ensures compliance with credit and operational policies. | Annex E.55, Page 200; Online Booking Portal |
| 22. | **System Integration** | **FULLY COMPLY** | Comprehensive integration includes weighbridge for weight capture, EDI with shipping agents for container movements, and PPSB for port data exchange. API gateway enables future integrations with emerging terminal technologies. | Annex F.6, Page 175; TMS System Integration Map |
| 23. | **APAD Requirements** | **FULLY COMPLY** | Full APAD compliance with pre-arrival booking system for hauliers, real-time TAT tracking from gate arrival to departure, and advance notification system for container drop-offs and pick-ups. | Annex E.56, Page 201; APAD Compliance Report |
| 24. | **Rate** | **FULLY COMPLY** | Flexible rate management supports multiple charge types (storage, handling, lifting) with customizable rates by container size, type, customer, and validity period. Automatic rate expiry alerts ensure accurate billing. | Annex E.57, Page 202; Terminal Rate Management |
| 25. | **Report and Enquiry** | **FULLY COMPLY** | Comprehensive reporting includes container inventory, gate activity, yard operations, M&R, financial/billing, and compliance reports with 40+ standard templates. Enquiry screens provide instant access to container status and history. | Annex E.58, Pages 203-206; TMS Report Library |

**Annexure C4 Summary:** 25/25 Features — **100% FULLY COMPLY**

---

## ANNEXURE C5: FINANCE MANAGEMENT SYSTEM (FMS)

**Location:** ALL Branches  
**System Version:** LogisticsPro FMS v4.2  
**Accounting Standards:** MFRS compliant, IRBM e-Invoicing ready

| No | Features | Comply | Comments | Evidence Ref |
|----|----------|--------|----------|--------------|
| 1. | **Dashboard - Real Time Reporting** | **FULLY COMPLY** | Financial Command Centre provides real-time visibility into cash flow, revenue, expenses, and profitability across all branches with drill-down to transaction level. Visual KPIs include budget vs actual, financial ratios, and trend analysis with export capability. | Annex E.59, Page 207; FMS Dashboard Video |
| 2. | **Multi platform interface** | **FULLY COMPLY** | Web-based interface accessible from any device with browser ensures finance team can work from office, home, or on the road. Mobile app provides approval workflows and alert notifications for critical financial events. | Annex E.2, Page 126; FMS Platform Matrix |
| 3. | **FMS able to link with other Business System** | **FULLY COMPLY** | Native integration with HMS, FFS, WMS, and TMS enables automatic posting of operational transactions to GL without manual data entry. Real-time synchronization ensures financial reports always reflect current operational activity. | Annex F.3, Page 172; FMS Integration Architecture |
| 4. | **User-friendly interface** | **FULLY COMPLY** | Accounting interface designed for both finance professionals and operational users with simplified screens for common tasks and advanced features for complex transactions. Contextual help and validation messages guide users through proper accounting procedures. | Annex E.60, Page 208; FMS UI Tour |
| 5. | **Interface with 3rd party system** | **FULLY COMPLY** | Integration with banking systems for payment processing, IRBM MyInvois for e-invoicing, and payroll systems for salary processing. API support for connecting with external accounting firms and audit systems. | Annex F.7, Page 176; FMS Integration Specs |
| 6. | **Credit & Collections Management** | **FULLY COMPLY** | Comprehensive AR management with automated credit limit enforcement, aging analysis, and collection workflows across all business units. Collection worklists prioritize accounts based on aging, amount, and payment history with automated correspondence. | Annex E.5, Page 131; Collections Module Demo |
| 7. | **Automated Locking for Overdue Customer** | **FULLY COMPLY** | System-wide credit control automatically blocks new transactions for overdue customers across HMS, FFS, WMS, and TMS with configurable grace periods. Override requires appropriate authorization with full audit trail of all credit decisions. | Annex E.6, Page 132; Credit Lock Mechanism |
| 8. | **Audit Trail & History** | **FULLY COMPLY** | Complete financial transaction audit trail captures all journal entries, adjustments, and postings with user identification, timestamp, and approval chain. Immutable log supports internal audits, external audits, and regulatory compliance requirements. | Annex D.2, Page 98; Financial Audit Trail |
| 9. | **Ability of the system to support attachment documents** | **FULLY COMPLY** | Document management supports financial records including invoices, receipts, POs, payment vouchers, and bank statements with automatic filing by transaction. OCR indexing enables text search for quick document retrieval during audits. | Annex E.7, Page 133; FMS Document Attachments |
| 10. | **Comprehensive security features** | **FULLY COMPLY** | Financial data security with role-based access ensuring staff only access authorized companies, branches, and functions. Segregation of duties enforced through workflow approvals with dual authorization for high-value transactions. | Annex D, Pages 95-110; FMS Security Matrix |
| 11. | **Tax Compliance** | **FULLY COMPLY** | Automated tax calculation for SST, GST, and withholding tax with configurable tax codes and rates. Tax reporting includes GST-03, CP58, and other statutory returns with audit trail for all tax-related transactions. | Annex E.61, Page 209; Tax Module Configuration |
| 12. | **Multi-Currency & Multi-Company** | **FULLY COMPLY** | Full multi-currency support with automatic exchange rate updates and gain/loss calculation for foreign currency transactions. Multi-company consolidation enables group-level reporting with intercompany transaction elimination. | Annex E.62, Page 210; Multi-Currency Setup |
| 13. | **Account Receivable - Customer Master** | **FULLY COMPLY** | Comprehensive customer master maintains all billing and credit information including multiple addresses, contact persons, payment terms, and credit limits. Customer hierarchy supports head office billing with delivery to multiple branches. | Annex E.63, Page 211; Customer Master UI |
| 14. | **Invoicing & Billing** | **FULLY COMPLY** | Flexible invoicing supports manual creation, automatic generation from operational systems, and recurring billing with customizable templates. Full IRBM e-Invoicing integration validates and submits invoices to MyInvois platform automatically. | Annex E.4, Pages 128-130; Invoicing Workflow |
| 15. | **Debit & Credit Notes** | **FULLY COMPLY** | DN/CN creation with automatic linking to original invoices and automatic GL posting. Approval workflows ensure proper authorization for adjustments with full audit trail of all debit/credit transactions. | Annex E.64, Page 212; DN/CN Process |
| 16. | **Payments Processing (AR)** | **FULLY COMPLY** | Multi-channel payment recording supports cash, cheque, bank transfer, credit card, and online payments with automatic receipt generation. Auto-reconciliation matches payments to invoices with manual override capability for complex allocations. | Annex E.65, Page 213; Payment Processing Demo |
| 17. | **Receipts & Cash Application** | **FULLY COMPLY** | Receipt management with suggestive matching based on amount, invoice number, and customer reference. Unapplied receipts tracking with automatic aging and follow-up workflows for unidentified payments. | Annex E.66, Page 214; Cash Application UI |
| 18. | **Account Payable - Vendor Management** | **FULLY COMPLY** | Complete vendor master with banking details, payment terms, and tax information supports local and international suppliers. Duplicate vendor detection prevents double payments with merge functionality for vendor consolidation. | Annex E.67, Page 215; Vendor Master |
| 19. | **AP Invoice Management and Payment Processing** | **FULLY COMPLY** | Three-way matching validates invoices against POs and GRNs with configurable tolerance levels. Approval workflows route invoices based on amount and department with automatic GL posting upon approval. | Annex E.68, Page 216; AP Workflow |
| 20. | **Payments Processing (AP)** | **FULLY COMPLY** | Batch payment processing with support for multiple payment methods and currencies. Payment proposals optimize cash flow while ensuring timely payment to maintain supplier relationships and capture early payment discounts. | Annex E.69, Page 217; Payment Processing |
| 21. | **General Ledger - Chart of Accounts** | **FULLY COMPLY** | Flexible chart of accounts supports multiple levels, segments, and dimensions for detailed financial analysis. Account templates accelerate setup with best-practice account structures for logistics businesses. | Annex E.70, Page 218; COA Setup |
| 22. | **Journal Entry Processing** | **FULLY COMPLY** | Journal entry creation with template support for recurring entries and auto-reversal for accruals. Validation ensures balanced entries with valid accounts and open periods before posting. | Annex E.71, Page 219; Journal Entry UI |
| 23. | **Period Management & Closing** | **FULLY COMPLY** | Period control enables soft close for reporting while preventing new postings, with hard close finalizing the period. Multi-module period management supports different closing schedules for GL, AP, and AR. | Annex E.72, Page 220; Period Management |
| 24. | **Budgeting & Forecasting** | **FULLY COMPLY** | Budget import and maintenance with multiple versions and comparison to actuals. Budget controls trigger alerts or hard stops when transactions exceed budgeted amounts by configurable thresholds. | Annex E.73, Page 221; Budget Module |
| 25. | **Fixed Asset - Asset Master Data Management** | **FULLY COMPLY** | Comprehensive asset register captures all asset details including acquisition information, location, custodian, and warranty with document attachments. QR code/barcode support enables physical asset tracking and verification. | Annex E.74, Page 222; Asset Master |
| 26. | **Asset Acquisition & Capitalization** | **FULLY COMPLY** | Asset acquisition workflow supports direct purchase, PO-based acquisition, and CWIP capitalization with automatic GL postings. Bulk upload capability accelerates asset register setup for new branches. | Annex E.75, Page 223; Asset Acquisition |
| 27. | **Depreciation Management** | **FULLY COMPLY** | Multiple depreciation methods (straight-line, reducing balance, sum-of-years) with automatic monthly calculation and GL posting. Depreciation override capability with audit trail for special adjustments. | Annex E.76, Page 224; Depreciation Engine |
| 28. | **Asset Revaluation** | **FULLY COMPLY** | Asset revaluation workflow supports index-based or manual revaluation with automatic recalculation of depreciation. Full revaluation history maintains compliance with accounting standards. | Annex E.77, Page 225; Revaluation Process |
| 29. | **Asset Transfers** | **FULLY COMPLY** | Inter-department and inter-branch asset transfers with automatic GL entries and movement history tracking. Custodian acknowledgment ensures accountability for asset custody. | Annex E.78, Page 226; Asset Transfer |
| 30. | **Asset Disposal / Retirement** | **FULLY COMPLY** | Asset disposal workflow handles sale, scrap, and donation scenarios with automatic gain/loss calculation and GL posting. Documentation requirements ensure proper authorization for asset disposals. | Annex E.79, Page 227; Asset Disposal |
| 31. | **Asset Write off** | **FULLY COMPLY** | Write-off processing for assets with no remaining value or utility with appropriate authorization workflows and GL impact. Write-off history supports audit requirements and asset lifecycle analysis. | Annex E.80, Page 228; Write-off Process |
| 32. | **Asset Maintenance & Tracking** | **FULLY COMPLY** | Maintenance scheduling and cost tracking with warranty management and service provider information. Preventive maintenance alerts ensure optimal asset performance and longevity. | Annex E.81, Page 229; Maintenance Module |
| 33. | **Profit and Loss Reporting** | **FULLY COMPLY** | Flexible P&L reporting by branch, department, or cost center with comparison to budget, prior year, and custom periods. Drill-down capability from summary to individual transactions for variance analysis. | Annex E.82, Page 230; P&L Reports |
| 34. | **Balance Sheet** | **FULLY COMPLY** | Balance sheet with current and comparative periods, automated ratio analysis, and drill-down to supporting schedules. Balance sheet integrity checks ensure accounting equation balance. | Annex E.83, Page 231; Balance Sheet |
| 35. | **Cash Flow** | **FULLY COMPLY** | Automated cash flow statement with direct method presentation itemizing receipts and payments by category. 12-month rolling view supports cash flow forecasting and working capital management. | Annex E.84, Page 232; Cash Flow Report |
| 36. | **Debtors and Creditors Ageing** | **FULLY COMPLY** | Automated ageing analysis with configurable buckets and automatic reminders for over-limit and overdue accounts. Drill-down from summary to individual invoices supports collection activities. | Annex E.85, Page 233; Ageing Reports |
| 37. | **Daily Revenue Reports** | **FULLY COMPLY** | Auto-generated daily revenue reports by branch, business unit, and customer with volume and value analysis. Comparison to budget, average, and prior periods highlights performance trends. | Annex E.86, Page 234; Daily Revenue Report |

**Annexure C5 Summary:** 37/37 Features — **100% FULLY COMPLY**

---

## 3. COMPLIANCE SUMMARY

### 3.1 Overall Compliance Matrix

| Annexure | System | Total Features | Fully Comply | Partially Comply | Not Comply | Compliance % |
|----------|--------|----------------|--------------|------------------|------------|--------------|
| C1 | HMS | 19 | 19 | 0 | 0 | **100%** |
| C2 | FFS | 21 | 21 | 0 | 0 | **100%** |
| C3 | WMS | 27 | 27 | 0 | 0 | **100%** |
| C4 | TMS | 25 | 25 | 0 | 0 | **100%** |
| C5 | FMS | 37 | 37 | 0 | 0 | **100%** |
| **TOTAL** | | **129** | **129** | **0** | **0** | **100%** |

### 3.2 Cross-System Integration Compliance

| Requirement | Status | Evidence |
|-------------|--------|----------|
| HMS ↔ FFS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| HMS ↔ WMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| HMS ↔ FMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| FFS ↔ WMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| FFS ↔ FMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| WMS ↔ FMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| TMS ↔ HMS Integration | ✅ FULLY COMPLY | Annex F.3, Page 172 |
| All Systems → 3rd Party | ✅ FULLY COMPLY | Annex F.4-F.7 |

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
| IRBM e-Invoicing Compliance | ✅ FULLY COMPLY | Annex E.4, Page 130 |
| Awan Kita Sovereign Cloud | ✅ FULLY COMPLY | Annex A.2, Page 16 |

---

## 4. PROJECT MANAGEMENT METHODOLOGY (PRINCE2)

### 4.1 Management Stages

| Stage | Duration | Key Deliverables | Stage Gate | Tolerance |
|-------|----------|------------------|------------|-----------|
| **Stage 1: Initiation** | 2 weeks | Project Initiation Document (PID), Risk Register, Project Plan | Go/No-Go Decision | Time: ±3 days |
| **Stage 2: Foundation** | 4 weeks | BRS/URS Signed-off, Technical Architecture, FSD | Requirements Freeze | Cost: ±10% |
| **Stage 3: Configuration** | 6 weeks | System Configured, Data Migration Scripts, UAT Plan | UAT Readiness | Scope: Minor only |
| **Stage 4: Deployment** | 4 weeks | UAT Completed, Training Delivered, Go-Live | Production Release | Quality: Zero defects |
| **Stage 5: Closure** | 2 weeks | Handover Documentation, Warranty Begins, Project Closure | Final Acceptance | None |

### 4.2 Product-Based Planning

**Specialist Products:**
- Configured LogisticsPro HMS/FFS/WMS/TMS/FMS instances
- Integrated data migration tools
- Custom reports and dashboards
- User training materials
- Technical documentation

**Management Products:**
- Project Plan with Work Packages
- Risk Register and Issue Log
- Quality Register with review records
- Stage Plans and End Stage Reports
- Highlight Reports (weekly)

### 4.3 Quality Register

| Product | Quality Criteria | Quality Method | Reviewer |
|---------|------------------|----------------|----------|
| BRS/URS | Completeness, traceability to MMF SOW | Peer Review + MMF Review | Business Analyst + MMF User |
| Technical Architecture | Scalability, security, integration feasibility | Technical Review | Solution Architect |
| FSD | Alignment with requirements, technical accuracy | Inspection | System Analyst + MMF IT |
| System Configuration | Functionality, performance, usability | System Testing | QA Lead |
| Data Migration | Accuracy, completeness, validation | Data Validation | Data Migration Lead |
| Training Materials | Clarity, coverage, accuracy | Walkthrough | Training Lead + MMF User |
| UAT Scripts | Coverage of all requirements | Traceability Check | QA Lead + MMF User |

### 4.4 Risk Management

| Risk ID | Risk Description | Probability | Impact | Mitigation Strategy |
|---------|------------------|-------------|--------|---------------------|
| R-001 | Legacy data quality issues affecting migration | Medium | High | Data profiling in Week 1; migration dry-runs; validation scripts |
| R-002 | User adoption challenges across 6 branches | Medium | Medium | Change management kit; super-user program; on-site support |
| R-003 | Integration complexity with 3rd party systems | Medium | High | Early API documentation review; proof-of-concept testing |
| R-004 | Branch-specific customization requests | High | Medium | Strict change control; MMF steering committee approvals |
| R-005 | Resource availability from MMF side | Medium | Medium | Clear commitment letter; dedicated MMF project coordinator |

---

## 5. TECHNICAL ARCHITECTURE

### 5.1 System Architecture Overview

Our solution is built on a **modern, cloud-native architecture** that ensures:

- **Scalability:** Auto-scaling handles peak loads during month-end billing
- **Reliability:** 99.9% uptime SLA with multi-zone redundancy
- **Security:** Defense-in-depth with encryption, MFA, and continuous monitoring
- **Integration:** API-first design enables seamless connectivity

### 5.2 Deployment Model

| Component | Technology | Deployment |
|-----------|------------|------------|
| Application Layer | Microservices (Docker/Kubernetes) | Awan Kita Sovereign Cloud |
| Database | PostgreSQL Cluster (Primary-Standby) | Malaysia Data Center |
| Cache Layer | Redis Cluster | Malaysia Data Center |
| Message Queue | RabbitMQ | Malaysia Data Center |
| File Storage | Distributed Object Storage | Malaysia Data Center |
| API Gateway | Kong | Malaysia Data Center |
| Mobile Apps | React Native | iOS App Store / Google Play |

### 5.3 Security Architecture

| Layer | Security Measure |
|-------|------------------|
| Network | WAF, DDoS Protection, VPC Isolation |
| Application | OAuth 2.0, JWT Tokens, RBAC, Input Validation |
| Data | AES-256 Encryption at Rest, TLS 1.3 in Transit |
| Access | MFA, Password Policies, Session Management |
| Audit | Immutable Logs, SIEM Integration, Alerting |

---

## 6. SERVICE LEVEL AGREEMENT (SLA)

| Service Metric | Target | Measurement |
|----------------|--------|-------------|
| **System Availability** | 99.9% | Monthly uptime calculation |
| **Critical Issue Response** | < 1 hour | From ticket creation to acknowledgment |
| **High Priority Response** | < 4 hours | From ticket creation to acknowledgment |
| **Medium Priority Response** | < 8 hours | From ticket creation to acknowledgment |
| **Low Priority Response** | < 24 hours | From ticket creation to acknowledgment |
| **Critical Issue Resolution** | < 24 hours | From acknowledgment to fix deployment |
| **High Priority Resolution** | < 72 hours | From acknowledgment to fix deployment |
| **Backup Success Rate** | 100% | Daily automated backups |
| **RTO (Recovery Time Objective)** | < 4 hours | From disaster declaration to service restoration |
| **RPO (Recovery Point Objective)** | < 1 hour | Maximum data loss window |

### Support Channels

- **24/7 Helpdesk:** Phone + Email + WhatsApp
- **Customer Portal:** Self-service ticket creation and tracking
- **Dedicated Account Manager:** Business hours support
- **Technical Account Manager:** Monthly business reviews

---

## 7. VALUE ADDED SERVICES (VAS) FRAMEWORK

### 7.1 Part 1: Software & Innovation (10 Items)

All services below are provided at **NO ADDITIONAL COST**.

| No. | Service Description | Market Value (RM) | Deliverable |
|-----|---------------------|-------------------|-------------|
| 1.1 | **AI-Powered Analytics Module** — Predictive analytics for demand forecasting, route optimization, and revenue leakage detection | 280,000 | Deployed module, training, documentation |
| 1.2 | **Sovereign Cloud Security Layer** — Awan Kita compliant infrastructure with local data residency and encryption key management | 350,000 | Security architecture, compliance certificate |
| 1.3 | **Executive Mobile Dashboard** — Real-time KPIs and alerts for senior management on iOS/Android | 120,000 | Mobile app, configuration, training |
| 1.4 | **Customer Self-Service Portal** — 24/7 online booking, tracking, and document access for MMF customers | 200,000 | Portal deployment, branding, training |
| 1.5 | **Advanced BI & Reporting Suite** — 100+ pre-built reports with custom report builder | 180,000 | Report library, builder tool, training |
| 1.6 | **Workflow Automation Engine** — Visual workflow designer for business process automation | 150,000 | Engine deployment, 5 workflows configured |
| 1.7 | **Document OCR & Auto-Classification** — Automated document processing with ML-based classification | 120,000 | OCR module, classification rules, training |
| 1.8 | **API Developer Portal** — Self-service API documentation and testing for MMF IT team | 100,000 | Portal, documentation, API keys |
| 1.9 | **Data Migration Accelerator** — Automated tools and services for legacy data migration | 180,000 | Migration scripts, validation tools, execution |
| 1.10 | **Custom Report Development** — 20 custom reports tailored to MMF specific requirements | 120,000 | Reports, documentation, training |
| | **PART 1 SUBTOTAL** | **RM 1,820,000** | |

### 7.2 Part 2: Support & Consultative (10 Items)

| No. | Service Description | Market Value (RM) | Deliverable |
|-----|---------------------|-------------------|-------------|
| 2.1 | **Change Management Launch Kit** — Communication plan, training materials, and user adoption program | 100,000 | Complete kit, execution support |
| 2.2 | **Annual System Health Checks** — 3 years of comprehensive health assessments and optimization recommendations | 150,000 | Annual reports, optimization roadmap |
| 2.3 | **24/7 Premium Support** — 3 years of round-the-clock technical support with 1-hour response SLA | 400,000 | Support service, portal access |
| 2.4 | **Quarterly Business Reviews** — Strategic reviews with roadmap planning and best practice sharing | 80,000 | Quarterly reports, recommendations |
| 2.5 | **User Training Program** — Unlimited users training including admin, super-user, and end-user sessions | 200,000 | Training materials, sessions, recordings |
| 2.6 | **Data Quality Assessment** — Comprehensive data profiling and cleansing recommendations | 100,000 | Quality report, cleansing plan |
| 2.7 | **Disaster Recovery Drill** — Annual DR testing with failover and recovery exercises | 120,000 | DR test plan, execution, report |
| 2.8 | **Process Optimization Consultation** — Business process re-engineering and optimization workshops | 100,000 | Optimization report, recommendations |
| 2.9 | **Knowledge Transfer Sessions** — Technical deep-dive sessions for MMF IT team | 80,000 | Technical documentation, training |
| 2.10 | **Strategic IT Roadmap** — 3-year IT roadmap aligned with MMF business objectives | 100,000 | Roadmap document, quarterly updates |
| | **PART 2 SUBTOTAL** | **RM 1,430,000** | |

### 7.3 Total Value Added Services

| Category | Value (RM) |
|----------|------------|
| Part 1: Software & Innovation | 1,820,000 |
| Part 2: Support & Consultative | 1,430,000 |
| **TOTAL VAS VALUE** | **RM 3,250,000** |

**Finance Committee Note:** These services, if procured separately, would cost **RM 3.25 Million**. Their inclusion demonstrates our commitment to long-term partnership and delivering exceptional value beyond the base contract price.

---

## 8. EVIDENCE & ANNEXURES

### 8.1 Supporting Documentation Index

| Annex | Description | Location |
|-------|-------------|----------|
| **Annex A** | Technical Architecture Diagrams | Page 15 |
| **Annex B** | Company Profile & Certifications | Page 20 |
| **Annex C1** | HMS Screenshots & Demo Videos | Page 120-150 |
| **Annex C2** | FFS Screenshots & Demo Videos | Page 151-164 |
| **Annex C3** | WMS Screenshots & Demo Videos | Page 166-188 |
| **Annex C4** | TMS Screenshots & Demo Videos | Page 189-206 |
| **Annex C5** | FMS Screenshots & Demo Videos | Page 207-234 |
| **Annex D** | Security Assessment & VAPT Report | Page 95-110 |
| **Annex E** | System Evidence (All Modules) | Page 120-234 |
| **Annex F** | API Integration Specifications | Page 165-176 |
| **Annex G** | UAT Test Scripts & Scenarios | Page 200-220 |
| **Annex H** | PRINCE2 Project Plan | Page 250-280 |
| **Annex I** | Training Program & Materials | Page 290-310 |
| **Annex J** | SLA & Support Framework | Page 320-330 |
| **Annex K** | Client References & Case Studies | Page 340-360 |

### 8.2 Live System Access

| System | Demo URL | QR Code |
|--------|----------|---------|
| HMS Demo | https://demo.logisticspro.com/hms | [QR Code] |
| FFS Demo | https://demo.logisticspro.com/ffs | [QR Code] |
| WMS Demo | https://demo.logisticspro.com/wms | [QR Code] |
| TMS Demo | https://demo.logisticspro.com/tms | [QR Code] |
| FMS Demo | https://demo.logisticspro.com/fms | [QR Code] |

---

## 9. CONCLUSION

### 9.1 Summary of Compliance

| Metric | Result |
|--------|--------|
| Total Requirements | 129 |
| Fully Comply | 129 (100%) |
| Partially Comply | 0 (0%) |
| Not Comply | 0 (0%) |
| **Overall Compliance** | **100%** |

### 9.2 Why Sinergi Elit Sdn Bhd

1. **Proven Solution:** 95% of MMF requirements already engineered and deployed in production environments
2. **Domain Expertise:** 15+ successful logistics enterprise implementations with 98% customer satisfaction
3. **Compliance Leadership:** Zero critical/high VAPT findings; full Awan Kita sovereign cloud compliance
4. **Accelerated Delivery:** 8-10 week go-live vs. industry standard 6-9 months
5. **Value Beyond Price:** RM 3.25 Million in Value-Added Services at no additional cost
6. **Local Presence:** Malaysian company with onshore support and data residency guarantee
7. **Risk Mitigation:** PRINCE2 methodology with stage gates ensuring MMF control throughout

### 9.3 Our Commitment

> *"We do not sell promises; we deliver documented results. Our LogisticsPro Enterprise Suite is ready for MMF today — fully compliant, thoroughly tested, and proven in production environments. We are committed to delivering a successful implementation that transforms MMF's operations and positions the company for future growth."*

---

**Document Control**

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement. All information is provided in strict confidence and is subject to the terms of the tender documentation.*
