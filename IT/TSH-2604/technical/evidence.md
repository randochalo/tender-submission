# Technical Evidence Documentation
## TSH-2604: Evidence & Value-Added Services Detail

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**System:** Business Operating & Finance IT System  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 4 February 2026

---

## Table of Contents

1. [Annexure C1: Haulage Management System (HMS)](#annexure-c1-haulage-management-system-hms)
2. [Annexure C2: Forwarding Management System (FFS)](#annexure-c2-forwarding-management-system-ffs)
3. [Annexure C3: Warehouse Management System (WMS)](#annexure-c3-warehouse-management-system-wms)
4. [Annexure C4: Terminal Management System (TMS)](#annexure-c4-terminal-management-system-tms)
5. [Annexure C5: Finance Management System (FMS)](#annexure-c5-finance-management-system-fms)

---

## ANNEXURE C1: HAULAGE MANAGEMENT SYSTEM (HMS)

**Location:** Port Klang (PK), Headquarters (HQ)  
**System Version:** LogisticsPro HMS v4.2  
**Deployment Model:** Cloud-native with offline mobile capability  
**Coverage:** Fleet operations, driver management, route optimization, and haulage billing

The Haulage Management System (HMS) represents a comprehensive solution designed specifically for the demanding requirements of modern logistics operations. Deployed across MMF's critical Port Klang operations and Headquarters, this system provides end-to-end visibility and control over fleet movements, driver performance, and customer deliveries. The cloud-native architecture ensures scalability during peak periods while the offline mobile capability guarantees uninterrupted operations even in areas with limited connectivity—a critical requirement for port and industrial zone operations.

---

### 1. Dashboards & Analytics

#### Evidence

Our HMS includes a sophisticated real-time Operations Command Centre that serves as the nerve center for MMF's haulage operations. This dashboard provides customizable KPI widgets that display critical operational metrics including fleet utilization percentages, on-time delivery rates, driver performance scores, fuel consumption trends, and maintenance scheduling alerts. The analytics engine employs advanced predictive algorithms that continuously analyze historical data patterns to forecast maintenance needs, identify optimal route configurations, and predict potential service disruptions before they occur.

The dashboard architecture supports role-based views, ensuring that operations managers see real-time fleet movements while executives focus on strategic KPIs such as revenue per kilometer, cost per trip, and customer satisfaction metrics. The system maintains data refresh rates of under 30 seconds, providing near real-time visibility into operations. Users can drill down from summary views to individual vehicle or driver details with a single click.

The predictive analytics module processes telematics data including engine diagnostics, mileage, driving patterns, and historical maintenance records to generate predictive maintenance alerts. This capability enables MMF to transition from reactive maintenance schedules to proactive interventions, significantly reducing unexpected breakdowns and associated service disruptions.

This comprehensive dashboard and analytics capability is fully documented in **Annex E.1, Pages 120-125**, which includes detailed screenshots of the Operations Command Centre interface, sample KPI configurations, and technical specifications of the analytics engine. Additionally, a Live Demo Video accessible via QR Code provides a walkthrough of the dashboard functionality and demonstrates the drill-down capabilities from executive summaries to operational details.

#### Value-Added Services

Beyond the standard dashboard capabilities, Sinergi Elit provides an **AI-Powered Natural Language Query Interface** that transforms how MMF management interacts with operational data. This innovative feature allows executives and managers to ask questions in plain English such as "Show me underperforming routes this month," "Compare fuel efficiency across branches," "Which drivers have the highest safety scores," or "What is the utilization trend for our prime movers" and receive instant visual answers in the form of charts, graphs, and data tables. This natural language interface eliminates the need for technical query skills or report generation requests, democratizing data access across the organization.

Additionally, our **Predictive Maintenance AI** represents a significant advancement over traditional maintenance scheduling. This system analyzes comprehensive telematics data including engine temperature patterns, vibration signatures, oil pressure trends, brake wear indicators, and historical failure data to predict potential breakdowns 7-14 days in advance with demonstrated 89% accuracy. The system generates work orders automatically, schedules maintenance during optimal windows, and orders required parts in advance. This proactive approach typically reduces unexpected downtime by up to 40%, extends vehicle lifespan through optimal maintenance timing, and prevents costly roadside breakdowns that disrupt customer service.

We also include **Executive Alert Intelligence** that learns from management response patterns to prioritize and filter alerts, ensuring that critical issues receive immediate attention while routine notifications are batched for review. This reduces alert fatigue and ensures that decision-makers focus on truly significant operational events.

---

### 2. Multi-Platform Interface

#### Evidence

The HMS architecture follows modern responsive design principles ensuring seamless functionality across the full spectrum of devices used in MMF's operations. The desktop application supports Windows and macOS operating systems, providing full functionality for office-based staff including planners, dispatchers, and management. The web browser interface is compatible with all modern browsers including Chrome, Edge, Safari, and Firefox, requiring no software installation and enabling access from any authorized computer.

For field operations, native mobile applications are available for both iOS and Android platforms, supporting smartphones and tablets used by drivers, supervisors, and mobile staff. All platforms share a unified codebase that ensures consistent functionality, user experience, and data integrity. Real-time synchronization is achieved through WebSocket connections that maintain persistent communication between devices and the central server, ensuring that all users see current information regardless of their access point.

The responsive design automatically adapts interface elements to screen size and input method, optimizing layouts for desktop monitors, laptop screens, tablets, and smartphones. Touch-optimized controls accommodate field use, while keyboard shortcuts and mouse interactions enhance productivity for office users. The system maintains session persistence across devices, allowing users to start tasks on one device and continue on another without data loss.

This comprehensive multi-platform support is documented in **Annex E.2, Page 126** with platform compatibility matrices, responsive design specifications, and synchronization architecture diagrams. The System Architecture Diagram illustrates the unified codebase approach and WebSocket communication protocols.

#### Value-Added Services

Beyond standard multi-platform support, we provide **Offline-First Architecture** specifically designed for the challenging connectivity environments encountered in Port Klang and remote branch operations. This advanced capability allows drivers and field staff to access job details, update delivery statuses, capture proof of delivery, and record operational events even when completely disconnected from the internet. All data is stored locally on the device and automatically synchronizes with the central system when connectivity returns.

The synchronization process includes intelligent conflict resolution algorithms that handle scenarios where the same record has been modified both offline and online by different users. The system maintains data integrity through timestamp-based reconciliation, user preference rules, and supervisor escalation for complex conflicts. This ensures that no operational data is lost due to connectivity issues, a critical requirement for port operations where cellular coverage can be inconsistent.

Our **Progressive Web App (PWA)** capability enables the system to be installed on any device without requiring app store approval processes, eliminating deployment delays. The PWA provides native-app-like functionality including push notifications for critical alerts such as vehicle breakdowns, urgent customer requests, system notifications, and emergency situations. These notifications ensure that appropriate personnel are alerted immediately, even when they are not actively using the application, enabling rapid response to operational events.

We also include **Cross-Device Workflow Continuity** that allows users to seamlessly transition between devices during their workday. For example, a dispatcher can begin reviewing routes on their desktop, continue monitoring on a tablet while walking the operations floor, and receive critical alerts on their smartphone after hours—all with synchronized data and consistent interface design.

---

### 3. Interface with 3rd Party System

#### Evidence

The HMS Integration Layer provides comprehensive connectivity capabilities supporting multiple protocols and standards commonly used in logistics ecosystems. The system natively supports RESTful APIs for modern web-based integrations, SOAP web services for legacy enterprise systems, SFTP for secure file transfers, and EDI (Electronic Data Interchange) for standardized business document exchange. This multi-protocol support enables connectivity with Port Klang Authority systems for port pass and container availability data, JPJ (Road Transport Department) for vehicle and driver compliance verification, Customs (MyGBS) for cargo clearance status, and customer ERP systems for seamless order integration.

Pre-built connectors are available for major enterprise systems including SAP (all major versions), Oracle E-Business Suite, Oracle NetSuite, Microsoft Dynamics 365, and Salesforce. For customers with custom or proprietary systems, the integration layer provides configurable adapters that can be rapidly deployed to support unique data formats and communication protocols. The connector framework includes data transformation capabilities that automatically convert between different data formats, field mappings, and business rules.

All integrations are monitored through a centralized dashboard that displays connection status, transaction volumes, error rates, and data flow metrics. The system includes automatic retry mechanisms for failed transactions, configurable escalation procedures for persistent issues, and comprehensive logging for audit and troubleshooting purposes.

This integration capability is fully documented in **Annex F, Pages 165-180**, which includes technical integration specifications, supported protocol details, connector documentation, and sample integration scenarios. The API Documentation provides complete endpoint specifications, authentication methods, request/response formats, and error handling procedures.

#### Value-Added Services

We provide a **Universal Integration Platform** that extends beyond the standard integration capabilities to include 150+ pre-built connectors for common logistics, supply chain, and business systems. This platform includes real-time webhook support that enables instant data synchronization without polling, reducing system load and improving data freshness. The webhook infrastructure supports event-driven architectures where downstream systems are immediately notified of relevant events such as job completion, status updates, or exception conditions.

Our **Integration Monitoring Dashboard** provides comprehensive visibility into all data flows across the organization. This dashboard displays real-time transaction volumes, latency metrics, error rates, and system health indicators for every integration point. The monitoring system includes automatic retry mechanisms with configurable backoff strategies, intelligent error alerting that categorizes issues by severity and business impact, and self-healing capabilities that can automatically resolve common integration problems without human intervention.

We also include an **Integration Development Kit (IDK)** that empowers MMF's internal IT team to build custom connectors and integrations without vendor dependency. The IDK includes a comprehensive development environment, sandbox testing facilities, sample code libraries, debugging tools, and deployment automation. This capability ensures that MMF can rapidly adapt to new integration requirements as the business evolves, add connections to new partners or systems, and maintain control over their integration architecture.

---

### 4. HMS Able to Link with Other Business/Support System

#### Evidence

Native integration with the Finance Management System (FMS), Warehouse Management System (WMS), and Terminal Management System (TMS) modules is achieved through an Enterprise Service Bus (ESB) architecture that enables real-time data exchange between systems. The ESB acts as a central communication hub, routing messages between systems, transforming data formats as needed, and ensuring reliable delivery even during temporary system unavailability.

Key integration workflows include automatic billing generation in FMS when job completion is recorded in HMS, ensuring that revenue is captured promptly and accurately without manual data entry. Inventory updates in WMS are triggered when containers are picked up or delivered, maintaining accurate stock visibility across the enterprise. Container status updates from HMS propagate to TMS for terminal operations coordination, ensuring consistent information across all business units.

The integration architecture supports both synchronous real-time updates for time-sensitive operations and asynchronous batch processing for high-volume transactions. Message queuing ensures that no data is lost during temporary system outages, and transactions are automatically processed when systems recover. The integration layer includes comprehensive logging and monitoring capabilities that track all data flows, identify bottlenecks, and alert administrators to integration issues.

This cross-system integration is documented in **Annex F.3, Page 172** with detailed Integration Flow Diagrams illustrating the data flows between HMS, FMS, WMS, and TMS. The diagrams show message types, frequency, data elements exchanged, and error handling procedures.

#### Value-Added Services

We provide a **Unified Data Lake** that consolidates data from all business systems into a single analytics platform. This unified repository enables cross-functional reporting and insights that span haulage, warehousing, forwarding, and finance operations. Business analysts can create reports that combine metrics from multiple systems without complex join operations or data export/import processes. The data lake supports advanced analytics including trend analysis, correlation studies, and predictive modeling across the entire enterprise.

Our **Event-Driven Architecture** ensures near-instantaneous data synchronization across systems with event replay capabilities for troubleshooting and audit purposes. Every significant business event is recorded in an immutable event log that maintains complete history of all system interactions. This event sourcing approach enables reconstruction of system state at any point in time, supports detailed audit requirements, and facilitates debugging of complex integration scenarios.

Additionally, we include **Cross-System Workflow Automation** that orchestrates business processes spanning multiple systems. For example, a customer delivery request can automatically trigger inventory reservation in WMS, job creation in HMS, billing setup in FMS, and customer notification through the portal—all coordinated through the workflow engine without manual intervention.

---

### 5. User-Friendly Interface

#### Evidence

The HMS user interface is designed following Nielsen's 10 usability heuristics, ensuring that the system is intuitive, efficient, and satisfying to use. The interface implements role-based navigation menus that present only the functions relevant to each user's job responsibilities, reducing cognitive load and training requirements. Contextual help tooltips provide guidance specific to the current field or function, and a consistent design language across all modules ensures that users can transfer learning between different parts of the system.

The user experience has been validated through extensive user acceptance testing with over 50 logistics operators in environments similar to MMF's operations. Testing participants represented various roles including dispatchers, planners, supervisors, and drivers. The testing achieved a satisfaction rating of 4.7 out of 5.0, with particular praise for the system's intuitive navigation, clear visual design, and efficient task completion flows. Minimal training was required, with most users becoming productive within their first day of system use.

The interface includes accessibility features ensuring compliance with WCAG 2.1 standards, supporting users with visual, motor, or cognitive impairments. Keyboard navigation is fully supported for users who cannot use pointing devices, and screen reader compatibility ensures that visually impaired users can access all system functions.

This usability evidence is documented in **Annex E.3, Page 127** with the UX Research Report detailing testing methodology, participant demographics, task completion rates, error rates, and satisfaction scores. Screenshots of key interfaces illustrate the design principles in practice.

#### Value-Added Services

We provide **Personalized User Workspaces** that adapt to individual user preferences and work patterns. The system learns from each user's behavior to automatically surface frequently-used functions, hide rarely-used features, and suggest shortcuts for common task sequences. Users can customize their dashboard layouts, save favorite reports, define personal alert preferences, and configure quick-action menus. This personalization significantly improves productivity by reducing the time required to access commonly-used functions.

Our **Contextual AI Assistant** provides in-app guidance and suggestions based on the user's current task and role. For new users, the assistant offers step-by-step guidance through complex procedures, explaining field meanings and validation requirements. For experienced users, the assistant suggests process improvements, highlights potential issues before they occur, and provides relevant reference information without requiring manual searches. The AI learns from organization-wide usage patterns to suggest best practices and optimizations.

We also include **Adaptive Training Modules** that provide targeted training content based on user role, experience level, and identified skill gaps. Rather than requiring all users to complete generic training, the system assesses individual competencies and delivers focused micro-learning content that addresses specific needs.

---

### 6. Automated Invoice & Receipts Generation

#### Evidence

The HMS Billing Engine is designed to handle the complex rating scenarios typical of haulage operations. The system supports multi-tier pricing structures where rates vary based on distance bands, container types, cargo categories, and customer classifications. Zone-based tariffs accommodate geographic pricing variations, while conditional surcharges automatically apply for after-hours service, hazardous cargo, detention, or other special circumstances.

Automated invoice generation can be triggered through scheduled batch processing (typically overnight for daily billing cycles) or real-time triggers for immediate invoicing requirements. The system maintains complete invoice history with full audit trails, supports multiple invoice formats and templates, and handles multi-currency billing for international customers.

Full IRBM e-Invoicing compliance is implemented through direct API integration with the MyInvois platform. The system automatically validates invoice content against IRBM requirements, submits invoices for validation, receives validation responses, and handles rejection corrections. Validated invoices are stored with their unique IRBM identifiers for compliance verification.

This billing capability is documented in **Annex E.4, Pages 128-130** with sample e-invoices showing compliant formatting, validation receipts from MyInvois, and detailed billing engine configuration options.

#### Value-Added Services

Beyond basic e-invoicing compliance, we provide **Dynamic Pricing Intelligence** that analyzes historical data, current fuel costs, route complexity factors, market conditions, and competitive pricing to recommend optimal pricing for new routes and customers. The system identifies underperforming routes where pricing may be too low, highlights opportunities for margin improvement, and suggests rate adjustments based on demand patterns. This intelligence typically improves average margins by 3-5% through optimized pricing.

Our **Revenue Leakage Detection AI** automatically identifies unbilled services, rate deviations from contracted rates, missed surcharges, and billing delays. The system compares actual operations against billing records, flags discrepancies for review, and can automatically generate corrective invoices where appropriate. This capability typically recovers 3-5% of revenue that would otherwise be lost through billing errors or omissions within the first 6 months of operation.

Additionally, we include **Smart Contract Automation** for recurring customers with self-executing billing based on predefined triggers. Once configured, the system automatically generates invoices for regular routes, subscription services, or contracted minimum volumes without requiring manual job creation or billing initiation. This reduces administrative overhead and ensures consistent billing for established customer relationships.

---

### 7. Credit & Collections Management

#### Evidence

The Credit Control Module provides comprehensive credit management capabilities essential for maintaining healthy cash flow in haulage operations. The system enforces customizable credit limits at multiple hierarchical levels including individual customer, customer group, and corporate parent levels. Automated credit checks are performed during job creation, displaying credit status warnings and preventing new job confirmation for customers exceeding their limits.

Collection worklists are automatically generated based on configurable aging buckets (typically current, 30 days, 60 days, 90 days, and 120+ days). The system prioritizes collection activities based on amount outstanding, days past due, customer history, and payment promise status. Configurable dunning letter templates support automatic correspondence generation, and promise-to-pay tracking maintains records of customer commitments and follow-up schedules.

The module integrates with FMS to provide comprehensive customer account views showing outstanding balances across all business units, payment history, credit utilization, and collection activity. This consolidated view enables informed credit decisions and coordinated collection efforts.

This credit management functionality is evidenced in **Annex E.5, Page 131** with the Credit Workflow Diagram illustrating the complete credit control process from initial customer setup through ongoing monitoring and collection activities.

#### Value-Added Services

We provide **Predictive Credit Risk Scoring** that analyzes customer payment patterns, industry trends, economic indicators, and external credit data to proactively identify at-risk accounts before they become delinquent. The system calculates risk scores for each customer, flags accounts showing deterioration patterns, and recommends specific actions such as credit limit reductions, additional guarantees, or increased monitoring. This proactive approach typically reduces bad debt write-offs by 15-25%.

Our **Automated Collection Campaigns** use AI-optimized communication timing and channel selection to maximize collection effectiveness. The system determines the optimal time of day, day of week, and communication channel (email, SMS, phone call) for each customer based on their historical response patterns. Personalized messaging improves response rates while maintaining positive customer relationships.

We also include **Cash Flow Forecasting Integration** that incorporates collection probability and timing predictions into cash flow projections. This enables more accurate working capital planning and early identification of potential cash shortfalls.

---

### 8. Automated Locking for Overdue Customer

#### Evidence

The automated credit hold system continuously monitors customer accounts and automatically places credit-hold status on customers who exceed their defined credit limits or payment terms. When a credit hold is activated, the system blocks new job creation for the affected customer while preserving existing operations and shipments already in progress. This graduated approach protects MMF from additional credit exposure without disrupting service for ongoing deliveries.

Override capability is available for exceptional circumstances, requiring dual-authorization from both the Finance Manager and General Manager. The system enforces this workflow, routing override requests to the appropriate approvers and maintaining complete audit trails of all override decisions including justification, approver identities, timestamps, and resulting actions.

Credit hold status is visible throughout the system, appearing as warnings during job creation, on customer inquiry screens, and in management dashboards. This visibility ensures that all relevant staff are aware of credit restrictions and can respond appropriately to customer inquiries.

This automated locking mechanism is evidenced in **Annex E.6, Page 132** with the Credit Control SOP documenting the complete process, authorization matrix, and exception handling procedures.

#### Value-Added Services

We provide **Graduated Credit Enforcement** that implements tiered restrictions based on severity and customer history. For minor overages or customers with strong payment histories, the system may allow partial service continuation with reduced credit limits rather than complete blocking. For serious delinquencies or repeated violations, stricter controls are automatically applied. This nuanced approach balances risk management with customer relationship preservation.

Our **Credit Intervention Recommendations** suggest optimal payment plan structures, negotiation strategies, and alternative arrangements based on customer history and risk profile. The system can automatically generate proposed payment schedules, calculate settlement amounts, and track compliance with agreed arrangements.

We also include **Customer Communication Automation** that proactively notifies customers approaching credit limits or payment due dates, providing early warnings and payment options before restrictions are applied. This transparency often prevents credit holds and maintains positive customer relationships.

---

### 9. Audit Trail & History

#### Evidence

The audit trail system captures comprehensive information about all data modifications within HMS. Each audit record includes the before and after values for changed fields, the identity of the user making the change, precise timestamp, IP address of the originating device, and the specific transaction or action that triggered the modification. This information is stored in tamper-resistant database tables with restricted access controls.

The Audit Inquiry screen provides flexible search and filtering capabilities, allowing users to review history by date range, user, transaction type, or affected record. Full history is viewable for any record in the system, showing the complete lifecycle from creation through all modifications. Export capabilities support compliance reporting and forensic analysis requirements, with data available in multiple formats including PDF, Excel, and CSV.

Audit logs are maintained for the required retention period (configurable, default 7 years) with automated archival processes ensuring system performance is not impacted by large audit volumes. The audit infrastructure is designed to support internal audits, external regulatory audits, and potential legal proceedings.

This audit capability is evidenced in **Annex D.2, Page 98** with an Audit Trail Sample showing the level of detail captured for a representative transaction.

#### Value-Added Services

We provide **Blockchain-Based Audit Immutability** that creates cryptographically-verifiable records of critical business events. Using distributed ledger technology, the system creates tamper-proof records that cannot be altered, deleted, or backdated even by database administrators with full system access. This provides the highest level of audit integrity, ensuring that audit trails can be trusted for regulatory compliance, dispute resolution, and legal proceedings.

Our **AI-Powered Anomaly Detection** continuously analyzes audit trails to identify suspicious patterns and potential fraud indicators. The system flags unusual activities such as transactions outside normal business hours, modifications to sensitive fields by unexpected users, unusual sequence patterns, or transactions that deviate from established norms. Automatic alerts notify management of potential issues requiring investigation.

We also include **Audit Analytics Dashboard** that provides visual summaries of system activity, user behavior patterns, and data modification trends. This dashboard helps auditors and management quickly identify areas requiring attention and supports continuous monitoring of internal controls.

---

### 10. Ability of the System to Support Attachment Documents

#### Evidence

The Document Management System integrated with HMS supports unlimited file attachments with a generous size limit of 50MB per file. Supported formats include standard business document types such as PDF, Microsoft Word (DOC/DOCX), Excel (XLS/XLSX), image formats (JPG, PNG, TIFF), and video files for incident documentation. This flexibility accommodates the diverse documentation requirements of haulage operations.

Documents are encrypted at rest using AES-256 encryption, ensuring that sensitive information remains protected even if storage media is compromised. Access controls are tied to user roles and job permissions, ensuring that users can only view documents related to operations they are authorized to access. Document versioning maintains history of changes, and the system tracks who uploaded, viewed, or downloaded each document.

Optical Character Recognition (OCR) indexing is applied to uploaded documents, enabling full-text search across document contents. Users can search for specific text strings within attached documents, significantly improving retrieval speed for large document repositories.

This document management capability is evidenced in **Annex E.7, Page 133** with Document Management UI screenshots showing the attachment interface, security settings, and search functionality.

#### Value-Added Services

We provide **Intelligent Document Classification** using machine learning to automatically categorize and tag uploaded documents based on content analysis. The system recognizes document types (delivery orders, permits, inspection reports, photos) and automatically applies appropriate metadata, filing them in the correct folders without manual intervention. This eliminates manual filing efforts and ensures consistent document organization.

Our **Document Version Intelligence** tracks document relationships and automatically surfaces the most recent version while maintaining complete version history for audit purposes. When multiple versions of the same document exist, the system clearly indicates which is current and provides easy access to historical versions. Change tracking highlights differences between versions.

We also include **Automated Document Retention** that manages document lifecycle according to regulatory requirements and internal policies. The system automatically archives documents after defined periods, flags documents approaching retention limits, and manages secure destruction of expired documents with appropriate audit trails.

---

### 11. Comprehensive Security Features

#### Evidence

The HMS security framework implements multiple layers of protection to safeguard sensitive operational and financial data. Multi-factor authentication (MFA) is supported through both TOTP (Time-based One-Time Password) applications and SMS delivery, providing flexibility while ensuring strong authentication. Role-Based Access Control (RBAC) implements 50+ granular permissions that can be combined to define precise access rights for each user role.

Password policy enforcement follows NIST 800-63B guidelines, requiring strong passwords, preventing common password patterns, and implementing appropriate rotation policies. All data is encrypted at rest using AES-256 encryption and in transit using TLS 1.3 protocols. Continuous security monitoring detects and alerts on suspicious activities, unauthorized access attempts, and potential security incidents.

Annual Vulnerability Assessment and Penetration Testing (VAPT) is conducted by CREST-accredited security firms. The most recent assessment found zero critical or high-severity findings, demonstrating the robustness of the security architecture. Regular security updates and patches are applied to address emerging threats.

This security posture is evidenced in **Annex D, Pages 95-110** with Security Certificate documentation from the VAPT assessment, security architecture diagrams, and detailed security control descriptions.

#### Value-Added Services

We implement **Zero-Trust Security Architecture** with behavioral biometrics that continuously authenticate users throughout their session, not just at login. The system analyzes typing patterns, mouse movements, device posture, and access patterns to verify user identity continuously. If anomalous behavior is detected—such as a different typing cadence or unusual navigation patterns—the system can trigger additional authentication challenges or automatically suspend the session, detecting compromised accounts within seconds.

Our **Blockchain-Based Audit Trail** creates immutable, cryptographically-verifiable logs of critical security events. These logs cannot be tampered with, backdated, or deleted, providing irrefutable evidence for forensic investigations and compliance audits. The distributed nature of blockchain storage ensures that audit records survive even catastrophic system failures.

We also provide **AI-Powered Threat Detection** that analyzes user behavior, system access patterns, and network traffic to identify insider threats and anomalous access patterns in real-time. The system learns normal behavior patterns for each user and role, automatically flagging deviations that may indicate compromised accounts, unauthorized data access, or malicious insider activity. Automatic account suspension and security team alerting ensure rapid response to potential threats.

---

### 12. Online Submission of Request & Tracking

#### Evidence

The Customer Portal provides self-service capabilities that enable MMF's customers to submit Request for Delivery (RFD) online without requiring phone calls or email exchanges. The portal guides customers through the booking process with validation to ensure all required information is provided. Once submitted, customers can track their deliveries in real-time through an interactive map view showing the current location of assigned Prime Movers.

Automated notifications keep customers informed throughout the delivery process. The system triggers notifications at 12 predefined status points including booking confirmation, driver assignment, container pickup, in-transit updates, approaching delivery, delivery completion, and proof of delivery confirmation. Notifications are delivered through multiple channels including email, SMS, and WhatsApp based on customer preferences.

The portal maintains complete delivery history for each customer, enabling them to review past shipments, download delivery documents, and analyze their logistics patterns. Customer-specific dashboards show key metrics such as on-time delivery rates, average transit times, and service quality scores.

This customer portal capability is evidenced in **Annex E.8, Page 134** with Customer Portal Demo showing the self-service interface, booking workflow, tracking map, and notification samples.

#### Value-Added Services

We provide **Predictive ETA Engine** that uses machine learning algorithms to provide accurate estimated time of arrival predictions. The system analyzes current traffic conditions, historical route performance, weather impacts, and real-time vehicle location to predict arrival times with high accuracy. Customers receive proactive notifications when ETAs change, enabling them to plan their operations accordingly.

Our **Proactive Exception Management** automatically identifies potential delays before they occur—such as traffic congestion, vehicle breakdowns, or customs delays—and notifies customers with revised ETAs and alternative options. This proactive communication transforms the customer experience from reactive problem-reporting to proactive service management.

We also include **Customer Self-Service Analytics** that provides customers with insights into their shipping patterns, costs, and service levels. Customers can generate their own reports, compare performance across periods, and identify optimization opportunities without requiring MMF staff intervention.

---

### 13. Container Tracking

#### Evidence

The Mobile Driver App provides comprehensive container tracking capabilities through GPS-enabled smartphones or tablets. Drivers capture container events including pickup, in-transit status, arrival at destination, and delivery completion through the mobile interface. Each event capture includes automatic timestamp and geolocation recording, providing precise records of when and where each event occurred.

Photo proof of delivery is captured through the device camera, with images automatically tagged with container number, location, timestamp, and driver identification. Digital signature capture on the mobile device provides legally valid proof of delivery acceptance. These digital records eliminate paper-based documentation and provide tamper-proof evidence of service completion.

Real-time tracking data is synchronized every 30 seconds when connectivity is available, providing near real-time visibility into container locations. The system includes an offline mode that queues updates during connectivity interruptions, automatically synchronizing when connection is restored. This ensures continuous tracking even in areas with poor cellular coverage.

This tracking capability is evidenced in **Annex E.9, Page 135** with Driver App Screenshots showing the event capture interface, photo documentation, and digital signature screens.

#### Value-Added Services

We provide **Computer Vision Container Validation** that uses artificial intelligence to automatically verify container numbers and assess container condition from driver-submitted photos. The system reads container numbers from images and validates them against expected values, flagging discrepancies for review. Condition assessment algorithms identify visible damage, cleanliness issues, or seal integrity concerns, reducing the manual verification effort required by dispatch staff.

Our **Chain of Custody Blockchain** creates tamper-proof records of every container handoff throughout the delivery process. Each transfer is recorded with cryptographic verification, providing irrefutable proof of possession for legal, insurance, and compliance purposes. This blockchain record can be shared with customers, customs authorities, or insurance providers as needed.

We also include **Geofence Intelligence** that automatically generates alerts when containers enter or exit defined geographic boundaries. This enables automated workflow triggers, customer notifications, and operational alerts without requiring manual monitoring of individual container positions.

---

### 14. Electronic Work Ticket

#### Evidence

Digital Job Cards are automatically populated on driver mobile devices when jobs are assigned, eliminating paper-based work tickets. Each electronic work ticket displays comprehensive job details including container information, pickup and delivery addresses, contact information, special handling instructions, and customer requirements. The interface is optimized for mobile use, with clear typography and touch-friendly controls suitable for use in vehicles and outdoor environments.

Drivers update job status through one-tap buttons designed for efficient operation while mobile. Status options include arrived at pickup, loaded, departed, arrived at destination, delivered, and any exception conditions. Each status update automatically captures timestamp and geolocation data, providing precise records for performance tracking and customer billing.

The electronic work ticket system integrates with the dispatch office in real-time, providing immediate visibility into job progress. Dispatchers can see which drivers have acknowledged jobs, current status of active deliveries, and any delays or issues requiring attention.

This electronic work ticket system is evidenced in **Annex E.10, Page 136** with Work Ticket Flow diagrams showing the complete lifecycle from job assignment through completion.

#### Value-Added Services

We provide **Dynamic Job Optimization** that automatically resequences jobs throughout the day based on real-time conditions. If a customer requests an urgent change, a new priority job is added, or traffic conditions shift, the system can recalculate optimal job sequences and notify drivers of updated priorities. This dynamic optimization maximizes fleet utilization and on-time performance.

Our **Voice-Activated Updates** allow drivers to update job status hands-free using natural language commands. Drivers can speak status updates, report delays, or request assistance without taking their hands off the wheel or eyes off the road, improving safety while maintaining operational visibility. Voice recognition is optimized for logistics terminology and operates effectively in typical vehicle noise environments.

We also include **Smart Job Assignment** that considers driver location, hours of service regulations, vehicle capabilities, and customer preferences when assigning jobs. The system optimizes assignments to minimize empty miles, balance workload, and ensure regulatory compliance.

---

### 15. Job Planning/PM, Trailers Assignment

#### Evidence

The AI-powered Job Planning Engine optimizes Prime Mover and trailer assignments based on multiple factors including geographic proximity to pickup locations, vehicle availability and capacity, driver hours of service compliance, delivery priorities, and customer requirements. The optimization algorithm considers real-time traffic conditions, historical route performance, and vehicle-specific constraints to recommend optimal assignments.

The system provides a visual planning interface with drag-and-drop manual override capability, allowing planners to adjust automated recommendations based on operational knowledge or special circumstances. Real-time visibility dashboard displays all active jobs with color-coded status indicators (pending, in-progress, completed, delayed) and calculates estimated time of arrival based on current position and traffic conditions.

Performance tracking monitors planner productivity, assignment efficiency, and optimization outcomes, providing feedback for continuous improvement of planning operations.

This planning capability is evidenced in **Annex E.11, Page 137** with Job Planning UI screenshots showing the optimization interface, assignment recommendations, and real-time status dashboard.

#### Value-Added Services

We provide **Predictive Demand Planning** that analyzes historical shipping patterns, seasonal trends, day-of-week variations, and market indicators to forecast resource needs days in advance. The system predicts peak demand periods, identifies potential capacity constraints, and recommends proactive measures such as scheduling additional shifts or arranging subcontractor support before demand spikes occur.

Our **What-If Scenario Modeling** allows planners to simulate different assignment strategies and see predicted outcomes before committing to decisions. Planners can model the impact of adding new jobs, removing vehicles from service, or changing priority sequences to understand the effects on overall operations, costs, and service levels.

We also include **Collaborative Planning Tools** that enable multiple planners to work on the same schedule simultaneously with real-time synchronization. Change notifications alert team members to modifications, and conflict detection prevents overlapping assignments or resource conflicts.

---

### 16. Trailer Monitoring

#### Evidence

The Trailer Master module maintains a comprehensive registry of all trailers in MMF's fleet, including detailed specifications, ownership information, maintenance history, and document records. The system automatically generates alerts at configurable intervals (typically 30, 60, and 90 days) before permit expiry, PUSPAKOM inspection due dates, insurance renewal deadlines, and other mandatory compliance events.

The system enforces compliance by blocking trailer assignment if any mandatory document is expired or if the trailer is flagged for maintenance. This automated enforcement ensures that non-compliant trailers cannot be inadvertently dispatched, protecting MMF from regulatory violations and safety incidents.

Complete maintenance history is maintained for each trailer, tracking all services, repairs, inspections, and parts replacements. This history supports maintenance planning, cost analysis, and replacement decisions.

This trailer monitoring is evidenced in **Annex E.12, Page 138** with the Trailer Registry interface showing fleet summary, individual trailer records, and alert configuration.

#### Value-Added Services

We provide **Predictive Maintenance Scheduling** that analyzes trailer usage patterns, inspection results, manufacturer recommendations, and historical failure data to optimize maintenance timing. Rather than following rigid calendar schedules, the system predicts when specific trailers are likely to require service, enabling just-in-time maintenance that prevents both premature servicing and breakdown risks.

Our **Regulatory Compliance Automation** automatically prepares and submits renewal applications where API integrations are available. For supported regulatory processes, the system can populate application forms, schedule inspections, and track submission status without manual intervention, significantly reducing administrative burden.

We also include **Trailer Utilization Analytics** that tracks actual usage against capacity, identifying underutilized assets and optimization opportunities. The system recommends trailer reallocation between branches or routes to maximize utilization and return on investment.

---

### 17. Automated Prime Mover Tracking via GPS

#### Evidence

GPS integration with industry-leading telematics platforms including Geotab and Wialon provides comprehensive fleet visibility. Real-time location tracking displays vehicle positions on interactive maps with configurable refresh rates. Speed monitoring generates automatic alerts when vehicles exceed configured thresholds (typically 90 km/h for heavy vehicles), enabling immediate intervention for safety violations.

Idle detection monitors engine status and movement, generating alerts when vehicles remain stationary with engines running for extended periods (typically >10 minutes). This capability identifies fuel waste, unauthorized breaks, or potential breakdowns. Geofence monitoring tracks entry and exit from defined geographic areas, enabling automated workflow triggers and security alerts.

Historical playback functionality reconstructs vehicle movements for any time period up to 2 years, supporting route analysis, incident investigation, and customer service verification. Playback can be viewed at various speeds and includes synchronized event markers showing stops, speed changes, and alerts.

This GPS tracking capability is evidenced in **Annex E.13, Page 139** with GPS Tracking Dashboard screenshots showing real-time map view, vehicle list with status indicators, and historical playback interface.

#### Value-Added Services

Beyond basic GPS tracking, our **Fleet Optimization AI** analyzes traffic patterns, weather conditions, delivery priorities, vehicle capacity, and driver availability to suggest optimal routes in real-time. The system considers current road conditions, construction delays, accident reports, and predicted traffic to recommend the fastest or most fuel-efficient routes. This optimization typically reduces fuel consumption by 15-20% and improves on-time delivery performance by 25%.

Our **Driver Behavior Analytics** continuously monitors driving patterns including harsh braking, rapid acceleration, sharp cornering, speeding, and idle time. The system generates safety scores for each driver and provides personalized coaching tips delivered through the mobile app. Gamification elements encourage safe driving through leaderboards, achievement badges, and performance recognition.

Additionally, our **Predictive Arrival Time Engine** uses machine learning to provide customers with accurate ETA predictions within 15 minutes of actual arrival time. The system analyzes historical route performance, current traffic conditions, weather impacts, and real-time vehicle position to generate reliable predictions. Accurate ETAs significantly improve customer satisfaction scores and reduce inbound inquiry calls.

---

### 18. Automated Driver Incentive

#### Evidence

The Incentive Calculation Engine supports unlimited formula configurations to accommodate diverse incentive schemes. Calculation parameters include revenue-generating trips, non-revenue movements (deadhead, positioning), special day multipliers (weekends, holidays), incremental tier bonuses, fuel efficiency bonuses, safety performance bonuses, and customer satisfaction ratings. Formulas can be configured by driver category, route type, or business unit.

Calculated incentives automatically post to the FMS Payroll module, ensuring seamless integration with the monthly payroll process. Detailed breakdown reports provide transparency for drivers, showing exactly how their incentive amounts were calculated with itemized trip-level detail. This transparency builds trust in the incentive program and motivates performance improvement.

Historical incentive data supports analysis of program effectiveness, identifying which incentive structures drive the desired behaviors and which may need adjustment.

This incentive automation is evidenced in **Annex E.14, Pages 140-142** with the Incentive Formula Sheet showing sample calculations, formula configuration options, and driver breakdown reports.

#### Value-Added Services

We provide **Gamification Module** that introduces achievement badges, leaderboards, progress tracking, and milestone celebrations to enhance driver motivation. Drivers earn recognition for achievements such as consecutive safe driving days, fuel efficiency targets, on-time delivery streaks, and customer compliments. The social recognition aspect of gamification often proves more motivating than financial incentives alone.

Our **Predictive Earnings Dashboard** allows drivers to see projected monthly earnings based on current performance trends, completed trips, and scheduled assignments. This visibility helps drivers understand the financial impact of their performance and make informed decisions about accepting additional assignments or adjusting their work patterns.

We also include **Incentive Program Optimization** analytics that analyze correlation between incentive structures and performance outcomes. The system recommends formula adjustments to maximize return on incentive investment, ensuring that MMF's incentive spending drives the desired operational results.

---

### 19. Reporting and Enquiries

#### Evidence

The HMS comprehensive report library includes 50+ standard reports covering all aspects of haulage operations. Trip reports detail completed deliveries, distances, times, and performance metrics. Vehicle reports track utilization, maintenance schedules, fuel consumption, and operating costs. Driver reports analyze performance, safety scores, productivity, and incentive earnings. Financial reports summarize revenue, costs, and profitability by route, customer, or vehicle. Fleet operations reports provide overall visibility into fleet status, capacity utilization, and service levels.

All reports feature customizable filters allowing users to focus on specific date ranges, branches, vehicles, drivers, customers, or routes. Multiple export formats are supported including PDF for distribution, Excel for analysis, and CSV for data integration. Scheduled report generation automatically delivers reports to email distribution lists on defined schedules.

The ad-hoc query builder enables users to create custom reports without IT assistance. A visual drag-and-drop interface allows users to select data fields, define filters, specify grouping, and choose output formats. Saved queries can be reused, shared with other users, and scheduled for automatic execution.

This reporting capability is evidenced in **Annex E.15, Pages 143-150** with the Report Catalogue listing all available reports, sample outputs, and query builder screenshots.

#### Value-Added Services

We provide **Natural Language Reporting** that allows users to request reports using plain English questions rather than navigating report menus or building queries. Users can simply type requests such as "Show me fuel consumption by driver for last month" or "What were the on-time delivery rates by route last quarter" and receive immediate results. This conversational interface democratizes data access and eliminates the learning curve associated with traditional reporting tools.

Our **Automated Report Distribution** schedules and delivers reports to stakeholders automatically based on their preferences and role requirements. Users can subscribe to reports of interest, specify delivery schedules, and choose preferred formats. Management can define distribution lists ensuring that the right information reaches the right people without manual intervention.

We also include **Executive Briefing Automation** that generates customized executive summaries with key metrics, trend highlights, and exception alerts formatted for senior management review. These briefings can be scheduled for daily, weekly, or monthly distribution and are optimized for consumption on mobile devices.

---

*Annexure C1 contains 19 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 800,000.*

---

## ANNEXURE C2: FORWARDING MANAGEMENT SYSTEM (FFS)

**Location:** Port Klang (PK), Global Logistics Dept (GLD), Butterworth (BTW), Pasir Gudang (PGD)  
**System Version:** LogisticsPro FFS v4.2  
**Trade Lane Coverage:** Import, Export, Cross-trade, Domestic  
**Deployment:** Multi-branch with centralized visibility

The Forwarding Management System (FFS) addresses the complex requirements of freight forwarding operations across MMF's four key operational locations. The system handles the full spectrum of forwarding activities including air freight, sea freight, and multimodal shipments, supporting both import and export operations as well as cross-trade and domestic movements. The multi-branch deployment provides local operational capabilities while maintaining centralized visibility and control across the entire forwarding network.

---

### 1. Dashboard - Real Time Reporting

#### Evidence

The FFS Command Centre provides executives and managers with real-time visibility into all shipments across MMF's forwarding operations. The dashboard displays comprehensive KPIs including shipment volumes by trade lane, revenue by service type, customs clearance status, and operational performance metrics. Drill-down capability enables users to navigate from summary views to individual shipment details with a single click, supporting both strategic oversight and operational intervention.

Role-based views ensure that different users see the information most relevant to their responsibilities. Management views emphasize revenue analytics, profitability metrics, and strategic trends. Operations views focus on pending collections, customs clearances, shipment exceptions, and immediate action items. Customer service views highlight customer inquiries, delivery statuses, and service issues requiring resolution.

The dashboard updates in real-time as shipment events occur, ensuring that displayed information reflects current operational status. Color-coded indicators highlight shipments requiring attention, approaching deadlines, or experiencing delays.

This dashboard capability is evidenced in **Annex E.16, Page 151** with the FFS Dashboard Video demonstrating the interface, drill-down capabilities, and role-based views.

#### Value-Added Services

We provide **Shipment Exception Prediction AI** that analyzes over 50 data points including weather conditions, port congestion indicators, carrier historical performance, customs processing patterns, and seasonal factors to predict potential delays 48-72 hours before they occur. With demonstrated 87% accuracy, this predictive capability allows MMF to proactively notify customers of anticipated delays and arrange alternative solutions before service failures occur. This transforms the customer experience from reactive problem management to proactive service excellence.

Our **Revenue Intelligence Module** continuously analyzes customer shipping patterns to identify cross-selling opportunities. The system suggests additional services such as cargo insurance, warehousing, expedited delivery, or value-added handling at the point of booking when customers are most receptive to upsell offers. This intelligent recommendation engine typically increases revenue per shipment by 8-12% through improved service penetration.

We also include **Customer Profitability Analytics** that tracks true profitability by customer when all costs including operational, administrative, and support resources are allocated. This visibility enables informed decisions about customer pricing, service levels, and relationship investment.

---

### 2. Multi-Platform Interface

#### Evidence

The FFS implements an identical multi-platform architecture to HMS, ensuring consistency across MMF's integrated systems. The responsive web interface adapts to desktop, tablet, and smartphone screens, supporting users across all locations and roles. Native mobile apps for iOS and Android provide optimized experiences for field staff including freight coordinators at Port Klang and other operational locations.

Offline capability is particularly critical for freight coordinators working in areas with limited connectivity such as port zones, customer warehouses, and remote inspection locations. The mobile app queues updates locally and synchronizes when connectivity returns, ensuring that shipment status updates are never lost due to network issues.

Platform synchronization ensures that users see consistent information regardless of their access point. A shipment status updated by a coordinator at Port Klang using a mobile app is immediately visible to headquarters staff using desktop browsers.

This platform support is evidenced in **Annex E.2, Page 126** with the Platform Matrix showing supported devices, operating systems, and browser versions.

#### Value-Added Services

We provide **Smart Sync Technology** that intelligently prioritizes data synchronization based on urgency and connectivity quality. Critical updates such as customs clearance confirmations or delivery completions are transmitted with highest priority, while less time-sensitive data such as document uploads may be queued for batch transmission during periods of better connectivity. This intelligent prioritization ensures that essential information flows quickly even on constrained networks.

Our **Collaborative Workspace** enables real-time document sharing and communication between field staff and office teams. Freight coordinators can share photos of cargo conditions, customs documents, or delivery confirmations instantly with customer service and operations teams, facilitating rapid decision-making and issue resolution.

We also include **Context-Aware Interface Adaptation** that adjusts available functions based on user location, time of day, and current operational conditions. For example, mobile users at port locations may see quick-access buttons for container status updates, while office users see comprehensive planning tools.

---

### 3. Interface with 3rd Party System

#### Evidence

Pre-built integrations with critical industry systems streamline forwarding operations. The Port Community System (PCS) integration provides real-time access to port schedules, container availability, and gate processing status. uCustoms (MyGBS) integration supports electronic customs declarations, status tracking, and clearance notifications. Direct integrations with major shipping lines including Maersk, MSC, and CMA CGM enable automatic retrieval of booking confirmations, vessel schedules, and container tracking information. Airline cargo system integrations provide similar capabilities for air freight operations.

EDI support for ANSI X12 and UN/EDIFACT standards ensures seamless communication with international partners, agents, and customers using these industry-standard message formats. The system can both send and receive standard EDI messages including booking requests, shipping instructions, arrival notices, and invoices.

API integrations with courier services enable last-mile delivery tracking and automated status updates for door-to-door shipments.

This integration capability is evidenced in **Annex F.4, Page 173** with the Integration Catalogue listing all supported systems, protocols, and message types.

#### Value-Added Services

We provide **Partner Performance Analytics** that tracks and benchmarks carrier and service provider performance across multiple dimensions including reliability, transit time consistency, cost competitiveness, and service quality. The system generates scorecards for each partner, identifies top performers, and flags underperformers for review. This data supports informed decisions about carrier selection and contract negotiations.

Our **Automated Dispute Resolution** uses shipment data to automatically identify and flag billing discrepancies with partners. The system compares expected charges against billed amounts, identifies variances, and generates dispute documentation with supporting evidence. This automation reduces the administrative burden of partner reconciliation and improves recovery of overcharges.

We also include **Integration Reliability Monitoring** that tracks uptime, response times, and error rates for all external connections. Proactive alerts notify technical staff of integration issues before they impact operations, and automatic failover procedures ensure business continuity during partner system outages.

---

### 4. FFS Able to Link with Other Business System

#### Evidence

Real-time data exchange with HMS enables coordination between forwarding and haulage operations. When a shipment requires ground transport, the system automatically creates haulage jobs with all relevant details including pickup/delivery addresses, container numbers, and special requirements. Shipment status updates from HMS flow back to FFS, providing complete visibility to customer service staff.

Integration with WMS supports warehouse coordination for shipments requiring storage, consolidation, or deconsolidation. Inventory reservations, receiving appointments, and release authorizations flow seamlessly between systems.

FMS integration ensures that billing information flows automatically from shipment completion to invoice generation. Revenue recognition, cost allocation, and profitability tracking are maintained consistently across systems.

This integration is evidenced in **Annex F.3, Page 172** with the System Integration Map showing data flows between FFS and other business systems.

#### Value-Added Services

We provide **End-to-End Shipment Visibility** that tracks cargo from origin to destination across all modes and systems in a unified timeline. Regardless of how many different systems or carriers handle a shipment, MMF staff and customers see a single consolidated view of the entire journey. This eliminates the need to check multiple systems and provides clear accountability for service performance.

Our **Automated Exception Routing** escalates issues to appropriate stakeholders based on shipment priority, delay severity, and customer requirements. High-priority shipments with delays are immediately brought to management attention, while routine issues are routed to operational staff for resolution.

We also include **Cross-System Workflow Automation** that orchestrates complex processes spanning forwarding, haulage, and warehousing. For example, an import shipment can automatically trigger customs clearance preparation, haulage scheduling, warehouse receiving appointments, and customer notifications through coordinated workflows.

---

### 5. User-Friendly Interface

#### Evidence

The FFS workflow-driven interface guides users through the shipment lifecycle stages in logical sequence: Booking → Documentation → Customs → Haulage → Delivery. Visual progress indicators show the current stage of each shipment and highlight pending actions required to advance to the next stage. This structured approach ensures that no required steps are missed and that users always understand what needs to be done next.

Context-sensitive menus reduce clicks by presenting only the actions relevant to the current shipment status and user role. Compared to traditional freight software, this optimized interface reduces the number of clicks required to complete common tasks by approximately 60%, significantly improving productivity and reducing user fatigue.

The interface design incorporates extensive user feedback from forwarding professionals, ensuring that the system aligns with industry best practices and user expectations.

This usability is evidenced in **Annex E.17, Page 152** with UX Walkthrough documentation showing the workflow interface, progress indicators, and task optimization.

#### Value-Added Services

We provide **Smart Form Completion** that uses artificial intelligence to auto-populate form fields based on historical data, document uploads, and pattern recognition. When processing shipments for repeat customers or common trade lanes, the system suggests field values based on previous entries, reducing data entry time by up to 70% while improving accuracy. The AI learns from corrections and approvals to continuously improve its suggestions.

Our **Contextual Help System** provides role-specific guidance and best practice recommendations at each workflow stage. New users receive detailed explanations of each step and field, while experienced users see tips for efficiency improvements and shortcuts. The help content is continuously updated based on regulatory changes and operational feedback.

We also include **Adaptive Interface Learning** that customizes the user experience based on individual work patterns. Frequently-used functions are promoted to prominent positions, while rarely-used features are accessible through menus but don't clutter the main workspace.

---

### 6. Automated Invoice & Receipts Generation

#### Evidence

The freight billing engine handles the complex rating scenarios typical of forwarding operations. Multi-currency support accommodates international shipments with automatic exchange rate application and gain/loss calculation. Multi-party billing handles scenarios where multiple parties (shipper, consignee, agent) share costs or where different parties pay for different service components.

Multi-leg shipment billing automatically apportions costs across multiple segments (origin handling, main carriage, destination handling) with appropriate revenue recognition timing. The system handles complex scenarios including transshipments, consolidations, and intermodal movements.

IRBM e-Invoicing integration ensures compliance with Malaysian tax regulations. Invoices are validated against MyInvois requirements, submitted for approval, and stored with regulatory identifiers.

This billing capability is evidenced in **Annex E.4, Pages 128-130** with Freight Invoice Samples showing complex multi-party, multi-currency billing scenarios.

#### Value-Added Services

We provide **Multi-Party Settlement Automation** that handles complex multi-party billing scenarios with automatic cost allocation and settlement scheduling. The system manages scenarios where shipper, consignee, and various agents each pay different portions of the total shipment cost, with appropriate invoicing, payment tracking, and reconciliation for each party.

Our **Revenue Recognition AI** ensures accurate revenue timing across complex shipment lifecycles with multi-modal components. The system applies appropriate accounting standards to recognize revenue as performance obligations are satisfied, supporting accurate financial reporting and audit compliance.

We also include **Billing Exception Intelligence** that identifies unusual billing patterns that may indicate errors or missed charges. The system flags shipments with unexpected cost ratios, missing surcharge applications, or unusual routing for review before invoicing.

---

### 7. Credit & Collections Management

#### Evidence

Integrated credit management shares customer credit data from HMS across FFS, providing a consolidated customer view across all business units. A customer with haulage services and forwarding services has a single combined credit limit that is enforced across both systems. This integration prevents situations where a customer might exceed their overall credit limit by splitting activity across different business units.

Automated collection workflows trigger based on shipment delivery and agreed payment terms. The system monitors payment due dates, generates collection worklists, and escalates overdue accounts through configurable procedures.

Escalation matrices ensure that collection activities are appropriate to the amount outstanding and days past due, with senior management involvement for significant exposures.

This credit management is evidenced in **Annex E.5, Page 131** with the Collections Dashboard showing integrated credit data across business units.

#### Value-Added Services

We provide **Shipment-Level Credit Control** that enables granular credit management at the individual shipment level rather than just customer level. This allows MMF to release some shipments for customers approaching credit limits while holding others, managing risk while preserving customer relationships and revenue opportunities.

Our **Customer Payment Prediction** analyzes historical payment patterns, current economic conditions, and customer communication to forecast when specific invoices are likely to be paid. This visibility enables proactive cash flow management and early identification of potential collection issues.

We also include **Automated Collection Correspondence** that generates personalized dunning letters, emails, and SMS messages based on customer history, amount outstanding, and payment behavior. The system optimizes communication timing and tone based on customer responsiveness.

---

### 8. Automated Locking for Overdue Customer

#### Evidence

Unified credit control across HMS, FFS, WMS, and TMS ensures consistent enforcement regardless of which business unit the customer interacts with. A customer on credit hold for overdue haulage invoices cannot create new forwarding shipments, preventing circumvention of credit controls through system switching.

Override workflows route credit hold overrides to appropriate authority based on credit exposure amount. Small overrides may be approved by branch managers, while large exposures require regional or headquarters approval. All overrides are logged with justification, approver identity, and timestamp.

Credit hold status is visible across all customer touchpoints, ensuring consistent communication and preventing confusion.

This unified control is evidenced in **Annex E.6, Page 132** with the Credit Policy Matrix showing enforcement rules across all systems.

#### Value-Added Services

We provide **Customer Risk Profiling** that dynamically adjusts credit enforcement based on customer history, market conditions, and relationship value. Long-standing customers with good payment histories may receive more flexible treatment than new or problematic accounts, balancing risk management with relationship preservation.

Our **Automated Payment Plan Management** facilitates structured payment arrangements for customers experiencing temporary difficulties. The system tracks agreed payment schedules, sends reminders, monitors compliance, and automatically adjusts credit status as payments are received.

We also include **Credit Limit Optimization** that recommends optimal credit limits based on customer payment capacity, business volume, and risk profile. The system identifies customers with excessive limits that expose MMF to unnecessary risk, as well as customers with insufficient limits that constrain business growth.

---

### 9. Audit Trail & History

#### Evidence

Comprehensive audit logging covers all shipment data changes, document uploads, status transitions, and financial transactions. Each audit record captures user identity, timestamp, before/after values, and the business context of the change. Audit data is stored in immutable storage that cannot be modified or deleted.

Complete shipment lifecycle history is accessible via a single-click Audit Trail button on every job screen. Users can view the complete sequence of events from booking creation through final delivery, including who performed each action and when.

This audit capability supports compliance with customs regulations, tax requirements, and industry standards. The complete history enables dispute resolution, service verification, and operational analysis.

This audit capability is evidenced in **Annex D.2, Page 98** with a Shipment Audit Sample showing the detailed event log for a representative shipment.

#### Value-Added Services

We provide **Shipment Timeline Reconstruction** that creates visual timelines of shipment events for dispute resolution and process improvement. The graphical representation makes it easy to identify delays, understand sequence dependencies, and communicate with customers about their shipment history.

Our **Compliance Automation** generates regulatory reports automatically from audit trail data. Customs authorities, tax regulators, and auditors can receive properly formatted reports showing complete transaction history without manual compilation.

We also include **Audit Analytics** that identify patterns in system usage, flag unusual activities, and support continuous improvement of operational processes.

---

### 10. Ability of the System to Support Attachment Documents

#### Evidence

Document management supports the full range of trade documents required in forwarding operations. Bill of Lading (BL), Air Waybill (AWB), Certificate of Origin (CO), packing lists, commercial invoices, and customs declarations can all be attached to shipments. The system supports both electronic documents and scanned paper documents.

Automatic metadata extraction identifies document types, extracts key data fields, and indexes content for search. Version control maintains document history with rollback capability. Sharing controls enable secure distribution to customers, agents, and authorities while maintaining access restrictions.

Document templates support standard formats with automatic population from shipment data, reducing document preparation time and ensuring consistency.

This document management is evidenced in **Annex E.7, Page 133** with the Trade Document Repository showing document organization, version control, and access controls.

#### Value-Added Services

We provide **Trade Document Validation AI** that verifies document completeness and compliance before submission. The system checks that all required documents are present, validates that document content matches shipment data, and identifies potential issues that could cause customs rejection or delays.

Our **Document Auto-Routing** intelligently distributes documents to appropriate parties based on shipment configuration and trade lane requirements. The system knows which documents are required by each customs authority, shipping line, and customer, and ensures that documents reach the right recipients at the right time.

We also include **Document Translation Services** integration that provides automated translation of trade documents for international shipments, supporting MMF's cross-border operations.

---

### 11. Comprehensive Security Features

#### Evidence

Enterprise-grade security ensures that forwarders only see shipments they are assigned to, and sensitive commercial data such as rates, margins, and customer contracts is restricted to authorized personnel. Data encryption, multi-factor authentication, and session management follow the same robust framework as HMS.

Role-based access can be configured by trade lane, customer, or geographic region, ensuring that staff have access only to the information they need for their responsibilities. This segregation prevents unauthorized viewing of competitive information or customer data.

All access is logged and monitored, with alerts for suspicious activities or unauthorized access attempts.

This security is evidenced in **Annex D, Pages 95-110** with the Security Whitepaper detailing the comprehensive security framework.

#### Value-Added Services

We provide **Data Loss Prevention (DLP)** that monitors and controls sensitive data movement, preventing unauthorized document exports or data exfiltration. The system can block, quarantine, or alert on attempts to download sensitive documents or export customer data.

Our **Customer Data Segregation** ensures complete logical separation of customer data with encrypted compartmentalization. Even within the same database, customer information is isolated to prevent cross-customer data leakage.

We also include **Security Awareness Training** modules integrated into the system to educate users about security best practices, phishing recognition, and proper handling of sensitive information.

---

### 12. Online Submission of Request & Tracking

#### Evidence

The Customer Self-Service Portal provides 24/7 availability for online booking requests, document uploads, real-time shipment tracking, and e-billing access. Customers can submit new shipment requests, upload required documentation, track their shipments through the entire lifecycle, view and pay invoices, and access historical shipment records.

Automated notifications keep customers informed at every milestone without requiring manual intervention from MMF staff. Notifications are triggered by system events such as booking confirmation, document receipt, customs clearance, departure, arrival, and delivery.

The portal is customizable with MMF branding and can be configured to match MMF's corporate identity and communication standards.

This portal capability is evidenced in **Annex E.8, Page 134** with the Customer Portal Tour demonstrating self-service capabilities.

#### Value-Added Services

We provide **Intelligent Quote Generation** that analyzes historical rates, current market conditions, and shipment characteristics to provide instant, competitive quotations. Customers can request quotes through the portal and receive immediate responses, improving the customer experience and reducing the sales cycle.

Our **Customer Behavior Analytics** tracks portal usage patterns to identify upsell opportunities and service improvement areas. The system identifies customers who may benefit from additional services, detect navigation difficulties that suggest usability improvements, and measure engagement levels.

We also include **White-Label Customer Portal** options that allow MMF to offer branded portal access to their customers' customers, extending the self-service benefits through the supply chain.

---

### 13. Job Planning / Tracking

#### Evidence

Visual shipment timelines display planned versus actual milestones with clear indicators for delays or deviations. Each shipment shows scheduled dates against actual completion dates, with color-coding to highlight variances. Automatic alerts notify responsible staff when shipments deviate from planned schedules.

Project management views consolidate multiple related shipments into single project dashboards. For large contracts or complex movements involving multiple containers, the project view shows overall status, consolidated revenue, and critical path items.

Resource allocation views show workload distribution across coordinators, identifying capacity constraints and balancing opportunities.

This planning capability is evidenced in **Annex E.18, Page 153** with the Shipment Timeline View showing planned versus actual progress.

#### Value-Added Services

We provide **Milestone Prediction AI** that forecasts milestone completion dates based on current progress, historical patterns, and external factors. This predictive capability enables proactive management of shipments at risk of delay.

Our **Resource Load Balancing** automatically distributes workload across freight coordinators based on current queue depth, expertise, and capacity. The system suggests task reallocations to optimize throughput and prevent bottlenecks.

We also include **Critical Path Analysis** that identifies the sequence of tasks that determine overall shipment duration. This visibility helps prioritize activities that impact delivery dates versus those with schedule flexibility.

---

### 14. Shipment Tracking

#### Evidence

Multi-modal tracking captures all transportation modes in a unified timeline. Sea freight tracking includes vessel names, voyage numbers, estimated and actual departure/arrival times, and container vessel positions. Air freight tracking captures flight details, departure/arrival times, and cargo terminal status. Land transport milestones from HMS integration provide complete door-to-door visibility.

Integration with shipping line track-and-trace APIs provides automatic updates without manual data entry. Container status, vessel schedules, and port events flow automatically into FFS from carrier systems.

Exception alerts notify staff of deviations from planned schedules, enabling proactive customer communication and issue resolution.

This tracking capability is evidenced in **Annex E.19, Page 154** with Multi-modal Tracking documentation showing unified visibility across transportation modes.

#### Value-Added Services

We provide **Carrier Performance Scoring** that benchmarks carrier reliability and service quality based on on-time performance, communication quality, and exception frequency. This data supports informed carrier selection and contract negotiations.

Our **Disruption Impact Analysis** automatically assesses the downstream impact of delays and suggests mitigation strategies. If a vessel is delayed, the system calculates affected shipments, identifies alternative routing options, and estimates customer impact.

We also include **Predictive Arrival Intelligence** that combines carrier data, historical patterns, and current conditions to provide accurate arrival predictions for improved customer communication.

---

### 15. Job Costing Automation

#### Evidence

Automated cost capture collects expenses from all sources including haulage charges from HMS, storage costs from WMS, documentation fees, customs charges, and carrier invoices. Real-time profit and loss visibility shows estimated and actual costs for each shipment as expenses are recorded.

Cost variance alerts notify management when actual costs exceed estimates by configurable thresholds. Early identification of cost overruns enables investigation and corrective action before shipment completion.

Cost allocation rules distribute shared costs (such as consolidation handling or multi-shipment documentation) across individual shipments based on configurable logic.

This costing automation is evidenced in **Annex E.20, Page 155** with the Job Costing Dashboard showing real-time profitability visibility.

#### Value-Added Services

We provide **Margin Optimization Recommendations** that suggest alternative routing, carrier selection, or service combinations to improve shipment profitability. The system analyzes cost components and identifies opportunities for savings.

Our **Cost Anomaly Detection** identifies unusual cost patterns that may indicate errors, fraud, or process breakdowns. Unexpected cost levels trigger review workflows before invoices are approved.

We also include **Customer Profitability Alerts** that flag shipments or customers with unexpectedly low margins, enabling pricing reviews and commercial discussions.

---

### 16. Data Bank

#### Evidence

The tender management module tracks all tender submissions with comprehensive status tracking from initial request through award or closure. Win/loss analysis captures reasons for outcomes, competitor information, and lessons learned. The document repository maintains all tender documentation including specifications, quotations, correspondence, and contracts.

Historical freight rate database maintains 3-year history of rates by carrier, route, and service type. This data enables accurate quotation and margin analysis for new tenders by comparing against historical benchmarks.

Rate trend analysis identifies market direction and cost inflation patterns, supporting procurement strategy and customer pricing decisions.

This data bank capability is evidenced in **Annex E.21, Page 156** with the Tender Database UI showing tender tracking and rate history.

#### Value-Added Services

We provide **Tender Success Prediction** that analyzes tender characteristics, historical win rates, and market conditions to predict success probability. This insight helps prioritize tender efforts and allocate resources to opportunities with highest expected return.

Our **Competitive Intelligence Module** tracks competitor pricing and service offerings from available market data, providing context for tender positioning and strategy development.

We also include **Automated Tender Response** that pre-populates tender documents with standard information, historical data, and pricing models, significantly reducing response preparation time.

---

### 17. Centralized Documentation Management

#### Evidence

Auto-generation of freight documents includes Bills of Lading, Air Waybills, and customs declarations with data populated automatically from shipment records. Digital signature capability enables legally valid electronic execution of documents without printing and scanning.

Template library supports multiple trade lanes and document types with automatic population from shipment data. Templates can be customized for specific carriers, trade lanes, or customer requirements while maintaining standard data fields.

Document validation checks ensure that generated documents contain all required information and comply with regulatory requirements before release.

This document management is evidenced in **Annex E.22, Page 157** with the Document Generation Demo showing automated document creation.

#### Value-Added Services

We provide **Blockchain Document Verification** that creates tamper-proof digital fingerprints of all shipping documents. Customers and customs authorities can instantly verify document authenticity through blockchain validation without contacting MMF, reducing verification delays and document fraud risk.

Our **AI Document Extraction** automatically reads and extracts data from unstructured documents including scanned BLs, handwritten forms, and PDFs with 95%+ accuracy. This eliminates manual data entry and accelerates document processing.

We also include **Digital Trade Corridor Integration** enabling direct electronic submission to customs authorities in Malaysia, Singapore, and Thailand with automatic status updates. This integration typically reduces customs clearance times by up to 60% compared to manual submission processes.

---

### 18. Freight Rate Sheets and Quotation

#### Evidence

Rate management supports multiple carriers, routes, and cargo types with comprehensive validity period tracking and automatic expiry alerts. Rate contracts are stored with effective dates, expiry dates, minimum quantities, and special terms, ensuring that quotations use current and valid rates.

Self-service customer portal enables instant quotations based on predefined rate cards. Customers can enter shipment details and receive immediate pricing for transportation alternatives including different carriers, service levels, and routing options.

Quotation history maintains records of all quotes provided, conversion rates, and reasons for wins/losses, supporting continuous improvement of quotation processes.

This rate management is evidenced in **Annex E.23, Page 158** with the Rate Management Module showing rate maintenance and quotation capabilities.

#### Value-Added Services

We provide **Dynamic Rate Optimization** that suggests rate adjustments based on capacity utilization, market demand, and competitive positioning. The system identifies opportunities for rate increases on high-demand lanes and flags overpriced services that may be losing business.

Our **Rate Profitability Analysis** forecasts margin impact of rate changes before implementation. Modeling tools show how proposed rate adjustments would affect volume, revenue, and profitability.

We also include **Market Rate Intelligence** integration that provides benchmark rate data from market sources, ensuring MMF's rates remain competitive while protecting margins.

---

### 19. Reporting and Enquiry

#### Evidence

40+ standard freight reports cover all aspects of forwarding operations including shipment volumes, documentation processing, customs clearance performance, carrier performance, and financial results. Flexible filtering enables analysis by date range, branch, customer, trade lane, carrier, or service type.

Custom report builder enables ad-hoc analysis without technical expertise. Users can select data fields, define filters, set grouping and sorting, and choose output formats through an intuitive visual interface.

Scheduled report generation automatically delivers reports to distribution lists on daily, weekly, or monthly schedules.

This reporting capability is evidenced in **Annex E.24, Pages 159-162** with the FFS Report Library listing all available reports.

#### Value-Added Services

We provide **Executive Briefing Automation** that generates customized executive summaries with key metrics, trends, and exception alerts formatted for senior management. These briefings highlight items requiring attention and provide context for strategic decisions.

Our **Cross-System Reporting** enables reports that combine freight data with financial and operational metrics from other modules. Consolidated views show complete business performance across all functions.

We also include **Predictive Reporting** that forecasts future trends based on historical patterns and current pipeline data, enabling proactive management rather than reactive response.

---

### 20. Financial Reports

#### Evidence

Freight-specific financial reports provide specialized analysis for forwarding operations. Revenue by trade lane shows profitability across different geographic markets. Profitability per customer identifies the most and least profitable customer relationships. Agent commission statements automate settlement calculations for partner agents. Cost breakdown analysis shows the composition of costs by category (transportation, handling, documentation, customs).

Real-time integration with FMS ensures financial data accuracy without manual reconciliation. Operational events automatically generate financial transactions, maintaining alignment between operational and financial records.

Period comparison reports show trends over time, highlighting growth, margin changes, and cost inflation.

These financial reports are evidenced in **Annex E.25, Page 163** with Freight Financial Reports samples.

#### Value-Added Services

We provide **Profitability Forecasting** that projects revenue and margin based on pipeline data and historical conversion rates. This visibility supports capacity planning, resource allocation, and strategic decision-making.

Our **Commission Optimization** analyzes agent performance and recommends optimal commission structures. The system identifies high-performing agents deserving increased incentives and flags underperforming relationships for review.

We also include **Automated Financial Consolidation** that combines data from all branches and business units into consolidated reports without manual spreadsheet work.

---

### 21. Enquiries

#### Evidence

Advanced enquiry screens support real-time search by multiple criteria including BL number, container number, customer reference, or job ID. Cross-module search returns results from all relevant systems, ensuring comprehensive visibility regardless of how information was originally entered.

Drill-down capability from summary to detailed transaction level enables users to navigate from search results to complete shipment details with a single click. Document attachments are viewable inline without requiring separate downloads.

Saved searches enable users to store frequently-used search criteria for quick re-execution. Search history provides quick access to recent enquiries.

This enquiry capability is evidenced in **Annex E.26, Page 164** with the Enquiry Interface showing search capabilities and drill-down features.

#### Value-Added Services

We provide **Natural Language Search** that allows users to search using conversational queries rather than structured criteria. Users can type "Show me all shipments for ABC Corp last month" or "Find containers arriving Port Klang this week" and receive relevant results.

Our **Saved Search Alerts** notify users when new records match their saved search criteria. Staff can monitor for specific shipment types, customers, or conditions without repeatedly running searches.

We also include **Search Analytics** that identify common search patterns and optimize system performance for frequently-accessed data.

---

*Annexure C2 contains 21 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 900,000.*

---

## ANNEXURE C3: WAREHOUSE MANAGEMENT SYSTEM (WMS)

**Location:** Port Klang (PK), Headquarters (HQ)  
**System Version:** LogisticsPro WMS v4.2  
**Warehouse Types:** Bonded, Free Zone, Cold Storage, General  
**Operations:** Receiving, storage, inventory management, order fulfillment

The Warehouse Management System (WMS) provides comprehensive control over MMF's warehousing operations at Port Klang and Headquarters locations. The system supports diverse warehouse types including bonded warehouses for duty-suspended cargo, free zone facilities for transshipment cargo, cold storage for temperature-sensitive goods, and general warehouses for standard cargo. The WMS optimizes space utilization, improves inventory accuracy, and streamlines order fulfillment processes to maximize warehouse productivity and customer service levels.

---

### 1. Dashboards & Analytics

#### Evidence

The WMS Control Tower provides warehouse managers with real-time visibility into all key performance indicators including inventory accuracy percentages, space utilization rates, order fulfillment rates, and labor productivity metrics. The dashboard displays current inventory levels by product category, location utilization heat maps showing occupied and available space, and operational metrics such as receipts processed, orders shipped, and cycle count accuracy.

Predictive analytics capabilities forecast inventory levels based on historical demand patterns, seasonal trends, and incoming shipment schedules. The system suggests optimal reorder points and safety stock levels to maintain service levels while minimizing carrying costs. Analytics also identify slow-moving inventory, excess stock situations, and potential stockout risks.

Labor productivity tracking monitors picks per hour, put-away rates, and task completion times by operator and zone. This visibility supports performance management, training identification, and resource optimization.

This dashboard capability is evidenced in **Annex E.27, Page 166** with the WMS Dashboard Video demonstrating real-time warehouse visibility.

#### Value-Added Services

We provide **Warehouse Digital Twin Technology** that creates a real-time 3D visualization of MMF's warehouse operations. This digital replica enables scenario modeling for layout changes, peak season planning, and automation investments before committing physical resources. Managers can simulate the impact of adding new racks, changing picking strategies, or implementing automation technologies.

Our **AI Slotting Optimizer** continuously analyzes SKU velocity, dimensions, weight, and seasonality to recommend optimal product placement. By positioning fast-moving items near shipping areas and optimizing pick paths, the system typically improves picking efficiency by 20-30% and reduces travel time significantly.

Additionally, our **Demand Forecasting Engine** integrates external data including weather patterns, local events, economic indicators, and industry trends to predict demand fluctuations with 92% accuracy. This enables proactive inventory positioning before demand spikes occur.

---

### 2. Multi-Platform Interface

#### Evidence

The WMS provides a full-featured web interface for office staff including warehouse managers, inventory planners, and customer service representatives. This interface supports complex queries, report generation, and administrative functions. For warehouse floor operations, responsive mobile apps are optimized for RF scanners, tablets, and other mobile computers commonly used in warehouse environments.

Touch-optimized screens support forklift-mounted devices used by operators moving throughout the warehouse. These screens feature large buttons, high-contrast displays for various lighting conditions, and simplified interfaces designed for use while operating material handling equipment. Voice-picking support enables hands-free operation for high-volume picking operations.

The multi-platform design ensures that warehouse staff can access required functions regardless of their location or device, while office staff have comprehensive tools for planning, analysis, and customer service.

This platform support is evidenced in **Annex E.2, Page 126** with the WMS Device Matrix showing supported hardware and interface options.

#### Value-Added Services

We provide **Adaptive Interface Scaling** that automatically adjusts UI elements based on device screen size and input method. Large touch targets for mobile devices, optimized keyboard navigation for desktop users, and voice commands for hands-free operation ensure optimal user experience across all access methods.

Our **Haptic Feedback Integration** provides tactile confirmation for critical actions on compatible devices, improving accuracy in noisy warehouse environments where audio confirmations may be difficult to hear.

We also include **Ambient Display Adaptation** that adjusts screen brightness and contrast based on lighting conditions, ensuring readability in both dim storage areas and brightly lit shipping docks.

---

### 3. Interface with 3rd Party System

#### Evidence

WMS integration capabilities include connectivity with Port Klang PCS for customs and port-related operations, Customs systems for bonded warehouse reporting and duty payments, and courier services including DHL, FedEx, and Pos Laju for last-mile delivery. E-commerce platform integrations with Shopify, Lazada, and Shopee support 3PL operations for online retailers.

The API gateway is designed for high-volume transaction processing, supporting the transaction rates required for busy 3PL operations. The gateway handles authentication, rate limiting, request routing, and response formatting for all external integrations.

Standard EDI support enables communication with trading partners using industry-standard message formats for purchase orders, advance ship notices, and inventory updates.

This integration capability is evidenced in **Annex F.5, Page 174** with the WMS Integration Specs detailing supported systems and protocols.

#### Value-Added Services

We provide **Multi-Carrier Optimization** that automatically selects the optimal courier service based on cost, service level requirements, destination, and current capacity. The system considers customer preferences, delivery timeframes, and historical carrier performance.

Our **E-Commerce Sync Automation** maintains real-time inventory synchronization with online marketplaces, preventing overselling situations and ensuring accurate product availability display. The system automatically updates stock levels as receipts and shipments occur.

We also include **Trading Partner Portal** that provides customers and suppliers with visibility into their inventory, shipment status, and operational metrics without requiring full system access.

---

### 4. WMS Able to Link with Other Business System

#### Evidence

Seamless integration with HMS enables coordination between warehouse operations and delivery scheduling. When orders are ready for shipment, the system automatically creates haulage jobs with appropriate timing to minimize dwell time. Integration with FFS allows forwarding shipments to trigger warehouse receiving appointments and release authorizations.

FMS integration ensures that all billable warehouse activities automatically generate charges. Storage fees, handling charges, and value-added services flow to billing without manual data entry or reconciliation.

Inventory reservations from FFS bookings automatically allocate warehouse space and trigger receiving workflows, ensuring that space is available when shipments arrive.

This integration is evidenced in **Annex F.3, Page 172** with the WMS Integration Flows showing data exchange with other business systems.

#### Value-Added Services

We provide **Synchronized Planning** that coordinates warehouse operations with haulage schedules to minimize container and cargo dwell time. The system optimizes receiving appointments, processing schedules, and shipping coordination to maximize asset utilization.

Our **Cross-Docking Optimization** automatically identifies opportunities to bypass put-away and ship directly from receiving. The system analyzes incoming and outgoing shipments to match flows and reduce handling costs.

We also include **End-to-End Visibility** that tracks inventory from supplier receipt through customer delivery, providing complete supply chain visibility across all systems.

---

### 5. User-Friendly Interface

#### Evidence

The warehouse-optimized UI features barcode scanning workflows that guide operators through receiving, put-away, picking, and shipping processes step-by-step. Color-coded location indicators help operators quickly identify correct storage locations, pick faces, and staging areas. Simplified screens for warehouse operators focus on the specific task at hand, presenting only the information needed for immediate action.

Supervisor dashboards provide management oversight with exception-based alerts highlighting issues requiring attention. Supervisors can monitor productivity metrics, identify bottlenecks, and intervene proactively when performance deviates from standards.

The interface design incorporates feedback from warehouse operators to ensure practicality in fast-paced operational environments.

This usability is evidenced in **Annex E.28, Page 167** with the WMS UI Tour showing warehouse-optimized interfaces.

#### Value-Added Services

We provide **Personalized Operator Dashboards** that adapt to individual user roles and frequently performed tasks. Each operator sees quick access to their assigned functions, current workload, and performance metrics.

Our **Guided Task Execution** provides step-by-step instructions for complex or infrequent operations, reducing training requirements and ensuring consistent process execution.

We also include **Performance Gamification** that introduces achievement badges, productivity leaderboards, and recognition programs to motivate warehouse staff and build engagement.

---

### 6. Automated Invoice & Receipts Generation

#### Evidence

Automated storage billing calculates charges based on multiple factors including occupied space (measured in CBM or square feet), storage duration from receipt to release, and handling activities performed. Configurable rate cards accommodate different customer agreements, product types, and service levels.

Full IRBM e-Invoicing support ensures compliance with Malaysian tax requirements for 3PL customer billing. The system supports both consolidated invoices summarizing all activity for a period and detailed invoices showing transaction-level charges.

Automatic billing triggers ensure that all chargeable activities are captured, including receiving, put-away, storage, picking, packing, and shipping.

This billing capability is evidenced in **Annex E.4, Pages 128-130** with Storage Invoice Samples showing detailed and consolidated billing options.

#### Value-Added Services

We provide **Activity-Based Billing** that captures and invoices for all value-added services performed in the warehouse including labeling, kitting, inspection, repacking, and special handling. The system ensures that all billable activities are charged appropriately.

Our **Billing Reconciliation Automation** matches invoiced amounts to contractual agreements and flags discrepancies automatically. Validation rules check for correct rates, proper surcharge application, and complete charge capture.

We also include **Customer Billing Portal** that allows customers to view their charges, download invoices, and access supporting documentation for self-service account management.

---

### 7. Credit & Collections Management

#### Evidence

Unified credit management across all systems ensures consistent credit control for warehouse customers who also use haulage or freight services. A customer's credit status is visible across all business units, preventing situations where credit issues in one area are unknown to staff in another.

Automated invoicing and collection workflows reduce Days Sales Outstanding (DSO) by an average of 15 days through timely billing, systematic follow-up, and efficient payment processing.

Collection worklists prioritize accounts based on aging, amount, payment history, and promise-to-pay status, ensuring that collection efforts focus on the most critical accounts.

This credit management is evidenced in **Annex E.5, Page 131** with WMS Credit Controls showing integrated credit management.

#### Value-Added Services

We provide **Release Authorization Integration** that coordinates credit holds with physical release processes. The system prevents unauthorized cargo movement by blocking gate pass generation for customers exceeding credit limits.

Our **Payment Plan Automation** facilitates and monitors structured payment arrangements for warehouse customers experiencing temporary difficulties.

We also include **Credit Risk Alerts** that provide early warning of customers approaching credit limits, enabling proactive customer communication before restrictions are applied.

---

### 8. Automated Locking for Overdue Customer

#### Evidence

The system prevents goods release for customers exceeding credit limits with configurable grace periods and partial payment options. Credit hold visibility across all warehouse operations ensures consistent enforcement, preventing situations where different staff apply different standards.

Partial payment options allow customers to make partial payments to release specific shipments while maintaining holds on remaining inventory, providing flexibility while protecting MMF's receivables.

All credit hold actions are logged with user identification, timestamp, and justification, supporting audit requirements and dispute resolution.

This locking mechanism is evidenced in **Annex E.6, Page 132** with the Release Control SOP documenting credit enforcement procedures.

#### Value-Added Services

We provide **Partial Release Management** that allows controlled release of partial shipments against partial payments. This maintains cash flow while preserving customer relationships and operational flexibility.

Our **Automated Hold Notifications** inform customers proactively when credit holds are applied, explaining the reason and required actions for release.

We also include **Credit Recovery Workflows** that systematically escalate collection efforts based on aging and amount, ensuring consistent treatment of overdue accounts.

---

### 9. Audit Trail & History

#### Evidence

Complete inventory transaction history captures every movement, adjustment, and count with user identification and precise timestamp. Full traceability supports compliance with customs regulations for bonded warehouses, audit requirements, and quality standards.

Seven-year retention ensures that historical records are available for regulatory compliance, tax audits, and dispute resolution. Automated archival processes manage data volume while maintaining accessibility.

Audit trails support forensic analysis, enabling reconstruction of inventory discrepancies and identification of root causes.

This audit capability is evidenced in **Annex D.2, Page 98** with the Inventory Audit Trail showing transaction logging detail.

#### Value-Added Services

We provide **Lot Traceability Mapping** that creates visual supply chain maps for lot-tracked products, enabling rapid identification of affected inventory in recall situations.

Our **Customs Compliance Reporting** automatically generates required regulatory reports from audit trail data, simplifying bonded warehouse compliance.

We also include **Audit Analytics** that identify unusual transaction patterns, flag potential issues, and support continuous improvement of inventory controls.

---

### 10. Ability of the System to Support Attachment Documents

#### Evidence

Document management supports all warehouse operation documents including Goods Receipt Notes (GRN), delivery orders, customs forms, damage photos, and inspection reports. Automatic filing by job number ensures that documents are organized and easily retrievable.

OCR indexing enables full-text search within uploaded documents, allowing users to find documents by searching for content rather than browsing folders. This capability is particularly valuable for large document repositories.

Version control maintains document history, ensuring that users can access previous versions if needed while always seeing the current version by default.

This document management is evidenced in **Annex E.7, Page 133** with WMS Document Attachments showing document organization and search capabilities.

#### Value-Added Services

We provide **Damage Documentation AI** that analyzes photos to assess damage severity and recommend appropriate disposition (resellable, repair, scrap, return to vendor).

Our **Document Retention Automation** manages document lifecycle according to regulatory requirements and internal policies, ensuring compliance without manual tracking.

We also include **Document Collaboration** features that enable secure document sharing with customers, suppliers, and inspectors with appropriate access controls.

---

### 11. Comprehensive Security Features

#### Evidence

Role-based access ensures warehouse staff only access assigned zones and functions. A picker in Zone A cannot access inventory records for Zone B or perform receiving functions. Supervisor approval workflows control sensitive operations such as inventory adjustments, location changes, and damage write-offs.

Data security follows the same robust framework as HMS/FFS with encryption, MFA, and comprehensive audit logging. Warehouse-specific security concerns such as after-hours access and temporary worker permissions are addressed through configurable controls.

Physical security integration can coordinate system access with door access controls, ensuring that system permissions align with physical zone access.

This security is evidenced in **Annex D, Pages 95-110** with the WMS Security Config showing access controls and permissions.

#### Value-Added Services

We provide **Zone-Based Access Control** that restricts system functionality based on physical location within the warehouse. Workers can only access functions for the zone where they are currently located.

Our **Biometric Integration** supports fingerprint and facial recognition for high-security operations or areas requiring enhanced access control.

We also include **Temporary Worker Management** with time-limited access that automatically expires, ensuring that temporary staff cannot access the system after their assignment ends.

---

### 12. Cargo In/Out (Barcode/RFID Reader)

#### Evidence

Native support for barcode scanners includes both 1D and 2D barcode formats commonly used in logistics. RFID reader support enables contactless identification for high-volume operations or environments where barcode scanning is impractical. Automatic device detection and configuration simplify setup and reduce IT support requirements.

GS1-128 and SSCC barcode standards are fully supported for standardized labeling and scanning, ensuring compatibility with supplier and customer systems.

The scanning interface is optimized for speed and accuracy, with visual and audio confirmations of successful scans and clear error messages for failed reads.

This scanning capability is evidenced in **Annex E.29, Page 168** with the Barcode Integration Spec showing supported standards and devices.

#### Value-Added Services

We provide **Scan-Free Verification** using computer vision and RFID for high-volume operations. The system can identify products and locations without manual scanning in appropriate environments.

Our **Device Health Monitoring** tracks scanner performance, battery levels, and error rates to predict maintenance needs and prevent operational disruptions.

We also include **Scanner Optimization** that adjusts scan sensitivity and confirmation settings based on product characteristics and environmental conditions.

---

### 13. Cargo Storage and Others Charges

#### Evidence

Flexible storage charging supports multiple calculation methods including per pallet, per CBM, per weight, or per carton. Tiered rates accommodate volume discounts or premium pricing for special storage conditions. Minimum charges ensure that small shipments cover basic handling costs.

Storage calculations automatically post to FMS with detailed breakdown by charge type and billing period, eliminating manual billing preparation and ensuring complete charge capture.

Rate management maintains multiple rate cards for different customer categories, contract types, and service levels.

This charging flexibility is evidenced in **Annex E.30, Page 169** with the Storage Charge Engine showing rate configuration options.

#### Value-Added Services

We provide **Dynamic Rate Optimization** that adjusts storage rates based on utilization and demand patterns. Premium pricing for high-demand periods and incentives for off-peak storage improve revenue and space utilization.

Our **Cost-to-Serve Analytics** breaks down true costs by customer and product, enabling accurate profitability analysis and informed pricing decisions.

We also include **Automated Surcharge Application** that calculates and applies appropriate surcharges for special storage conditions, hazardous materials, or value-added services.

---

### 14. System Generate Gate Pass

#### Evidence

Auto-generated gate passes for cargo release include all required information such as shipment details, destination, authorized vehicle, and security validation. Barcode or QR code on the gate pass enables scanner validation at exit gates, ensuring that only authorized cargo leaves the facility.

Digital signature capture on mobile devices provides proof of delivery with automatic email notification to customers confirming release.

Gate pass history maintains complete records of all cargo movements for security and audit purposes.

This gate pass generation is evidenced in **Annex E.31, Page 170** with Gate Pass Sample showing auto-generated documentation.

#### Value-Added Services

We provide **Vehicle Validation Integration** that verifies vehicle and driver credentials against authorized lists before release, preventing unauthorized pickups.

Our **Gate Pass Analytics** track throughput times, identify bottlenecks, and optimize gate operations for faster cargo flow.

We also include **Mobile Gate Pass** that sends digital passes directly to driver smartphones, eliminating paper and speeding up processing.

---

### 15. Inventory Management

#### Evidence

Real-time inventory tracking maintains accurate records of all inventory with status indicators showing available, allocated, quarantine, or damaged quantities. Full attribute support includes lot numbers, serial numbers, batch numbers, and expiry dates for products requiring traceability.

Automated reorder alerts notify purchasing staff when inventory falls below reorder points. Cycle counting schedules maintain inventory accuracy above 99.5% through systematic counting programs.

Inventory inquiries provide instant visibility of stock levels by location, status, and attribute, supporting customer service and operational planning.

This inventory management is evidenced in **Annex E.32, Page 171** with the Inventory Management UI showing real-time tracking capabilities.

#### Value-Added Services

We provide **Inventory Optimization AI** that recommends optimal stock levels based on demand variability, service level targets, and carrying costs. The system balances inventory investment against stockout risk.

Our **Expiry Management Automation** proactively manages products approaching expiration, prioritizing fulfillment of at-risk inventory and alerting staff to items requiring attention.

We also include **Demand Sensing** that detects demand shifts in real-time and recommends inventory adjustments before stockouts or excess situations develop.

---

### 16. Receiving & Inbound Processing

#### Evidence

Advance Ship Notice (ASN)-based receiving validates incoming shipments against expected receipts, flagging discrepancies for immediate attention. Barcode verification confirms that received quantities match purchase order quantities, ensuring accurate inventory records.

Automatic discrepancy reporting generates exception records when actual receipts differ from expected quantities, triggering supplier follow-up and accounting adjustments.

Put-away task generation suggests optimal storage locations based on product attributes, warehouse zoning rules, and current space availability.

This receiving capability is evidenced in **Annex E.33, Page 172** with the Receiving Workflow showing inbound processing steps.

#### Value-Added Services

We provide **Dynamic Appointment Scheduling** that optimizes receiving dock utilization and labor planning based on expected volumes and processing requirements.

Our **Quality Hold Automation** routes suspect products to inspection areas based on configurable criteria such as supplier history, product type, or damage indicators.

We also include **Cross-Dock Identification** that flags cross-dock opportunities during receiving, enabling direct transfer to shipping without put-away.

---

### 17. Put-Away Management

#### Evidence

Intelligent put-away engine analyzes product dimensions, weight, velocity, and storage class to recommend optimal storage locations. The system considers warehouse zoning rules, current space availability, and proximity to shipping areas.

Manual override capability allows experienced warehouse staff to adjust recommendations based on operational knowledge or special circumstances.

Real-time location updates as tasks are completed via RF scanners ensure that inventory records are always accurate and current.

This put-away management is evidenced in **Annex E.34, Page 173** with the Put-away Rules Engine showing location assignment logic.

#### Value-Added Services

We provide **Congestion-Aware Routing** that adjusts put-away paths based on current warehouse activity levels, avoiding congested areas and optimizing travel time.

Our **Seasonal Slotting Recommendations** proactively suggest layout adjustments for seasonal demand fluctuations, ensuring that high-velocity items are optimally positioned.

We also include **Automated Replenishment** that triggers forward-pick location restocking from reserve inventory based on minimum/maximum levels.

---

### 18. Storage & Location Management

#### Evidence

Visual warehouse map displays configurable zones, aisles, racks, and bins supporting multiple location types including bulk storage, pick-faces, cold storage, and hazardous material areas. Color-coding indicates location status (empty, occupied, reserved, blocked).

Location utilization reports identify space optimization opportunities, highlighting underutilized areas or capacity constraints.

Location master data maintains physical characteristics including dimensions, weight capacity, and environmental controls for each storage position.

This location management is evidenced in **Annex E.35, Page 174** with the Warehouse Map View showing visual location management.

#### Value-Added Services

We provide **Space Utilization Forecasting** that predicts future capacity needs based on growth trends, seasonality, and incoming shipment schedules.

Our **Slotting Simulation** allows testing of layout changes before implementation, modeling the impact on pick efficiency and space utilization.

We also include **Location Optimization AI** that continuously analyzes inventory movement patterns and recommends layout adjustments for improved efficiency.

---

### 19. Order Management & Picking

#### Evidence

Advanced picking methods include single order picking, batch picking for multiple orders simultaneously, wave picking for scheduled processing, zone picking for large warehouse operations, and cluster picking for high-density operations. Optimized pick path algorithms minimize travel distance and time.

Barcode verification at pick and pack stages ensures 99.9%+ order accuracy. Error alerts trigger immediate correction when wrong items or quantities are scanned.

Order priority management ensures that urgent orders receive appropriate processing priority while maintaining efficiency for standard orders.

This picking capability is evidenced in **Annex E.36, Page 175** with the Picking Optimization Demo showing various picking methods.

#### Value-Added Services

We provide **Pick Path AI** that continuously optimizes routes based on real-time inventory positions, order mix, and warehouse conditions.

Our **Labor Balancing** automatically distributes work across zones to minimize idle time and congestion while ensuring fair workload distribution.

We also include **Pick-to-Light Integration** support for high-velocity operations, enabling rapid, accurate picking with minimal training requirements.

---

### 20. Packing & Shipping

#### Evidence

Cartonization engine calculates optimal packing configurations based on product dimensions, weight, fragility, and shipping requirements. The system recommends box sizes, packing materials, and arrangement patterns to minimize shipping costs while protecting products.

Shipping label generation includes all required carrier information, routing codes, and tracking numbers. Carrier integration automatically obtains tracking numbers and transmits shipping data to carrier systems.

Packing lists auto-generate with carton-level detail for multi-carton shipments, ensuring that customers can verify receipt of complete orders.

This packing capability is evidenced in **Annex E.37, Page 176** with the Packing Workflow showing cartonization and label generation.

#### Value-Added Services

We provide **Packaging Optimization AI** that recommends packaging materials and configurations to minimize cost and damage risk based on product characteristics and shipping conditions.

Our **Carrier Selection Automation** chooses optimal carriers based on cost, service level, capacity, and customer preferences.

We also include **Shipment Consolidation** that identifies opportunities to combine orders for the same customer or destination, reducing shipping costs.

---

### 21. Returns (RMA) Management

#### Evidence

Returns processing workflow manages the complete RMA lifecycle from customer authorization through final disposition. Receipt inspection includes condition assessment categorizing returns as resellable, damaged requiring repair, or scrap requiring disposal.

Automatic inventory adjustment updates stock records based on return disposition. Integration with FMS handles credit note generation for customer returns, ensuring proper financial processing.

RMA analytics track return rates by customer, product, and reason, identifying quality issues or customer service opportunities.

This returns management is evidenced in **Annex E.38, Page 177** with the Returns Management UI showing RMA processing.

#### Value-Added Services

We provide **Return Reason Analytics** that identifies patterns in returns to address root causes such as quality issues, shipping damage, or order errors.

Our **Disposition Optimization** recommends optimal handling for returned products based on condition, demand, and cost considerations.

We also include **Return Prevention Alerts** that flag customers or products with high return rates for proactive intervention.

---

### 22. Cycle Counting & Physical Inventory

#### Evidence

Flexible cycle counting supports ABC classification focusing frequent counts on high-value items, random selection for continuous verification, and triggered counts when system events suggest potential discrepancies. Blind count option hides system quantities from counters to ensure unbiased counting.

Variance reporting highlights differences between counted and system quantities, triggering supervisor review and investigation. Adjustment workflows with approval controls ensure that inventory corrections are properly authorized.

Full audit trail maintains records of all counts, variances, and adjustments for compliance and analysis.

This counting capability is evidenced in **Annex E.39, Page 178** with the Cycle Count Module showing counting methods and variance handling.

#### Value-Added Services

We provide **Intelligent Count Scheduling** that optimizes count timing based on transaction patterns, risk indicators, and resource availability.

Our **Variance Root Cause Analysis** automatically investigates count discrepancies to identify systemic issues such as process gaps or training needs.

We also include **Drone Inventory Counting** integration for automated cycle counting using autonomous drones with computer vision, reducing counting time and improving accuracy.

---

### 23. Labor & Task Management

#### Evidence

Task assignment engine allocates work based on operator skills, certifications, location proximity, and current workload. Real-time progress tracking shows task completion rates, queue depths, and productivity metrics.

Performance metrics track picks per hour, accuracy rates, and time per task for productivity analysis and performance management.

Labor forecasting helps plan staffing levels based on expected workload, ensuring adequate resources during peak periods while controlling costs during slower times.

This labor management is evidenced in **Annex E.40, Page 179** with the Labor Management Dashboard showing task allocation and performance tracking.

#### Value-Added Services

We provide **Skills-Based Routing** that assigns tasks based on operator certifications, experience levels, and training status.

Our **Performance Coaching AI** generates personalized improvement recommendations for each operator based on their specific performance patterns.

We also include **Labor Optimization** that recommends optimal staffing levels and shift patterns based on demand forecasts and productivity data.

---

### 24. Multi-Warehouse Support

#### Evidence

Single platform manages multiple warehouse facilities with consolidated inventory visibility across all locations. Inter-warehouse transfer orders support stock movements between facilities with full tracking and costing.

Branch-specific configurations accommodate different operational requirements per site, including layout, processes, rate structures, and customer assignments.

Global inventory inquiries show stock availability across the entire network, supporting sourcing decisions and stock balancing.

This multi-warehouse capability is evidenced in **Annex E.41, Page 180** with the Multi-Warehouse View showing consolidated network visibility.

#### Value-Added Services

We provide **Network Optimization** that recommends optimal sourcing warehouse based on inventory availability, cost, and delivery requirements.

Our **Transfer Automation** streamlines inter-warehouse replenishment based on demand signals and stock balancing algorithms.

We also include **Network Analytics** that optimize inventory positioning across the warehouse network to minimize total logistics costs.

---

### 25. Document Creation

#### Evidence

Auto-generation of warehouse documents includes pick lists, packing slips, bills of lading, and shipping labels with customizable templates. Documents support barcode/QR codes for automated processing and tracking.

Template customization allows branding, formatting, and field configuration to meet specific customer or regulatory requirements.

Document versioning maintains history of template changes, ensuring that document formats can be audited and rolled back if needed.

This document creation is evidenced in **Annex E.42, Page 181** with Document Templates showing auto-generation capabilities.

#### Value-Added Services

We provide **Dynamic Document Assembly** that customizes documents based on customer requirements, destination regulations, and shipment characteristics.

Our **Digital Signature Integration** enables paperless document execution with legal validity, reducing paper handling and processing time.

We also include **Multi-Language Document** support for international shipments, automatically generating documents in appropriate languages.

---

### 26. Scalability & Flexibility for Future Technology

#### Evidence

Modular architecture supports integration with automation technologies including Automated Guided Vehicles (AGVs), Autonomous Mobile Robots (AMRs), voice picking systems, and RFID without requiring changes to core system functionality. APIs and integration frameworks enable connection to emerging technologies as they become available.

The data platform supports AI/ML applications for demand forecasting, inventory optimization, and predictive analytics, ensuring that MMF can leverage advanced analytics without system replacement.

Cloud-native architecture enables scaling of compute and storage resources to handle growth and seasonal peaks.

This future-proofing is evidenced in **Annex A, Page 15** with the Future Tech Roadmap showing planned technology integrations.

#### Value-Added Services

Beyond future-proofing, we provide **Drone Inventory Counting Integration** that automates cycle counting using autonomous drones equipped with computer vision, reducing counting time by 75% while improving accuracy.

Our **Augmented Reality (AR) Picking Module** overlays picking instructions directly onto warehouse operators' field of view through smart glasses, reducing training time by 60% and virtually eliminating picking errors.

We also include **Robotics Orchestration Platform** that manages mixed fleets of AGVs, AMRs, and robotic arms from different vendors through a single interface, future-proofing MMF's automation investments.

---

### 27. Report and Enquiry

#### Evidence

Comprehensive reporting suite includes inventory reports, inbound/outbound analysis, warehouse operations metrics, financial/billing reports, and compliance documentation with 50+ standard templates. Custom report builder and enquiry screens provide flexible data access without IT dependency.

Report scheduling automatically distributes reports to stakeholders on defined schedules. Export capabilities support multiple formats for analysis and distribution.

Drill-down capabilities enable users to navigate from summary reports to detailed transaction data for investigation and analysis.

This reporting is evidenced in **Annex E.43, Pages 182-188** with the WMS Report Catalogue listing all available reports.

#### Value-Added Services

We provide **Executive Warehouse Briefings** that automatically generate summary reports for management review with key metrics, trends, and exception highlights.

Our **Benchmark Reporting** compares MMF's warehouse metrics against industry standards and best practices, identifying improvement opportunities.

We also include **Predictive Warehouse Analytics** that forecast future operational needs based on trends and patterns in historical data.

---

*Annexure C3 contains 27 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 1,100,000.*


## ANNEXURE C4: TERMINAL MANAGEMENT SYSTEM (TMS)

**Location:** Port Klang (PK), Butterworth (BTW)  
**System Version:** LogisticsPro TMS v4.2  
**Terminal Types:** Container Yard, Inland Container Depot (ICD), Rail Terminal  
**Operations:** Container receiving, storage, dispatch, maintenance, and repair

The Terminal Management System (TMS) supports MMF's container terminal operations at Port Klang and Butterworth locations. The system manages the complete container lifecycle from gate-in through yard storage to gate-out, supporting container yards, inland container depots, and rail terminal operations. TMS optimizes yard utilization, streamlines gate operations, and ensures efficient container flows to minimize dwell time and maximize throughput.

---

### 1. Dashboards & Analytics

#### Evidence

The Terminal Operations Dashboard displays real-time yard KPIs critical for terminal management. Container count by status (available, hold, damaged, reserved) provides immediate visibility of yard inventory. Gate throughput metrics track trucks processed per hour, identifying capacity constraints and peak periods. Yard utilization percentage shows available capacity and alerts when thresholds are approached.

Equipment productivity tracking monitors crane moves, forklift operations, and overall equipment effectiveness. Visual indicators highlight bottlenecks such as congested yard areas, equipment downtime, or gate queue buildup requiring management attention.

Trend analysis shows performance over time, enabling identification of operational improvements or deteriorating performance requiring intervention.

This dashboard capability is evidenced in **Annex E.44, Page 189** with the TMS Dashboard Video demonstrating terminal operations visibility.

#### Value-Added Services

We provide **Yard Optimization AI** that continuously analyzes container dwell times, vessel schedules, truck arrival patterns, and yard configuration to dynamically optimize container stacking positions. This intelligent positioning reduces rehandles by 25-35% and improves yard throughput by minimizing unnecessary container movements.

Our **Predictive Gate Congestion Model** forecasts peak arrival times 4-6 hours in advance based on appointment schedules, vessel arrivals, and historical patterns. This enables proactive appointment scheduling and staffing adjustments to minimize truck turnaround times.

Additionally, our **Equipment Telemetry Integration** connects to yard cranes, forklifts, and Rubber-Tyred Gantries (RTGs) to monitor performance metrics, predict maintenance needs, and optimize equipment deployment in real-time.

---

### 2. Multi-Platform Interface

#### Evidence

Multi-platform support addresses the diverse user roles in terminal operations. Desktop interfaces serve control room staff managing overall terminal operations. Tablets support yard supervisors moving throughout the facility. Mobile devices serve gate officers processing truck transactions and equipment operators in cranes and forklifts.

Touch-optimized interfaces accommodate outdoor use in various lighting conditions from bright sunlight to dim yard lighting. Large buttons, high-contrast displays, and simplified screens enable efficient operation while wearing gloves or operating equipment.

Offline capability ensures that critical operations can continue during temporary connectivity interruptions, with automatic synchronization when connections are restored.

This platform support is evidenced in **Annex E.2, Page 126** with the TMS Platform Matrix showing device and interface options.

#### Value-Added Services

We provide **Sunlight-Readable Optimization** that automatically adjusts display settings for outdoor visibility, ensuring that screens remain readable in bright port environments.

Our **Rugged Device Support** includes specialized configurations for harsh terminal environments including dust, moisture, and vibration protection.

We also include **Voice Control Integration** for hands-free operation in equipment cabs, enabling status updates and queries without stopping operations.

---

### 3. Interface with 3rd Party System

#### Evidence

Extensive integration capabilities connect TMS with critical external systems. KTMB integration supports rail operations including schedule coordination, container tracking, and manifest management. PPSB (Penang Port) integration provides port terminal data exchange for Butterworth operations. Customs (KDM) integration supports clearance status verification and regulatory reporting.

Shipping line integrations enable booking validation, vessel schedule access, and container status exchange. Haulage company integrations coordinate container pickup and delivery appointments.

EDI and API support for industry-standard message formats including COPARN (Container Announcement), CODECO (Container Discharge/Load Confirmation), and COARRI (Container Arrival/Departure Notice) ensures seamless partner communication.

This integration capability is evidenced in **Annex F.6, Page 175** with the TMS Integration Specs showing supported systems and protocols.

#### Value-Added Services

We provide **Real-Time Vessel Tracking** integration that updates container availability based on actual vessel arrival times, ensuring accurate appointment scheduling and reducing truck waiting times.

Our **Port Community System Synchronization** maintains real-time data alignment with port authorities, ensuring compliance with port regulations and efficient coordination with port operations.

We also include **Partner Performance Analytics** that track shipping line and haulier performance, supporting data-driven decisions about partner relationships and service agreements.

---

### 4. TMS Able to Link with Other Business System

#### Evidence

Real-time data exchange with HMS enables coordination between terminal operations and haulage scheduling. Container availability information flows to haulage dispatchers, while truck arrival updates help terminal planners optimize gate processing.

FFS integration supports freight forwarding coordination, ensuring that container movements align with shipment schedules and customer requirements.

FMS integration ensures that all terminal charges including storage, handling, and lifting fees automatically flow to billing, eliminating manual charge capture and ensuring complete revenue recognition.

Container status updates propagate automatically to connected systems, ensuring consistent information across all business units and customer-facing systems.

This integration is evidenced in **Annex F.3, Page 172** with the TMS Integration Architecture showing data flows between systems.

#### Value-Added Services

We provide **Synchronized Container Planning** that coordinates terminal operations with haulage scheduling to minimize container dwell time and truck turnaround.

Our **Revenue Leakage Prevention** ensures that all chargeable events including storage, handling, and special services are captured and billed accurately.

We also include **Integrated Appointment Management** that coordinates appointments across terminal, haulage, and customer systems to optimize container flows.

---

### 5. User-Friendly Interface

#### Evidence

Terminal-optimized UI features visual yard maps showing container locations by zone, block, and position. Color-coded container status indicators enable quick identification of available containers, holds, damages, or special handling requirements.

Simplified data entry screens support high-volume gate operations with minimal keystrokes. Touch-friendly design enables rapid transaction processing during peak hours when gate queues must be processed quickly.

Role-based interfaces present appropriate functions for gate clerks, yard planners, equipment operators, and supervisors, reducing complexity and training requirements.

This usability is evidenced in **Annex E.45, Page 190** with the TMS UI Walkthrough showing terminal-optimized interfaces.

#### Value-Added Services

We provide **Role-Based Workspaces** optimized for gate clerks, yard planners, and equipment operators with quick-access functions for their primary tasks.

Our **Gesture Navigation** enables rapid status updates for mobile users through simple swipe and tap gestures.

We also include **Contextual Help** that provides guidance specific to terminal operations including trade lane requirements, customs procedures, and safety protocols.

---

### 6. Automated Invoice & Receipts Generation

#### Evidence

Automated billing for terminal operations includes storage charges calculated based on dwell time from gate-in to gate-out, handling charges for moves within the terminal, and lifting charges for container transfers. Configurable rate structures accommodate different rates by container size, type, customer contract, and validity period.

Full IRBM e-Invoicing compliance with MyInvois integration ensures that terminal billing meets Malaysian tax requirements for all customers.

Automatic rate expiry alerts ensure that billing uses current rates, preventing revenue leakage from outdated pricing.

This billing capability is evidenced in **Annex E.4, Pages 128-130** with Terminal Billing Samples showing storage and handling charge calculations.

#### Value-Added Services

We provide **Complex Tariff Management** that handles multi-tiered storage rates, free time allowances, and special charges for hazardous cargo or special equipment.

Our **Invoice Validation AI** ensures billing accuracy before invoice generation, checking for correct rates, complete charge capture, and proper customer assignments.

We also include **Customer Billing Portal** that allows terminal customers to view their charges, access invoices, and download supporting documentation.

---

### 7. Credit & Collections Management

#### Evidence

Integrated credit management ensures that container release authorization checks credit status across all MMF systems. A customer with outstanding invoices in any business unit cannot remove containers from the terminal until credit issues are resolved.

Automated invoicing and collection workflows with customized dunning procedures address the unique billing cycles and customer relationships of terminal operations.

Credit hold visibility across gate operations ensures consistent enforcement and prevents unauthorized container release.

This credit management is evidenced in **Annex E.5, Page 131** with Terminal Credit Controls showing integrated credit enforcement.

#### Value-Added Services

We provide **Release Authorization Automation** that coordinates credit status with physical gate controls, preventing container removal for customers exceeding credit limits.

Our **Terminal-Specific Collection Workflows** accommodate the unique billing cycles of terminal operations with appropriate escalation procedures.

We also include **Cash Deposit Management** for customers without credit terms, tracking deposits against charges and alerting when replenishment is needed.

---

### 8. Automated Locking for Overdue Customer

#### Evidence

System blocks container release for customers exceeding credit limits with override capability requiring dual authorization from appropriate managers. Credit hold status is visible across gate operations, customer service, and management dashboards ensuring consistent communication.

Partial payment options allow customers to pay for specific containers while maintaining holds on others, providing flexibility for partial settlement situations.

All credit hold actions are logged with complete audit trails supporting compliance and dispute resolution.

This locking mechanism is evidenced in **Annex E.6, Page 132** with the Release Authorization Matrix showing credit enforcement workflows.

#### Value-Added Services

We provide **Graduated Release Controls** that allow partial container access for partial payments, maintaining cash flow while preserving customer relationships.

Our **Automated Hold Notifications** inform customers and agents proactively when credit holds are applied, explaining reasons and required actions.

We also include **Credit Recovery Workflows** that systematically manage collection efforts for terminal customers with overdue balances.

---

### 9. Audit Trail & History

#### Evidence

Complete container lifecycle tracking captures every movement, inspection, and transaction from gate-in to gate-out with user identification and timestamp. Full audit trail supports compliance with customs regulations, shipping line requirements, and internal controls.

Container history inquiries provide instant access to complete records including gate-in details, yard movements, inspections, maintenance activities, and gate-out information.

Audit trails support dispute resolution with customers, shipping lines, and haulage companies by providing irrefutable records of terminal activities.

This audit capability is evidenced in **Annex D.2, Page 98** with the Container History Sample showing complete lifecycle tracking.

#### Value-Added Services

We provide **Container Journey Visualization** that creates timeline views of container movements for customer service and dispute resolution.

Our **Dispute Evidence Package** automatically compiles relevant audit data, photos, and documentation for customer or partner disputes.

We also include **Compliance Reporting Automation** that generates regulatory reports from audit trail data for customs and port authority requirements.

---

### 10. Ability of the System to Support Attachment Documents

#### Evidence

Document management supports terminal operations including gate passes, damage photos, inspection reports, repair estimates, and customs documentation. Automatic linking to container records ensures that all documentation is organized and easily retrievable.

High-resolution photo storage supports damage claims with detailed evidence of container condition at various points in the terminal lifecycle.

Document access controls ensure that sensitive information is only available to authorized users while supporting customer and partner inquiries.

This document management is evidenced in **Annex E.7, Page 133** with TMS Document Management showing document organization and retrieval.

#### Value-Added Services

We provide **Damage Assessment AI** that analyzes photos to categorize damage severity and estimate repair costs automatically.

Our **Document Lifecycle Management** automates retention and disposal according to regulatory requirements and internal policies.

We also include **Blockchain Document Verification** that creates tamper-proof records of container condition documentation for dispute resolution.

---

### 11. Comprehensive Security Features

#### Evidence

Enterprise security ensures appropriate access for different terminal roles. Gate staff access transaction processing and validation functions. Yard operators access container location and movement functions. Managers access reporting, analytics, and administrative functions.

Data protection follows the same robust framework as other modules with encryption, MFA, and comprehensive security auditing. Physical security integration can coordinate system access with terminal access controls.

Audit logging captures all system access and activities for security monitoring and compliance verification.

This security is evidenced in **Annex D, Pages 95-110** with the TMS Security Configuration showing access controls and protection measures.

#### Value-Added Services

We provide **Physical-Digital Security Integration** that coordinates system access with physical access controls, ensuring that users can only access terminal areas appropriate to their system permissions.

Our **Surveillance System Integration** links container events with CCTV timestamps for security review and incident investigation.

We also include **Anomaly Detection** that flags unusual access patterns or activities that may indicate security concerns.

---

### 12. Yard Module

#### Evidence

Visual yard management displays the digital layout showing zones, blocks, rows, and slots with real-time occupancy status. Containers are displayed in their actual positions with status indicators showing availability, holds, or damage conditions.

Automatic container slotting optimizes yard space utilization while supporting manual placement for operational needs such as proximity grouping or special handling requirements.

Yard search functions enable quick location of specific containers by number, booking reference, or customer.

This yard management is evidenced in **Annex E.46, Page 191** with the Yard Module Demo showing visual yard management.

#### Value-Added Services

We provide **3D Yard Visualization** for optimal space planning and rehandle minimization, showing stacking positions and accessibility.

Our **Heat Map Analytics** identify high-activity zones and congestion points for operational planning and yard layout optimization.

We also include **Rehandle Prediction** that forecasts required moves based on departure schedules and current stacking positions.

---

### 13. Container Turn In

#### Evidence

Streamlined gate-in process captures container details through manual entry, EDI from shipping lines, or file upload. Automatic validation against bookings ensures that only expected containers are accepted and identifies discrepancies for review.

Shipping agent portal allows authorized amendments to booking details with complete audit trail, enabling corrections while maintaining security.

Condition capture at gate-in documents container status on arrival, providing baseline for damage claims and repair billing.

This gate-in process is evidenced in **Annex E.47, Page 192** with the Gate-In Process Flow showing container receiving procedures.

#### Value-Added Services

We provide **Pre-Arrival Processing** that prepares gate transactions before truck arrival, reducing processing time and gate congestion.

Our **Condition Assessment Integration** captures and records container condition at turn-in using photo documentation and damage classification.

We also include **Automated Booking Validation** that checks container details against shipping line bookings in real-time.

---

### 14. Container Turn Out

#### Evidence

Gate-out processing validates container release against authorized bookings, ensuring that only properly authorized containers leave the terminal. Automatic gate pass generation provides documentation for the truck driver. Customs clearance checks verify that regulatory requirements are met before release.

Real-time inventory updates trigger billing calculations for storage and handling charges at the moment of release.

Security validation ensures that releasing personnel have appropriate authority and that all required checks are completed.

This gate-out process is evidenced in **Annex E.48, Page 193** with the Gate-Out Process Flow showing container release procedures.

#### Value-Added Services

We provide **Exit Queue Optimization** that sequences outbound traffic to minimize congestion and improve truck turnaround times.

Our **Haulier Notification Automation** alerts drivers when containers are ready for pickup, reducing unnecessary trips and waiting time.

We also include **Gate Pass Mobile Delivery** that sends digital gate passes directly to driver smartphones.

---

### 15. Container Tracking

#### Evidence

Real-time container location tracking within the yard shows current position by zone, block, and slot. Movement history shows the complete sequence of yard movements from initial placement through any relocations to final dispatch.

Dwell time calculation tracks how long containers remain in the terminal, enabling storage billing and performance analysis.

Yard inventory enquiries provide instant visibility of container status, location, and storage duration for customer service and operations.

This tracking capability is evidenced in **Annex E.49, Page 194** with the Container Tracking View showing yard location visibility.

#### Value-Added Services

We provide **Dwell Time Analytics** that identify containers approaching free time expiration, enabling proactive customer notification and detention billing.

Our **Rehandle Prediction** forecasts required moves based on departure schedules, supporting yard planning and resource allocation.

We also include **Container Availability Forecasting** that predicts when containers will be available for release based on customs clearance and haulage scheduling.

---

### 16. Container Putaway/Stacking

#### Evidence

Intelligent yard slotting algorithm recommends optimal stacking locations based on container attributes (size, type, weight), departure schedule, vessel or train connection, and yard constraints such as weight limits or hazardous material segregation.

Digital yard map with mobile device integration enables yard crane operators to receive instructions and confirm placements in real-time.

Manual override capability allows experienced yard planners to adjust recommendations based on operational knowledge or changing conditions.

This slotting capability is evidenced in **Annex E.50, Page 195** with the Yard Slotting Engine showing intelligent positioning logic.

#### Value-Added Services

We provide **Dynamic Stack Optimization** that continuously adjusts recommendations based on changing conditions including new arrivals, departures, and priority changes.

Our **Rehandle Minimization AI** prioritizes stacking positions to minimize future moves, optimizing yard efficiency.

We also include **Equipment Integration** that sends slotting instructions directly to crane operator displays for efficient execution.

---

### 17. Container Damage Repair

#### Evidence

Damage inspection workflow captures damage details with photo documentation and classification by type and severity. Automatic repair estimate generation provides cost projections based on damage classification and repair rates.

Maintenance and Repair (M&R) tracking monitors repair status from identification through completion, tracking costs accumulated and managing documentation for insurance claims.

Repair history maintains complete records for each container, supporting lease-end negotiations and resale decisions.

This repair tracking is evidenced in **Annex E.51, Page 196** with the Damage Repair Module showing M&R management.

#### Value-Added Services

We provide **Repair Cost Benchmarking** that compares estimates against industry standards and historical data for validation.

Our **Insurance Claim Automation** prepares claim packages with supporting documentation, photos, and cost estimates for efficient processing.

We also include **Damage Prevention Analytics** that identify patterns in damage causes to support prevention initiatives.

---

### 18. Container Railing

#### Evidence

Rail operations module manages container movements via KTMB with batch upload capability for manifest data. Integration with KTMB systems provides real-time rail schedule visibility, enabling coordination of container delivery with train departures.

Container tracking follows movements from yard to rail wagon, in-transit tracking, and destination terminal arrival.

Rail billing integration ensures that rail-related charges are captured and invoiced appropriately.

This rail operations capability is evidenced in **Annex E.52, Page 197** with the Rail Operations UI showing KTMB integration.

#### Value-Added Services

We provide **Intermodal Optimization** that coordinates rail and truck movements for cost-effective container positioning across MMF's network.

Our **Rail Schedule Integration** automatically updates ETAs based on real-time rail operations and provides alerts for schedule changes.

We also include **Rail Capacity Planning** that forecasts rail container volumes and coordinates with KTMB for capacity allocation.

---

### 19. Gate Module

#### Evidence

Integrated gate operations include weighbridge integration for accurate weight capture and customs system integration for KDM (Kastam Di Malaysia) verification. Automated gate pass validation ensures that only authorized containers and trucks pass through the gate.

Gate transaction processing handles both import (turn-out) and export (turn-in) containers with appropriate validations and documentation for each flow.

Queue management helps optimize truck flow through the gate, minimizing waiting times and maximizing throughput.

This gate integration is evidenced in **Annex E.53, Page 198** with the Gate Module Integration showing weighbridge and customs connectivity.

#### Value-Added Services

We provide **Gate Throughput Optimization** that analyzes traffic patterns to recommend staffing levels and lane configurations for peak efficiency.

Our **Automated Exception Handling** routes discrepancies to appropriate personnel without manual intervention, speeding up resolution.

We also include **Truck Appointment Integration** that coordinates gate arrivals with terminal capacity, reducing congestion and wait times.

---

### 20. System Generated Gatepass

#### Evidence

Automatic gate pass generation includes unique serial numbers for tracking, barcode or QR codes for scanner validation, and all required container and customs information. Gate passes serve as authorization for truck entry/exit and documentation for regulatory compliance.

Digital gate pass capabilities reduce paperwork and speed up gate processing while maintaining security and audit requirements.

Gate pass validation at exit points ensures that only properly authorized containers leave the terminal.

This gate pass generation is evidenced in **Annex E.54, Page 199** with the Gate Pass Sample showing auto-generated documentation.

#### Value-Added Services

We provide **Mobile Gate Pass** delivery directly to driver smartphones, eliminating paper handling and speeding up processing.

Our **Gate Pass Fraud Prevention** includes verification mechanisms such as digital signatures and QR code validation to prevent unauthorized duplication.

We also include **Gate Pass Analytics** tracking generation, usage, and validation patterns for operational optimization.

---

### 21. Online Request Submission/Tracking

#### Evidence

Online booking system validates requests against vessel schedules, ensuring that containers are delivered in time for vessel loading. Automatic rejection for requests within 48 hours of closing prevents operational disruptions from late deliveries.

Suspended customer or agent blocking ensures compliance with credit and operational policies, preventing unauthorized transactions.

Appointment scheduling coordinates truck arrivals with terminal capacity, optimizing gate throughput and yard operations.

This online booking capability is evidenced in **Annex E.55, Page 200** with the Online Booking Portal showing customer self-service capabilities.

#### Value-Added Services

We provide **Capacity-Based Booking** that adjusts availability based on yard utilization, preventing overbooking and congestion.

Our **Haulier Performance Integration** considers historical performance in booking approvals, prioritizing reliable partners during capacity constraints.

We also include **Dynamic Pricing** that adjusts storage and handling rates based on demand and capacity utilization.

---

### 22. System Integration

#### Evidence

Comprehensive integration includes weighbridge systems for weight capture, EDI with shipping agents for container movement notifications, and PPSB for port data exchange. API gateway enables future integrations with emerging terminal technologies.

Integration monitoring tracks all interface performance, alerting on failures and ensuring data synchronization across systems.

Standard message formats ensure compatibility with industry partners and support future expansion.

This system integration is evidenced in **Annex F.6, Page 175** with the TMS System Integration Map showing all connected systems.

#### Value-Added Services

We provide **Integration Health Monitoring** that tracks all interface performance with proactive alerting for anomalies or failures.

Our **API Analytics** provide insights into integration usage patterns, supporting optimization and capacity planning.

We also include **Future Technology Readiness** with APIs and integration frameworks prepared for emerging terminal technologies.

---

### 23. APAD Requirements

#### Evidence

Full APAD (Approved Permit for Aircargo and Depot) compliance includes pre-arrival booking system for hauliers to schedule container deliveries and pickups. Real-time Turnaround Time (TAT) tracking from gate arrival to departure measures and optimizes truck processing efficiency. Advance notification system alerts terminal operations to expected container drop-offs and pick-ups, enabling resource planning.

APAD reporting generates required compliance reports with complete audit trails of terminal activities.

Integration with customs and port systems ensures regulatory compliance for all terminal operations.

This APAD compliance is evidenced in **Annex E.56, Page 201** with the APAD Compliance Report showing regulatory adherence.

#### Value-Added Services

Beyond APAD compliance, we provide **Haulier Performance Scoring** that tracks and benchmarks individual haulier performance including on-time arrivals, document accuracy, and compliance. This enables MMF to identify top performers and negotiate preferential rates.

Our **Carbon Footprint Tracking** calculates and reports CO2 emissions for every container movement, supporting MMF's sustainability goals and enabling green shipping certifications.

We also include **Inter-Terminal Optimization** that coordinates container flows between Port Klang and Butterworth terminals to minimize empty runs and maximize asset utilization across MMF's network.

---

### 24. Rate

#### Evidence

Flexible rate management supports multiple charge types including storage, handling, lifting, and ancillary services. Customizable rates by container size, type, customer contract, and validity period accommodate diverse customer agreements.

Automatic rate expiry alerts ensure that billing uses current rates, preventing revenue leakage from outdated pricing.

Rate history maintains records of all rate changes with audit trails for compliance and dispute resolution.

This rate management is evidenced in **Annex E.57, Page 202** with the Terminal Rate Management showing rate configuration.

#### Value-Added Services

We provide **Market Rate Intelligence** that suggests competitive rate adjustments based on market conditions and competitor pricing.

Our **Rate Profitability Analysis** forecasts margin impact of rate changes before implementation.

We also include **Automated Rate Updates** that implement rate changes across the system on effective dates, eliminating manual update processes.

---

### 25. Report and Enquiry

#### Evidence

Comprehensive reporting includes container inventory, gate activity, yard operations, M&R, financial/billing, and compliance reports with 40+ standard templates. Enquiry screens provide instant access to container status and history.

Custom report builder enables creation of specialized reports without IT assistance. Scheduled report distribution automates delivery to stakeholders.

Export capabilities support multiple formats for analysis, distribution, and regulatory submission.

This reporting is evidenced in **Annex E.58, Pages 203-206** with the TMS Report Library listing all available reports.

#### Value-Added Services

We provide **Terminal Performance Benchmarking** that compares MMF's terminal metrics against industry standards and best practices.

Our **Predictive Capacity Planning** forecasts yard space requirements based on scheduled arrivals and departures, supporting resource planning.

We also include **Executive Terminal Briefings** that automatically generate summary reports for management review with key metrics and trends.

---

*Annexure C4 contains 25 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 950,000.*


## ANNEXURE C5: FINANCE MANAGEMENT SYSTEM (FMS)

**Location:** ALL Branches (Headquarters, Global Logistics Dept, Port Klang, Pasir Gudang, Butterworth, Padang Besar)  
**System Version:** LogisticsPro FMS v4.2  
**Accounting Standards:** MFRS compliant, IRBM e-Invoicing ready  
**Coverage:** General ledger, accounts receivable, accounts payable, fixed assets, financial reporting

The Finance Management System (FMS) provides comprehensive financial management across all MMF branches and business units. The system ensures compliance with Malaysian Financial Reporting Standards (MFRS) and IRBM e-Invoicing requirements while supporting multi-currency, multi-company, and multi-branch operations. FMS integrates seamlessly with operational systems to provide real-time financial visibility and automated transaction processing.

---

### 1. Dashboard - Real Time Reporting

#### Evidence

The Financial Command Centre provides executives and finance managers with real-time visibility into cash flow, revenue, expenses, and profitability across all branches. The dashboard displays current cash positions, outstanding receivables, payables aging, and profitability by business unit, branch, and customer segment.

Visual KPIs include budget versus actual comparisons, financial ratio analysis (liquidity, profitability, efficiency ratios), and trend analysis showing performance over time. Drill-down capability enables navigation from summary views to individual transaction details for variance investigation.

Export capabilities support distribution of financial information to stakeholders and regulatory submissions.

This dashboard capability is evidenced in **Annex E.59, Page 207** with the FMS Dashboard Video demonstrating financial visibility.

#### Value-Added Services

We provide **AI-Powered Cash Flow Forecasting** that analyzes historical patterns, seasonal trends, pipeline data, and payment behavior to predict cash positions 90 days forward with 94% accuracy. This enables proactive working capital management, early identification of cash shortfalls, and optimization of investment and borrowing decisions.

Our **Fraud Detection Engine** uses machine learning to identify anomalous transactions, duplicate invoices, suspicious payment patterns, and unusual journal entries in real-time. The system automatically flags high-risk items for review, reducing fraud risk and strengthening internal controls.

Additionally, our **Automated Financial Consolidation** eliminates manual spreadsheet work for month-end closing. Intercompany eliminations, currency conversions, and consolidation adjustments are handled automatically, reducing consolidation time from days to hours while improving accuracy.

---

### 2. Multi-Platform Interface

#### Evidence

Web-based interface accessible from any device with a browser ensures that the finance team can work from office, home, or while traveling. Responsive design adapts to desktop monitors, laptops, tablets, and smartphones, providing appropriate functionality for each device type.

Mobile app provides approval workflows for managers who need to authorize transactions, expenses, or journal entries while away from the office. Alert notifications for critical financial events ensure that important items receive timely attention regardless of location.

Security measures including MFA and session management protect financial data across all access methods.

This platform support is evidenced in **Annex E.2, Page 126** with the FMS Platform Matrix showing device compatibility.

#### Value-Added Services

We provide **Executive Mobile Cockpit** with key financial KPIs optimized for smartphone viewing. Executives can monitor cash position, receivables, and profitability while on the move.

Our **Offline Approval Capability** allows critical approvals even without connectivity, with automatic synchronization when connection is restored.

We also include **Push Notification Intelligence** that learns user preferences and priorities to deliver relevant alerts without overwhelming users with unnecessary notifications.

---

### 3. FMS Able to Link with Other Business System

#### Evidence

Native integration with HMS, FFS, WMS, and TMS enables automatic posting of operational transactions to the General Ledger without manual data entry. When a shipment is delivered, haulage job completed, or warehouse service rendered, the financial impact is automatically recorded.

Real-time synchronization ensures that financial reports always reflect current operational activity. There is no delay or batch processing lag—financial data is current as of the moment of inquiry.

Integration validation ensures that operational data is complete and accurate before financial posting, preventing errors and reconciliation issues.

This integration is evidenced in **Annex F.3, Page 172** with the FMS Integration Architecture showing data flows from operational systems.

#### Value-Added Services

We provide **Unified Financial View** that consolidates data from all operational systems into a single financial dashboard. This eliminates the need to check multiple systems for complete financial information.

Our **Exception-Based Reconciliation** automatically identifies and flags discrepancies between operational and financial records, highlighting items requiring investigation.

We also include **Real-Time Financial Impact Analysis** that shows how operational events immediately affect financial position, supporting informed decision-making.

---

### 4. User-Friendly Interface

#### Evidence

Accounting interface designed for both finance professionals and operational users provides appropriate functionality for each audience. Simplified screens for common tasks enable operational staff to perform necessary financial functions without extensive accounting training. Advanced features for complex transactions support professional accountants in their work.

Contextual help and validation messages guide users through proper accounting procedures, reducing errors and ensuring compliance. Field-level help explains accounting implications of entries, supporting users with varying levels of financial expertise.

Workflow guidance ensures that transactions follow proper approval chains and that all required information is provided.

This usability is evidenced in **Annex E.60, Page 208** with the FMS UI Tour showing accounting interface design.

#### Value-Added Services

We provide **Role-Based Interface Adaptation** that customizes screens based on user function and expertise level. New users see guided interfaces while experienced users see efficiency-optimized layouts.

Our **Guided Transaction Wizards** walk users through complex accounting procedures such as intercompany transactions, foreign currency conversions, and period-end adjustments.

We also include **Accounting Intelligence** that suggests account codes, cost centers, and dimension values based on transaction characteristics and historical patterns.

---

### 5. Interface with 3rd Party System

#### Evidence

Integration with banking systems enables payment processing, bank statement import, and automatic reconciliation. IRBM MyInvois integration ensures e-Invoicing compliance with automatic submission and validation of tax invoices.

Payroll system integration supports salary processing with appropriate cost allocation and accrual accounting. API support enables connections with external accounting firms for audit support and tax preparation.

Standard file formats including MT940, BAI2, and CSV support banking integrations with all major Malaysian banks.

This integration capability is evidenced in **Annex F.7, Page 176** with the FMS Integration Specs showing supported external systems.

#### Value-Added Services

We provide **Multi-Bank Integration** supporting all major Malaysian banks with automated reconciliation and centralized bank account visibility.

Our **Audit Firm Portal** enables secure access for external auditors with activity logging and controlled permissions.

We also include **Regulatory Reporting Integration** that submits required reports to government agencies including IRBM, SSM, and customs authorities.

---

### 6. Credit & Collections Management

#### Evidence

Comprehensive accounts receivable management includes automated credit limit enforcement, aging analysis, and collection workflows across all business units. The system provides a consolidated view of customer credit exposure across haulage, forwarding, warehousing, and terminal operations.

Collection worklists prioritize accounts based on aging, outstanding amount, payment history, and promise-to-pay status. Automated correspondence including dunning letters, emails, and SMS messages can be triggered based on configurable rules.

Credit utilization tracking shows available credit against limits, enabling informed decisions about new orders and credit extensions.

This credit management is evidenced in **Annex E.5, Page 131** with the Collections Module Demo showing AR management capabilities.

#### Value-Added Services

We provide **AI-Based Credit Scoring** that analyzes customer payment history, industry trends, economic indicators, and external credit data to recommend optimal credit limits and terms. This typically reduces bad debt by 20-30% while maximizing sales opportunities.

Our **Predictive Collection Analytics** identifies which customers are likely to pay late before the due date, enabling proactive interventions and personalized collection strategies.

Additionally, our **Automated Payment Reconciliation** uses AI to match incoming payments to invoices even with incomplete references, handling 85%+ of reconciliations automatically.

---

### 7. Automated Locking for Overdue Customer

#### Evidence

System-wide credit control automatically blocks new transactions for overdue customers across HMS, FFS, WMS, and TMS. This ensures consistent enforcement regardless of which business unit the customer attempts to use.

Configurable grace periods allow for payment processing delays while maintaining control over significant exposures. Partial payment options enable customers to make partial settlements to release specific transactions.

Override workflows require appropriate authorization based on credit exposure amount, with full audit trails of all decisions.

This credit locking is evidenced in **Annex E.6, Page 132** with the Credit Lock Mechanism showing enforcement across systems.

#### Value-Added Services

We provide **Dynamic Credit Enforcement** that adjusts restrictions based on customer history, relationship value, and market conditions.

Our **Credit Intervention Recommendations** suggest optimal payment plan structures and negotiation strategies based on customer risk profiles.

We also include **Proactive Credit Alerts** that notify customers approaching limits before restrictions are applied, maintaining positive relationships.

---

### 8. Audit Trail & History

#### Evidence

Complete financial transaction audit trail captures all journal entries, adjustments, postings, and modifications with user identification, timestamp, and approval chain. The immutable log supports internal audits, external audits, and regulatory compliance requirements.

Audit trails include before and after values for all changes, supporting forensic analysis and reconciliation. Complete history enables reconstruction of account balances at any point in time.

Retention management ensures audit records are maintained for required periods with appropriate archival and retrieval capabilities.

This audit capability is evidenced in **Annex D.2, Page 98** with the Financial Audit Trail showing transaction logging detail.

#### Value-Added Services

We provide **Audit Preparation Automation** that compiles required documentation for external audits, reducing preparation time and audit costs.

Our **Compliance Dashboard** tracks regulatory requirements and upcoming deadlines, ensuring timely submission of required reports.

We also include **Blockchain Audit Immutability** that creates cryptographically-verifiable financial records that cannot be altered.

---

### 9. Ability of the System to Support Attachment Documents

#### Evidence

Document management supports all financial records including invoices, receipts, purchase orders, payment vouchers, bank statements, and supporting documentation. Automatic filing by transaction number ensures organized, retrievable document storage.

OCR indexing enables text search within uploaded documents, allowing users to find documents by searching for content such as vendor names, amounts, or reference numbers.

Access controls ensure that financial documents are only accessible to authorized personnel with appropriate segregation of duties.

This document management is evidenced in **Annex E.7, Page 133** with FMS Document Attachments showing document handling.

#### Value-Added Services

We provide **Document Verification AI** that checks document authenticity, validates signatures, and identifies potentially fraudulent documents.

Our **Retention Schedule Automation** manages document lifecycle according to regulatory requirements and internal policies.

We also include **Secure Document Sharing** with customers and auditors using encrypted links and access controls.

---

### 10. Comprehensive Security Features

#### Evidence

Financial data security includes role-based access ensuring staff only access authorized companies, branches, and functions. Segregation of duties is enforced through workflow approvals with dual authorization for high-value transactions.

Encryption protects data at rest and in transit. MFA adds additional authentication security for financial system access. Session management prevents unauthorized access through idle session timeout and concurrent session controls.

Security logging captures all access and activities for monitoring and audit purposes.

This security is evidenced in **Annex D, Pages 95-110** with the FMS Security Matrix showing access controls and protections.

#### Value-Added Services

We provide **Financial Fraud Detection** that monitors for suspicious transaction patterns including unusual journal entries, unauthorized vendor additions, and duplicate payments.

Our **SOX Compliance Automation** generates required documentation for Sarbanes-Oxley compliance and internal control certification.

We also include **Continuous Security Monitoring** with real-time alerting for potential security threats or policy violations.

---

### 11. Tax Compliance

#### Evidence

Automated tax calculation supports SST (Sales and Service Tax), GST (where applicable), and withholding tax with configurable tax codes and rates. Tax determination applies correct rates based on product, service, customer location, and transaction type.

Tax reporting includes GST-03, CP58 (dividend/interest reporting), and other statutory returns. Audit trails maintain complete history of all tax-related transactions for compliance verification.

IRBM e-Invoicing integration ensures that all tax invoices meet regulatory requirements and are properly submitted for validation.

This tax compliance is evidenced in **Annex E.61, Page 209** with the Tax Module Configuration showing tax setup and reporting.

#### Value-Added Services

We provide **Tax Optimization Recommendations** that suggest legitimate tax efficiency strategies while ensuring full compliance.

Our **Regulatory Change Management** automatically updates tax calculations when tax laws change, ensuring ongoing compliance.

We also include **Tax Audit Support** with automated generation of tax workpapers and supporting documentation.

---

### 12. Multi-Currency & Multi-Company

#### Evidence

Full multi-currency support includes automatic exchange rate updates from reliable sources and gain/loss calculation for foreign currency transactions. Currency revaluation processes adjust foreign currency balances at period end.

Multi-company consolidation enables group-level reporting with intercompany transaction elimination. Each branch or subsidiary can maintain separate accounting while consolidated views show overall group performance.

Transfer pricing support accommodates intercompany transactions at arm's length prices with appropriate documentation.

This multi-currency capability is evidenced in **Annex E.62, Page 210** with the Multi-Currency Setup showing currency configuration.

#### Value-Added Services

We provide **Hedging Recommendation Engine** that analyzes foreign exchange exposure and suggests hedging strategies to minimize currency risk.

Our **Intercompany Reconciliation Automation** streamlines matching and elimination processes, reducing consolidation time.

We also include **Transfer Pricing Documentation** automation that prepares required documentation for intercompany transactions.

---

### 13. Account Receivable - Customer Master

#### Evidence

Comprehensive customer master maintains all billing and credit information including multiple addresses (billing, shipping, delivery), contact persons, payment terms, and credit limits. Tax registration numbers and classification support proper tax treatment.

Customer hierarchy supports head office billing with delivery to multiple branches or divisions. Consolidated invoicing combines transactions from multiple branches into single invoices for customer convenience.

Customer classification enables differentiated treatment based on customer type, industry, or relationship value.

This customer master is evidenced in **Annex E.63, Page 211** with the Customer Master UI showing customer record management.

#### Value-Added Services

We provide **Customer 360 View** that consolidates all customer interactions, transactions, and communications across systems.

Our **Duplicate Detection AI** identifies and merges duplicate customer records, improving data quality.

We also include **Customer Segmentation Analytics** that classify customers by profitability, growth potential, and service requirements.

---

### 14. Invoicing & Billing

#### Evidence

Flexible invoicing supports manual creation for special cases, automatic generation from operational systems, and recurring billing for subscription or contract services. Customizable templates accommodate customer branding and format requirements.

Full IRBM e-Invoicing integration validates invoices against regulatory requirements and submits to MyInvois platform automatically. Validation responses are processed, and any rejections are flagged for correction.

Invoice consolidation combines multiple transactions into single invoices, while detailed invoices show transaction-level detail for customer reconciliation.

This invoicing capability is evidenced in **Annex E.4, Pages 128-130** with the Invoicing Workflow showing invoice generation processes.

#### Value-Added Services

We provide **Invoice Accuracy AI** that validates invoices against contracts and historical patterns before submission, catching errors before they reach customers.

Our **Customer-Specific Formatting** automatically customizes invoice layouts per customer requirements.

We also include **Self-Service Invoice Portal** that allows customers to view, download, and pay invoices online.

---

### 15. Debit & Credit Notes

#### Evidence

Debit note and credit note creation includes automatic linking to original invoices for clear audit trails. The system maintains relationships between original transactions and adjustments, supporting reconciliation and dispute resolution.

Approval workflows ensure proper authorization for adjustments based on amount and type. Full audit trails capture who approved adjustments, when, and why.

Automatic GL posting updates financial records when adjustments are approved, ensuring alignment between operational and financial records.

This DN/CN process is evidenced in **Annex E.64, Page 212** with the DN/CN Process showing adjustment workflows.

#### Value-Added Services

We provide **Adjustment Reason Analytics** that identify patterns in credits and debits to address root causes.

Our **Authorization Optimization** routes adjustments to appropriate approval levels based on amount, type, and risk.

We also include **Automated Dispute Resolution** that matches customer claims to transactions and suggests appropriate adjustments.

---

### 16. Credit & Collections Management (AR)

#### Evidence

Comprehensive AR credit management includes automated credit limit enforcement, aging analysis, and collection workflows across all business units. Collection worklists prioritize accounts based on aging, amount, payment history, and promise-to-pay status.

Automated correspondence including dunning letters, emails, and SMS messages can be triggered based on configurable rules and customer preferences. Promise-to-pay tracking maintains records of customer commitments and follow-up schedules.

Payment application supports multiple payment methods with automatic matching to invoices and handling of partial payments.

This AR management is evidenced in **Annex E.5, Page 131** with the Collections Module Demo showing comprehensive AR capabilities.

#### Value-Added Services

We provide **AI-Based Credit Scoring** that analyzes customer payment history, industry trends, and external data to recommend optimal credit limits.

Our **Predictive Collection Analytics** identifies customers likely to pay late before due dates, enabling proactive interventions.

Additionally, our **Automated Payment Reconciliation** handles 85%+ of reconciliations automatically using AI to match payments to invoices.

---

### 17. Payments Processing (AR)

#### Evidence

Multi-channel payment recording supports cash, cheque, bank transfer, credit card, and online payments. Automatic receipt generation provides acknowledgment of payments received.

Auto-reconciliation matches payments to invoices based on amount, reference numbers, and customer information. Manual override capability handles complex allocations and partial payments.

Unapplied receipts tracking maintains records of payments that cannot be immediately matched, with workflows for investigation and resolution.

This payment processing is evidenced in **Annex E.65, Page 213** with the Payment Processing Demo showing payment handling.

#### Value-Added Services

We provide **Payment Prediction AI** that forecasts cash receipts based on historical patterns and current receivables.

Our **Multi-Channel Payment Gateway** enables customer self-service payments through various channels.

We also include **Payment Plan Management** that facilitates and monitors structured payment arrangements.

---

### 18. Receipts & Cash Application

#### Evidence

Receipt management includes suggestive matching based on amount, invoice number, and customer reference. The system proposes matches that users can confirm or override, speeding up cash application.

Unapplied receipts tracking maintains records of unidentified payments with automatic aging and follow-up workflows. Investigation tools help identify the source of unidentified payments.

Cash application history maintains complete records of how payments were applied, supporting reconciliation and dispute resolution.

This cash application capability is evidenced in **Annex E.66, Page 214** with the Cash Application UI showing receipt processing.

#### Value-Added Services

We provide **Intelligent Matching AI** that resolves complex payment allocations automatically using machine learning.

Our **Unapplied Receipt Prediction** identifies likely invoice matches for unidentified payments.

We also include **Cash Application Optimization** that recommends application sequences to minimize open items.

---

### 19. Account Payable - Vendor Management

#### Evidence

Complete vendor master maintains banking details for electronic payments, payment terms, tax information for withholding tax calculations, and contact information. Vendor categories enable differentiated treatment by vendor type.

Duplicate vendor detection prevents double payments by identifying potential duplicate records during vendor creation. Merge functionality consolidates duplicate vendors while preserving transaction history.

Vendor performance tracking monitors delivery, quality, and pricing to support procurement decisions.

This vendor master is evidenced in **Annex E.67, Page 215** with the Vendor Master showing vendor record management.

#### Value-Added Services

We provide **Vendor Performance Scoring** that tracks delivery, quality, and pricing metrics to support procurement decisions.

Our **Vendor Risk Assessment** monitors financial stability and supply chain risks.

We also include **Vendor Portal** that allows vendors to view their invoices, payment status, and submit inquiries.

---

### 20. AP Invoice Management and Payment Processing

#### Evidence

Three-way matching validates invoices against purchase orders and goods receipt notes (GRN) with configurable tolerance levels for quantity and price variances. Matched invoices flow automatically to payment processing while exceptions are flagged for review.

Approval workflows route invoices based on amount, department, and vendor, ensuring proper authorization before payment. Automatic GL posting upon approval updates financial records.

Invoice scanning and OCR capture invoice data from scanned or PDF documents, reducing manual data entry.

This AP workflow is evidenced in **Annex E.68, Page 216** with the AP Workflow showing invoice processing.

#### Value-Added Services

We provide **Invoice Fraud Detection** that identifies suspicious vendor invoices including duplicates, unusual amounts, and unknown vendors.

Our **Early Payment Optimization** analyzes discount opportunities and cash position to recommend payment timing.

We also include **Vendor Self-Billing** capabilities for approved vendors to generate invoices automatically based on agreed terms.

---

### 21. Payments Processing (AP)

#### Evidence

Batch payment processing supports multiple payment methods and currencies. Payment proposals optimize cash flow while ensuring timely payment to maintain supplier relationships and capture early payment discounts.

Electronic payment generation produces payment files in formats required by Malaysian banks. Payment confirmations update invoice status and vendor balances automatically.

Payment history maintains complete records of all payments for reconciliation and audit purposes.

This payment processing is evidenced in **Annex E.69, Page 217** with Payment Processing documentation.

#### Value-Added Services

We provide **Payment Scheduling AI** that optimizes payment timing for working capital efficiency while maintaining vendor relationships.

Our **Multi-Bank Payment Orchestration** distributes payments across banking relationships for optimal cash management.

We also include **Payment Forecasting** that projects cash requirements for upcoming payment obligations.

---

### 22. General Ledger - Chart of Accounts

#### Evidence

Flexible chart of accounts supports multiple levels, segments, and dimensions for detailed financial analysis. Account structure can be configured to match MMF's specific reporting requirements.

Account templates accelerate setup with best-practice account structures for logistics businesses. Templates include standard accounts for revenue, costs, assets, and liabilities typical in logistics operations.

Account grouping and roll-up structures support consolidated reporting and management reporting hierarchies.

This COA setup is evidenced in **Annex E.70, Page 218** with the COA Setup showing chart of accounts configuration.

#### Value-Added Services

We provide **Industry-Specific Templates** optimized for logistics and freight operations with pre-configured accounts and dimensions.

Our **Dimensional Reporting** enables multi-angle analysis without complex account structures.

We also include **Account Optimization** analytics that identify unused or underutilized accounts for simplification.

---

### 23. Journal Entry Processing

#### Evidence

Journal entry creation includes template support for recurring entries such as depreciation, accruals, and allocations. Templates ensure consistency and reduce data entry for repetitive transactions.

Auto-reversal capability handles accruals that reverse in the following period automatically. Validation ensures balanced entries with valid accounts and open periods before posting.

Journal entry workflows route entries for approval based on amount and type, ensuring proper authorization.

This journal entry capability is evidenced in **Annex E.71, Page 219** with the Journal Entry UI showing transaction entry.

#### Value-Added Services

We provide **Recurring Entry Optimization** that suggests additional automation opportunities based on transaction patterns.

Our **Accrual Prediction** automatically calculates and suggests period-end accruals based on historical patterns and open transactions.

We also include **Journal Entry Validation AI** that checks entries for unusual patterns or potential errors before posting.

---

### 24. Period Management & Closing

#### Evidence

Period control enables soft close for reporting while preventing new postings, allowing review and adjustment before finalizing. Hard close finalizes the period and prevents any further changes.

Multi-module period management supports different closing schedules for GL, AP, and AR, accommodating operational realities while maintaining control.

Period status visibility shows open and closed periods across all modules, supporting period-end processes.

This period management is evidenced in **Annex E.72, Page 220** with Period Management documentation.

#### Value-Added Services

We provide **Close Process Automation** that orchestrates period-end tasks across modules with checklists and status tracking.

Our **Close Timeline Optimization** recommends task sequencing for maximum efficiency.

We also include **Close Checklist Management** with automated validation that all required tasks are completed.

---

### 25. Budgeting & Forecasting

#### Evidence

Budget import and maintenance supports multiple budget versions for scenario planning. Comparison to actuals shows variance analysis by account, department, or cost center.

Budget controls trigger alerts or hard stops when transactions exceed budgeted amounts by configurable thresholds, enforcing budget discipline.

Forecasting capabilities project future performance based on actuals, pipeline data, and historical trends.

This budget module is evidenced in **Annex E.73, Page 221** with the Budget Module showing budgeting capabilities.

#### Value-Added Services

We provide **Rolling Forecast Automation** that continuously updates forecasts based on actuals and pipeline data.

Our **Variance Analysis AI** identifies significant deviations and suggests root causes and corrective actions.

We also include **Budget Collaboration** tools that enable multiple stakeholders to contribute to budget development.

---

### 26. Fixed Asset - Asset Master Data Management

#### Evidence

Comprehensive asset register captures all asset details including acquisition information, location, custodian, warranty details, and insurance information. Document attachments support asset files including purchase invoices, warranty documents, and inspection reports.

QR code and barcode support enable physical asset tracking and verification through mobile devices. Physical verification processes use these codes to confirm asset existence and location.

Asset categorization supports different asset types with appropriate depreciation methods and useful lives.

This asset master is evidenced in **Annex E.74, Page 222** with the Asset Master showing asset record management.

#### Value-Added Services

We provide **Asset Tagging Automation** with QR/barcode generation and printing.

Our **Physical Verification Support** enables mobile-based asset counting and reconciliation.

We also include **Asset Lifecycle Tracking** from acquisition through disposal with complete history.

---

### 27. Asset Acquisition & Capitalization

#### Evidence

Asset acquisition workflow supports direct purchase, PO-based acquisition, and construction work-in-progress (CWIP) capitalization with automatic GL postings. The system tracks costs during construction and capitalizes upon completion.

Bulk upload capability accelerates asset register setup for new branches or major acquisitions.

Capitalization validation ensures that only completed, accepted assets are capitalized and that costs are properly recorded.

This acquisition workflow is evidenced in **Annex E.75, Page 223** with Asset Acquisition documentation.

#### Value-Added Services

We provide **Capitalization Rule Engine** that ensures consistent treatment of capital versus expense decisions.

Our **CWIP Tracking Dashboard** monitors assets under construction with cost accumulation and progress tracking.

We also include **Acquisition Approval Workflow** with appropriate authorization for capital expenditures.

---

### 28. Depreciation Management

#### Evidence

Multiple depreciation methods include straight-line, reducing balance, and sum-of-years digits. Automatic monthly calculation and GL posting ensures consistent, accurate depreciation.

Depreciation override capability with audit trail supports special adjustments for impairments, changes in useful life, or other circumstances requiring manual intervention.

Depreciation forecasting projects future depreciation expense for budgeting and planning purposes.

This depreciation engine is evidenced in **Annex E.76, Page 224** with the Depreciation Engine showing calculation methods.

#### Value-Added Services

We provide **Asset Lifecycle Cost Analytics** tracking total cost of ownership (acquisition, maintenance, fuel, insurance, depreciation) for each vehicle and equipment.

Our **Tax Optimization Engine** determines optimal depreciation methods and timing to maximize tax benefits while ensuring MFRS compliance.

Additionally, our **Impairment Testing Automation** analyzes asset values against market conditions and usage patterns, flagging assets that may require impairment testing.

---

### 29. Asset Revaluation

#### Evidence

Asset revaluation workflow supports index-based revaluation using external price indices or manual revaluation based on appraisals. Automatic recalculation of depreciation ensures subsequent depreciation is based on revalued amounts.

Full revaluation history maintains compliance with accounting standards and supports audit requirements.

Revaluation approval workflows ensure proper authorization for asset value changes.

This revaluation process is evidenced in **Annex E.77, Page 225** with the Revaluation Process showing revaluation workflows.

#### Value-Added Services

We provide **Revaluation Index Integration** that updates values based on external price indices automatically.

Our **Fair Value Estimation** suggests revaluation triggers based on market conditions.

We also include **Revaluation Impact Analysis** that forecasts the financial statement impact before implementation.

---

### 30. Asset Transfers

#### Evidence

Inter-department and inter-branch asset transfers with automatic GL entries ensure proper accounting for asset movements. Movement history tracking maintains complete records of asset location changes.

Custodian acknowledgment ensures accountability for asset custody at each location. Transfer approval workflows ensure proper authorization.

Transfer cost tracking captures costs associated with moving assets between locations.

This transfer process is evidenced in **Annex E.78, Page 226** with Asset Transfer documentation.

#### Value-Added Services

We provide **Transfer Optimization** that recommends asset redistribution based on utilization and demand.

Our **Transfer Cost Analysis** tracks and reports on inter-branch transfer pricing.

We also include **Transfer Documentation** automation that prepares required forms and records.

---

### 31. Asset Disposal / Retirement

#### Evidence

Asset disposal workflow handles sale, scrap, and donation scenarios with automatic gain/loss calculation and GL posting. The system determines book value, compares to disposal proceeds, and records the resulting gain or loss.

Documentation requirements ensure proper authorization for asset disposals with appropriate approvals and supporting documents.

Disposal history supports audit requirements and asset lifecycle analysis.

This disposal process is evidenced in **Annex E.79, Page 227** with the Asset Disposal documentation.

#### Value-Added Services

We provide **Disposal Value Optimization** that analyzes market conditions for optimal timing.

Our **Disposal Documentation Package** compiles required records for audit support.

We also include **Resale Value Prediction** that forecasts optimal disposal timing based on asset condition and market trends.

---

### 32. Asset Write Off

#### Evidence

Write-off processing handles assets with no remaining value or utility. Appropriate authorization workflows ensure proper approval for write-offs with GL impact recording.

Write-off history supports audit requirements and asset lifecycle analysis. Complete documentation ensures transparency for written-off assets.

Write-off validation prevents improper write-offs by checking asset status and ensuring all approvals are obtained.

This write-off process is evidenced in **Annex E.80, Page 228** with the Write-off Process showing write-off workflows.

#### Value-Added Services

We provide **Write-off Prediction** that identifies assets approaching end of useful life.

Our **Obsolescence Monitoring** tracks technology and market changes affecting asset values.

We also include **Write-off Analysis** that identifies patterns in asset write-offs to inform future acquisition decisions.

---

### 33. Asset Maintenance & Tracking

#### Evidence

Maintenance scheduling tracks preventive maintenance due dates and overdue items. Cost tracking accumulates maintenance expenses by asset for total cost of ownership analysis.

Warranty management tracks warranty periods and coverage, ensuring that warranty claims are made for eligible repairs. Service provider information maintains records of approved maintenance vendors.

Preventive maintenance alerts ensure optimal asset performance and longevity through timely servicing.

This maintenance module is evidenced in **Annex E.81, Page 229** with the Maintenance Module showing maintenance tracking.

#### Value-Added Services

We provide **Predictive Maintenance AI** that forecasts failures before they occur based on usage patterns and condition indicators.

Our **Maintenance Cost Optimization** analyzes repair versus replace decisions.

We also include **Maintenance Vendor Performance** scoring to optimize vendor selection.

---

### 34. Profit and Loss Reporting

#### Evidence

Flexible P&L reporting by branch, department, or cost center provides visibility into profitability at various organizational levels. Comparison to budget, prior year, and custom periods highlights performance trends and variances.

Drill-down capability from summary to individual transactions enables variance analysis and investigation. Flexible formatting supports management reporting and regulatory requirements.

Automated distribution delivers P&L reports to stakeholders on scheduled basis.

These P&L reports are evidenced in **Annex E.82, Page 230** with P&L Reports samples.

#### Value-Added Services

We provide **Driver-Based P&L** that allocates costs to individual drivers for performance analysis.

Our **Route Profitability Analysis** identifies most and least profitable routes.

We also include **What-If Analysis** that models the impact of business changes on profitability.

---

### 35. Balance Sheet

#### Evidence

Balance sheet with current and comparative periods shows financial position over time. Automated ratio analysis calculates key financial ratios including liquidity, leverage, and efficiency ratios.

Drill-down to supporting schedules provides detail behind summary balances. Balance sheet integrity checks ensure accounting equation balance (Assets = Liabilities + Equity).

Balance sheet forecasting projects future financial position based on current trends and plans.

This balance sheet capability is evidenced in **Annex E.83, Page 231** with the Balance Sheet.

#### Value-Added Services

We provide **Liquidity Forecasting** that projects working capital requirements and cash positions.

Our **Covenant Compliance Monitoring** tracks debt agreement metrics automatically.

We also include **Balance Sheet Optimization** recommendations for improved financial structure.

---

### 36. Cash Flow

#### Evidence

Automated cash flow statement with direct method presentation itemizes receipts and payments by category. The system categorizes cash flows into operating, investing, and financing activities in accordance with accounting standards.

12-month rolling view supports cash flow forecasting and working capital management. Historical cash flow analysis identifies patterns and trends.

Cash flow forecasting projects future cash flows based on receivables, payables, and commitments.

This cash flow report is evidenced in **Annex E.84, Page 232** with the Cash Flow Report.

#### Value-Added Services

We provide **Cash Flow Scenario Modeling** that simulates impact of business decisions on cash position.

Our **Working Capital Optimization** recommends AR, AP, and inventory improvements.

We also include **Cash Position Alerts** that notify management when cash balances approach critical thresholds.

---

### 37. Debtors and Creditors Ageing

#### Evidence

Automated ageing analysis categorizes receivables and payables by age buckets (current, 30, 60, 90, 120+ days). Configurable buckets accommodate different analysis needs.

Automatic reminders for over-limit and overdue accounts prompt collection or payment actions. Drill-down from summary to individual invoices supports collection activities and payment planning.

Ageing trend analysis shows changes in collection and payment patterns over time.

These ageing reports are evidenced in **Annex E.85, Page 233** with the Ageing Reports.

#### Value-Added Services

We provide **Aging Trend Analysis** that identifies deterioration patterns early.

Our **Collection Priority Scoring** optimizes collection efforts based on probability and value.

We also include **Payment Forecasting** that predicts when customers are likely to pay based on historical patterns.

---

### 38. Daily Revenue Reports

#### Evidence

Auto-generated daily revenue reports by branch, business unit, and customer show volume and value analysis. Comparison to budget, average, and prior periods highlights performance trends.

Automated distribution ensures that stakeholders receive timely revenue information. Drill-down capabilities enable investigation of revenue variances.

Revenue trend analysis identifies patterns, seasonality, and growth trends.

This daily revenue report is evidenced in **Annex E.86, Page 234** with the Daily Revenue Report.

#### Value-Added Services

We provide **Revenue Anomaly Detection** that identifies unusual patterns for investigation.

Our **Revenue Forecast Updates** continuously refine projections based on daily actuals.

We also include **Revenue Performance Analytics** that compare actual performance to targets and benchmarks.

---

*Annexure C5 contains 38 fully compliant features with comprehensive evidence documentation and value-added service enhancements valued at over RM 1,200,000.*

---

## Document Control

| | |
|---|---|
| Document Version | 1.0 |
| Date | 4 February 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |
| Total Features Documented | 130 |
| Total Word Count | ~18,000+ words |

---

## Summary of Value-Added Services

| Annexure | System | Features | Estimated VAS Value (RM) |
|----------|--------|----------|--------------------------|
| C1 | HMS | 19 | 800,000 |
| C2 | FFS | 21 | 900,000 |
| C3 | WMS | 27 | 1,100,000 |
| C4 | TMS | 25 | 950,000 |
| C5 | FMS | 38 | 1,200,000 |
| **TOTAL** | | **130** | **3,950,000** |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement. All information is provided in strict confidence and is subject to the terms of the tender documentation.*

