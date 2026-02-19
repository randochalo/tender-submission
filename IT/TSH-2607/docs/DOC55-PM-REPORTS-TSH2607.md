# TSH-2607: USP Claims Management System (UCMS)
## Document 55: Preventive Maintenance Reports Template

---

| **Document Control** | |
|----------------------|---|
| **Tender Reference** | TSH-2607 |
| **Project** | USP Claims Management System (UCMS) |
| **Support Period** | 48 Months (12 Months Warranty + 36 Months Extended) |
| **Document Version** | 1.0 |
| **Classification** | Tender Submission - Phase 11: Maintenance & Support |

---

## 1. OVERVIEW

This Preventive Maintenance Reports Template establishes the standardized format for documenting all scheduled preventive maintenance activities performed on the USP Claims Management System (UCMS) during the 48-month support period.

### 1.1 Purpose
- Ensure consistent documentation of preventive maintenance activities
- Track system health metrics and trends over time
- Demonstrate compliance with SLAs and maintenance schedules
- Support audit and compliance requirements

### 1.2 Scope
- Hardware preventive maintenance
- Software health checks and optimization
- Database maintenance and tuning
- Security configuration reviews
- Backup and recovery verification

---

## 2. PREVENTIVE MAINTENANCE REPORT TEMPLATE

### 2.1 Report Header Information

| **Field** | **Description** |
|-----------|-----------------|
| Report ID | PM-YYYY-MM-XXX (Sequential numbering) |
| Report Date | [DD/MM/YYYY] |
| Reporting Period | [From: DD/MM/YYYY To: DD/MM/YYYY] |
| Resident Engineer | [Name] |
| Reviewed By | [Name/Title] |
| Approved By | [Name/Title] |
| Distribution | [Recipient List] |

### 2.2 System Information

| **Field** | **Details** |
|-----------|-------------|
| System Name | USP Claims Management System (UCMS) |
| Environment | Production / Staging / Development |
| Server Details | [Hostname, IP Address] |
| Software Version | [Current UCMS Version] |
| Database Version | [Current Database Version] |
| Last PM Date | [Previous maintenance date] |

### 2.3 Maintenance Schedule Compliance

| **Activity** | **Scheduled Frequency** | **Last Completed** | **Due Date** | **Status** |
|--------------|------------------------|--------------------|--------------|------------|
| System Health Check | Monthly | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Database Optimization | Monthly | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Security Patch Review | Monthly | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Full System Backup Test | Quarterly | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Performance Baseline Review | Quarterly | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Disaster Recovery Drill | Semi-Annual | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |
| Capacity Planning Review | Annual | [Date] | [Date] | ☐ Completed ☐ Pending ☐ Overdue |

---

## 3. DETAILED MAINTENANCE ACTIVITIES

### 3.1 Hardware Maintenance

| **Component** | **Activity** | **Status** | **Findings** | **Action Required** |
|---------------|--------------|------------|--------------|---------------------|
| Servers | Physical inspection, cleaning | ☐ Pass ☐ Fail | | |
| Storage | Capacity check, health status | ☐ Pass ☐ Fail | | |
| Network | Connectivity, bandwidth test | ☐ Pass ☐ Fail | | |
| UPS/Power | Battery test, load check | ☐ Pass ☐ Fail | | |
| Cooling | Temperature monitoring | ☐ Pass ☐ Fail | | |

### 3.2 Software Maintenance

| **Component** | **Activity** | **Status** | **Findings** | **Action Required** |
|---------------|--------------|------------|--------------|---------------------|
| Operating System | Patch status, log review | ☐ Pass ☐ Fail | | |
| UCMS Application | Version check, log analysis | ☐ Pass ☐ Fail | | |
| Middleware | Status check, config review | ☐ Pass ☐ Fail | | |
| Antivirus | Definition update, scan | ☐ Pass ☐ Fail | | |
| Monitoring Tools | Agent status, alert test | ☐ Pass ☐ Fail | | |

### 3.3 Database Maintenance

| **Activity** | **Status** | **Before Value** | **After Value** | **Findings** |
|--------------|------------|------------------|-----------------|--------------|
| Index fragmentation check | ☐ Pass ☐ Fail | | | |
| Statistics update | ☐ Pass ☐ Fail | | | |
| Log file management | ☐ Pass ☐ Fail | | | |
| Database integrity check | ☐ Pass ☐ Fail | | | |
| Backup verification | ☐ Pass ☐ Fail | | | |
| Storage space analysis | ☐ Pass ☐ Fail | % used | % used | |
| Query performance review | ☐ Pass ☐ Fail | Avg: ms | Avg: ms | |

### 3.4 Security Maintenance

| **Activity** | **Status** | **Findings** | **Remediation** |
|--------------|------------|--------------|-----------------|
| User access review | ☐ Pass ☐ Fail | | |
| Privilege audit | ☐ Pass ☐ Fail | | |
| Password policy compliance | ☐ Pass ☐ Fail | | |
| Security log review | ☐ Pass ☐ Fail | | |
| SSL certificate expiry check | ☐ Pass ☐ Fail | | |
| Firewall rule review | ☐ Pass ☐ Fail | | |
| Vulnerability scan | ☐ Pass ☐ Fail | | |

---

## 4. PERFORMANCE METRICS

### 4.1 System Performance Indicators

| **Metric** | **Baseline** | **Previous Reading** | **Current Reading** | **Status** |
|------------|--------------|----------------------|---------------------|------------|
| CPU Utilization (Avg) | | % | % | ☐ Normal ☐ Warning ☐ Critical |
| Memory Utilization (Avg) | | % | % | ☐ Normal ☐ Warning ☐ Critical |
| Disk I/O (Avg) | | IOPS | IOPS | ☐ Normal ☐ Warning ☐ Critical |
| Network Latency | | ms | ms | ☐ Normal ☐ Warning ☐ Critical |
| Application Response Time | | ms | ms | ☐ Normal ☐ Warning ☐ Critical |
| Database Query Time (Avg) | | ms | ms | ☐ Normal ☐ Warning ☐ Critical |
| Concurrent Users (Peak) | | users | users | ☐ Normal ☐ Warning ☐ Critical |

### 4.2 Availability Statistics

| **Period** | **Target Uptime** | **Actual Uptime** | **Availability %** | **Status** |
|------------|-------------------|-------------------|--------------------|------------|
| This Reporting Period | 99.9% | | | ☐ Met ☐ Not Met |
| Year-to-Date | 99.9% | | | ☐ Met ☐ Not Met |
| Since Go-Live | 99.9% | | | ☐ Met ☐ Not Met |

---

## 5. ISSUES IDENTIFIED AND RESOLUTION

| **ID** | **Issue Description** | **Severity** | **Date Identified** | **Resolution** | **Status** | **Closed Date** |
|--------|----------------------|--------------|---------------------|----------------|------------|-----------------|
| 1 | | ☐ Low ☐ Medium ☐ High ☐ Critical | | | ☐ Open ☐ Closed | |
| 2 | | ☐ Low ☐ Medium ☐ High ☐ Critical | | | ☐ Open ☐ Closed | |
| 3 | | ☐ Low ☐ Medium ☐ High ☐ Critical | | | ☐ Open ☐ Closed | |

---

## 6. RECOMMENDATIONS

| **ID** | **Recommendation** | **Priority** | **Expected Benefit** | **Estimated Effort** |
|--------|-------------------|--------------|---------------------|----------------------|
| 1 | | ☐ Low ☐ Medium ☐ High | | |
| 2 | | ☐ Low ☐ Medium ☐ High | | |
| 3 | | ☐ Low ☐ Medium ☐ High | | |

---

## 7. MAINTENANCE ACTIVITY LOG

| **Date/Time** | **Activity** | **Performed By** | **Duration** | **Outcome** |
|---------------|--------------|------------------|--------------|-------------|
| | | | minutes | ☐ Successful ☐ Issues Encountered |
| | | | minutes | ☐ Successful ☐ Issues Encountered |
| | | | minutes | ☐ Successful ☐ Issues Encountered |

---

## 8. SIGN-OFF

### 8.1 Resident Engineer Certification

I certify that the preventive maintenance activities documented in this report have been performed in accordance with the maintenance schedule and procedures defined for the UCMS system.

| **Field** | **Details** |
|-----------|-------------|
| Name | |
| Signature | |
| Date | |
| Employee ID | |

### 8.2 Client Acknowledgment

| **Field** | **Details** |
|-----------|-------------|
| Name | |
| Title | |
| Signature | |
| Date | |

### 8.3 Management Review

| **Field** | **Details** |
|-----------|-------------|
| Reviewed By | |
| Review Date | |
| Comments | |

---

## 9. APPENDICES

### Appendix A: Maintenance Checklists Used
- [ ] Hardware Maintenance Checklist
- [ ] Software Maintenance Checklist
- [ ] Database Maintenance Checklist
- [ ] Security Maintenance Checklist

### Appendix B: Supporting Documentation
- [ ] Performance Charts
- [ ] Log File Excerpts
- [ ] Backup Verification Reports
- [ ] Vulnerability Scan Results

### Appendix C: Change Records
| **Version** | **Date** | **Author** | **Changes Made** |
|-------------|----------|------------|------------------|
| 1.0 | | | Initial template creation |

---

## 10. DISTRIBUTION LIST

| **Role** | **Name** | **Organization** | **Date Sent** |
|----------|----------|------------------|---------------|
| Resident Engineer | | | |
| IT Manager | | USP | |
| System Administrator | | USP | |
| Contract Manager | | | |

---

*End of Preventive Maintenance Reports Template*

**Document Classification:** Tender Submission Document  
**Tender Reference:** TSH-2607 - USP Claims Management System (UCMS)  
**Page 1 of 1**
