# ANNEX H: SERVICE LEVEL AGREEMENT (SLA)

**Tender Reference:** T/SUKSEL/04-2026  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Client:** Pejabat Setiausaha Kerajaan Negeri Selangor  
**Project:** Sistem ePINGAT Negeri Selangor  
**Date:** 31 January 2026

---

## 1. SLA OVERVIEW

### 1.1 Scope

This Service Level Agreement defines the service levels, performance standards, and support commitments provided by SESB for the Sistem ePINGAT Negeri Selangor for 27 months (18 months development + 9 months warranty).

### 1.2 SLA Period

| Phase | Duration | Coverage |
|-------|----------|----------|
| **Development Phase** | Month 1-18 | Project delivery |
| **Warranty Phase** | Month 19-27 | Support at no charge |

---

## 2. SYSTEM AVAILABILITY

### 2.1 Uptime Commitments (Post Go-Live)

| Component | Target Uptime | Measurement |
|-----------|---------------|-------------|
| **Production System** | 99.5% | 24/7/365 monitoring |
| **Database** | 99.9% | 24/7/365 monitoring |
| **Backup System** | 99.9% | 24/7/365 monitoring |

### 2.2 Scheduled Maintenance

| Maintenance Type | Frequency | Duration | Window |
|------------------|-----------|----------|--------|
| **Routine Maintenance** | Monthly | 2-4 hours | Sunday 2:00-6:00 AM |
| **Major Updates** | Quarterly | 4-8 hours | Sunday 12:00-8:00 AM |
| **Emergency** | As needed | < 1 hour | Any time with notice |

### 2.3 Service Credits (Warranty Phase Only)

| Actual Uptime | Service Credit |
|---------------|----------------|
| 99.5% - 99.0% | 5% of monthly maintenance fee |
| 99.0% - 98.0% | 10% of monthly maintenance fee |
| < 98.0% | 25% of monthly maintenance fee |

---

## 3. PERFORMANCE STANDARDS

### 3.1 Response Time Targets

| Operation | Target | Maximum |
|-----------|--------|---------|
| **Page Load (Simple)** | < 2 seconds | 5 seconds |
| **Page Load (Complex)** | < 5 seconds | 10 seconds |
| **Database Query** | < 1 second | 3 seconds |
| **Report Generation** | < 10 seconds | 30 seconds |
| **File Upload (<5MB)** | < 5 seconds | 15 seconds |

### 3.2 Concurrent User Support

| Metric | Target |
|--------|--------|
| **Supported Concurrent Users** | 500+ |
| **Peak Load Handling** | 1,000 concurrent users |
| **Session Timeout** | 30 minutes idle |

---

## 4. SUPPORT SERVICES

### 4.1 Support Levels (Warranty Phase)

| Support Level | Hours | Response Time |
|--------------|-------|---------------|
| **Business Hours** | 8 AM - 6 PM (Mon-Fri) | 4 hours |
| **Extended Hours** | 8 AM - 8 PM (Mon-Sat) | 8 hours |
| **Emergency** | 24/7 (Critical issues only) | 2 hours |

### 4.2 Incident Response (Warranty Phase)

| Priority | Definition | Response Time | Resolution Target |
|----------|------------|---------------|-------------------|
| **P1 - Critical** | System down, no workaround | 2 hours | 24 hours |
| **P2 - High** | Major feature unavailable | 4 hours | 48 hours |
| **P3 - Medium** | Minor feature issue | 8 hours | 5 business days |
| **P4 - Low** | Cosmetic issue | 24 hours | 10 business days |

### 4.3 Support Channels

| Channel | Availability | Target Response |
|---------|--------------|-----------------|
| **Email** | 24/7 | Per priority SLA |
| **Phone** | Business hours | Immediate (P1) |
| **WhatsApp** | Business hours | < 4 hours |
| **Self-Service Portal** | 24/7 | N/A |

---

## 5. DELIVERABLES & TIMELINE

### 5.1 Development Phase Deliverables

| Deliverable | Due Date | Status Update |
|-------------|----------|---------------|
| URS Document | Month 2 | Monthly |
| SRS Document | Month 2 | Monthly |
| Design Documents | Month 4 | Monthly |
| Progress Reports | Monthly | Monthly |
| Test Reports | Month 14 | Monthly |
| User Manuals | Month 16 | Monthly |
| Training Completion | Month 17 | Monthly |
| System Handover | Month 18 | Final |

### 5.2 Development Progress Reporting

| Report | Frequency | Contents |
|--------|-----------|----------|
| **Progress Report** | Bi-weekly | Tasks completed, upcoming tasks, blockers |
| **Monthly Report** | Monthly | Overall progress, risks, issues |
| **Quarterly Review** | Quarterly | Strategic review, milestone status |

---

## 6. SECURITY & DATA PROTECTION

### 6.1 Security Commitments

| Control | Implementation |
|---------|----------------|
| **Data Encryption** | AES-256 at rest, TLS 1.3 in transit |
| **Access Control** | RBAC with principle of least privilege |
| **Audit Logging** | All user actions logged |
| **Backup** | Daily encrypted backups |
| **Password Policy** | Strong passwords, regular rotation |

### 6.2 Data Protection (PDPA Compliance)

| Requirement | Implementation |
|-------------|----------------|
| **Data Minimization** | Only collect necessary data |
| **Consent Management** | Record and manage user consent |
| **Data Retention** | Define and enforce retention periods |
| **Right to Access** | Users can view their data |
| **Right to Deletion** | Secure deletion upon request |

---

## 7. BACKUP & DISASTER RECOVERY

### 7.1 Backup Schedule

| Backup Type | Frequency | Retention |
|-------------|-----------|-----------|
| **Database Full** | Daily | 30 days |
| **Database Incremental** | Hourly | 7 days |
| **File Storage** | Daily | 30 days |
| **Offsite Backup** | Weekly | 90 days |

### 7.2 Recovery Objectives

| Metric | Target |
|--------|--------|
| **RPO (Data Loss)** | < 1 hour |
| **RTO (Recovery Time)** | < 4 hours |

### 7.3 Disaster Recovery Testing

| Test Type | Frequency |
|-----------|-----------|
| **Backup Restore Test** | Monthly |
| **Failover Test** | Quarterly |
| **Full DR Drill** | Annually |

---

## 8. ACCEPTANCE CRITERIA

### 8.1 UAT Acceptance Criteria

| Criterion | Requirement |
|-----------|-------------|
| **Functionality** | All requirements from URS implemented |
| **Performance** | Response times meet SLA targets |
| **Security** | Security testing passed |
| **Documentation** | All documentation delivered |
| **Training** | Users trained and competent |
| **Bug Severity** | No Critical or High bugs remaining |

### 8.2 Final Acceptance Criteria

| Criterion | Requirement |
|-----------|-------------|
| **System Live** | Successfully deployed to production |
| **UAT Sign-off** | Client sign-off on UAT |
| **Training Complete** | All training sessions completed |
| **Documentation** | All manuals delivered |
| **Knowledge Transfer** | Client IT team trained |

---

## 9. ROLES & RESPONSIBILITIES

### 9.1 SESB Responsibilities

- Deliver system as per URS/SRS specifications
- Provide regular progress reports
- Conduct training sessions
- Provide warranty support for 9 months
- Maintain system security
- Perform regular backups

### 9.2 Client Responsibilities

- Provide timely feedback on deliverables
- Assign key users for UAT
- Provide necessary system access
- Attend training sessions
- Timely review and approval of documents

---

## 10. GOVERNANCE & REPORTING

### 10.1 Governance Structure

| Meeting | Frequency | Participants |
|---------|-----------|--------------|
| **Steering Committee** | Monthly | Directors |
| **Project Review** | Weekly | PM, Client Lead |
| **Technical Review** | Bi-weekly | Tech leads |

### 10.2 SLA Review

- SLA review at project milestones
- Annual review during warranty period
- Amendments require written agreement

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Tender Reference | T/SUKSEL/04-2026 |

---

*This document is part of the tender submission for Pejabat Setiausaha Kerajaan Negeri Selangor.*
