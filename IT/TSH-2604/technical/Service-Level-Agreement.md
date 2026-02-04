# Service Level Agreement

## Document Information

| Attribute | Details |
|-----------|---------|
| **Document Version** | 1.0 |
| **Effective Date** | Upon Contract Execution |
| **Prepared By** | Sinergi Elit Sdn Bhd (SESB) |
| **Classification** | Tender Submission - Confidential |
| **Applicable To** | Enterprise IT System Support Services |

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Scope of Services](#2-scope-of-services)
3. [Service Level Objectives](#3-service-level-objectives)
4. [Incident Management](#4-incident-management)
5. [Service Request Management](#5-service-request-management)
6. [Problem Management](#6-problem-management)
7. [Change Management](#7-change-management)
8. [Service Availability](#8-service-availability)
9. [Performance Standards](#9-performance-standards)
10. [Reporting & Governance](#10-reporting--governance)
11. [Service Credits & Penalties](#11-service-credits--penalties)
12. [Roles & Responsibilities](#12-roles--responsibilities)
13. [Appendices](#13-appendices)

---

## 1. Executive Summary

This Service Level Agreement (SLA) defines the service levels, performance standards, and responsibilities for the support and maintenance of enterprise IT systems. The SLA establishes measurable targets for service delivery, response times, and system availability while providing mechanisms for monitoring, reporting, and continuous improvement.

The agreement is designed to ensure that IT systems operate reliably, issues are resolved promptly, and the client organization receives consistent, high-quality support services. The SLA balances service excellence with practical constraints, establishing achievable yet challenging targets that drive continuous improvement.

### 1.1 Agreement Objectives

**Service Reliability**: Ensure systems operate with minimal disruption to business operations

**Responsive Support**: Provide timely response and resolution to issues and requests

**Transparency**: Maintain clear visibility into service performance and issues

**Continuous Improvement**: Drive ongoing enhancement of service quality and efficiency

**Risk Mitigation**: Minimize business impact from system failures and disruptions

**Partnership**: Foster collaborative relationship focused on business success

### 1.2 Agreement Scope

This SLA covers:

- Production system support and maintenance
- Application support services
- Infrastructure support services
- Database administration
- Security management
- Performance monitoring and optimization
- Backup and recovery services
- User support and help desk
- System updates and patches
- Technical advisory services

### 1.3 Service Period

The service period commences upon successful system handover and acceptance, continuing for the duration of the support contract. Initial periods typically include:

**Warranty Period**: First 90 days post go-live with enhanced support

**Standard Support**: Ongoing operational support

**Extended Support**: Available for long-term engagements

---

## 2. Scope of Services

### 2.1 Service Categories

Services are categorized by nature and scope:

**Corrective Services**: Addressing system defects and failures
- Bug fixes and defect resolution
- System restoration after failure
- Data correction and recovery
- Emergency patches and hotfixes

**Adaptive Services**: Responding to environmental changes
- Regulatory compliance updates
- Platform compatibility updates
- Interface modifications for third-party changes
- Security patch implementation

**Perfective Services**: Enhancing system functionality
- Performance optimization
- Minor feature enhancements
- Report customizations
- Workflow improvements

**Preventive Services**: Avoiding future issues
- Proactive monitoring
- Health checks and assessments
- Capacity planning
- Preventive maintenance

### 2.2 Service Delivery Model

Services are delivered through multiple channels:

**24/7 Helpdesk**: Continuous support for critical issues

**Business Hours Support**: Standard support during working hours

**Remote Support**: Remote diagnosis and resolution

**On-Site Support**: Physical presence when required

**Self-Service Portal**: User-accessible knowledge base and tools

### 2.3 Service Hours

**Standard Support Hours**:
- Monday to Friday: 08:00 - 18:00 (local time)
- Excluding public holidays

**Extended Support Hours**:
- Monday to Sunday: 07:00 - 22:00 (local time)
- Including most public holidays

**24/7 Support**:
- Continuous availability for critical issues
- Emergency response capability

### 2.4 Service Exclusions

The following are outside the scope of standard support:

- New system development (treated as separate project)
- Major functional enhancements (require change request)
- Third-party software not covered by agreement
- Issues caused by unauthorized modifications
- Force majeure events beyond reasonable control
- Client-provided infrastructure failures (hardware warranty)

---

## 3. Service Level Objectives

### 3.1 Response Time Targets

Response times are measured from incident or request logging to initial vendor acknowledgment:

| Priority | Definition | Response Time | Target |
|----------|------------|---------------|--------|
| P1 - Critical | Complete system failure, no workaround | < 1 hour | 99% |
| P2 - High | Significant functionality impaired | < 4 hours | 98% |
| P3 - Medium | Limited functionality affected | < 8 hours | 95% |
| P4 - Low | Minimal impact, cosmetic issues | < 24 hours | 90% |

### 3.2 Resolution Time Targets

Resolution times are measured from incident logging to permanent resolution:

| Priority | Target Resolution | Achievement Target |
|----------|-------------------|-------------------|
| P1 - Critical | < 24 hours | 95% |
| P2 - High | < 72 hours | 90% |
| P3 - Medium | < 5 business days | 85% |
| P4 - Low | < 10 business days | 80% |

Note: Resolution times may vary based on complexity and root cause. Workarounds may be provided pending permanent resolution.

### 3.3 Service Request Fulfillment

Standard service requests are fulfilled within:

| Request Type | Fulfillment Time | Target |
|--------------|------------------|--------|
| User Account Creation | 4 hours | 95% |
| Password Reset | 1 hour | 99% |
| Access Modification | 8 hours | 95% |
| Report Generation | 24 hours | 90% |
| Data Export | 48 hours | 90% |
| Training Request | 5 business days | 85% |

### 3.4 System Availability Targets

System availability is measured monthly:

| System Category | Availability Target | Allowed Downtime/Month |
|-----------------|---------------------|----------------------|
| Critical Production | 99.9% | 43 minutes |
| Important Production | 99.5% | 3.6 hours |
| Standard Production | 99.0% | 7.2 hours |
| Non-Production | 95.0% | 36 hours |

Availability calculation excludes:
- Scheduled maintenance windows (with 7-day notice)
- Force majeure events
- Client-caused outages
- Third-party service failures

### 3.5 Performance Targets

System performance standards:

| Metric | Target | Measurement |
|--------|--------|-------------|
| Page Load Time | < 3 seconds | 95th percentile |
| Transaction Response | < 5 seconds | 95th percentile |
| Report Generation | < 30 seconds | Simple reports |
| Batch Processing | Per agreed schedule | Job completion |
| API Response Time | < 2 seconds | 95th percentile |
| Database Query Time | < 1 second | 95th percentile |

---

## 4. Incident Management

### 4.1 Incident Classification

Incidents are classified by priority based on impact and urgency:

**Priority 1 - Critical**:
- Complete system failure
- All users affected
- No workaround available
- Revenue or safety impact
- Immediate attention required

**Priority 2 - High**:
- Major functionality impaired
- Significant user impact
- Workaround available but difficult
- Business operations affected
- Urgent attention required

**Priority 3 - Medium**:
- Limited functionality affected
- Minor user impact
- Workaround available
- Business continuing
- Standard attention required

**Priority 4 - Low**:
- Minimal impact
- Single user or cosmetic issue
- Easy workaround
- No immediate business impact
- Queue for next available resource

### 4.2 Incident Management Process

**Detection**: Automated monitoring or user report identifies issue

**Logging**: Incident recorded in service management system

**Classification**: Priority assigned based on impact and urgency

**Initial Response**: Acknowledgment and initial assessment within SLA

**Investigation**: Root cause analysis and resolution planning

**Resolution**: Implementation of fix or workaround

**Verification**: Confirmation that issue is resolved

**Closure**: Incident formally closed with documentation

### 4.3 Communication During Incidents

Communication protocols ensure stakeholders are informed:

**P1 Incidents**:
- Immediate notification to stakeholders
- 30-minute update intervals
- Executive briefing within 1 hour
- Post-incident report within 24 hours

**P2 Incidents**:
- Notification within response SLA
- 2-hour update intervals
- Management updates as needed
- Resolution report within 48 hours

**P3/P4 Incidents**:
- Standard notification
- Daily updates until resolved
- Resolution summary at closure

### 4.4 Escalation Procedures

Escalation ensures appropriate attention for unresolved issues:

**Technical Escalation**:
- Level 1: Service Desk (initial handling)
- Level 2: Technical Specialist (after 2 hours for P1, 8 hours for P2)
- Level 3: Senior Engineer (after 4 hours for P1, 16 hours for P2)
- Level 4: Product Engineering (after 8 hours for P1, 24 hours for P2)

**Management Escalation**:
- Vendor Account Manager (P1 after 4 hours, P2 after 16 hours)
- Vendor Service Director (P1 after 8 hours, P2 after 24 hours)
- Executive Escalation (P1 after 16 hours, P2 after 48 hours)

---

## 5. Service Request Management

### 5.1 Service Request Categories

Service requests are categorized by type:

**Access Requests**:
- User account creation
- Password resets
- Role and permission changes
- Access removals

**Configuration Requests**:
- System parameter changes
- Workflow modifications
- Report configuration
- Interface configuration

**Information Requests**:
- Documentation requests
- Training requests
- Reporting requests
- Advisory consultations

**Standard Changes**:
- Scheduled maintenance
- Routine updates
- Data refreshes
- Environment refreshes

### 5.2 Service Request Process

**Submission**: Request submitted through portal, email, or phone

**Logging**: Request recorded with unique identifier

**Assessment**: Effort and resource requirements evaluated

**Approval**: Approval obtained if required (cost, impact)

**Scheduling**: Work scheduled based on priority and resources

**Execution**: Request fulfilled according to specification

**Verification**: Client confirmation of satisfactory completion

**Closure**: Request formally closed

### 5.3 Request Prioritization

Service requests are prioritized based on:

**Urgency**: Business impact of delay

**Importance**: Strategic or operational significance

**Effort**: Resource requirements

**Dependencies**: Relationship to other work

**SLA**: Any associated service commitments

### 5.4 Service Request Fulfillment Standards

Standard fulfillment times by category:

| Category | Standard Time | Expedited Time* |
|----------|---------------|-----------------|
| Access - Standard | 4 hours | 1 hour |
| Access - Complex | 8 hours | 4 hours |
| Configuration - Simple | 24 hours | 8 hours |
| Configuration - Complex | 5 business days | 2 business days |
| Information | 24 hours | 4 hours |
| Standard Change | Per schedule | Per schedule |

*Expedited service may incur additional charges

---

## 6. Problem Management

### 6.1 Problem Identification

Problems are underlying causes of incidents:

**Reactive Problem Management**: Investigation following major incidents

**Proactive Problem Management**: Analysis of trends and patterns

**Known Error Identification**: Documenting known issues and workarounds

### 6.2 Problem Management Process

**Problem Detection**: Identification through incident analysis or monitoring

**Problem Logging**: Recording in problem management system

**Categorization**: Classification by type and system area

**Investigation**: Root cause analysis

**Workaround**: Developing temporary solutions

**Resolution**: Implementing permanent fixes

**Review**: Post-implementation review

### 6.3 Root Cause Analysis

Root cause analysis techniques:

**5 Whys**: Iterative questioning to identify root cause

**Fishbone Diagram**: Categorizing potential causes

**Fault Tree Analysis**: Logical analysis of failure paths

**Timeline Analysis**: Chronological reconstruction

**Component Analysis**: Hardware/software component examination

### 6.4 Known Error Database

Known errors are documented in a central database:

**Error Description**: Symptoms and manifestation

**Root Cause**: Underlying problem

**Workaround**: Temporary solution

**Permanent Fix**: Planned resolution

**Related Incidents**: Historical occurrence record

---

## 7. Change Management

### 7.1 Change Categories

Changes are classified by impact and risk:

**Standard Changes**: Pre-approved, low-risk, routine
- Examples: Password resets, user additions, scheduled backups
- Process: Pre-authorized, expedited approval

**Normal Changes**: Require assessment and authorization
- Examples: Configuration changes, patch installation, minor updates
- Process: Change request, assessment, approval, implementation

**Emergency Changes**: Urgent fixes requiring immediate implementation
- Examples: Critical security patches, system recovery actions
- Process: Expedited review, post-implementation documentation

**Major Changes**: High-impact, complex modifications
- Examples: Major releases, architecture changes, data migrations
- Process: Full change management with CAB review

### 7.2 Change Management Process

**Request**: Change request submitted with justification

**Assessment**: Impact analysis including risk, effort, and dependencies

**Approval**: Authorization by appropriate authority

**Planning**: Detailed implementation planning

**Testing**: Validation in non-production environment

**Implementation**: Deployment to production

**Review**: Post-implementation review

### 7.3 Change Advisory Board

The Change Advisory Board (CAB) reviews significant changes:

**CAB Membership**:
- Service Delivery Manager (Chair)
- Technical Architects
- Application Specialists
- Infrastructure Representatives
- Client Representatives
- Security Representative

**CAB Responsibilities**:
- Review and approve major changes
- Assess change risks and impacts
- Coordinate change schedules
- Review change failures

**CAB Meetings**: Weekly or as needed for emergency changes

### 7.4 Maintenance Windows

Scheduled maintenance windows for planned changes:

**Regular Maintenance Windows**:
- Weekly: Saturday 02:00 - 06:00
- Monthly: Last Sunday 00:00 - 08:00

**Emergency Maintenance**:
- As required with minimum 4-hour notice for critical issues
- Immediate for security emergencies

**Change Freeze Periods**:
- Year-end: 15 December - 5 January
- Month-end: Last 2 days of month
- Special periods as announced

---

## 8. Service Availability

### 8.1 Availability Commitments

Availability targets by service tier:

**Tier 1 - Critical Services**:
- 99.9% availability (excluding planned maintenance)
- 24/7 monitoring and support
- Immediate failover capabilities
- Sub-hour recovery commitment

**Tier 2 - Important Services**:
- 99.5% availability
- Extended hours monitoring
- Defined recovery procedures
- 4-hour recovery commitment

**Tier 3 - Standard Services**:
- 99.0% availability
- Business hours monitoring
- Standard recovery procedures
- 24-hour recovery commitment

### 8.2 Planned Maintenance

Planned maintenance is scheduled to minimize business impact:

**Maintenance Scheduling**:
- Minimum 7 days advance notice
- Scheduling during low-usage periods
- Coordination with business schedules
- Emergency maintenance with 4-hour notice

**Maintenance Types**:
- Patch installation
- Security updates
- Performance optimization
- Infrastructure upgrades
- Database maintenance

**Maintenance Communication**:
- Maintenance notification with scope and duration
- Progress updates during extended maintenance
- Completion notification with results

### 8.3 Monitoring & Alerting

Continuous monitoring ensures rapid issue detection:

**Infrastructure Monitoring**:
- Server health and performance
- Network availability
- Storage capacity and performance
- Environmental conditions

**Application Monitoring**:
- Application availability
- Response times
- Error rates
- Transaction volumes

**Database Monitoring**:
- Database availability
- Query performance
- Connection pooling
- Lock contention

**Alerting Thresholds**:
- Critical alerts: Immediate notification
- Warning alerts: Dashboard notification
- Informational: Logging only

### 8.4 High Availability Architecture

High availability is achieved through:

**Redundancy**: Elimination of single points of failure

**Failover**: Automatic switching to backup components

**Load Balancing**: Distribution of workload

**Health Checks**: Continuous component monitoring

**Self-Healing**: Automatic recovery from component failures

---

## 9. Performance Standards

### 9.1 Performance Metrics

System performance is measured against defined standards:

**Response Time Metrics**:
- Web page load time: < 3 seconds
- API response time: < 2 seconds
- Database query time: < 1 second
- Report generation time: < 30 seconds (simple)

**Throughput Metrics**:
- Concurrent users supported
- Transactions per second
- Records processed per hour
- API calls per minute

**Resource Utilization Metrics**:
- CPU utilization: < 80% average
- Memory utilization: < 85% average
- Disk utilization: < 85% capacity
- Network utilization: < 70% capacity

### 9.2 Performance Monitoring

Continuous performance monitoring includes:

**Real-Time Monitoring**: Current performance metrics

**Trend Analysis**: Performance over time

**Capacity Planning**: Future capacity needs

**Bottleneck Identification**: Performance constraint analysis

**Optimization Recommendations**: Performance improvement suggestions

### 9.3 Performance Reporting

Performance reports include:

**Daily Reports**: Key performance indicators

**Weekly Reports**: Performance trends and issues

**Monthly Reports**: Comprehensive performance analysis

**Quarterly Reviews**: Capacity planning and optimization

### 9.4 Performance Optimization

Proactive performance optimization:

**Regular Assessments**: Monthly performance reviews

**Optimization Recommendations**: Suggested improvements

**Implementation Support**: Assistance with optimizations

**Validation Testing**: Confirming optimization effectiveness

---

## 10. Reporting & Governance

### 10.1 Service Reports

Regular service reports provide visibility:

**Daily Reports** (Automated):
- System availability status
- Open critical incidents
- Backup status
- Performance alerts

**Weekly Reports**:
- Incident summary and trends
- Service request fulfillment
- Change implementation status
- Performance metrics

**Monthly Service Reports**:
- SLA performance summary
- Incident analysis
- Problem status
- Change summary
- Availability statistics
- Performance trends

**Quarterly Business Reviews**:
- Strategic performance review
- Improvement initiatives
- Roadmap alignment
- Relationship assessment

### 10.2 SLA Performance Tracking

Performance against SLA targets:

**Availability Tracking**: Actual vs. target availability

**Response Time Tracking**: Incident and request response performance

**Resolution Time Tracking**: Time to incident resolution

**Service Request Tracking**: Request fulfillment performance

**Customer Satisfaction**: User satisfaction surveys

### 10.3 Governance Meetings

Regular governance ensures alignment:

**Weekly Operational Reviews**:
- Incident review
- Service request review
- Upcoming changes
- Issues and concerns

**Monthly Service Reviews**:
- SLA performance review
- Trend analysis
- Improvement initiatives
- Resource planning

**Quarterly Business Reviews**:
- Strategic alignment
- Roadmap review
- Contract performance
- Relationship strengthening

**Annual Strategic Review**:
- Long-term planning
- Investment priorities
- Partnership assessment
- Contract renewal planning

### 10.4 Continuous Improvement

Continuous improvement processes:

**Service Improvement Plan**: Quarterly improvement initiatives

**Process Optimization**: Regular process review and enhancement

**Technology Refresh**: Keeping current with technology advances

**Skills Development**: Ongoing team capability enhancement

**Client Feedback**: Regular feedback collection and action

---

## 11. Service Credits & Penalties

### 11.1 Service Credit Structure

Service credits apply for SLA failures:

**Availability Credits**:
| Availability Shortfall | Credit Percentage |
|------------------------|-------------------|
| 0.1% - 0.5% below SLA | 5% of monthly fee |
| 0.5% - 1.0% below SLA | 10% of monthly fee |
| 1.0% - 2.0% below SLA | 15% of monthly fee |
| > 2.0% below SLA | 25% of monthly fee |

**Response Time Credits**:
| Response Time Failure | Credit Percentage |
|-----------------------|-------------------|
| 5% - 10% of incidents | 2% of monthly fee |
| 10% - 20% of incidents | 5% of monthly fee |
| > 20% of incidents | 10% of monthly fee |

Maximum monthly credits: 30% of monthly service fee

### 11.2 Credit Calculation

Service credits are calculated as:

- Based on monthly recurring charges for affected services
- Calculated separately for each SLA metric
- Cumulative up to maximum cap
- Applied as credit against future invoices

### 11.3 Credit Exclusions

Credits do not apply for:

- Scheduled maintenance windows
- Client-caused outages
- Force majeure events
- Third-party service failures outside vendor control
- Issues caused by client modifications

### 11.4 Continuous Service Commitment

Service credits are not penalties but recognition of service shortfall. The vendor commits to:

- Root cause analysis of all SLA failures
- Implementation of preventive measures
- Investment in service improvements
- Transparent communication about improvements

---

## 12. Roles & Responsibilities

### 12.1 Vendor Responsibilities

**Service Delivery Management**:
- Overall service delivery accountability
- SLA performance management
- Resource allocation
- Continuous improvement

**Technical Support**:
- Incident diagnosis and resolution
- Problem management
- Change implementation
- Performance optimization

**Account Management**:
- Relationship management
- Business alignment
- Escalation handling
- Contract administration

### 12.2 Client Responsibilities

**Service Consumption**:
- Appropriate use of services
- Issue reporting and cooperation
- Testing and validation
- Change approval

**Environment Management**:
- Infrastructure maintenance
- Network connectivity
- Security compliance
- Access management

**Governance Participation**:
- Attendance at review meetings
- Feedback provision
- Decision-making
- Issue escalation

### 12.3 Shared Responsibilities

**Communication**: Both parties maintain open communication

**Change Management**: Collaborative change planning and approval

**Security**: Joint responsibility for security posture

**Testing**: Cooperative testing of changes and fixes

**Documentation**: Maintaining current documentation

### 12.4 Escalation Contacts

**Vendor Escalation**:
| Level | Role | Contact | Response Time |
|-------|------|---------|---------------|
| 1 | Service Desk | | < 1 hour |
| 2 | Technical Lead | | < 4 hours |
| 3 | Service Manager | | < 8 hours |
| 4 | Account Director | | < 24 hours |

**Client Escalation**:
| Level | Role | Contact | Usage |
|-------|------|---------|-------|
| 1 | System Administrator | | Routine issues |
| 2 | IT Manager | | Service issues |
| 3 | IT Director | | Major concerns |
| 4 | Executive Sponsor | | Strategic issues |

---

## 13. Appendices

### Appendix A: SLA Summary Table

| Metric | Target | Measurement | Credit Applied |
|--------|--------|-------------|----------------|
| System Availability | 99.9% | Monthly | Yes |
| P1 Response Time | < 1 hour | Per incident | Yes |
| P2 Response Time | < 4 hours | Per incident | Yes |
| P1 Resolution Time | < 24 hours | Per incident | No |
| Service Request Fulfillment | Per type | Per request | Yes |

### Appendix B: Priority Definitions

**Priority 1 (Critical)**:
- Complete system failure
- All users affected
- No workaround available
- Response: < 1 hour

**Priority 2 (High)**:
- Major functionality impaired
- Significant user impact
- Workaround available
- Response: < 4 hours

**Priority 3 (Medium)**:
- Limited functionality affected
- Minor user impact
- Workaround available
- Response: < 8 hours

**Priority 4 (Low)**:
- Minimal impact
- Single user affected
- Easy workaround
- Response: < 24 hours

### Appendix C: Service Request Catalog

| Request Type | Description | Standard Time | Expedited |
|--------------|-------------|---------------|-----------|
| User Account | Create/modify user | 4 hours | 1 hour |
| Password Reset | Reset password | 1 hour | 15 min |
| Access Change | Modify permissions | 8 hours | 4 hours |
| Report Request | Generate report | 24 hours | 4 hours |
| Configuration | System config change | 24-48 hours | 8 hours |
| Training | Schedule training | 5 days | 2 days |

### Appendix D: Change Request Form

**Change Request Information**:
- Request ID
- Request Date
- Requester
- System/Service

**Change Details**:
- Change Description
- Business Justification
- Expected Benefits

**Impact Assessment**:
- Technical Impact
- Business Impact
- Risk Assessment
- Rollback Plan

**Approval**:
- Requested By
- Reviewed By
- Approved By
- Implementation Date

### Appendix E: Incident Report Template

**Incident Summary**:
- Incident ID
- Date/Time Reported
- Reporter
- Priority
- Status

**Incident Details**:
- Description
- Symptoms
- Affected Users/Systems
- Business Impact

**Resolution**:
- Root Cause
- Resolution Actions
- Time to Resolve
- Preventive Measures

### Appendix F: Glossary of Terms

**Availability**: Percentage of time system is operational and accessible

**Escalation**: Process of raising issue to higher authority

**Incident**: Unplanned interruption or reduction in service quality

**MTTR (Mean Time to Repair)**: Average time to restore service after failure

**MTBF (Mean Time Between Failures)**: Average time between system failures

**Problem**: Underlying cause of one or more incidents

**RTO (Recovery Time Objective)**: Target time for service restoration

**Service Credit**: Financial credit for SLA failure

**Service Request**: Formal request for service or information

**SLA (Service Level Agreement)**: Contract defining service levels

### Appendix G: Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | | | Initial version |

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Vendor Representative | | | |
| Client Representative | | | |

---

*This Service Level Agreement forms part of the support services contract. All information is provided in strict confidence and is subject to the terms of the agreement.*
