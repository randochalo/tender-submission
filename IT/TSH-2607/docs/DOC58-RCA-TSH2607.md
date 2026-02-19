# TSH-2607: USP Claims Management System (UCMS)
## Document 58: Root Cause Analysis (RCA) Template

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

This Root Cause Analysis (RCA) Template establishes the standardized methodology and format for conducting thorough investigations of significant incidents, system failures, and recurring issues affecting the USP Claims Management System (UCMS) during the 48-month support period.

### 1.1 Purpose
- Ensure systematic investigation of incidents and failures
- Identify true root causes rather than symptoms
- Prevent recurrence of issues through corrective actions
- Support continuous improvement of system reliability
- Provide documentation for audit and compliance purposes

### 1.2 When to Perform RCA
RCA is required for:
- Priority 1 (Critical) incidents
- Priority 2 (High) incidents with business impact
- Any incident causing system outage > 30 minutes
- Recurring issues (3+ occurrences within 30 days)
- Security breaches or data integrity issues
- SLA violations
- Any issue deemed significant by USP or the Resident Engineer

### 1.3 RCA Timeline Requirements

| **Priority** | **RCA Completion SLA** | **Interim Report** |
|--------------|------------------------|-------------------|
| Critical (P1) | Within 24 hours | Within 4 hours |
| High (P2) | Within 48 hours | Within 12 hours |
| Medium (P3) | Within 5 business days | Within 24 hours |

---

## 2. INCIDENT SUMMARY

### 2.1 Basic Information

| **Field** | **Details** |
|-----------|-------------|
| **RCA ID** | RCA-YYYY-XXXX |
| **Related Incident ID** | INC-YYYY-XXXX |
| **Related Ticket/Change Request** | [Reference numbers] |
| **Incident Date & Time** | [DD/MM/YYYY HH:MM] |
| **Detection Date & Time** | [DD/MM/YYYY HH:MM] |
| **Resolution Date & Time** | [DD/MM/YYYY HH:MM] |
| **Total Downtime** | [Duration] |
| **Detection Source** | ☐ Monitoring Alert ☐ User Report ☐ Automated Alert ☐ Routine Check ☐ Other: ___ |

### 2.2 Incident Classification

| **Field** | **Classification** |
|-----------|-------------------|
| **Severity Level** | ☐ Critical ☐ High ☐ Medium ☐ Low |
| **Priority Level** | ☐ P1 - Critical ☐ P2 - High ☐ P3 - Medium ☐ P4 - Low |
| **Incident Category** | ☐ Hardware Failure ☐ Software Defect ☐ Configuration Error ☐ Network Issue ☐ Database Issue ☐ Security Incident ☐ Performance Degradation ☐ Data Corruption ☐ User Error ☐ Third-Party Failure ☐ Environmental ☐ Unknown |
| **Affected Module(s)** | |
| **Affected Environment** | ☐ Production ☐ Staging ☐ Development ☐ Multiple |

### 2.3 Impact Assessment

| **Impact Area** | **Impact Level** | **Details** |
|-----------------|------------------|-------------|
| **Business Operations** | ☐ Critical ☐ High ☐ Medium ☐ Low | |
| **Users Affected** | ☐ All ☐ Many ☐ Some ☐ Few | |
| **Data Integrity** | ☐ Compromised ☐ At Risk ☐ Verified OK | |
| **Financial Impact** | ☐ Significant ☐ Moderate ☐ Minimal ☐ None | |
| **Regulatory Impact** | ☐ Yes ☐ No | |
| **Reputation Impact** | ☐ Significant ☐ Moderate ☐ Minimal ☐ None | |
| **SLA Breach** | ☐ Yes ☐ No | |

### 2.4 Incident Timeline

| **Time (from start)** | **Event** | **Action Taken** | **Responsible** |
|-----------------------|-----------|------------------|-----------------|
| T+0 min | Incident occurred | | |
| | | | |
| | | | |
| | | | |
| | | | |

---

## 3. PROBLEM DESCRIPTION

### 3.1 What Happened?
[Provide a clear, factual description of the incident from start to finish]

### 3.2 Symptoms Observed
| **Symptom** | **First Observed** | **Duration** | **Severity** |
|-------------|-------------------|--------------|--------------|
| | | | |
| | | | |
| | | | |

### 3.3 Error Messages and Logs
| **Source** | **Error/Log Entry** | **Timestamp** |
|------------|---------------------|---------------|
| Application Log | | |
| System Log | | |
| Database Log | | |
| Monitoring Tool | | |

---

## 4. INVESTIGATION METHODOLOGY

### 4.1 Investigation Approach
The following investigation methods were employed:

| **Method** | **Used** | **Findings** |
|------------|----------|--------------|
| 5 Whys Analysis | ☐ Yes ☐ No | |
| Fishbone/Ishikawa Diagram | ☐ Yes ☐ No | |
| Fault Tree Analysis | ☐ Yes ☐ No | |
| Timeline Reconstruction | ☐ Yes ☐ No | |
| Log Analysis | ☐ Yes ☐ No | |
| Stakeholder Interviews | ☐ Yes ☐ No | |
| System State Review | ☐ Yes ☐ No | |
| Change History Review | ☐ Yes ☐ No | |

### 4.2 Investigation Team

| **Role** | **Name** | **Organization** | **Responsibility** |
|----------|----------|------------------|-------------------|
| RCA Lead | | | Overall coordination |
| Technical Lead | | | Technical investigation |
| Resident Engineer | | | System context |
| Subject Matter Expert | | | Domain expertise |
| Business Representative | | USP | Business impact assessment |

### 4.3 Evidence Collected

| **Evidence Type** | **Description** | **Collected By** | **Date** |
|-------------------|-----------------|------------------|----------|
| System Logs | | | |
| Application Logs | | | |
| Configuration Files | | | |
| Screenshots | | | |
| Network Traces | | | |
| Database Snapshots | | | |
| User Reports | | | |

---

## 5. ROOT CAUSE ANALYSIS

### 5.1 5 Whys Analysis

| **Why Level** | **Question** | **Answer** |
|---------------|--------------|------------|
| Why 1 | Why did the incident occur? | |
| Why 2 | Why did [answer to Why 1] happen? | |
| Why 3 | Why did [answer to Why 2] happen? | |
| Why 4 | Why did [answer to Why 3] happen? | |
| Why 5 | Why did [answer to Why 4] happen? | |

### 5.2 Root Cause Categorization

| **Category** | **Description** |
|--------------|-----------------|
| **Primary Root Cause** | |
| Category | ☐ Human Error ☐ Process Failure ☐ Technical Defect ☐ Configuration Issue ☐ Environmental ☐ Third-Party ☐ Other |
| **Contributing Factors** | |
| 1 | |
| 2 | |
| 3 | |

### 5.3 Detailed Root Cause Description
[Provide comprehensive explanation of the root cause identified]

### 5.4 Contributing Factors Analysis

| **Factor** | **Category** | **Impact** | **Evidence** |
|------------|--------------|------------|--------------|
| | ☐ People ☐ Process ☐ Technology | | |
| | ☐ People ☐ Process ☐ Technology | | |
| | ☐ People ☐ Process ☐ Technology | | |

### 5.5 Fishbone Diagram Summary (Optional)

| **Category** | **Potential Causes** | **Validated?** | **Root Cause?** |
|--------------|----------------------|----------------|-----------------|
| **People** | | ☐ Yes ☐ No | ☐ Yes ☐ No |
| **Process** | | ☐ Yes ☐ No | ☐ Yes ☐ No |
| **Technology** | | ☐ Yes ☐ No | ☐ Yes ☐ No |
| **Environment** | | ☐ Yes ☐ No | ☐ Yes ☐ No |
| **Materials/Data** | | ☐ Yes ☐ No | ☐ Yes ☐ No |

---

## 6. CORRECTIVE ACTIONS

### 6.1 Immediate Actions (Taken)
Actions already performed to resolve the immediate issue:

| **Action** | **Taken By** | **Date** | **Outcome** |
|------------|--------------|----------|-------------|
| | | | ☐ Successful ☐ Partial ☐ Failed |
| | | | ☐ Successful ☐ Partial ☐ Failed |
| | | | ☐ Successful ☐ Partial ☐ Failed |

### 6.2 Short-Term Corrective Actions (0-30 days)

| **ID** | **Action** | **Owner** | **Target Date** | **Status** | **Verification** |
|--------|------------|-----------|-----------------|------------|------------------|
| ST-01 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |
| ST-02 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |
| ST-03 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |

### 6.3 Long-Term Corrective Actions (30+ days)

| **ID** | **Action** | **Owner** | **Target Date** | **Status** | **Verification** |
|--------|------------|-----------|-----------------|------------|------------------|
| LT-01 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |
| LT-02 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |
| LT-03 | | | | ☐ Not Started ☐ In Progress ☐ Complete | |

### 6.4 Preventive Actions (To prevent recurrence)

| **ID** | **Action** | **Owner** | **Target Date** | **Status** |
|--------|------------|-----------|-----------------|------------|
| PR-01 | | | | ☐ Not Started ☐ In Progress ☐ Complete |
| PR-02 | | | | ☐ Not Started ☐ In Progress ☐ Complete |
| PR-03 | | | | ☐ Not Started ☐ In Progress ☐ Complete |

---

## 7. LESSONS LEARNED

### 7.1 What Went Well?
[Identify aspects of the response that were effective]

| **Aspect** | **Description** |
|------------|-----------------|
| | |
| | |

### 7.2 What Could Be Improved?
[Identify areas for improvement in prevention, detection, or response]

| **Area** | **Issue** | **Improvement Suggestion** |
|----------|-----------|---------------------------|
| Detection | | |
| Response | | |
| Communication | | |
| Resolution | | |

### 7.3 Knowledge Gaps Identified

| **Gap** | **Impact** | **Action to Address** | **Owner** |
|---------|------------|----------------------|-----------|
| | | | |
| | | | |

---

## 8. RECOMMENDATIONS

### 8.1 Process Improvements

| **ID** | **Recommendation** | **Priority** | **Expected Benefit** | **Effort** |
|--------|-------------------|--------------|---------------------|------------|
| 1 | | ☐ High ☐ Medium ☐ Low | | ☐ High ☐ Medium ☐ Low |
| 2 | | ☐ High ☐ Medium ☐ Low | | ☐ High ☐ Medium ☐ Low |
| 3 | | ☐ High ☐ Medium ☐ Low | | ☐ High ☐ Medium ☐ Low |

### 8.2 Technical Improvements

| **ID** | **Recommendation** | **Priority** | **Expected Benefit** | **Effort** |
|--------|-------------------|--------------|---------------------|------------|
| 1 | | ☐ High ☐ Medium ☐ Low | | ☐ High ☐ Medium ☐ Low |
| 2 | | ☐ High ☐ Medium ☐ Low | | ☐ High ☐ Medium ☐ Low |

### 8.3 Training Needs

| **Audience** | **Training Required** | **Priority** | **Timeline** |
|--------------|----------------------|--------------|--------------|
| | | ☐ High ☐ Medium ☐ Low | |
| | | ☐ High ☐ Medium ☐ Low | |

---

## 9. APPROVAL AND SIGN-OFF

### 9.1 RCA Prepared By

| **Field** | **Details** |
|-----------|-------------|
| Name | |
| Title | |
| Organization | |
| Signature | |
| Date | |

### 9.2 Technical Review

| **Field** | **Details** |
|-----------|-------------|
| Reviewed By | |
| Title | |
| Date | |
| Comments | |

### 9.3 Management Approval

| **Field** | **Details** |
|-----------|-------------|
| Approved By | |
| Title | |
| Organization | |
| Signature | |
| Date | |

### 9.4 Client Acceptance

| **Field** | **Details** |
|-----------|-------------|
| Accepted By | |
| Title | |
| Organization | USP |
| Signature | |
| Date | |

---

## 10. APPENDICES

### Appendix A: Supporting Documentation
- [ ] Incident Report
- [ ] System Logs (relevant extracts)
- [ ] Change History
- [ ] Configuration Files
- [ ] Network Diagrams
- [ ] Monitoring Data
- [ ] Communication Records

### Appendix B: Related RCAs
| **RCA ID** | **Incident** | **Date** | **Relation to Current RCA** |
|------------|--------------|----------|----------------------------|
| | | | |

### Appendix C: Change Records
| **Version** | **Date** | **Author** | **Changes Made** |
|-------------|----------|------------|------------------|
| 1.0 | | | Initial RCA created |
| | | | |

---

## 11. DISTRIBUTION LIST

| **Role** | **Name** | **Organization** | **Date Sent** |
|----------|----------|------------------|---------------|
| Resident Engineer | | | |
| IT Manager | | USP | |
| System Administrator | | USP | |
| IT Security Officer | | USP | |
| Contract Manager | | | |
| Service Delivery Manager | | | |

---

## 12. REVIEW SCHEDULE

| **Review Type** | **Scheduled Date** | **Completed** | **Outcome** |
|-----------------|-------------------|---------------|-------------|
| Action Items Review | | ☐ Yes ☐ No | |
| Effectiveness Review | | ☐ Yes ☐ No | |
| Closure Verification | | ☐ Yes ☐ No | |

---

*End of Root Cause Analysis (RCA) Template*

**Document Classification:** Tender Submission Document  
**Tender Reference:** TSH-2607 - USP Claims Management System (UCMS)  
**Page 1 of 1**

---

## QUICK REFERENCE: RCA TRIGGERS

| **Trigger Condition** | **RCA Required** | **Timeline** |
|----------------------|------------------|--------------|
| Priority 1 Incident | Yes | Within 24 hours |
| System Outage > 30 min | Yes | Within 48 hours |
| Data Integrity Issue | Yes | Within 24 hours |
| Security Breach | Yes | Within 24 hours |
| Recurring Issue (3+ in 30 days) | Yes | Within 5 days |
| SLA Breach | Yes | Within 48 hours |
| Priority 2 with Business Impact | Yes | Within 48 hours |
