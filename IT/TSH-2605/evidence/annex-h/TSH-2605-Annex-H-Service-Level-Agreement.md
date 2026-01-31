# ANNEX H: SERVICE LEVEL AGREEMENT (SLA)

**Tender Reference:** MMFSB/TD 02/2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Client:** Multimodal Freight Sdn Bhd (MMF)  
**Effective Date:** [Project Go-Live Date]  
**Date:** 31 January 2026

---

## 1. SLA OVERVIEW

### 1.1 Purpose

This Service Level Agreement (SLA) defines the service levels, performance standards, and support commitments provided by Sinergi Elit Sdn Bhd (SESB) for the Support IT System (EMS, PS, HRMS) delivered to Multimodal Freight Sdn Bhd (MMF).

### 1.2 Scope

This SLA covers:
- System availability and uptime
- Performance standards
- Support response and resolution times
- Maintenance windows
- Escalation procedures
- Reporting and monitoring

### 1.3 SLA Period

| Phase | Duration | Coverage |
|-------|----------|----------|
| **Warranty Phase** | 12 months from Go-Live | Full SLA coverage at no charge |
| **Annual Maintenance** | Year 2 onwards | As per signed maintenance contract |

---

## 2. SYSTEM AVAILABILITY

### 2.1 Availability Commitment

| Metric | Target | Measurement |
|--------|--------|-------------|
| **System Uptime** | 99.9% | 24/7/365 monitoring |
| **Scheduled Downtime** | <4 hours/month | Outside business hours (8 PM - 6 AM) |
| **Unplanned Downtime** | <1 hour/month | Emergency maintenance only |

### 2.2 Availability Calculation

```
Availability % = (Total Time - Downtime) / Total Time × 100

Where:
- Total Time = 24 hours × 7 days × measurement period
- Downtime = Time when system is unavailable for business use
- Exclusions: Scheduled maintenance with 72-hour notice
```

### 2.3 Availability Tiers

| Component | Target Uptime | Criticality |
|-----------|---------------|-------------|
| **EMS Application** | 99.9% | High |
| **PS Application** | 99.9% | High |
| **HRMS Application** | 99.9% | High |
| **Database** | 99.95% | Critical |
| **Network Connectivity** | 99.9% | High |
| **Backup Systems** | 99.99% | Critical |

### 2.4 Service Credits for Downtime

| Actual Uptime | Service Credit |
|---------------|----------------|
| 99.9% - 99.0% | 5% of monthly fee |
| 99.0% - 98.0% | 10% of monthly fee |
| 98.0% - 95.0% | 25% of monthly fee |
| < 95.0% | 50% of monthly fee |

*Service credits are capped at 50% of monthly maintenance fee and exclude force majeure events.*

---

## 3. PERFORMANCE STANDARDS

### 3.1 Response Time Targets

| Transaction Type | Target Response Time | Maximum Response Time |
|------------------|----------------------|----------------------|
| **Simple Query** | < 2 seconds | 5 seconds |
| **Complex Report** | < 10 seconds | 30 seconds |
| **Dashboard Load** | < 3 seconds | 8 seconds |
| **Search Results** | < 3 seconds | 10 seconds |
| **File Upload (<10MB)** | < 15 seconds | 60 seconds |
| **Batch Processing** | < 5 minutes | 15 minutes |

### 3.2 Concurrent User Support

| Metric | Target |
|--------|--------|
| **Supported Concurrent Users** | 250+ |
| **Peak Load Handling** | 300 concurrent users |
| **Session Timeout** | 30 minutes idle |
| **Maximum Session Duration** | 12 hours |

### 3.3 Data Processing Performance

| Operation | Target Throughput |
|-----------|-------------------|
| **Payroll Processing** | 500 employees/hour |
| **Invoice Processing** | 1,000 invoices/hour |
| **Report Generation** | 50 concurrent reports |
| **Data Import** | 10,000 records/hour |

---

## 4. SUPPORT SERVICES

### 4.1 Support Hours

| Support Level | Hours | Coverage |
|---------------|-------|----------|
| **Standard Support** | 8 AM - 6 PM (Mon-Fri) | Business hours |
| **Extended Support** | 8 AM - 8 PM (Mon-Sat) | Extended hours |
| **Premium Support** | 24/7/365 | Full time |

*Note: Premium Support included for Year 1 (Warranty Phase)*

### 4.2 Incident Priority & Response Times

| Priority | Definition | Response Time | Resolution Target | Escalation Time |
|----------|------------|---------------|-------------------|-----------------|
| **P1 - Critical** | System down, no workaround | 15 minutes | 4 hours | 1 hour |
| **P2 - High** | Major feature unavailable | 1 hour | 8 hours | 4 hours |
| **P3 - Medium** | Minor feature issue | 4 hours | 2 business days | 24 hours |
| **P4 - Low** | Cosmetic issue, enhancement | 8 hours | 5 business days | N/A |

### 4.3 Incident Priority Definitions

**P1 - Critical:**
- Complete system outage
- Security breach
- Data corruption
- No workaround available
- Business operations severely impacted

**P2 - High:**
- Major feature unavailable
- Significant performance degradation
- Workaround exists but impacts productivity
- Multiple users affected

**P3 - Medium:**
- Single feature not working correctly
- Intermittent issues
- Limited user impact
- Workaround available

**P4 - Low:**
- Cosmetic issues
- Enhancement requests
- Documentation errors
- Single user affected

### 4.4 Support Channels

| Channel | Availability | Target Response |
|---------|--------------|-----------------|
| **Phone Hotline** | 24/7 | Immediate (P1), <5 min (others) |
| **Email** | 24/7 | Per priority SLAs |
| **WhatsApp Business** | 24/7 | <30 minutes |
| **Self-Service Portal** | 24/7 | N/A (self-help) |
| **Remote Desktop** | Business hours | <1 hour |

### 4.5 Escalation Matrix

| Level | Timeframe | Responsibility | Action |
|-------|-----------|----------------|--------|
| **L1** | 0-15 min | Helpdesk | Log, categorize, initial triage |
| **L2** | 15 min - 2 hrs | Technical Support | Troubleshooting, workaround |
| **L3** | 2-4 hrs | Senior Engineer | Deep technical analysis |
| **L4** | 4-8 hrs | Development Team | Code fix, patch development |
| **Management** | 8+ hrs | Project Manager | Executive notification |
| **Executive** | 24+ hrs | Managing Director | Client relationship |

---

## 5. MAINTENANCE & UPDATES

### 5.1 Scheduled Maintenance Windows

| Maintenance Type | Frequency | Duration | Window |
|------------------|-----------|----------|--------|
| **Routine Maintenance** | Monthly | 2-4 hours | Sunday 2 AM - 6 AM |
| **Security Patches** | As needed | 1-2 hours | Sunday 2 AM - 4 AM |
| **Version Upgrades** | Quarterly | 4-8 hours | Sunday 12 AM - 8 AM |
| **Database Maintenance** | Monthly | 2 hours | Sunday 2 AM - 4 AM |

### 5.2 Maintenance Notification

| Maintenance Type | Advance Notice | Communication Method |
|------------------|----------------|----------------------|
| **Planned** | 72 hours | Email + Portal announcement |
| **Emergency** | 4 hours | Email + WhatsApp |
| **Urgent Security** | 2 hours | All channels |

### 5.3 Change Management

| Change Type | Approval Required | Notice Period |
|-------------|-------------------|---------------|
| **Minor (P4)** | SESB PM | 24 hours |
| **Standard (P3)** | MMF IT Manager | 72 hours |
| **Major (P1-P2)** | Steering Committee | 1 week |

---

## 6. BACKUP & RECOVERY

### 6.1 Backup Schedule

| Backup Type | Frequency | Retention |
|-------------|-----------|-----------|
| **Full Database** | Daily | 30 days |
| **Incremental** | Every 6 hours | 7 days |
| **Transaction Log** | Continuous | 24 hours |
| **File/Documents** | Daily | 90 days |
| **Offsite Backup** | Weekly | 1 year |

### 6.2 Recovery Objectives

| Metric | Target | Maximum |
|--------|--------|---------|
| **RPO (Recovery Point)** | < 1 hour | < 4 hours |
| **RTO (Recovery Time)** | < 4 hours | < 8 hours |

### 6.3 Disaster Recovery Testing

| Test Type | Frequency | Scope |
|-----------|-----------|-------|
| **Tabletop Exercise** | Quarterly | Process validation |
| **Failover Test** | Semi-annually | Technical validation |
| **Full DR Drill** | Annually | End-to-end validation |

---

## 7. SECURITY & COMPLIANCE

### 7.1 Security Commitments

| Security Control | Implementation |
|------------------|----------------|
| **Data Encryption** | AES-256 at rest, TLS 1.3 in transit |
| **Access Control** | Role-based (RBAC) + Multi-factor authentication |
| **Audit Logging** | 100% of administrative actions logged |
| **Vulnerability Scanning** | Monthly automated scans |
| **Penetration Testing** | Annual third-party VAPT |
| **Security Patching** | Critical patches within 72 hours |

### 7.2 Compliance Obligations

| Standard | Requirement | Verification |
|----------|-------------|--------------|
| **PDPA 2010** | Data protection compliance | Annual audit |
| **ISO 27001** | Information security management | Certificate valid |
| **KRISA/JDN** | Data sovereignty | Awan Kita deployment |
| **Industry Standards** | Best practice adherence | Quarterly review |

---

## 8. REPORTING & MONITORING

### 8.1 Service Reports

| Report | Frequency | Distribution |
|--------|-----------|--------------|
| **System Availability** | Monthly | MMF IT Manager |
| **Incident Summary** | Monthly | MMF IT Manager |
| **Performance Metrics** | Monthly | MMF IT Manager |
| **Security Status** | Quarterly | MMF CIO |
| **Capacity Planning** | Quarterly | MMF IT Manager |
| **SLA Compliance** | Quarterly | Steering Committee |

### 8.2 Report Contents

**Monthly Service Report includes:**
- System uptime percentage
- Incident count by priority
- Average resolution times
- Open issues status
- Performance metrics
- Upcoming maintenance

### 8.3 Real-Time Monitoring

| Monitoring Aspect | Tool | Alert Threshold |
|-------------------|------|-----------------|
| **System Availability** | Prometheus/Grafana | < 99.9% uptime |
| **Performance** | APM Tools | Response > 5 seconds |
| **Error Rates** | Sentry | > 1% error rate |
| **Resource Usage** | CloudWatch | CPU > 80%, Memory > 85% |
| **Security Events** | SIEM | Any critical alert |

---

## 9. ROLES & RESPONSIBILITIES

### 9.1 SESB Responsibilities

- Ensure system availability per SLA targets
- Provide technical support per response time commitments
- Apply security patches and updates
- Perform scheduled maintenance
- Provide monthly service reports
- Maintain backup and recovery systems
- Conduct regular health checks
- Provide training and documentation updates

### 9.2 MMF Responsibilities

- Provide timely issue reporting with adequate details
- Designate primary contacts for escalations
- Grant necessary access for maintenance activities
- Maintain network connectivity to system
- Ensure user compliance with security policies
- Review and approve scheduled maintenance windows
- Provide feedback on service quality
- Timely payment of maintenance fees

---

## 10. SLA REVIEW & AMENDMENT

### 10.1 Review Schedule

| Review Type | Frequency | Participants |
|-------------|-----------|--------------|
| **Operational Review** | Monthly | Support teams |
| **Service Review** | Quarterly | IT Managers |
| **Strategic Review** | Annually | Executives |

### 10.2 Amendment Process

1. Either party may request SLA amendment with 30 days written notice
2. Proposed changes must include business justification
3. Both parties must agree to amendments in writing
4. Amendments effective upon mutual signature

---

## 11. DEFINITIONS

| Term | Definition |
|------|------------|
| **Availability** | Percentage of time system is operational and accessible |
| **Business Hours** | 8:00 AM - 6:00 PM, Monday to Friday (MYT) |
| **Downtime** | Period when system is unavailable for normal business use |
| **Emergency Maintenance** | Unscheduled maintenance required to restore service |
| **Response Time** | Time from incident logging to initial support contact |
| **Resolution Time** | Time from incident logging to permanent fix or workaround |
| **Scheduled Maintenance** | Planned maintenance communicated in advance |
| **Service Credit** | Fee reduction applied for SLA breaches |
| **Workaround** | Temporary solution that restores partial functionality |

---

## 12. SIGNATURES

This Service Level Agreement is entered into on the date of final project acceptance.

**For SESB:**

___________________________  
**Encik Ahmad Bin Hassan**  
Managing Director  
Sinergi Elit Sdn Bhd  

Date: _______________

**For MMF:**

___________________________  
**[Name]**  
**[Title]**  
Multimodal Freight Sdn Bhd  

Date: _______________

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 02/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
