# Technical Evidence Documentation
## TSH-2605: Evidence & Value-Added Services Detail

**Tender Reference:** MMFSB/TD 02/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Support IT System (EMS, PS, HRMS)  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 4 February 2026

---

## Table of Contents

1. [Annexure C1: Equipment Management System (EMS)](#annexure-c1-equipment-management-system-ems)
2. [Annexure C2: Procurement System (PS)](#annexure-c2-procurement-system-ps)
3. [Annexure C3: Human Resource Management System (HRMS)](#annexure-c3-human-resource-management-system-hrms)

---

## ANNEXURE C1: EQUIPMENT MANAGEMENT SYSTEM (EMS)

**System:** LogisticsPro EMS v4.2  
**Location:** Port Klang (PK), Pasir Gudang (PGD)  
**Total Requirements:** 26  
**Coverage:** Fleet management, maintenance scheduling, fuel management, compliance tracking

The Equipment Management System (EMS) provides comprehensive management of MMF's diverse fleet including Prime Movers, Trailers, Trucks, Excavators, and other heavy equipment. Deployed at Port Klang and Pasir Gudang operations, EMS ensures optimal equipment utilization, regulatory compliance, and proactive maintenance to maximize asset availability and minimize operational disruptions. The system integrates seamlessly with HMS, FMS, and Finance systems to provide a unified view of equipment operations and costs.

---

### 1. Dashboards & Analytics (Online Report Including Management Dashboard)

#### Evidence

Our EMS Command Centre provides a comprehensive nerve centre for fleet operations that serves as the central monitoring and decision-making platform for MMF's equipment management. The management dashboards display real-time KPIs including total asset count (currently tracking 247 assets), active utilization rates (averaging 80%), maintenance status across all equipment categories, warranty expiry alerts for equipment under coverage, and year-to-date maintenance costs with budget comparison.

The dashboard architecture provides differentiated reporting based on user roles. Management receives comprehensive performance analysis broken down by prime movers, trailers, and drivers, enabling strategic decisions about fleet composition and deployment. Contribution analysis by customers shows which accounts generate the highest equipment utilization and profitability. Fuel consumption analytics track efficiency trends across the fleet, while tyre usage reports monitor this significant operational cost category. Maintenance reports provide visibility into preventive and corrective maintenance activities.

Operations staff receive functional reports tailored to their daily responsibilities including fuel consumption reports for monitoring dispensing and usage, preventive maintenance schedules for planning workshop activities, and repair tracking for managing breakdown responses. The real-time nature of these dashboards ensures that decision-makers always have current information for operational planning and resource allocation.

This comprehensive dashboard capability is evidenced in **Annex C1.1, Page 1** with the EMS Dashboard screenshots showing the Command Centre interface, KPI widgets, and role-based views.

#### Value-Added Services

We provide **AI-Powered Predictive Analytics** that transforms equipment maintenance from reactive to proactive. The system analyzes over 50 telemetry data points including engine temperature patterns, hydraulic pressure trends, vibration signatures, brake wear indicators, and historical failure data to forecast equipment failures 7-14 days in advance with demonstrated 89% accuracy. This predictive capability enables MMF to schedule maintenance during optimal windows, order required parts in advance, and prevent costly roadside breakdowns that disrupt customer service. The predictive analytics module typically reduces unexpected downtime by up to 40% and extends equipment lifespan through optimal maintenance timing.

Additionally, our **Executive Alert Intelligence** learns from management response patterns to prioritize and filter alerts, ensuring that critical equipment issues receive immediate attention while routine notifications are batched for review. This intelligent filtering reduces alert fatigue and ensures that decision-makers focus on truly significant operational events rather than being overwhelmed by routine status updates.

---

### 2. Multi-Platform Interface

#### Evidence

EMS is accessible through multiple platforms ensuring that all users can access the system regardless of their location or device preference. Web browser access supports Chrome, Edge, and Safari, providing full functionality for office-based staff including fleet managers, maintenance planners, and finance personnel. The responsive design automatically adapts to screen size, providing appropriate layouts for desktop monitors, laptops, and tablets.

Native mobile applications for iOS and Android platforms support field technicians, drivers, and supervisors who need system access while away from their desks. Field technicians can update maintenance records, log repairs, and access equipment history via mobile devices even in areas with poor connectivity. The offline-first architecture ensures that critical functions remain available without internet connection, with automatic synchronization when connectivity returns.

Progressive Web App (PWA) capabilities enable users to add EMS to their home screen without requiring app store downloads or approvals. This eliminates deployment delays and ensures that users always have quick access to the system. The PWA provides native-app-like functionality including push notifications for critical maintenance alerts and offline data storage.

This multi-platform support is evidenced in **Annex C1.8, Page 134** with Mobile App Screenshots showing the mobile interface, offline capabilities, and responsive design.

#### Value-Added Services

We provide **Push Notifications for Urgent Maintenance Alerts** that ensure critical equipment issues are addressed within minutes of identification. The notification system intelligently routes alerts to appropriate personnel based on equipment assignment, maintenance specialty requirements, and staff availability. Notifications can be delivered through multiple channels including mobile push, SMS, email, and in-app alerts based on urgency and user preferences.

Our **Smart Notification Bundling** prevents alert fatigue by grouping related notifications and delivering them at appropriate intervals. Rather than sending individual alerts for every status change, the system intelligently batches notifications and delivers summaries at user-defined intervals, ensuring that users stay informed without being overwhelmed.

---

### 3. Interface with 3rd Party System

#### Evidence

The EMS integration architecture supports multiple protocols and standards to ensure connectivity with external systems. RESTful APIs provide modern web-based integration capabilities for real-time data exchange. SOAP web services support legacy enterprise systems that require this protocol. Middleware connectors enable integration with specialized equipment and systems that use proprietary communication methods.

The API gateway manages all external integrations with features including authentication management to ensure only authorized systems can access EMS data, rate limiting to prevent system overload from excessive API calls, and comprehensive monitoring to track integration performance and alert on failures. Pre-built connectors are available for common logistics platforms, significantly reducing integration time and cost.

Standard data formats and protocols ensure compatibility with equipment telematics systems, fuel management systems, and maintenance workshop management tools. The integration framework supports both real-time data synchronization for time-critical information and batch processing for high-volume transactions.

This integration capability is evidenced in **Annex F.3, Page 172** with the API Integration Specification showing supported protocols, authentication methods, and data formats.

#### Value-Added Services

We provide an **API Developer Portal included at no additional cost**, empowering MMF's internal IT team to build custom integrations without vendor dependency. The portal includes comprehensive API documentation with interactive testing capabilities, code samples in multiple programming languages, sandbox environment for testing integrations without affecting production data, and usage analytics to track API consumption and performance. This capability ensures that MMF can rapidly adapt to new integration requirements as the business evolves and maintains control over their integration architecture.

Our **Integration Health Monitoring** provides real-time visibility into all external connections with proactive alerting for anomalies or failures. The monitoring dashboard shows connection status, transaction volumes, error rates, and response times for every integration point, enabling rapid identification and resolution of integration issues.

---

### 4. EMS Able to Link with Other Business System

#### Evidence

EMS seamlessly integrates with other MMF business systems to ensure data consistency and eliminate duplicate data entry. Integration with HMS enables vehicle maintenance schedules and preventive maintenance status to be visible to dispatchers and planners, ensuring that equipment under maintenance is not assigned to jobs. This integration prevents service disruptions and ensures that only available, properly maintained equipment is deployed.

FMS integration supports asset depreciation tracking, ensuring that equipment values are accurately reflected in financial statements. Maintenance costs flow automatically from EMS to FMS for proper expense recognition and cost center allocation. This integration eliminates manual data transfer and ensures that financial reports accurately reflect equipment operating costs.

Finance system integration enables automated billing for equipment rentals, maintenance charge-backs, and cost allocations. Bi-directional data synchronization ensures consistency across all systems—when equipment status changes in EMS, the update propagates to all connected systems in real-time.

This system integration is evidenced in **Annex F.3, Page 172** with the System Integration documentation showing data flows between EMS and other MMF systems.

#### Value-Added Services

We provide **Real-Time Data Synchronization with Conflict Resolution and Audit Logging** that ensures data integrity across all connected systems. When the same data element is modified in multiple systems simultaneously, the conflict resolution algorithm determines the correct value based on timestamps, system priorities, and business rules. Complete audit logging maintains records of all data synchronization activities, enabling troubleshooting and compliance verification.

Our **Unified Equipment View** consolidates data from all connected systems into a single dashboard showing equipment operational status, financial metrics, maintenance history, and utilization analytics. This unified view eliminates the need to check multiple systems for complete equipment information.

---

### 5. User-Friendly Interface

#### Evidence

The EMS user interface follows Nielsen's usability heuristics to ensure that the system is intuitive and efficient for all users. Role-based navigation presents only the functions relevant to each user's job responsibilities, reducing cognitive load and training requirements. Contextual help provides guidance specific to the current field or function, and a consistent design language across all modules ensures that users can transfer learning between different parts of the system.

Equipment operators can log issues with photo capture in under 30 seconds through the streamlined mobile interface. The Voice Command Interface allows hands-free status updates, enabling technicians to update maintenance records while working on equipment without stopping to type. The interface is designed for use in workshop environments where technicians may be wearing gloves or have limited mobility.

The system includes accessibility features ensuring compliance with WCAG standards, supporting users with visual, motor, or cognitive impairments. Keyboard navigation is fully supported for users who cannot use pointing devices.

This usability is evidenced in **Annex C1.9, Page 135** with the UI Walkthrough showing interface design, voice command capabilities, and mobile optimization.

#### Value-Added Services

We provide **Natural Language Processing** that understands conversational commands such as "Log repair for PM-047, replaced brake pads, job complete" or "Check maintenance schedule for trailer T-123." This voice-enabled interface improves technician productivity by 20% by eliminating the need to navigate through menus and type detailed descriptions. The system learns from user patterns to improve recognition accuracy over time and supports multiple languages commonly used in MMF's workforce.

Our **Contextual AI Assistant** provides in-app guidance and suggestions based on the user's current task and role. For equipment operators, the assistant offers maintenance tips and troubleshooting guidance. For managers, the assistant suggests optimization opportunities and highlights exceptions requiring attention.

---

### 6. Audit Trail & History

#### Evidence

The EMS audit trail system captures comprehensive information about all asset modifications. Each audit record includes before and after values for changed fields, the identity of the user making the change, precise timestamp, and IP address of the originating device. This information is stored in tamper-resistant database tables with restricted access controls to prevent unauthorized modification.

Full history is viewable via the Audit Inquiry screen with flexible search and filtering capabilities. Users can review history by date range, user, transaction type, or affected asset. Export capability supports compliance reporting and forensic analysis with data available in multiple formats including PDF, Excel, and CSV.

Blockchain-based verification creates cryptographically-secure records that cannot be tampered with, backdated, or deleted. This provides the highest level of audit integrity for critical equipment records.

This audit capability is evidenced in **Annex D.2, Page 98** with the Audit Trail Sample showing the level of detail captured for equipment transactions.

#### Value-Added Services

We provide **Cryptographically-Verifiable Records** that provide audit-proof evidence for insurance claims and regulatory compliance. Using distributed ledger technology, the system creates tamper-proof records of critical equipment events including accidents, repairs, and maintenance activities. These blockchain-verified records can be presented to insurance companies, regulatory authorities, or in legal proceedings with confidence in their integrity. This capability typically reduces audit preparation time by 60% and accelerates insurance claim processing.

Our **Audit Analytics Dashboard** provides visual summaries of system activity, user behavior patterns, and data modification trends. This dashboard helps auditors and management quickly identify areas requiring attention and supports continuous monitoring of internal controls.

---

### 7. Ability of the System to Support Attachment Documents

#### Evidence

The EMS document management system supports unlimited document attachments per asset, accommodating the comprehensive documentation requirements of fleet management. Supported formats include PDFs for certificates and reports, images for damage documentation and inspections, scanned documents for legacy records, and videos for training or incident documentation.

Documents are indexed and searchable through multiple methods including metadata tagging, full-text search for PDF and document files, and categorization by document type. Version control maintains document history, ensuring that users can access previous versions while always seeing the current version by default.

Document access controls ensure that sensitive information is only available to authorized personnel. Documents can be shared with external parties such as insurance companies, regulatory authorities, or maintenance vendors through secure links with expiration dates.

This document management capability is evidenced in **Annex C1.12, Page 140** with the Document Management interface showing attachment capabilities, search functions, and version control.

#### Value-Added Services

We provide **OCR Extraction** that automatically reads and indexes document content for full-text search. When documents are uploaded, the system extracts text content making it searchable even within scanned PDFs and images. This eliminates the need for manual indexing and ensures that documents can be found quickly using keyword searches. The OCR engine supports multiple languages and document formats commonly used in logistics operations.

Our **Intelligent Document Classification** uses machine learning to automatically categorize uploaded documents based on content analysis. The system recognizes document types such as insurance certificates, inspection reports, or maintenance invoices and automatically applies appropriate metadata and filing rules.

---

### 8. Ability to Provide Comprehensive Security Features

#### Evidence

The EMS security framework implements multiple layers of protection to safeguard sensitive equipment and operational data. Multi-factor authentication (MFA) is supported through both TOTP applications and SMS delivery, providing flexibility while ensuring strong authentication. Role-Based Access Control (RBAC) implements 50+ granular permissions that can be combined to define precise access rights for each user role including equipment operators, maintenance technicians, supervisors, and managers.

Password policy enforcement follows NIST 800-63B guidelines, requiring strong passwords, preventing common password patterns, and implementing appropriate rotation policies. All data is encrypted at rest using AES-256 encryption and in transit using TLS 1.3 protocols. Continuous security monitoring detects and alerts on suspicious activities, unauthorized access attempts, and potential security incidents.

Annual Vulnerability Assessment and Penetration Testing (VAPT) is conducted by CREST-accredited security firms. The most recent assessment found zero critical or high-severity findings, demonstrating the robustness of the security architecture. Zero-Trust Security with behavioral biometrics continuously authenticates users based on typing patterns and access behaviors.

This security posture is evidenced in **Annex D, Pages 95-110** with the Security Certificate and detailed security control documentation.

#### Value-Added Services

We provide **AI-Powered Threat Detection** that analyzes user behavior, system access patterns, and network traffic to identify anomalous access patterns in real-time. The system learns normal behavior patterns for each user and role, automatically flagging deviations that may indicate compromised accounts, unauthorized data access, or malicious insider activity. Automatic account suspension and security team alerting ensure rapid response to potential threats before significant damage occurs.

Our **Security Awareness Integration** embeds security training modules within the system to educate users about best practices, phishing recognition, and proper handling of sensitive information. Micro-learning modules deliver targeted training based on user roles and identified knowledge gaps.

---

### 9. Master Equipment Profile

#### Evidence

The comprehensive asset registry maintains detailed information for each piece of equipment in MMF's fleet. Core data includes Equipment ID and Asset Number for unique identification, Category classification (Prime Mover, Trailer, Truck, Excavator, Forklift, etc.), Manufacturer/Model/Year for equipment specifications, and Plate Number/Chassis Number/Engine Number for regulatory compliance and identification.

Ownership Status tracks whether equipment is Owned, Leased, or Hired, affecting depreciation, costing, and return requirements. GPS/Telematics ID links equipment to tracking systems for location monitoring and performance data collection. Operating Region(s) define where equipment is authorized to operate, supporting regulatory compliance and operational planning.

Each asset is assigned a unique QR code and barcode for quick identification and scanning throughout the facility. Mobile devices can scan these codes to instantly access equipment records, maintenance history, and operating procedures.

This asset registry is evidenced in **Annex C1.1, Page 120** with the Asset Detail View showing comprehensive equipment profiles.

#### Value-Added Services

We provide **IoT Sensor Integration** that monitors equipment health in real-time through connected sensors. Engine temperature, hydraulic pressure, brake wear, oil quality, and vibration sensors continuously stream data to EMS, enabling condition-based maintenance and early failure detection. The system generates alerts when sensor readings exceed normal thresholds, enabling proactive intervention before catastrophic failures occur.

Our **Digital Equipment Twin** creates a virtual representation of each physical asset, maintaining real-time status, historical performance data, and predictive models. This digital twin enables simulation of maintenance scenarios and optimization of operating parameters.

---

### 10. Status Tracking

#### Evidence

Real-time status tracking provides immediate visibility into equipment availability and condition. Status categories include: Active (equipment is operational and available for assignment), Under Maintenance (equipment is in workshop for scheduled or unscheduled maintenance), Out of Service (equipment is not operational due to breakdown or other issues), To Be Disposed (equipment is scheduled for disposal or sale), Sold (equipment has been disposed of), and Under Repair (equipment is being repaired but expected to return to service).

Status changes are logged with timestamps and user attribution, providing complete audit trails of equipment availability history. Visual indicators on all dashboards use color-coding to show status at a glance—green for active, yellow for maintenance, red for out of service.

Status history reports track equipment availability over time, supporting utilization analysis and maintenance planning. Integration with HMS ensures that dispatchers see current status when assigning equipment to jobs.

This status tracking is evidenced in **Annex C1.1, Page 120** with the Status Dashboard showing real-time equipment status.

#### Value-Added Services

We provide **Automated Status Transitions** based on maintenance schedules and IoT sensor thresholds. When preventive maintenance comes due, the system can automatically change status to "Under Maintenance" and notify assigned technicians. When sensors detect critical failures, status automatically changes to "Out of Service" and alerts maintenance supervisors. These automated transitions ensure that status information is always current without requiring manual updates.

Our **Status Prediction** uses historical patterns and scheduled activities to forecast future equipment availability. Dispatchers can see when equipment is expected to return from maintenance or when scheduled downtime is approaching.

---

### 11. Permit, License, Insurance & Compliance Management - Document Types

#### Evidence

The compliance management module tracks all document types required for equipment operation. Equipment License/Registration documents establish legal authority to operate. Road Tax records ensure compliance with Malaysian road tax requirements. Transportation Permits authorize specific transportation activities. Fitness Certificates from PUSPAKOM verify that equipment meets safety standards.

Insurance documentation includes third-party liability coverage and comprehensive insurance policies. Emission Test Certificates demonstrate compliance with environmental regulations. Special Operating Permits authorize oversize or overweight cargo movements. Driver/Operator licenses ensure that only qualified personnel operate equipment.

Each document type has specific data fields, validity periods, and renewal requirements configured in the system. The system maintains complete records of all compliance documents with easy retrieval for audits or inspections.

This document type management is evidenced in **Annex C1.5, Page 128** with the Document Types configuration showing supported compliance documents.

#### Value-Added Services

We provide **Integration with JPJ and Insurance Provider APIs** for automatic status verification. The system can query JPJ databases to verify road tax status and insurance provider systems to confirm coverage validity. This automatic verification eliminates manual checking, ensures that expired documents are immediately flagged, and provides confidence that all equipment is properly licensed and insured before deployment.

Our **Compliance Calendar** provides a unified view of all upcoming renewals, inspections, and compliance deadlines across the entire fleet, enabling proactive planning and preventing lapses.

---

### 12. Permit, License, Insurance & Compliance Management - Document Upload & Metadata

#### Evidence

Each compliance document is stored with comprehensive metadata including Document name for easy identification, Category classification for organization, Issue date tracking when the document became valid, Expiry date for renewal planning, Document number for reference and verification, Issuing authority identification, and Attachments in PDF, image, or scan format.

OCR automatically extracts key data from uploaded documents, populating metadata fields without manual data entry. When a road tax certificate is uploaded, the system extracts the plate number, expiry date, and amount paid automatically.

Document version control maintains history of renewals and replacements, ensuring that previous versions remain accessible for audit purposes while current versions are clearly identified.

This document metadata management is evidenced in **Annex C1.5, Page 128** with the Document Metadata interface showing extracted data fields.

#### Value-Added Services

We provide **Automatic Document Classification and Data Extraction** that reduces manual entry by 90%. When documents are uploaded, the system recognizes document types, extracts relevant data fields, and populates the database automatically. This intelligent processing eliminates typing errors, accelerates document processing, and ensures consistent data quality. The system learns from corrections to continuously improve extraction accuracy.

Our **Document Validation** checks uploaded documents for completeness, authenticity indicators, and compliance with required formats, flagging issues for review before acceptance.

---

### 13. Permit, License, Insurance & Compliance Management - Expiry Tracking

#### Evidence

The system automatically calculates days until expiry for all compliance documents and displays status on dashboards with color-coded highlighting: Expired documents show in red requiring immediate action, documents expiring within 7 days show in orange requiring urgent attention, documents expiring within 30 days show in yellow for upcoming renewal planning, and valid documents show in green indicating compliance.

The system can block equipment from operations when documents are critically near expiry based on user-defined rules. This enforcement ensures that non-compliant equipment cannot be inadvertently deployed, protecting MMF from regulatory violations, fines, and insurance issues.

Expiry reports provide lists of upcoming renewals organized by timeframe, enabling proactive renewal planning and preventing last-minute rushes.

This expiry tracking is evidenced in **Annex C1.5, Page 128** with the Expiry Dashboard showing color-coded compliance status.

#### Value-Added Services

We provide **Predictive Renewal Recommendations** based on processing time requirements. The system learns from historical renewal processing times for different document types and authorities, recommending when to initiate renewal applications to ensure continuous compliance. For documents requiring lengthy processing, the system alerts earlier than for simple renewals, ensuring adequate lead time.

Our **Renewal Workflow Automation** tracks renewal applications through approval and submission processes, ensuring that no renewals fall through cracks due to procedural delays.

---

### 14. Automated Notifications

#### Evidence

The notification system supports multiple delivery channels including Email for detailed notifications with attachments, In-App Alerts for immediate visibility when users are logged in, and optional SMS for urgent notifications requiring immediate attention. Users can configure their preferred notification channels based on urgency and document type.

Customizable notification schedules support user-defined alerting timelines including 30 days before expiry for early planning, 14 days before expiry for renewal initiation, 7 days before expiry for urgent action, on expiry day for immediate attention, and escalation to management after expiry for compliance enforcement.

Notification templates can be customized for different document types and recipient roles, ensuring that messages contain appropriate information and instructions.

This notification capability is evidenced in **Annex C1.5, Page 128** with the Notification Settings showing configuration options.

#### Value-Added Services

We provide **Smart Escalation** based on criticality and user response patterns. If a notification is not acknowledged within a defined timeframe, the system automatically escalates to supervisors or alternative contacts. The system learns from historical response patterns to optimize notification timing and escalation paths, ensuring that critical compliance issues receive appropriate attention.

Our **Notification Effectiveness Analytics** track notification delivery, open rates, and response times, enabling continuous improvement of the notification strategy.

---

### 15. Maintenance & Inspection Module - Maintenance Scheduling

#### Evidence

Preventive maintenance schedules support multiple trigger types to accommodate different equipment types and operating conditions. Mileage-based triggers schedule maintenance when vehicles reach defined distance intervals (e.g., every 10,000 km). Engine-hours-based triggers are used for equipment where operating hours are more relevant than distance. Time-based triggers schedule maintenance at calendar intervals (e.g., monthly, quarterly) regardless of usage.

Daily inspection checklists are configurable per equipment type, ensuring that operators check appropriate items for each category of equipment. Checklist completion is tracked and reported, supporting compliance and safety requirements.

Service history tracking maintains complete records of all maintenance activities including dates, parts used, labor hours, costs, and technician assignments. This history supports warranty claims, trend analysis, and replacement decisions.

This maintenance scheduling is evidenced in **Annex C1.2, Page 122** with the PM Calendar showing scheduled maintenance activities.

#### Value-Added Services

We provide **AI-Powered Predictive Maintenance** that analyzes 50+ telemetry data points to predict failures 7-14 days in advance with 89% accuracy. Rather than following rigid schedules, the system determines optimal maintenance timing based on actual equipment condition, operating conditions, and historical patterns. This predictive approach prevents both premature maintenance and unexpected breakdowns, optimizing maintenance costs and equipment availability.

Our **Maintenance Optimization** recommends the most cost-effective maintenance approach—whether to perform maintenance in-house, use external workshops, or defer based on condition assessment.

---

### 16. Maintenance & Inspection Module - Breakdown/Repair Recording

#### Evidence

Defect reports can be lodged by operators, drivers, or maintenance staff with photo attachments showing the issue. The mobile interface enables quick reporting from the field or workshop floor. Reported issues are automatically logged with equipment identification, date/time, reporter information, and problem description.

Mechanics and technicians are auto-assigned based on specialty and availability. The system tracks assignments, monitors workload distribution, and ensures that qualified personnel work on appropriate equipment. Repair progress is tracked in real-time with status updates showing work started, parts ordered, work in progress, and completion.

Costs are tracked including labor hours, parts consumed, and external services, providing complete visibility into repair expenses for each equipment unit.

This breakdown recording is evidenced in **Annex C1.3, Page 124** with the Work Order Management interface showing defect reporting and assignment.

#### Value-Added Services

We provide **Root Cause Analysis** that tracks failure patterns to identify systemic issues. When similar failures occur repeatedly on the same equipment type or component, the system flags these patterns for investigation. Root cause identification enables preventive measures that eliminate recurring problems, reducing long-term maintenance costs and improving equipment reliability.

Our **Repair Recommendation Engine** suggests repair approaches based on historical data, cost comparisons, and equipment criticality, helping maintenance supervisors make informed decisions.

---

### 17. Maintenance & Inspection Module - Internal Work Order (IWO)

#### Evidence

The Internal Work Order system records repair activities performed by MMF's own maintenance staff. IWO records include Dates IN/Out of workshop tracking repair duration, Repairman details identifying who performed the work, Workshop details showing where work was performed, Cost of repair including labor and parts, Details of parts changed with part numbers and quantities, Scanned repair invoice attachments for external purchases, and Requested By / Person Approved fields for authorization tracking.

IWOs link to the Procurement System (PS) for parts procurement, ensuring that required parts are ordered through proper channels with appropriate approvals. This integration prevents ad-hoc purchasing and ensures proper cost tracking.

Work order history provides complete maintenance records for each equipment unit, supporting warranty claims, performance analysis, and replacement decisions.

This IWO capability is evidenced in **Annex C1.3, Page 124** with the IWO Interface showing internal work order management.

#### Value-Added Services

We provide **Automatic Cost Rollup to Asset TCO and Budget Tracking** that accumulates all maintenance costs—both internal and external—into total cost of ownership calculations. The system compares actual maintenance spending against budgets by equipment category, department, or time period, alerting when spending approaches or exceeds budgeted amounts. This visibility supports financial planning and equipment replacement decisions.

Our **Work Order Efficiency Analytics** track repair duration, labor productivity, and parts usage to identify opportunities for process improvement.

---

### 18. Maintenance & Inspection Module - External Work Order (EWO)

#### Evidence

The External Work Order system manages maintenance activities performed by external vendors and workshops. EWO records include Schedule Maintenance Date/Time for appointments, Dates IN/Out of workshop tracking vendor performance, Repairman identification from the vendor, Workshop details including vendor name and location, Cost of repair for budgeting and payment, Details of parts changed with source information, Requested By / Person Approved for authorization tracking, and Scanned repair invoice attachments for payment processing.

Vendor management features track which external workshops are authorized for different types of work, ensuring that equipment is sent only to qualified vendors. Cost comparison features help identify the most cost-effective vendors for different maintenance categories.

EWO integration with FMS ensures that external maintenance costs are properly recorded for payment and cost analysis.

This EWO capability is evidenced in **Annex C1.3, Page 124** with the EWO Interface showing external work order management.

#### Value-Added Services

We provide **Vendor Performance Tracking for External Workshops** that monitors vendor performance across multiple dimensions including turnaround time, cost competitiveness, quality of work, and warranty claim rates. Vendor scorecards enable data-driven vendor selection and support negotiations for better rates and service levels. Underperforming vendors are flagged for review or replacement.

Our **EWO Cost Benchmarking** compares vendor quotes and actual costs against historical data and industry benchmarks, identifying opportunities for cost savings.

---

### 19. Fuel Management - Fuel Dispensing Management

#### Evidence

The fuel management system records every fueling event with comprehensive data including Vehicle ID and Driver ID for accountability, Date and time of fueling for usage tracking, Fuel type ensuring correct fuel is dispensed, Quantity dispensed for consumption analysis, Fuel station ID identifying dispensing location, and Odometer or engine-hour reading for efficiency calculations.

The system enforces critical rules to prevent fraud and errors: maximum tank capacity limits prevent over-dispensing, allowed fuel types ensure diesel vehicles receive diesel and not petrol, and authorized drivers only ensures that only qualified personnel can fuel assigned vehicles. The system locks the pump if unauthorized fueling is attempted.

Real-time monitoring shows fuel levels in storage tanks, dispensing activity, and alerts for unusual patterns.

This fuel dispensing management is evidenced in the Annex C1 Fuel Module with Dispensing Log showing transaction records.

#### Value-Added Services

We provide **Real-Time Fuel Theft Detection** through rapid drop alerts. When fuel levels in vehicle tanks or storage tanks drop unexpectedly—indicating potential theft or leakage—the system immediately alerts security and management. GPS correlation can determine if drops occurred while vehicles were stationary, helping identify theft locations. This capability typically reduces fuel losses by 15-25%.

Our **Fuel Efficiency Analytics** track consumption patterns by vehicle, driver, and route, identifying opportunities for fuel savings through operational improvements.

---

### 20. Fuel Management - Fuel Pump Control & Authorization

#### Evidence

The fuel management system supports limits on per-transaction or per-day fuel allocation to prevent excessive fueling. These limits can be configured by vehicle type, driver category, or specific operational requirements. RFID card or mobile app authorization is required before fuel is dispensed, ensuring that only authorized personnel can access fuel.

Real-time validation against the asset and driver authorization database occurs at the point of fueling. The system verifies that the vehicle is authorized for fuel, the driver is assigned to the vehicle, and fuel limits have not been exceeded before authorizing pump activation.

Fuel pump integration enables automated control of dispensers, capturing transaction data directly into the system without manual entry.

This fuel pump control is evidenced in the Annex C1 Fuel Module with Pump Control showing authorization mechanisms.

#### Value-Added Services

We provide **Dynamic Limits Based on Route Requirements and Historical Consumption** that adjust fuel allocations based on planned routes, vehicle efficiency ratings, and historical consumption patterns. Vehicles assigned to long-distance routes receive higher limits than local delivery vehicles. Efficient vehicles receive standard allocations while vehicles with higher consumption patterns trigger investigation. This intelligent allocation prevents both fuel shortages and excessive dispensing.

Our **Route-Based Fuel Planning** calculates expected fuel needs based on assigned routes and vehicle consumption rates, alerting dispatchers when additional fuel may be required.

---

### 21. Fuel Management - Fuel Inventory & Tank Monitoring

#### Evidence

The system tracks on-site storage tank volumes through real-time sensors or periodic manual readings. Tank level monitoring generates low-level alerts when fuel stocks approach reorder points, ensuring that tanks never run dry. Tank volume reconciliation compares physical tank levels with dispensing data, identifying discrepancies that may indicate leakage, theft, or meter calibration issues.

The system monitors critical tank conditions including water contamination detection, temperature variations that affect fuel volume, and fuel quality parameters when optional sensors are installed. Automatic import from Automatic Tank Gauging (ATG) systems eliminates manual data entry for facilities with advanced monitoring equipment.

Tank history provides usage trends, delivery patterns, and consumption analytics supporting procurement planning.

This tank monitoring is evidenced in the Annex C1 Fuel Module with Tank Monitoring showing storage tank management.

#### Value-Added Services

We provide **Predictive Reordering Based on Consumption Patterns and Delivery Lead Times**. The system analyzes historical fuel consumption, seasonal variations, and operational schedules to predict when fuel levels will reach reorder points. Lead time analysis considers vendor delivery schedules and processing times to ensure that orders are placed with adequate time for delivery. This predictive approach prevents stockouts while minimizing working capital tied up in fuel inventory.

Our **Fuel Quality Monitoring Integration** connects to fuel quality sensors to detect contamination, water intrusion, or degradation that could damage equipment.

---

### 22. Fuel Management - Fuel & Cost Management

#### Evidence

Fuel card integration with fuel providers enables centralized billing and comprehensive transaction tracking. SKDS (Subsidi Kenderaan Diesel Sabah/Sarawak) fuel subsidy enablement supports operations in East Malaysia with appropriate regulatory compliance. Automated fuel consumption analysis calculates km/litre metrics for each vehicle, identifying efficient and inefficient performers.

Fuel theft detection capabilities identify rapid fuel drops, unusual consumption patterns, and discrepancies between expected and actual consumption. Cost reporting provides comprehensive visibility including Fuel cost by vehicle, route, and time period, Maintenance cost correlation with fuel quality and usage, and Operational expenses including tolls, permits, and other vehicle costs.

Integration with FMS ensures that fuel costs are properly allocated to cost centers and jobs for accurate profitability analysis.

This fuel cost management is evidenced in the Annex C1 Fuel Module with Cost Analysis showing comprehensive fuel expense tracking.

#### Value-Added Services

We provide **AI-Powered Fuel Efficiency Recommendations** based on driver behavior analysis and route optimization. The system analyzes acceleration patterns, idling time, speed variations, and route characteristics to identify opportunities for fuel savings. Personalized coaching tips are provided to drivers through the mobile app, helping them improve fuel efficiency. Route optimization suggestions help dispatchers plan more fuel-efficient journeys. These combined capabilities typically improve fleet fuel efficiency by 10-15%.

Our **Fuel Price Optimization** analyzes fuel price trends and recommends optimal timing and locations for fuel purchases.

---

### 23. Spare Part & Tyre Management - Tyre/Spare Parts Inventory Management

#### Evidence

The inventory management system maintains comprehensive records for all spare parts and tyres with unique identification through Serial number, RFID tag, or barcode for tracking. Brand, model, size, ply rating, and type specifications ensure correct parts are used. Purchase date, vendor, and cost information support warranty claims and cost analysis. Stock classification tracks whether items are new, used, retreaded, or damaged.

Inventory alerts monitor stock levels and generate notifications for low stock conditions requiring reorder and warranty expiry for items approaching warranty end dates. The system links to the Procurement System (PS) for automatic reorder generation when stock falls below minimum levels.

Inventory valuation tracks current stock value using FIFO or average cost methods as appropriate for accounting requirements.

This parts inventory management is evidenced in **Annex C1.7, Page 132** with the Parts Inventory showing stock management capabilities.

#### Value-Added Services

We provide **Smart Inventory Optimization Using Machine Learning** that predicts parts demand based on scheduled maintenance, failure rates, and historical consumption patterns. The system calculates optimal reorder points, safety stock levels, and economic order quantities to minimize stockholding costs while preventing stockouts. This intelligent optimization typically reduces parts inventory holding costs by 25-30% while improving parts availability for maintenance.

Our **Vendor-Managed Inventory Integration** enables key suppliers to monitor stock levels and initiate replenishment automatically, reducing procurement administrative costs.

---

### 24. Spare Part & Tyre Management - Tyre/Spare Parts Lifecycle Tracking

#### Evidence

Unique ID tracking maintains complete lifecycle records for each tyre and major spare part including Installation and dismounting dates, Vehicle assignment history showing which equipment used the part, Tyre position tracking (LHF, RHF, LHR, RHR for vehicles), Distance travelled and usage hours accumulated, and Retreading records showing number of retreads and dates.

Tyre lifecycle cost analysis calculates cost per kilometre for each tyre, enabling comparison of different brands, models, and retreading strategies. Performance analytics identify which tyre specifications provide the best value for different operating conditions.

Warranty tracking monitors tyre warranty periods and mileage limits, ensuring that warranty claims are submitted for eligible failures.

This lifecycle tracking is evidenced in **Annex C1.7, Page 132** with the Lifecycle Tracking interface showing tyre history records.

#### Value-Added Services

We provide **Predictive Tyre Replacement Forecast** based on wear patterns and usage projections. The system analyzes current tread depth, accumulated mileage, operating conditions, and historical wear rates to predict when each tyre will require replacement. This forecasting enables proactive ordering of replacement tyres and scheduling of fitting appointments, preventing unexpected tyre failures and operational disruptions.

Our **Tyre Performance Analytics** compare different brands, models, and retreading strategies across actual operating conditions, identifying optimal specifications for MMF's fleet.

---

### 25. Reporting and Enquiries - Reporting

#### Evidence

The comprehensive reporting suite includes essential equipment management reports: Fuel Consumption report tracking usage by vehicle, driver, and time period; Productivity report per Equipment showing utilization rates and revenue generation; PM schedule report listing upcoming preventive maintenance; Maintenance history report providing complete service records; Corrective/breakdown maintenance report tracking unscheduled repairs; Overdue maintenance report highlighting missed scheduled maintenance; Maintenance cost report analyzing expenses by equipment, category, and time; Tyre lifecycle cost analysis showing cost per kilometre by tyre; Cost per kilometre metrics for overall operating efficiency; Inventory reports for parts stock levels and valuation; Tyre performance comparison by brand and model; Vehicle tyre cost summary for fleet-wide analysis; and Predictive tyre replacement forecast based on wear patterns.

Reports can be filtered by date range, equipment category, location, and other dimensions. Export capabilities support PDF for distribution, Excel for analysis, and CSV for data integration.

This reporting capability is evidenced in **Annex C1.12, Pages 140-145** with the Report Library showing available reports and sample outputs.

#### Value-Added Services

We provide **Natural Language Reporting** that allows managers to ask questions using conversational queries rather than navigating report menus. Managers can ask "Show me equipment with maintenance cost exceeding 30% of book value" or "Which vehicles have the highest fuel consumption this month?" and receive instant visual answers in chart or table format. This natural language interface democratizes data access and eliminates the learning curve associated with traditional reporting tools.

Our **Automated Report Distribution** schedules and delivers reports to stakeholders automatically based on their roles and preferences.

---

### 26. Reporting and Enquiries - Enquiries (Real-Time Queries)

#### Evidence

Real-time enquiry capabilities provide instant access to critical equipment information including Equipment availability enquiry showing which equipment is ready for assignment, Equipment status enquiry showing active, idle, or under maintenance status, PM schedule enquiry for upcoming maintenance planning, Work order status enquiry tracking maintenance progress, Maintenance history enquiry providing complete service records, Pending/overdue maintenance enquiry highlighting action items, Spare parts availability enquiry for maintenance planning, Equipment usage enquiry showing utilization metrics, Hour meter/odometer enquiry for maintenance trigger tracking, Fuel consumption enquiry for efficiency monitoring, Productivity enquiry showing operational performance, Cost tracking enquiry for expense analysis, Rental cost enquiry for hired equipment, Depreciation enquiry for asset valuation, Vendor invoice enquiry for payment tracking, Inspection status enquiry for compliance monitoring, and Permit/certificate validity enquiry for regulatory compliance.

Advanced filtering enables users to narrow results by equipment type, location, date range, and other criteria. Saved queries allow quick re-execution of frequently used enquiries.

This enquiry capability is evidenced in **Annex C1.12, Pages 140-145** with the Enquiry Interface showing real-time query capabilities.

#### Value-Added Services

We provide **Advanced Filtering and Saved Queries** for frequently accessed information. Users can create complex filter combinations and save them for quick access. Saved queries can be scheduled for automatic execution with results delivered by email, ensuring that stakeholders always have current information without repeatedly running the same queries.

Our **Cross-Reference Enquiries** enable users to drill down from summary information to detailed records with a single click, providing comprehensive visibility without navigating multiple screens.

---

*Annexure C1 contains 26 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 800,000.*

---

## ANNEXURE C2: PROCUREMENT SYSTEM (PS)

**System:** LogisticsPro PS v4.2  
**Location:** ALL Branches (Port Klang, Butterworth, Padang Besar, Headquarters, Global Logistics Dept, Pasir Gudang)  
**Total Requirements:** 34  
**Coverage:** Purchase requisitions, work orders, RFQ, purchase orders, goods receipt, inventory, tender management, contract management

The Procurement System (PS) provides comprehensive procurement management across all MMF branches, streamlining the acquisition of goods and services while ensuring compliance, cost control, and operational efficiency. The system manages the complete procurement lifecycle from initial requisition through vendor selection, purchase order management, goods receipt, and payment processing. PS integrates seamlessly with FMS for financial control, HRMS for user authentication and approval workflows, and EMS for maintenance-related procurement.

---

### 1. Overall Requirements - Dashboards & Analytics (Online Report Including Management Dashboard)

#### Evidence

The Procurement Dashboard provides comprehensive visibility into procurement operations and spend analysis. The system analyzes historical purchase prices and trends to identify cost saving opportunities, enabling procurement managers to negotiate better rates and consolidate purchasing volumes. Detailed insights into expenses show spending patterns by category, department, vendor, and time period, highlighting areas of concentration and potential savings.

Cost opportunities are identified through spend analysis, vendor performance comparison, and budget variance reporting. Visibility into KPIs for procurement efficiency includes metrics such as spend by category, vendor performance scores, budget utilization percentages, purchase order cycle times, and requisition approval turnaround times. The dashboard provides both summary views for executive oversight and detailed views for operational management.

Real-time updates ensure that displayed information reflects current procurement activities, commitments, and budget status. Drill-down capabilities enable users to navigate from summary metrics to individual transactions for investigation and analysis.

This dashboard capability is evidenced in **Annex C2.7, Page 162** with the Spend Analysis dashboard showing procurement KPIs and analytics.

#### Value-Added Services

We provide **AI Spend Classification** that automatically categorizes purchases based on item descriptions, vendor information, and historical patterns. The system suggests preferred vendors for each category based on past performance, pricing, and delivery reliability. This intelligent classification typically identifies 10-15% of spending that is misclassified or could be consolidated for volume discounts, leading to significant cost savings.

Our **Procurement Benchmarking** compares MMF's spending patterns and pricing against industry benchmarks, identifying opportunities for cost reduction and process improvement.

---

### 2. Overall Requirements - Multi Platform Interface

#### Evidence

PS is accessible via web browsers providing full functionality for procurement staff, requestors, and approvers. Native mobile apps for iOS and Android enable approvers to review and approve requisitions from anywhere, ensuring that procurement processes are not delayed by approver unavailability. The responsive tablet design supports users who need portability with larger screen visibility.

Push notifications alert approvers to urgent requisitions requiring immediate attention, ensuring that critical procurement needs are addressed promptly. The mobile interface is optimized for quick review with summary information presented clearly and approval actions accessible with minimal navigation.

Offline capabilities allow users to draft requisitions and save them for submission when connectivity is available, ensuring productivity even in areas with limited network coverage.

This multi-platform support is evidenced in **Annex C2.9, Page 166** with the Mobile Approval interface showing approver capabilities on mobile devices.

#### Value-Added Services

We provide **Smart Approval Assistant** that summarizes key information from requisitions into a concise format enabling one-tap approval for routine requests. The assistant highlights exceptions such as unusual vendors, high-value items, or budget impacts that require additional consideration. Voice approval is supported for hands-free processing, allowing approvers to approve requests while driving or in situations where hands are occupied.

Our **Approval Delegation Intelligence** automatically routes approvals to delegates when primary approvers are on leave or unavailable, preventing delays in the procurement process.

---

### 3. Overall Requirements - Interface with 3rd Party System

#### Evidence

The PS integration architecture supports RESTful APIs for modern web-based integrations, SOAP web services for legacy enterprise systems, and middleware connectors for specialized procurement platforms. These integration capabilities enable connectivity with vendor portals for electronic quotation submission and order acknowledgment, banking systems for payment processing, and logistics platforms for delivery tracking.

API security includes authentication management, rate limiting to prevent system overload, and comprehensive logging for audit and troubleshooting. Standard data formats ensure compatibility with common procurement and financial systems used by MMF's vendors and partners.

The integration framework supports both real-time synchronization for time-critical transactions and batch processing for high-volume data exchange.

This integration capability is evidenced in **Annex F.3, Page 172** with the API Integration specification showing supported protocols and data formats.

#### Value-Added Services

We provide **Pre-Built Connectors for Major Malaysian Banks and E-Procurement Platforms**, significantly reducing integration time and cost. These connectors enable automatic payment processing, bank reconciliation, and electronic fund transfers without custom development. E-procurement platform connectors facilitate participation in government and corporate procurement portals, expanding MMF's business opportunities.

Our **Integration Monitoring Dashboard** provides real-time visibility into all external connections with proactive alerting for failures or performance issues.

---

### 4. Overall Requirements - PS Able to Link with Other Business System

#### Evidence

PS seamlessly integrates with FMS for three-way matching between purchase orders, goods receipts, and vendor invoices. This integration ensures that payments are only made for properly received goods at agreed prices, preventing overpayments and fraud. Accounts Payable invoice processing flows automatically from PS to FMS, eliminating duplicate data entry.

HRMS integration provides user authentication services, ensuring that only authorized personnel can create requisitions or approve purchases. Approval workflows leverage HRMS organizational data to route requests to appropriate approvers based on department, cost center, and authority levels.

EMS integration supports Internal Work Order (IWO) and External Work Order (EWO) parts procurement, linking maintenance activities to procurement processes. When maintenance requires parts, the system can automatically generate requisitions or purchase orders with appropriate references.

This system integration is evidenced in **Annex F.3, Page 172** with the System Integration documentation showing data flows between PS and other MMF systems.

#### Value-Added Services

We provide **Bi-Directional Synchronization** that ensures data consistency across all systems. When vendor information is updated in PS, the changes propagate to FMS. When payment status is updated in FMS, the information flows back to PS. This synchronization eliminates data discrepancies and ensures that all users see current, accurate information regardless of which system they access.

Our **Unified Procurement View** consolidates data from all connected systems into a single dashboard showing requisition status, purchase order status, receipt status, and payment status for complete visibility.

---

### 5. Overall Requirements - User-Friendly Interface

#### Evidence

The PS interface is designed for intuitive operation with guided workflows that lead users through procurement processes step-by-step. Smart defaults pre-populate fields based on user history, department preferences, and item characteristics, reducing data entry time. Contextual help provides guidance specific to each field and process, enabling users to complete tasks correctly without extensive training.

New users can create their first purchase requisition within 10 minutes without formal training, demonstrating the system's ease of use. The interface design follows established usability principles with consistent navigation, clear labeling, and logical workflow sequences.

Role-based customization presents appropriate functions and information for each user's responsibilities, reducing complexity and focusing attention on relevant tasks.

This usability is evidenced in **Annex C2.10, Page 167** with the Conversational UI demonstrating user-friendly design.

#### Value-Added Services

We provide **Conversational Procurement** that allows users to submit requisitions via natural language inputs. Users can type or speak requests such as "Order 10 boxes of A4 paper for HQ office" or "Need new tyres for PM-047, budget code TRANSPORT-001" and the system interprets the request, identifies the items, and creates the requisition automatically. This natural language interface reduces requisition creation time by 70% and eliminates errors from manual data entry.

Our **Intelligent Form Completion** uses AI to suggest field values based on historical patterns and context, further accelerating procurement processes.

---

### 6. Overall Requirements - Audit Trail & History

#### Evidence

The complete audit trail captures all procurement activities including requisition creation, approval actions, purchase order issuance, goods receipt, and invoice processing. Each audit record includes user identification, timestamp, before/after values for changes, and the business context of the transaction.

Full history supports internal audits by providing complete records of procurement decisions and actions. External regulatory compliance is supported through comprehensive documentation of procurement processes, approvals, and vendor selections. Audit trails are maintained for required retention periods with appropriate archival and retrieval capabilities.

Audit analytics identify unusual patterns, frequent approvers, and potential process bottlenecks, supporting continuous improvement initiatives.

This audit capability is evidenced in **Annex D.2, Page 98** with the Audit Trail showing procurement activity logging.

#### Value-Added Services

We provide **Fraud Detection Analytics** that analyzes procurement patterns to identify suspicious activities such as split purchases to bypass approval thresholds, unusual vendor relationships, approvers who never reject requests, or requisitioners who consistently select the same vendor. The system flags these patterns for review, helping prevent procurement fraud and ensuring compliance with policies.

Our **Audit Preparation Automation** compiles required documentation for internal and external audits, significantly reducing audit preparation time and costs.

---

### 7. Overall Requirements - Ability of the System to Support Attachment Documents

#### Evidence

The system supports unlimited document attachments throughout the procurement process including PR supporting documents such as specifications and justifications, vendor quotes for comparison and selection, contracts and agreements with vendors, and delivery receipts and proof of delivery. OCR extraction enables text searchability within uploaded documents, allowing users to find documents by searching for content rather than browsing folders.

Document version control maintains history of revisions, ensuring that previous versions remain accessible while current versions are clearly identified. Document access controls ensure that sensitive procurement information is only available to authorized personnel.

Integration with document management systems enables centralized storage and retrieval of procurement documentation.

This document management is evidenced in **Annex C2.1, Page 150** with the Document Attachments interface showing attachment capabilities.

#### Value-Added Services

We provide **Automatic Document Classification and Data Extraction** that processes uploaded documents using AI to identify document types, extract key data fields, and populate appropriate system fields automatically. Vendor quotes are analyzed to extract pricing, terms, and conditions without manual data entry. This automation reduces document processing time by 80% and improves data accuracy.

Our **Document Validation** checks uploaded documents for completeness, proper authorization signatures, and compliance with required formats.

---

### 8. Overall Requirements - Ability to Provide Comprehensive Security Features

#### Evidence

Enterprise-grade security protects sensitive procurement data and processes. Multi-factor authentication ensures that only authorized users can access the system. Role-Based Access Control (RBAC) provides granular permissions controlling who can create requisitions, approve purchases, receive goods, or access sensitive vendor information.

Segregation of duties is enforced through system controls—requisitioners cannot approve their own requests, approvers cannot receive goods, and receivers cannot approve invoices. This separation prevents fraud and ensures proper checks and balances.

Dynamic Access Control adjusts permissions based on risk factors such as transaction value, vendor status, or user location. High-value transactions may require additional approvals or video verification.

This security is evidenced in **Annex D, Pages 95-110** with the Security Matrix showing access controls and segregation of duties.

#### Value-Added Services

We provide **Bank-Grade Security for Sensitive Transactions** with dual authorization requirements for high-value purchases and video verification for critical approvals. These enhanced security measures protect against fraud and ensure that significant procurement decisions receive appropriate scrutiny.

Our **Continuous Security Monitoring** detects and alerts on suspicious activities such as after-hours access, unusual approval patterns, or attempts to bypass controls.

---

### 9. Supplier Master - Supplier Master File Management

#### Evidence

The centralized supplier repository maintains comprehensive information for all vendors including Company profile with business registration details, Contact details for primary and alternative contacts, Bank information for electronic payments, Tax registration numbers for compliance, Classification and categories for organizing vendors by product/service type, Performance history with ratings and feedback, and Document management for certificates, licenses, and contracts.

Supplier records include approval status indicating whether vendors are authorized for procurement, and risk ratings based on financial stability, delivery performance, and quality metrics.

Search and filter capabilities enable quick location of vendors by name, category, location, or performance rating.

This supplier management is evidenced in **Annex C2.2, Page 152** with the Supplier Registry showing vendor record management.

#### Value-Added Services

We provide **Automated Data Enrichment from External Sources** including SSM (Companies Commission of Malaysia) for company registration verification, credit bureaus for financial risk assessment, and industry databases for supplier information. This automatic enrichment ensures that supplier records are current and accurate without manual research, and identifies potential risks before they impact operations.

Our **Supplier Risk Monitoring** continuously tracks external data sources for changes in supplier status, legal actions, or financial difficulties that might affect MMF.

---

### 10. Supplier Master - Approved Supplier List (ASL)

#### Evidence

The Approved Supplier List (ASL) maintains the roster of vendors authorized for procurement at MMF. Vendor classification organizes suppliers by product categories, service types, and strategic importance. Approval status indicates whether vendors are active, under review, suspended, or disqualified. Validity periods define when approvals expire and require renewal.

Expiry tracking monitors vendor certifications, insurance coverage, and approval validity periods. Auto-alerts notify procurement staff when ASL renewals are required, ensuring that vendor approvals remain current.

New vendor onboarding workflows manage the process of evaluating and approving new suppliers, including document collection, reference checks, and trial orders.

This ASL management is evidenced in **Annex C2.2, Page 152** with the ASL Management interface showing approved vendor tracking.

#### Value-Added Services

We provide **Vendor Risk Intelligence** that monitors external data sources for proactive risk identification. The system alerts when approved vendors experience financial difficulties, legal issues, ownership changes, or other events that might affect their ability to deliver. This early warning enables MMF to take preventive actions such as diversifying sources or increasing safety stock before disruptions occur.

Our **Vendor Performance Prediction** uses historical data to forecast future vendor performance, identifying vendors at risk of declining service quality.

---

### 11. Purchase Requisition (PR) - PR Creation

#### Evidence

The purchase requisition creation process enables requestors to select items from a catalog of pre-approved items or enter free-text descriptions for non-catalog items. Quantity specification ensures that correct amounts are ordered, while required date entry ensures that procurement can meet operational timelines. Cost center allocation ensures proper budget charging.

Attachments allow inclusion of supporting documents such as specifications, quotations, or justifications. AI recommendations suggest preferred vendors based on historical data, past performance, and pricing, helping requestors make informed vendor selections.

Budget checking validates that requested items are within approved budgets before submission, preventing overspending.

This PR creation is evidenced in **Annex C2.1, Page 150** with the PR Creation interface showing requisition entry.

#### Value-Added Services

We provide **Duplicate Request Detection** that identifies similar recent requests to prevent accidental duplication of orders. The system alerts requestors when items matching their request were recently ordered, allowing them to cancel or modify if the existing order meets their needs.

Our **Smart Autocomplete** learns from purchase history to suggest items, vendors, and cost centers as users type, accelerating requisition creation and improving accuracy.

---

### 12. Purchase Requisition (PR) - PR Validation

#### Evidence

Budget check integration prevents overspending by validating that requested items are within approved budgets before allowing submission. The system displays available budget balances and alerts when requests exceed remaining budget. Duplicate request detection flags similar recent requests that may indicate accidental duplication.

Automatic validation of mandatory fields ensures that all required information is provided before submission, reducing back-and-forth for missing data. Approval authority validation ensures that requests are routed to appropriate approvers based on value, category, and organizational rules.

Validation rules can be customized to enforce organizational policies such as preferred vendor requirements, maximum order quantities, or mandatory justifications for certain categories.

This PR validation is evidenced in **Annex C2.1, Page 150** with the PR Validation showing budget checking and validation rules.

#### Value-Added Services

We provide **Predictive Budget Impact Analysis** for multi-year projects. The system analyzes the impact of current requisitions on future budget periods, alerting when projected spending will exceed future budgets. This forward-looking analysis prevents budget overruns and supports better financial planning.

Our **Budget Optimization Recommendations** suggest timing or vendor changes that could reduce costs while meeting operational requirements.

---

### 13. Purchase Requisition (PR) - PR Approval Workflow

#### Evidence

Configurable multi-level approvals support complex organizational structures with routing by value thresholds (higher values require higher-level approval), departments (ensuring departmental managers approve their own budgets), and categories (specialized approval for IT, equipment, or services). Parallel and sequential approval routing accommodates different approval scenarios—some requests may need simultaneous approval from multiple departments, while others require sequential approval through management levels.

Delegation rules manage approver absence by automatically routing to designated delegates when primary approvers are unavailable. Approval reminders notify approvers of pending requests at configurable intervals.

Approval history maintains complete records of all approval actions, supporting audit and compliance requirements.

This approval workflow is evidenced in **Annex C2.1, Page 150** with the Approval Workflow showing routing configuration.

#### Value-Added Services

We provide **Smart Routing** that sends urgent requests to available approvers based on calendar integration. The system checks approver calendars and availability status to route requests to approvers who are present and available, reducing cycle time by 40-50% for urgent procurement needs.

Our **Approval Load Balancing** distributes approval workload across multiple approvers when available, preventing bottlenecks when single approvers have large queues.

---

### 14. Purchase Requisition (PR) - PR Status Tracking

#### Evidence

Full status visibility tracks requisitions through their lifecycle from Draft (being prepared), Submitted (awaiting approval), Under Review (with approvers), to Approved or Rejected final states. Real-time notifications alert requestors at each status change, keeping them informed of progress without requiring manual checking.

Comments and rejection reasons are captured when approvers reject or return requests, providing feedback for resubmission. Requestors can view the complete approval chain, seeing who has approved and who is pending.

Status history provides complete audit trails of all status changes with timestamps and user identification.

This status tracking is evidenced in **Annex C2.1, Page 150** with the Status Tracking showing requisition progress.

#### Value-Added Services

We provide **Bottleneck Identification** with automatic escalation for stalled approvals. The system monitors approval cycle times and identifies requests that have been pending longer than normal. Automatic escalation notifies supervisors or alternative approvers when requests stall, ensuring that procurement processes continue to flow smoothly.

Our **Status Prediction** estimates completion times based on current queue depths and historical approval times, helping requestors plan accordingly.

---

### 15. Internal Work Order (IWO) - Work Order Creation

#### Evidence

IWO creation uses standardized forms capturing essential information including Requestor identification for accountability, Department and cost center for budget allocation, Location where work is to be performed, Equipment Number for maintenance-related work, Work Type/Category classification for routing and reporting, Description of work detailing requirements, and Requested completion date for scheduling.

Optional attachments support inclusion of documents, images, or specifications that help explain the work requirements. The mobile interface enables quick IWO creation from the field or workshop floor.

IWO templates for common work types accelerate creation by pre-filling standard information and requirements.

This IWO creation is evidenced in **Annex C2, Page 150** with the IWO Creation interface showing work order entry.

#### Value-Added Services

We provide **AI Categorization** that automatically classifies work types based on description text and suggests estimated completion times based on historical data for similar work. This intelligent categorization ensures proper routing to appropriate maintenance teams and helps with resource planning and scheduling.

Our **Work Order Templates** provide pre-configured forms for common maintenance activities, significantly reducing data entry time and ensuring consistency.

---

### 16. Internal Work Order (IWO) - Work Order Validation & Approval Workflow

#### Evidence

Automatic routing directs work orders to appropriate approvers based on department and work type. Maintenance work orders may route to maintenance supervisors, IT work orders to IT managers, and facility work orders to facilities management. Approver notification via email or in-app alerts ensures that pending work orders receive timely attention.

Approvers can take actions including Approve (authorizing work to proceed), Reject (with reason provided), or Request Clarification (returning to requestor for additional information). All actions are timestamped and logged for audit purposes.

Approval delegation ensures that work orders are not delayed when primary approvers are unavailable.

This IWO workflow is evidenced in **Annex C2, Page 150** with the IWO Workflow showing approval processes.

#### Value-Added Services

We provide **Smart Escalation** based on urgency and approver availability. High-priority work orders are escalated more quickly if not approved, and alternative approvers are automatically assigned when primary approvers are out of office.

Our **Risk-Based Approval Routing** directs high-value or critical work orders through additional approval layers for enhanced oversight.

---

### 17. Internal Work Order (IWO) - Assignment & Scheduling

#### Evidence

Supervisors assign work orders to teams or specific staff members based on skills, workload, and availability. Scheduling features include Priority level setting (Low, Medium, High, Urgent) for work sequencing, and Estimated start and end dates for planning and resource allocation.

Reassignment capability allows supervisors to move work between team members as priorities change or staff become unavailable, with full history maintained of all assignments. Requestor notification alerts requestors when their work orders are assigned, providing visibility into when work will begin.

Calendar integration shows work order schedules alongside other commitments for comprehensive resource planning.

This assignment capability is evidenced in **Annex C2, Page 150** with the Assignment Screen showing work order allocation.

#### Value-Added Services

We provide **Skills-Based Automatic Assignment** that matches work requirements to staff capabilities. The system analyzes work descriptions, required skills, and staff certifications to recommend optimal assignments. This intelligent matching ensures that qualified personnel work on appropriate tasks and helps balance workload across teams.

Our **Capacity Planning Integration** shows available capacity for upcoming periods, helping supervisors plan work assignments and identify resource constraints.

---

### 18. Internal Work Order (IWO) - IWO Execution (Task Management)

#### Evidence

Executors update work orders with Actual start and end time tracking work duration, Materials used listing consumables and parts consumed, Labor hours for cost tracking, and Completion notes documenting what was done and any issues encountered. Status transitions track progress through Open → Assigned → In Progress → On Hold → Completed → Closed.

Real-time progress tracking enables supervisors to monitor work order status and intervene when work is stalled or delayed. Time tracking supports cost analysis and productivity measurement.

Mobile access allows technicians to update work orders while in the field or workshop without returning to their desks.

This task execution is evidenced in **Annex C2, Page 150** with the Task Execution interface showing work order updates.

#### Value-Added Services

We provide **Real-Time Progress Tracking** with estimated completion times based on work remaining and historical performance data. Supervisors can see at a glance which work orders are on track and which are at risk of missing deadlines.

Our **Work Order Analytics** track completion times, resource utilization, and backlog trends to identify process improvement opportunities.

---

### 19. External Work Order (EWO) - EWO Creation

#### Evidence

EWO creation captures comprehensive information for external maintenance and services including Requestor and Department/Cost Center for accountability, Location where work is to be performed, Equipment Number for equipment-related services, Work Category classification (maintenance, IT services, repairs, construction), Detailed description of required work, Attachments such as photos, bills of quantities, or specifications, Required timeline for completion, and Estimated cost for budgeting.

The detailed information ensures that external vendors understand requirements clearly and can provide accurate quotations. Document attachments help convey complex requirements that cannot be described in text alone.

EWO templates for common external services accelerate creation and ensure consistent information capture.

This EWO creation is evidenced in **Annex C2, Page 150** with the EWO Creation interface showing external work order entry.

#### Value-Added Services

We provide **Template Library for Common EWO Types** with pre-filled specifications, standard requirements, and recommended vendors. When creating EWOs for common services, users can select templates that automatically populate standard information, significantly reducing data entry time and ensuring completeness.

Our **Vendor Recommendation** suggests qualified external vendors based on work category, historical performance, and availability.

---

### 20. External Work Order (EWO) - EWO Approval Workflow

#### Evidence

Multi-stage approval routing ensures appropriate oversight for external work orders based on value, category, and vendor status. Approvers can review supporting documents, specifications, and vendor information before making decisions. Available actions include Approve (authorizing vendor engagement), Reject (with comments explaining why), Request Revision (returning to requestor for changes), or Put on Hold (pausing for additional information).

Timestamps and digital signatures capture approval authority and timing for audit purposes. High-value EWOs may require multiple approvals from different departments or management levels.

Approval history provides complete records of all approval actions and justifications.

This EWO approval is evidenced in **Annex C2, Page 150** with the EWO Approval showing external work order authorization.

#### Value-Added Services

We provide **Risk-Based Approval Routing** for high-value or critical EWOs. The system automatically routes high-value external work orders through additional approval layers, requires additional documentation, or mandates competitive bidding based on configurable risk rules.

Our **Approval Analytics** track approval cycle times and identify bottlenecks in the external work order process.

---

### 21. External Work Order (EWO) - EWO Execution Tracking

#### Evidence

Progress updates by internal staff track external vendor performance including work start, milestone completion, and delivery of interim deliverables. Progress verification workflow ensures that completed work is inspected and accepted before payment authorization. Status tracking follows EWOs through Pending → Approved → Assigned → In Progress → Completed → Verified → Closed.

Vendor communication logs maintain records of all interactions with external vendors, supporting dispute resolution and performance evaluation. Issue tracking documents problems encountered during execution and their resolution.

Integration with PS ensures that vendor invoices are matched against approved EWOs before payment.

This EWO tracking is evidenced in **Annex C2, Page 150** with the EWO Tracking showing external work order progress.

#### Value-Added Services

We provide **Vendor Portal for External Contractors** to update progress directly. Vendors can log in to report work completion, upload deliverables, and communicate status without requiring MMF staff to manually enter updates. This self-service capability reduces administrative overhead and improves data accuracy.

Our **Vendor Performance Tracking** captures delivery performance, quality ratings, and cost adherence for continuous vendor evaluation.

---

### 22. Request For Quotation (RFQ) - Request for Quotation (RFQ)

#### Evidence

RFQ creation from PR or EWO enables procurement of goods and services through competitive bidding. Distribution to selected vendors via email or portal ensures that qualified suppliers receive opportunity to quote. Vendor notification includes submission deadlines and clear instructions for response format and content.

Auto-reminders notify vendors of pending quote deadlines, improving response rates. Side-by-side comparison sheets are auto-generated from vendor responses, enabling easy evaluation of pricing, terms, and delivery across multiple vendors.

Procurement selects winning vendors based on comparison results, with full audit trail of selection criteria and decisions.

This RFQ capability is evidenced in **Annex C2.3, Page 154** with the RFQ Comparison showing vendor quote evaluation.

#### Value-Added Services

We provide **AI Price Benchmarking** that compares quotes against market rates and historical data. The system identifies quotes that are significantly above or below market rates, flags unusual pricing patterns, and typically saves 8-12% on procurement costs by ensuring competitive pricing. Historical price tracking shows price trends over time, helping procurement negotiate better rates.

Our **Vendor Selection Optimization** recommends optimal vendors based on price, quality ratings, delivery performance, and risk factors.

---

### 23. Purchase Order (PO) - PO Creation

#### Evidence

Purchase orders are auto-generated from approved PRs, IWOs, or EWOs, ensuring that purchasing aligns with approved requirements. Editable terms allow customization of payment terms, delivery instructions, and special conditions for specific vendors or purchases. Equipment Number reference capability links POs to specific assets for tracking and costing.

Templates for standard PO types accelerate creation for recurring purchases with pre-filled vendor information, standard terms, and common items. PO numbering follows organizational conventions for document control and audit.

Budget validation ensures that PO creation is within approved budgets before finalization.

This PO creation is evidenced in **Annex C2.4, Page 156** with the PO Creation interface showing purchase order generation.

#### Value-Added Services

We provide **Smart PO Consolidation** that identifies opportunities to combine multiple requisitions into single purchase orders for volume discounts. The system analyzes pending requisitions for the same vendor, similar items, or compatible delivery schedules and suggests consolidation opportunities that reduce costs and administrative overhead.

Our **Optimal Order Quantity Calculation** recommends order quantities that balance volume discounts against carrying costs.

---

### 24. Purchase Order (PO) - PO Approval

#### Evidence

Configurable approval workflow routes purchase orders based on value (higher values require higher-level approval), category (specialized approval for capital equipment, services, or specific commodities), and vendor (additional scrutiny for new or high-risk vendors). Approver comments capture additional instructions or conditions, and complete audit trails document all approval actions.

Delegation and escalation rules ensure that POs are not delayed when approvers are unavailable. Budget validation confirms that POs are within approved budgets before final approval.

Approval notifications alert vendors when POs are approved, enabling them to begin fulfillment.

This PO approval is evidenced in **Annex C2.4, Page 156** with the PO Approval showing authorization processes.

#### Value-Added Services

We provide **Risk-Based Approval Requirements** for new or high-risk vendors. The system automatically applies additional approval layers or documentation requirements when purchasing from new vendors, vendors with performance issues, or high-risk categories. This enhanced scrutiny protects against procurement fraud and vendor failures.

Our **Approval Delegation Intelligence** automatically routes approvals to designated delegates when primary approvers are on leave or unavailable.

---

### 25. Purchase Order (PO) - PO Dispatch

#### Evidence

Email and portal notification to vendors delivers POs with PDF attachments for vendor records. Digital signature option provides authorized signatures on PO documents, giving vendors confidence in order validity. Delivery instructions and terms are clearly specified to prevent misunderstandings about shipping methods, delivery locations, and timing.

Delivery confirmation tracking ensures that vendors have received and acknowledged POs. Failed delivery alerts notify procurement when POs cannot be delivered, enabling follow-up with correct contact information.

PO status updates show dispatch status and vendor acknowledgment in real-time.

This PO dispatch is evidenced in **Annex C2.4, Page 156** with the PO Dispatch showing vendor notification.

#### Value-Added Services

We provide **Electronic Signature Integration** for paperless processing. POs can be digitally signed using legally recognized electronic signatures, eliminating printing, signing, scanning, and email exchanges. This accelerates the procurement cycle and ensures document integrity.

Our **Multi-Channel Delivery** sends POs through vendor-preferred channels including EDI, portal, email, or API integration.

---

### 26. Purchase Order (PO) - PO Tracking

#### Evidence

Vendor acknowledgement tracking confirms that vendors have received and accepted POs. Delivery schedule tracking provides ETA visibility for incoming shipments, enabling receiving preparation and operational planning. Automatic notifications alert procurement staff when delays occur or exceptions are reported by vendors.

Shipment tracking integration with carrier systems provides real-time location information for in-transit orders. Delivery confirmation captures proof of delivery for vendor payment authorization.

PO history maintains complete records of all communications, acknowledgments, and delivery events.

This PO tracking is evidenced in **Annex C2.4, Page 156** with the PO Tracking showing order status monitoring.

#### Value-Added Services

We provide **Predictive Delivery Delay Alerts** based on vendor historical performance. The system analyzes vendor on-time delivery rates and current order progress to predict potential delays before vendors report them. Early warning enables proactive communication with internal stakeholders and expediting actions to minimize impact.

Our **Delivery Risk Assessment** scores orders by delivery risk based on vendor performance, order complexity, and external factors.

---

### 27. Goods Receive (GR) - Goods Receive (GR)

#### Evidence

Goods Receipt Note (GRN) creation by receivers documents delivery of ordered items. Partial receipt capability allows recording of partial deliveries when complete orders are not received, updating expected quantities for remaining items. Capture of delivered quantity, batch or serial numbers for traceability, delivery note number for reference, and supplier invoice information supports three-way matching.

Quality check workflow (optional) routes received items through inspection processes when quality verification is required. Linking to PO lines ensures that receipts are matched to authorized purchases.

Mobile receiving enables warehouse staff to record receipts using handheld devices without returning to desktop computers.

This goods receipt is evidenced in **Annex C2.5, Page 158** with the GRN Interface showing goods receipt processing.

#### Value-Added Services

We provide **Barcode/RFID Scanning for Rapid Receiving**. Warehouse staff can scan item barcodes or RFID tags to automatically identify items, match them to PO lines, and record receipts without manual data entry. This scanning capability accelerates receiving processes by 60-70% and eliminates data entry errors.

Our **Inspection Automation** routes items requiring quality checks to inspection queues and tracks inspection results.

---

### 28. Inventory Management - Store Issue (SI)

#### Evidence

Store issue management handles internal consumption of inventory items from stock. Allocation to specific work orders or departments ensures proper cost charging and traceability. Stock deduction updates inventory records in real-time as items are issued.

Cost center allocation ensures that issued items are charged to appropriate budgets. Issue history maintains records of who received items, when, and for what purpose, supporting audit and traceability requirements.

Reorder alerts notify procurement when issued items reduce stock below minimum levels.

This store issue is evidenced in **Annex C2.5, Page 158** with the Store Issue interface showing inventory allocation.

#### Value-Added Services

We provide **Automatic Reorder Suggestions Based on Consumption Patterns**. The system analyzes historical consumption rates, lead times, and safety stock requirements to recommend optimal reorder timing and quantities. This intelligent replenishment prevents stockouts while minimizing inventory carrying costs.

Our **Inventory Optimization** uses machine learning to predict demand patterns and optimize stock levels for each item.

---

### 29. Tender Management

#### Evidence

Streamlined tender management ensures transparency, auditability, and customization for complex procurements. The system enables creation of comprehensive tenders with detailed specifications, evaluation criteria, and terms to ensure accurate vendor responses. Customizable events and forms accommodate different tender types while maintaining transparency and compliance.

Vendor registration and qualification ensure that only qualified vendors can participate in tenders. Bid submission management handles document uploads, pricing submissions, and communications during the tender period.

Evaluation workflows support structured evaluation by multiple evaluators with scoring and consensus building.

This tender management is evidenced in the Annex C2 Tender Module with Tender Creation showing tender processes.

#### Value-Added Services

We provide **Tender Analytics** that track vendor participation rates, bid patterns, and competition levels. The system identifies tenders with limited participation that may benefit from extended timelines or additional vendor outreach.

Our **Automated Tender Evaluation** uses AI to assist evaluators by highlighting anomalies, comparing bids against benchmarks, and identifying best value proposals.

---

### 30. Contract Management

#### Evidence

Vendor contract management maintains records of all agreements with negotiated terms, pricing, and conditions. Compliance monitoring tracks contract adherence including volume commitments, delivery performance, and service level agreements. Rate enforcement ensures that invoicing aligns with contracted rates, preventing overcharges.

Digital storage and organization provide centralized access to all contracts with search and retrieval capabilities. Real-time tracking of utilized and remaining contract value shows spending against commitments and helps identify contracts approaching renewal.

Renewal alerts notify procurement staff when contracts are approaching expiration, enabling timely renewal negotiations.

This contract management is evidenced in the Annex C2 Contract Module with Contract Tracking showing agreement management.

#### Value-Added Services

We provide **Contract Renewal Alerts and Automated Compliance Checking**. The system monitors contract utilization, performance metrics, and expiration dates to alert when contracts require renewal or when vendors are not meeting commitments. Automated compliance checking validates vendor invoices against contracted rates and terms, flagging discrepancies for review.

Our **Contract Performance Analytics** track vendor adherence to service levels, delivery commitments, and quality standards.

---

### 31. Workflow Management

#### Evidence

User-designed configurable workflows enable customization of procurement processes to match MMF's specific requirements. Workflows can be designed for creating requests with specific approval sequences, enforcing policies such as mandatory justifications or preferred vendor requirements, and managing approvals with defined routing rules.

Fully customizable workflows accommodate different procurement types, value thresholds, and organizational structures. Visual workflow designers enable business users to modify processes without IT involvement.

Workflow simulation allows testing of new workflows before deployment to ensure they function as intended.

This workflow management is evidenced in **Annex C2.1, Page 150** with the Workflow Designer showing process configuration.

#### Value-Added Services

We provide **Visual Workflow Designer** with drag-and-drop configuration. Business users can design, modify, and deploy procurement workflows without programming knowledge, using intuitive visual tools to define steps, conditions, and routing rules.

Our **Workflow Optimization Analytics** identify bottlenecks and inefficiencies in procurement processes, suggesting improvements to reduce cycle times.

---

### 32. Budget

#### Evidence

Every expense is tracked, monitored, and approved through integrated budget controls. Budget limits are enforced based on dimensions such as departments, cost centers, and project codes, ensuring that spending stays within authorized amounts. Budget visibility is controlled based on permissions and roles—managers see their department budgets while executives see consolidated views.

Real-time budget checking validates requisitions and purchase orders against available budgets before approval. Budget variance reporting highlights areas where spending is above or below planned amounts.

Budget forecasting projects year-end positions based on committed and projected spending.

This budget management is evidenced in **Annex C2.8, Page 164** with the Budget Dashboard showing budget tracking.

#### Value-Added Services

We provide **Predictive Budget Forecasting** that analyzes historical spending patterns to forecast year-end position. The system identifies trends, seasonal variations, and projected spending to predict whether budgets will be exceeded or underspent. This forecasting capability prevents 95%+ of budget overruns by providing early warning when corrective action is needed.

Our **Budget Scenario Modeling** enables "what-if" analysis to understand the impact of proposed spending on overall budget positions.

---

### 33. Notifications & Alerts

#### Evidence

The notification system supports multiple types including Email for detailed notifications with attachments, in-app notifications for immediate visibility when users are logged in, and optional SMS for urgent alerts requiring immediate attention. Triggers include PR, IWO, EWO, PO submission and approval events, pending approval reminders, RFQ responses due, PO dispatched and acknowledged, and goods receipt pending.

Configurable alert rules enable customization of notification timing, recipients, and channels based on event type and urgency. Recipient groups allow notifications to be sent to teams or departments rather than individuals.

Notification history maintains records of all alerts sent for audit and troubleshooting purposes.

This notification capability is evidenced in **Annex C2, Page 150** with the Notification Settings showing alert configuration.

#### Value-Added Services

We provide **Smart Notification Bundling** to prevent alert fatigue. The system intelligently groups related notifications and delivers them at appropriate intervals rather than sending individual alerts for every event. AI-powered priority scoring ensures that high-priority notifications receive immediate attention while routine updates are batched for periodic review.

Our **Notification Effectiveness Analytics** track open rates, response times, and user feedback to continuously improve notification strategy.

---

### 34. Reporting & Analytics

#### Evidence

Standard reports and enquiries provide comprehensive procurement visibility including Spend analysis showing spending by category, vendor, and time period; Supplier performance tracking delivery, quality, and pricing metrics; PR aging showing how long requisitions have been pending; PO cycle time measuring procurement process efficiency; Invoice aging tracking outstanding vendor invoices; Budget vs Actual Spend showing variance analysis; EWO summary list with filtering for external work order visibility; Vendor performance dashboards with scorecards; Monthly outsourcing cost reports; and Budget utilization per department.

Import and export capabilities in PDF, Excel, or CSV formats support data analysis, distribution, and integration with other systems. Report scheduling automatically delivers reports to stakeholders on defined schedules.

This reporting capability is evidenced in **Annex C2.7, Page 162** with the Report Library showing available procurement reports.

#### Value-Added Services

We provide **Procurement Cockpit** that gives executives real-time visibility into procurement KPIs with natural language query capabilities. Executives can ask questions like "What is our spend with top 10 vendors this quarter?" or "Show me departments exceeding their budgets" and receive instant visual answers. This executive dashboard provides strategic insights without requiring technical report generation skills.

Our **Predictive Procurement Analytics** forecast spending trends, identify cost saving opportunities, and predict vendor performance issues before they occur.

---

*Annexure C2 contains 34 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 900,000.*


## ANNEXURE C3: HUMAN RESOURCE MANAGEMENT SYSTEM (HRMS)

**System:** LogisticsPro HRMS v4.2  
**Location:** ALL Branches (Headquarters, Global Logistics Dept, Port Klang, Pasir Gudang, Butterworth, Padang Besar)  
**Total Requirements:** 22  
**Coverage:** Employee management, payroll, attendance, leave, claims, recruitment, performance, training

The Human Resource Management System (HRMS) provides comprehensive human capital management across all MMF branches, supporting the complete employee lifecycle from recruitment through retirement. The system manages employee information, payroll processing, attendance tracking, leave management, claims processing, performance management, and training administration. HRMS integrates seamlessly with FMS for payroll and claims reimbursement, EMS for driver assignment and equipment operator records, and PS for user authentication and procurement approvals.

---

### 1. Dashboard — HR Analytical

#### Evidence

The HR Command Centre displays all critical human resource information in a single screen, providing executives and HR managers with comprehensive workforce visibility. Actionable insights optimize recruitment processes, performance management, and employee retention strategies. The dashboard presents key metrics including headcount by department and location, attrition rates and trends, recruitment pipeline status, training completion rates, and payroll summaries.

Reports vary by user level and requirement—executives see strategic workforce analytics, HR managers see operational metrics, line managers see team-specific information, and employees see personal data. Role-based access ensures that users see only information appropriate to their responsibilities.

Real-time updates ensure that displayed information reflects current workforce status, new hires, terminations, and status changes.

This dashboard capability is evidenced in **Annex C3.8, Page 189** with the HR Dashboard showing workforce analytics.

#### Value-Added Services

We provide **Predictive Workforce Analytics** for strategic HR planning. The system analyzes historical trends, business growth projections, and turnover patterns to forecast future workforce needs including hiring requirements, skills gaps, and succession planning. This predictive capability enables proactive talent acquisition and development rather than reactive responses to vacancies.

Our **HR Benchmarking** compares MMF's HR metrics against industry standards, identifying areas where the organization leads or lags compared to logistics industry peers.

---

### 2. HRMS Able to Link with Other Business System

#### Evidence

HRMS seamlessly integrates with FMS for payroll processing, ensuring that salary calculations, deductions, and statutory contributions flow automatically to financial records. Claims reimbursement from HRMS flows to FMS for payment processing and cost allocation. This integration eliminates duplicate data entry and ensures consistency between HR and financial records.

EMS integration supports driver assignment by linking qualified drivers to vehicles and tracking equipment operator certifications and qualifications. Equipment operators cannot be assigned to equipment they are not certified to operate, ensuring safety and compliance.

PS integration provides user authentication for procurement approvals, ensuring that only authorized employees can approve requisitions based on their HR-defined authority levels and job roles.

This system integration is evidenced in **Annex F.3, Page 172** with the Integration Spec showing data flows between HRMS and other MMF systems.

#### Value-Added Services

We provide **Single Source of Truth** for employee data across all MMF systems. When employee information is updated in HRMS—such as promotions, department transfers, or certification updates—the changes propagate automatically to all connected systems. This eliminates data inconsistencies and ensures that all systems reflect current, accurate employee information.

Our **Cross-System Analytics** enable reporting that combines HR data with operational and financial metrics, such as labor cost per shipment or productivity by employee tenure.

---

### 3. Interface with 3rd Party System

#### Evidence

HRMS supports integration with external HR platforms for specialized functions such as recruitment or learning management. Banking systems integration enables direct deposit payroll processing with major Malaysian banks. Government portal integrations connect to EPF (Employees Provident Fund), SOCSO (Social Security Organization), and LHDN (Inland Revenue Board) for statutory compliance.

Biometric attendance device integration captures clock-in/clock-out data from fingerprint or facial recognition systems, ensuring accurate attendance records. Integration with insurance providers enables employee benefits administration and claims processing.

Standard data formats and APIs ensure compatibility with commonly used HR systems and government platforms.

This integration capability is evidenced in **Annex F.3, Page 172** with the API Integration showing supported external systems.

#### Value-Added Services

We provide **Pre-Built Connectors for Major Malaysian Statutory Bodies** including EPF, SOCSO, LHDN, and EIS (Employment Insurance System). These connectors automate statutory submissions, generate required reports, and ensure compliance with Malaysian employment regulations. Automatic updates accommodate changes in statutory requirements without requiring system modifications.

Our **Bank Integration** supports payroll direct deposit with all major Malaysian banks, with automatic reconciliation and error handling.

---

### 4. Multi Platform Interface

#### Evidence

HRMS is accessible via web browsers for HR staff and managers, providing full functionality for employee management, reporting, and administration. Mobile apps enable employees to view payslips, apply for leave, and update personal details from anywhere. Managers can approve requests on mobile devices, ensuring that HR processes are not delayed by approver unavailability.

The mobile interface is optimized for quick actions such as leave application, attendance viewing, and approval workflows. Push notifications alert employees and managers to pending actions requiring attention.

Responsive design ensures usability across smartphones, tablets, and desktop computers.

This multi-platform support is evidenced in **Annex C3.9, Page 191** with the Mobile App showing employee self-service capabilities.

#### Value-Added Services

We provide **Employee Self-Service Chatbot** that handles common HR queries via WhatsApp, Teams, or web chat. Employees can ask questions like "How much annual leave do I have left?" or "When is my next payday?" and receive instant answers without contacting HR staff. This chatbot reduces HR administration workload by 60% by handling routine inquiries automatically.

Our **Voice-Enabled HR** allows natural language interactions for hands-free access to HR information and services.

---

### 5. Audit Trail & History

#### Evidence

Complete audit trail captures all HR data changes with user identification, timestamps, and before/after values. Every modification to employee records—including salary changes, department transfers, leave balance adjustments, and personal information updates—is logged with full details of who made the change, when, and what was changed.

Audit trails support compliance with Malaysian employment regulations including the Personal Data Protection Act (PDPA) and labor law requirements. Internal audit capabilities enable HR to review and verify data changes for accuracy and authorization.

Retention management ensures audit records are maintained for required periods with appropriate security controls.

This audit capability is evidenced in **Annex D.2, Page 98** with the Compliance Audit showing HR data change logging.

#### Value-Added Services

We provide **GDPR/PDPA Compliance Module** that manages data retention policies, consent tracking, and data subject access requests. The module ensures that personal data is retained only as long as legally necessary, that employee consent for data processing is properly recorded, and that data subject rights (access, correction, deletion) can be fulfilled efficiently. This module significantly reduces compliance risk and audit findings.

Our **Privacy Impact Assessment** tools help evaluate HR processes for privacy risks and recommend mitigation measures.

---

### 6. User-Friendly Interface

#### Evidence

The modern, intuitive interface requires minimal training, enabling rapid adoption across all employee levels. Employees can access payslips and submit leave requests within minutes of first login, demonstrating the system's ease of use. Contextual help guides users through complex processes such as tax declarations, benefit enrollments, or performance evaluations.

Role-based customization presents appropriate functions for each user type—employees see self-service options, managers see team management tools, and HR sees administrative functions. Consistent navigation and design patterns across modules reduce learning curves.

Accessibility features ensure compliance with standards supporting users with disabilities.

This usability is evidenced in **Annex C3.10, Page 192** with the Voice Interface demonstrating user-friendly design.

#### Value-Added Services

We provide **Voice-Enabled HR** that allows natural language interactions. Employees can speak commands such as "Apply for 2 days annual leave starting tomorrow" or "Show me my payslip for last month" and the system processes the request without requiring menu navigation. This voice interface is particularly valuable for field staff and drivers who need hands-free access.

Our **Personalized User Experience** adapts to individual user preferences and frequently used functions, providing quick access to commonly needed features.

---

### 7. Ability of the System to Support Attachment Documents

#### Evidence

The system supports uploading and managing employee documents including identification documents (IC, passport), educational certificates, professional certifications, employment contracts, and performance evaluation forms. Document version control maintains history of revised documents such as updated contracts or renewed certifications.

Expiry tracking monitors certification validity periods and alerts when renewals are required. Document access controls ensure that sensitive employee documents are only accessible to authorized HR personnel and the employee themselves.

Document search and retrieval enable quick location of specific employee documents when needed for audits, verifications, or reference.

This document management is evidenced in **Annex C3.1, Page 175** with the Document Management interface showing employee document handling.

#### Value-Added Services

We provide **OCR Extraction** for automatic data capture from ID documents. When employees upload identification documents, the system extracts name, ID number, address, and other relevant fields automatically, reducing manual data entry and improving accuracy. This capability accelerates employee onboarding and document processing.

Our **Document Verification** checks uploaded documents for authenticity indicators and flags suspicious submissions for review.

---

### 8. Ability to Provide Comprehensive Security Features

#### Evidence

Role-based access ensures employees see only their own data while managers see team data and HR sees all employee data. This hierarchical access model protects privacy while enabling necessary visibility. Sensitive information such as salary, IC numbers, and performance ratings are encrypted with field-level access controls ensuring that only authorized personnel can view confidential data.

Multi-factor authentication protects HR system access, particularly for functions involving sensitive data or financial transactions. Session management prevents unauthorized access through timeout controls and concurrent session limits.

Audit logging tracks all access to sensitive employee data, supporting compliance and security monitoring.

This security is evidenced in **Annex D, Pages 95-110** with the Security Framework showing access controls and encryption.

#### Value-Added Services

We provide **Privacy-Preserving Analytics** that allows trend analysis without exposing individual data using differential privacy techniques. HR can analyze salary trends, turnover patterns, and performance distributions across the organization while protecting individual employee privacy. This capability enables data-driven decision making while maintaining strict confidentiality.

Our **Data Loss Prevention** monitors and controls the movement of sensitive HR data, preventing unauthorized exports or sharing.

---

### 9. Employee Information Management

#### Evidence

The system stores and manages detailed employee profiles including personal information (name, contact details, emergency contacts), contact information for communications, job details (position, department, grade, reporting structure), and document attachments (contracts, certifications, IDs). Employees can update selected personal information such as address or contact numbers with HR approval, ensuring data accuracy while maintaining control.

Employee status tracking monitors whether employees are active, inactive, terminated, or on leave, supporting workforce planning and reporting. Status history maintains records of promotions, transfers, and other significant career events.

Organization chart views show reporting relationships and departmental structures.

This employee management is evidenced in **Annex C3.1, Page 175** with the Employee Portal showing profile management.

#### Value-Added Services

We provide **Employee Lifecycle Analytics** that track engagement and attrition risk factors using sentiment analysis and behavioral indicators. The system analyzes attendance patterns, performance trends, peer relationships, and survey responses to identify employees at risk of leaving. Early warning alerts enable HR and managers to intervene with retention measures, typically reducing voluntary turnover by 20-25%.

Our **Career Path Planning** tools help employees and managers identify development opportunities and career progression paths within MMF.

---

### 10. Recruitment & Applicant Tracking

#### Evidence

The system accepts job applications through online portals and stores applicant information in a centralized database. HR can track candidates through recruitment stages including Screening (initial qualification review), Interview (scheduling and feedback), Offer (generating and managing employment offers), and Hire (onboarding new employees).

Auto-generation of offer letters streamlines the offer process with templates that can be customized for different positions and levels. Candidate notification via email or portal keeps applicants informed of their application status throughout the process.

Recruitment analytics track time-to-hire, source effectiveness, and candidate quality metrics.

This recruitment capability is evidenced in **Annex C3.7, Page 187** with the ATS Interface showing applicant tracking.

#### Value-Added Services

We provide **AI Resume Screening** that automatically parses and ranks resumes based on job requirements. The system extracts skills, experience, education, and qualifications from submitted resumes, matching them against job specifications to identify the most qualified candidates. This AI screening reduces screening time by 75% and improves quality of hire by 30% by ensuring that recruiters focus on the most promising candidates.

Our **Interview Scheduling Automation** coordinates interviewer availability and candidate preferences to schedule interviews without manual back-and-forth.

---

### 11. Attendance & Time Tracking

#### Evidence

The system records employee attendance through multiple methods including manual entry for exceptions, biometric devices (fingerprint or facial recognition) for accurate clock-in/clock-out, and integrated systems for automated capture. Work schedule management handles shift patterns, rotating schedules, and flexible work arrangements.

Overtime tracking captures hours worked beyond standard schedules with approval workflows for authorization. Remote work logs document work-from-home arrangements and output. Employees can view their attendance records through self-service, promoting transparency and enabling employees to identify and report discrepancies.

Monthly attendance reports summarize presence, absences, late arrivals, and early departures for payroll processing.

This attendance tracking is evidenced in **Annex C3.2, Page 177** with the Attendance Dashboard showing time tracking.

#### Value-Added Services

We provide **AI Absence Prediction** that analyzes attendance patterns to identify potential issues before they escalate. The system detects patterns such as frequent Monday/Friday absences, increasing tardiness, or unusual absence clusters that may indicate engagement problems, health issues, or workplace concerns. Early alerts enable managers to intervene with support or corrective action.

Our **GPS-Enabled Mobile Clocking** with customizable geofencing ensures that remote and field staff can clock in only from authorized locations.

---

### 12. Leave System

#### Evidence

The leave system captures information on all leave types including Annual Leave, Medical Leave (with MC upload capability), Emergency Leave, Unpaid Leave, and other organization-specific leave types. Employees submit leave applications through the app or web interface, specifying leave type, dates, and reason where required.

Approval workflows route leave requests to appropriate approvers based on employee department and reporting structure. Track leave functionality shows leave balances, upcoming approved leave, and history of past leave taken. Integrated calendar displays team leave schedules, helping managers plan workload coverage.

Notifications alert employees when leave is approved or rejected, and remind managers of pending leave approvals.

This leave management is evidenced in **Annex C3.2, Page 177** with the Leave Application showing leave request and tracking.

#### Value-Added Services

We provide **Smart Leave Balance Forecasting** that projects future leave balances based on accrual rates and planned leave. The system also manages blackout dates—periods when leave cannot be taken due to operational requirements—with automatic enforcement and approval escalation for critical requests.

Our **Leave Optimization** analyzes leave patterns to identify employees who may need to take leave before year-end balance expiration or those with excessive leave accumulation.

---

### 13. Staff Claims

#### Evidence

The claims system defines all claim types and enforces business rules regarding eligibility, quantum, and ceilings. Different claim categories (medical, mileage, outstation, entertainment) have specific rules about who can claim, maximum amounts, and required documentation. Automated mileage calculation determines reimbursement based on distance traveled and approved rates.

Medical claim processing handles healthcare expense reimbursement with receipt attachment requirements. Other claim types include outstation allowances, meal claims, and entertainment expenses with appropriate approval workflows.

Claim status tracking shows submitted, pending, approved, and paid status, providing visibility to employees and managers.

This claims processing is evidenced in **Annex C3.4, Page 181** with the Claims Portal showing expense submission.

#### Value-Added Services

We provide **Receipt Intelligence** that automatically reads and validates receipts using OCR technology. The system extracts merchant name, date, amount, and GST information from uploaded receipts, flagging duplicates, out-of-policy claims, and suspicious submissions. This intelligent processing reduces claim processing time by 70% and improves policy compliance.

Our **Claims Fraud Detection** analyzes claim patterns to identify potential fraud such as duplicate submissions, excessive claims, or unusual spending patterns.

---

### 14. Insurance (Link/Integrate with Others System Which Related with Insurance. Eg: EMS)

#### Evidence

The system caters to all types of insurance for the company including Employee Medical Insurance covering healthcare benefits, Group Personal Accident insurance for work-related accidents, and Equipment Insurance linked with EMS for asset protection. Insurance policy management tracks coverage details, beneficiaries, premiums, and renewal dates.

Employee self-service allows employees to view their insurance coverage, submit claims, and track claim status. Integration with EMS links equipment insurance to asset records, ensuring that all equipment is properly insured and that claims can be processed efficiently when incidents occur.

Insurance reporting tracks premiums, claims, and coverage utilization.

This insurance management is evidenced in the Annex C3 Insurance Module with Coverage Tracking showing insurance records.

#### Value-Added Services

We provide **Insurance Coverage Analytics** that analyze utilization patterns, claim trends, and coverage gaps. The system identifies employees who may be under-insured, coverage areas with high claim rates, and opportunities for premium optimization through coverage adjustments.

Our **Claims Optimization** tracks insurance claim outcomes and identifies opportunities to improve claim success rates and settlement times.

---

### 15. Performance Management System

#### Evidence

The system customizes appraisal forms and achievement certificate designs to match MMF's evaluation criteria and branding. Weightage and scoring can be configured based on different criteria and job roles, ensuring that evaluations reflect the specific requirements of each position. Goal tracking monitors individual and team objectives throughout the evaluation period.

Review workflows manage the performance evaluation process from self-assessment through manager review and final approval. Report generation produces performance summaries, comparative analytics, and development recommendations.

Performance history maintains records of past evaluations for trend analysis and succession planning.

This performance management is evidenced in **Annex C3.5, Page 183** with the Performance Dashboard showing evaluation processes.

#### Value-Added Services

We provide **Continuous Performance Management** that replaces traditional annual reviews with ongoing feedback and check-ins. Managers and employees can record achievements, provide feedback, and adjust goals throughout the year rather than waiting for annual evaluations. AI analyzes performance data to identify high-potential employees and those who may need additional support or development.

Our **360-Degree Feedback Integration** enables multi-source performance input from peers, subordinates, and customers.

---

### 16. Training Management

#### Evidence

The system produces individual training plans based on performance management outcomes, identifying skills gaps and development needs for each employee. Training course booking manages enrollment in internal and external training programs with calendar integration and availability checking. Learning options management tracks various training types including classroom, online, and on-the-job training.

Follow-on evaluation and feedback processes assess training effectiveness and capture participant feedback. Training expenditure tracking monitors spending against budget allocations by department, category, and individual.

Training records maintain history of completed training, certifications earned, and skills acquired.

This training management is evidenced in **Annex C3.6, Page 185** with the Training Portal showing learning management.

#### Value-Added Services

We provide **AI Learning Recommendations** that analyze job roles, performance gaps, and career aspirations to suggest personalized learning paths for each employee. The system recommends specific courses, certifications, and development activities that will enhance employee capabilities and career progression. This personalization increases training completion rates from typical 40% to 75% by ensuring that training is relevant and aligned with employee needs.

Our **Skills Gap Analysis** identifies organizational skills shortages and recommends training programs to address critical gaps.

---

### 17. Discipline Management

#### Evidence

The system records all disciplinary actions for various reasons including misconduct, performance issues, attendance violations, and safety breaches. Behavioral pattern tracking over time identifies employees with repeated disciplinary issues who may require additional intervention or counseling. Documentation supports legal compliance by maintaining complete records of incidents, investigations, actions taken, and outcomes.

Evidence management stores supporting documents such as incident reports, witness statements, and investigation findings. Appeal tracking manages the process when employees contest disciplinary actions.

Disciplinary reports identify patterns across departments, types of violations, and outcomes.

This discipline management is evidenced in the Annex C3 Discipline Module with Case Management showing disciplinary records.

#### Value-Added Services

We provide **Pattern Analysis** that identifies early warning signs for intervention before issues escalate. The system detects patterns such as declining attendance, performance deterioration, or behavioral changes that may precede disciplinary issues. Early alerts enable managers to provide coaching, support, or corrective action before formal disciplinary processes become necessary.

Our **Discipline Outcome Analytics** track the effectiveness of different interventions, helping HR identify which approaches are most successful for rehabilitation.

---

### 18. Payroll Management

#### Evidence

The system processes salaries with automatic calculations including base pay, allowances, overtime, and deductions. Predefined rules ensure consistent application of payroll policies across all employees. Online payments through integration with major Malaysian banks enable efficient salary disbursement.

Statutory compliance includes automatic calculation and reporting for EPF (Employees Provident Fund), SOCSO (Social Security Organization), EIS (Employment Insurance System), and LHDN (Inland Revenue Board). Integration with employees' leave and claims ensures that salary calculations reflect approved leave and reimbursable expenses.

Automated Driver Incentive calculations from EMS data ensure that driver performance bonuses are accurately computed and paid.

This payroll management is evidenced in **Annex C3.3, Page 179** with the Payroll Module showing salary processing.

#### Value-Added Services

We provide **Intelligent Payroll Validation** that uses AI to detect anomalies before processing. The system flags unusual salary amounts, unexpected deductions, missing payments, or discrepancies that may indicate errors or fraud. Tax optimization throughout the year analyzes employee situations and recommends actions to maximize take-home pay within legal limits.

Our **Payslip Chatbot** allows employees to query payslip details through natural language, reducing HR inquiries.

---

### 19. Inventory (Link/Integrate with Purchasing System)

#### Evidence

The system manages information on stationery inventory and other HR-related supplies. Stock level tracking shows current quantities on hand, consumption rates, and reorder points. Issue tracking records distribution to departments and employees with cost center allocation.

Reorder management triggers procurement requests when stock falls below minimum levels. Links to PS (Procurement System) ensure that replenishment follows proper procurement processes with appropriate approvals.

Inventory valuation tracks the value of HR supplies on hand for financial reporting.

This inventory management is evidenced in the Annex C3 Inventory Module with Stock Tracking showing supply management.

#### Value-Added Services

We provide **Automatic Reorder Suggestions Based on Consumption Patterns**. The system analyzes historical consumption, seasonal variations, and departmental needs to recommend optimal reorder timing and quantities. This ensures that supplies are always available while minimizing carrying costs.

Our **Departmental Allocation Analytics** track consumption by department, identifying unusual patterns or opportunities for consolidation.

---

### 20. Workflow & Notifications

#### Evidence

The system sends automated notifications for approvals including leave requests, expense claims, performance evaluations, and other HR processes. Configurable workflow rules enable customization of approval chains based on request type, amount, employee level, and department.

Notification types include email for detailed communications, in-app alerts for immediate visibility, and SMS for urgent matters. Escalation rules ensure that requests are not stalled when approvers are unavailable.

Workflow history maintains records of all routing decisions and approval actions for audit purposes.

This workflow is evidenced in **Annex C3.2, Page 177** with the Workflow Engine showing process automation.

#### Value-Added Services

We provide **Smart Routing and Escalation** based on approver availability and urgency. The system checks approver calendars, out-of-office status, and workload to route requests to available approvers. Urgent requests are escalated more quickly, and automatic delegation ensures that approvals are not delayed when primary approvers are unavailable.

Our **Workflow Analytics** identify bottlenecks in approval processes and recommend optimizations to reduce cycle times.

---

### 21. Reporting & Enquiries

#### Evidence

The system generates standard HR reports and enquiries including Headcount by department, location, and employment type; Attrition analysis showing turnover rates and trends; Payroll summary for financial reporting; and Attendance trends identifying patterns and issues. Reports can be imported and exported in PDF, Excel, or CSV formats for further analysis and distribution.

Ad-hoc query capabilities enable HR to create custom reports without IT assistance. Report scheduling automatically delivers recurring reports to stakeholders.

Drill-down capabilities allow navigation from summary reports to individual employee records for investigation.

This reporting is evidenced in **Annex C3.8, Page 189** with the Report Library showing HR analytics.

#### Value-Added Services

We provide **Natural Language Queries** that enable instant answers to complex HR questions. Users can ask "What is the turnover rate for drivers in Port Klang?" or "Show me employees with medical leave exceeding 10 days this year" and receive immediate results without building reports or queries. This conversational interface makes HR data accessible to all managers.

Our **Predictive HR Analytics** forecast future trends such as likely resignations, hiring needs, and training requirements.

---

### 22. Self-Service Portal

#### Evidence

Employees can view payslips showing detailed salary breakdowns, deductions, and year-to-date totals. Attendance records display clock-in/clock-out times, leave taken, and attendance statistics. Leave balance shows available annual leave, medical leave, and other entitlements.

Profile management allows employees to update certain personal information such as address, contact numbers, and emergency contacts. HR request submission enables employees to request letters, submit claims, and request documents through the portal. Permission to travel can be submitted for work-related travel authorization.

Mobile accessibility ensures that employees can access self-service functions from anywhere.

This self-service is evidenced in **Annex C3.1, Page 175** with the Self-Service Portal showing employee access.

#### Value-Added Services

We provide **24/7 Employee Support via AI-Powered Chatbot** integrated with WhatsApp and Teams. Employees can get answers to common questions, submit requests, and check status at any time without waiting for HR office hours. The chatbot handles routine inquiries, freeing HR staff to focus on complex issues requiring human expertise.

Our **Personalized Dashboard** shows each employee relevant information including upcoming training, pending approvals, and company announcements tailored to their role and location.

---

*Annexure C3 contains 22 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 700,000.*

---

## Document Control

| | |
|---|---|
| Document Version | 1.0 |
| Date | 4 February 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |
| Total Features Documented | 82 |
| Total Word Count | ~18,000+ words |

---

## Summary of Value-Added Services

| Annexure | System | Features | Estimated VAS Value (RM) |
|----------|--------|----------|--------------------------|
| C1 | EMS | 26 | 800,000 |
| C2 | PS | 34 | 900,000 |
| C3 | HRMS | 22 | 700,000 |
| **TOTAL** | | **82** | **2,400,000** |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement. All information is provided in strict confidence and is subject to the terms of the tender documentation.*

