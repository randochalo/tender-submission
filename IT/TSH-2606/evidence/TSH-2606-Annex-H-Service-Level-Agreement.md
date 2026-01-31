# ANNEX H: SERVICE LEVEL AGREEMENT

**Tender Reference:** JMYR/RFP/2026/001  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Client:** JMYR Sdn. Bhd.  
**Effective Date:** [Project Go-Live Date]  
**Date:** 31 January 2026

---

## 1. SLA OVERVIEW

### 1.1 Scope

This Service Level Agreement (SLA) defines the service levels, performance standards, and support commitments provided by SESB for the JMYR Cross-Border Payment Gateway.

### 1.2 SLA Period

| Phase | Duration | Coverage |
|-------|----------|----------|
| **Warranty Phase** | 12 months from Go-Live | Full SLA at no charge |
| **Maintenance Phase** | Year 2 onwards | As per maintenance contract |

---

## 2. SYSTEM AVAILABILITY

### 2.1 Uptime Commitments

| Component | Target Uptime | Measurement |
|-----------|---------------|-------------|
| **Payment Gateway API** | 99.99% | 24/7/365 monitoring |
| **Web Application** | 99.99% | 24/7/365 monitoring |
| **Mobile Applications** | 99.95% | 24/7/365 monitoring |
| **Blockchain Node** | 99.99% | 24/7/365 monitoring |
| **Database** | 99.999% | 24/7/365 monitoring |

### 2.2 Scheduled Maintenance

| Maintenance Type | Frequency | Duration | Window |
|------------------|-----------|----------|--------|
| **Routine** | Weekly | 2 hours | Sunday 2:00-4:00 AM MYT |
| **Major Updates** | Monthly | 4 hours | Sunday 12:00-4:00 AM MYT |
| **Emergency** | As needed | < 1 hour | Any time with notice |

### 2.3 Service Credits

| Actual Uptime | Service Credit |
|---------------|----------------|
| 99.99% - 99.9% | 5% of monthly fee |
| 99.9% - 99.0% | 10% of monthly fee |
| 99.0% - 95.0% | 25% of monthly fee |
| < 95.0% | 50% of monthly fee |

*Credits capped at 50% of monthly fee. Excludes force majeure.*

---

## 3. PERFORMANCE STANDARDS

### 3.1 Response Time Targets

| Operation | Target | Maximum |
|-----------|--------|---------|
| **API Authentication** | < 100ms | 500ms |
| **Quote Generation** | < 200ms | 1 second |
| **Transaction Submission** | < 500ms | 3 seconds |
| **Balance Query** | < 100ms | 500ms |
| **Transaction History** | < 500ms | 2 seconds |
| **KYC Verification** | < 3 seconds | 10 seconds |
| **Settlement Confirmation** | < 5 seconds | 15 seconds |

### 3.2 Throughput Capacity

| Metric | Target | Burst Capacity |
|--------|--------|----------------|
| **Peak TPS** | 1,000 | 2,000 |
| **Daily Transactions** | 5,000,000 | 10,000,000 |
| **Concurrent Users** | 50,000 | 100,000 |

---

## 4. SUPPORT SERVICES

### 4.1 Support Levels

| Support Tier | Hours | Coverage |
|--------------|-------|----------|
| **L1 - Basic** | 8x5 (Business hours) | General inquiries, how-to support |
| **L2 - Professional** | 12x6 | Technical issues, troubleshooting |
| **L3 - Enterprise** | 24x7 | Critical issues, production incidents |

### 4.2 Incident Response Times

| Priority | Definition | Response Time | Resolution Target | Escalation |
|----------|------------|---------------|-------------------|------------|
| **P1 - Critical** | Complete system outage, no workaround | 15 minutes | 4 hours | Immediate |
| **P2 - High** | Major feature unavailable, workaround exists | 1 hour | 8 hours | 4 hours |
| **P3 - Medium** | Minor feature issue, limited impact | 4 hours | 2 business days | 24 hours |
| **P4 - Low** | Cosmetic issue, enhancement request | 8 hours | 5 business days | N/A |

### 4.3 Critical Incident (P1) Examples

- Users unable to complete transactions
- Blockchain settlement failures
- Security breach or suspected compromise
- Database corruption or data loss
- Regulatory compliance system failure

### 4.4 Support Channels

| Channel | Availability | Target Response |
|---------|--------------|-----------------|
| **Phone Hotline** | 24x7 (P1-P2) | Immediate (P1), <5 min (P2) |
| **Email** | 24x7 | Per priority SLA |
| **Slack/Teams** | Business hours | <30 minutes |
| **Self-Service Portal** | 24x7 | N/A (self-help) |
| **Emergency Escalation** | 24x7 | <15 minutes |

---

## 5. SECURITY & COMPLIANCE

### 5.1 Security Commitments

| Control | Implementation | Verification |
|---------|----------------|--------------|
| **Data Encryption** | AES-256 at rest, TLS 1.3 in transit | Continuous |
| **Access Control** | MFA, RBAC, least privilege | Quarterly review |
| **Audit Logging** | 100% of transactions logged | Real-time |
| **Vulnerability Scanning** | Weekly automated scans | Weekly reports |
| **Penetration Testing** | Quarterly by third party | Quarterly reports |
| **Blockchain Monitoring** | 24/7 anomaly detection | Real-time alerts |

### 5.2 Compliance Reporting

| Report | Frequency | Distribution |
|--------|-----------|--------------|
| **Transaction Reports** | Daily | JMYR Operations |
| **AML/SAR Reports** | As required | JMYR Compliance |
| **Reserve Attestation** | Weekly | JMYR + Public |
| **Security Status** | Monthly | JMYR Security |
| **Audit Logs** | On demand | JMYR + Auditors |

---

## 6. BACKUP & DISASTER RECOVERY

### 6.1 Backup Schedule

| Data Type | Frequency | Retention | Location |
|-----------|-----------|-----------|----------|
| **Database** | Continuous WAL + Hourly | 30 days | Primary + DR |
| **Blockchain State** | Real-time sync | Full history | Primary + DR |
| **Audit Logs** | Real-time replication | 7 years | Immutable storage |
| **Configuration** | Daily + On change | 90 days | Version control |

### 6.2 Recovery Objectives

| Metric | Target | Maximum |
|--------|--------|---------|
| **RPO (Data Loss)** | < 1 minute | < 5 minutes |
| **RTO (Recovery Time)** | < 30 minutes | < 2 hours |

### 6.3 DR Testing

| Test Type | Frequency | Scope |
|-----------|-----------|-------|
| **Tabletop Exercise** | Quarterly | Process validation |
| **Failover Test** | Monthly | Technical validation |
| **Full DR Drill** | Quarterly | End-to-end validation |

---

## 7. REPORTING & MONITORING

### 7.1 Service Reports

| Report | Frequency | Contents |
|--------|-----------|----------|
| **Availability Report** | Daily | Uptime %, incidents, maintenance |
| **Performance Report** | Weekly | Response times, throughput, errors |
| **Security Report** | Monthly | Incidents, vulnerabilities, patches |
| **SLA Compliance** | Monthly | All metrics vs. targets |
| **Quarterly Business Review** | Quarterly | Strategic review, roadmap |

### 7.2 Real-Time Dashboard

SESB provides access to:
- System health status
- Transaction volume and success rates
- API performance metrics
- Security event feed
- Blockchain network status

---

## 8. ROLES & RESPONSIBILITIES

### 8.1 SESB Responsibilities

- Maintain system availability per SLA
- Provide 24/7 incident response
- Apply security patches within 72 hours
- Conduct regular security assessments
- Provide monthly service reports
- Maintain disaster recovery capability

### 8.2 JMYR Responsibilities

- Provide timely escalation contacts
- Grant necessary system access
- Review and approve maintenance windows
- Maintain network connectivity
- Ensure timely payment of fees
- Provide feedback on service quality

---

## 9. GOVERNANCE & REVIEW

### 9.1 Governance Structure

| Meeting | Frequency | Participants |
|---------|-----------|--------------|
| **Operations Review** | Weekly | Operations teams |
| **Service Review** | Monthly | IT Managers |
| **Strategic Review** | Quarterly | Executives |

### 9.2 SLA Amendment

- Either party may request amendment with 30 days notice
- Amendments require written agreement
- Emergency changes may be implemented with mutual consent

---

## 10. DEFINITIONS

| Term | Definition |
|------|------------|
| **Availability** | System operational and accessible for transactions |
| **Business Hours** | 9:00 AM - 6:00 PM MYT, Monday-Friday |
| **Downtime** | Period when critical functions are unavailable |
| **Response Time** | Time from incident report to initial response |
| **Resolution Time** | Time from incident report to permanent fix |
| **RPO** | Recovery Point Objective - acceptable data loss |
| **RTO** | Recovery Time Objective - acceptable downtime |
| **TPS** | Transactions Per Second |

---

## SIGNATURES

**For SESB:**

___________________________  
**Encik Ahmad Bin Hassan**  
Managing Director  
Sinergi Elit Sdn Bhd  

Date: _______________

**For JMYR:**

___________________________  
**[Name]**  
**[Title]**  
JMYR Sdn. Bhd.  

Date: _______________

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Tender Reference | JMYR/RFP/2026/001 |

---

*This document is part of the tender submission for JMYR Sdn. Bhd.*
