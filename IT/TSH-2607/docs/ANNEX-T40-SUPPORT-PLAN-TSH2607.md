# ANNEX T40: SUPPORT PLAN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive support plan for the USP Claims Management System, ensuring continuous operational excellence through multi-tiered support, clear SLAs, and proactive maintenance.

### 1.1 Support Standards
- **ITIL 4**: Service management best practices
- **ISO 20000**: IT service management standard
- **KRISA Section 20**: ICT service continuity requirements

---

## 2. SUPPORT STRUCTURE

### 2.1 Support Tiers

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    MULTI-TIER SUPPORT STRUCTURE                             │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  TIER 1: SERVICE DESK (First Line)                                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Initial contact and logging    • Basic troubleshooting           │   │
│  │  • User account management        • Password resets                 │   │
│  │  • FAQ and knowledge base         • Ticket categorization           │   │
│  │  Escalation: 15 minutes           Resolution Target: 4 hours        │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  TIER 2: TECHNICAL SUPPORT (Second Line)                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Application troubleshooting    • Functional issue resolution     │   │
│  │  • Report generation support      • Workflow configuration          │   │
│  │  • Data correction (approved)     • Integration issue triage        │   │
│  │  Escalation: 4 hours              Resolution Target: 8 hours        │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  TIER 3: SPECIALIST SUPPORT (Third Line)                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Complex technical issues       • Database performance tuning     │   │
│  │  • Code-level debugging           • Architecture changes            │   │
│  │  • Security incident response     • Root cause analysis             │   │
│  │  Escalation: 8 hours              Resolution Target: 24-72 hours    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  VENDOR SUPPORT (Oracle/Third-Party)                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Product defects                • Patch management                │   │
│  │  • License issues                 • Product roadmap consultation    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Support Team Structure

| Role | Count | Responsibility | Coverage |
|------|-------|----------------|----------|
| Service Desk Analyst | 3 | Tier 1 support | 24x7 |
| Technical Analyst | 2 | Tier 2 support | Business hours |
| Senior Developer | 2 | Tier 3 support | On-call |
| Database Administrator | 1 | Database support | On-call |
| Infrastructure Engineer | 1 | Infrastructure | On-call |
| Support Manager | 1 | Escalations, SLAs | Business hours |

---

## 3. SERVICE LEVEL AGREEMENTS (SLAs)

### 3.1 Incident Response SLAs

| Priority | Definition | Response Time | Resolution Target | Escalation |
|----------|------------|---------------|-------------------|------------|
| P1 - Critical | System down, no workaround | 15 min | 4 hours | 30 min |
| P2 - High | Major function impaired | 1 hour | 8 hours | 4 hours |
| P3 - Medium | Minor function impaired | 4 hours | 3 days | 1 day |
| P4 - Low | Cosmetic, workaround exists | 8 hours | 10 days | 3 days |

### 3.2 Service Request SLAs

| Request Type | Standard Delivery | Expedited | Approval |
|--------------|-------------------|-----------|----------|
| User account creation | 1 business day | 4 hours | Manager |
| Password reset | 15 minutes | 15 minutes | Automated |
| Report generation | 2 business days | 1 day | Requestor |
| Data export | 3 business days | 1 day | Data Owner |
| Access modification | 2 business days | 1 day | Security |
| Training request | 5 business days | 2 days | Manager |

### 3.3 System Availability SLAs

| Environment | Availability | Maintenance Window | Monitoring |
|-------------|--------------|-------------------|------------|
| Production | 99.9% (8.76h downtime/year) | Sunday 02:00-06:00 | 24x7 |
| DR | 99.5% (Warm standby) | As needed | 24x7 |
| Non-Production | 95% | Flexible | Business hours |

---

## 4. SUPPORT CHANNELS

### 4.1 Contact Methods

| Channel | Availability | Purpose | Target Response |
|---------|--------------|---------|-----------------|
| Phone Hotline | 24x7 | P1/P2 incidents | Immediate |
| Email | 24x7 | All requests | Per SLA |
| Self-Service Portal | 24x7 | Ticket creation, tracking | Automated |
| Live Chat | Business hours | Quick queries | 5 minutes |
| Mobile App | 24x7 | SP support | Per SLA |
| In-Person | Business hours | Complex issues | By appointment |

### 4.2 Service Desk Contact

```
┌─────────────────────────────────────────────────────────────────┐
│              SUPPORT CONTACT INFORMATION                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  PHONE HOTLINE                                                  │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  Internal: 8888 (from MCMC extensions)                  │   │
│  │  External: +603-XXXX-8888                               │   │
│  │  Service Providers: 1-800-UCMS-HELP                     │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  EMAIL                                                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  General: ucms-support@mcmc.gov.my                      │   │
│  │  Urgent: ucms-urgent@mcmc.gov.my                        │   │
│  │  Service Providers: sp-support@mcmc.gov.my              │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  SELF-SERVICE PORTAL                                            │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  URL: https://support.ucms.mcmc.gov.my                  │   │
│  │  Features: Knowledge Base, Ticket Tracking, Chat        │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ESCALATION PATH                                                │
│  Tier 1 → Tier 2 → Tier 3 → Vendor → Management                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 5. SUPPORT PROCESSES

### 5.1 Incident Management Process

```
┌─────────────────────────────────────────────────────────────────┐
│              INCIDENT MANAGEMENT PROCESS                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. DETECTION & LOGGING                                         │
│     • Automated monitoring alerts                               │
│     • User reports via any channel                              │
│     • System event triggers                                     │
│     → Create ticket, assign priority                            │
│                                                                 │
│  2. INITIAL DIAGNOSIS                                           │
│     • Tier 1 performs initial assessment                        │
│     • Classify and prioritize                                   │
│     • Attempt immediate resolution                              │
│     → Resolve OR Escalate                                       │
│                                                                 │
│  3. INVESTIGATION & RESOLUTION                                  │
│     • Escalated tiers perform deep analysis                     │
│     • Apply fixes, workarounds                                  │
│     • Coordinate with vendors if needed                         │
│     → Implement resolution                                      │
│                                                                 │
│  4. RECOVERY & VERIFICATION                                     │
│     • Restore normal service                                    │
│     • Verify resolution with user                               │
│     • Monitor for recurrence                                    │
│     → Close ticket                                              │
│                                                                 │
│  5. POST-INCIDENT REVIEW (P1/P2 only)                           │
│     • Root cause analysis                                       │
│     • Preventive measures                                       │
│     • Documentation update                                      │
│     → Update knowledge base                                     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 5.2 Problem Management

| Activity | Frequency | Purpose |
|----------|-----------|---------|
| Trend Analysis | Weekly | Identify patterns |
| Root Cause Analysis | Per major incident | Prevent recurrence |
| Known Error Database | Continuous | Quick reference |
| Proactive Problem ID | Monthly | Prevent before occur |

---

## 6. MAINTENANCE WINDOWS

### 6.1 Scheduled Maintenance

| Type | Frequency | Duration | Window |
|------|-----------|----------|--------|
| Patch Tuesday | Monthly | 4 hours | Sunday 02:00-06:00 |
| Security Updates | As needed | 2 hours | Sunday 02:00-04:00 |
| Major Releases | Quarterly | 8 hours | Scheduled in advance |
| Database Maintenance | Monthly | 4 hours | Sunday 02:00-06:00 |
| Infrastructure | Bi-annual | 8 hours | Scheduled in advance |

### 6.2 Emergency Maintenance

| Criteria | Approval | Notification | Downtime |
|----------|----------|--------------|----------|
| Critical security patch | CIO | 4 hours prior | < 1 hour |
| System failure recovery | Automatic | Immediate | As needed |
| Data corruption fix | Data Owner | 2 hours prior | < 2 hours |

---

## 7. KNOWLEDGE MANAGEMENT

### 7.1 Knowledge Base Structure

| Category | Content | Maintenance |
|----------|---------|-------------|
| FAQs | Common questions | Monthly review |
| How-To Guides | Step-by-step procedures | Per release |
| Troubleshooting | Problem resolution | Continuous |
| Known Issues | Workarounds for bugs | Per incident |
| Video Tutorials | Visual guides | Quarterly |

### 7.2 Knowledge Metrics

| Metric | Target | Purpose |
|--------|--------|---------|
| Article Usage | 100 views/month | Identify popular topics |
| Self-Service Rate | > 40% | Reduce ticket volume |
| First Contact Resolution | > 70% | Efficiency |
| Knowledge Article Accuracy | > 95% | Quality |

---

## 8. REPORTING & GOVERNANCE

### 8.1 Support Reports

| Report | Frequency | Recipients | Content |
|--------|-----------|------------|---------|
| Daily Operations | Daily | Support Team | Incident summary |
| Weekly Metrics | Weekly | Management | SLA performance |
| Monthly Review | Monthly | Stakeholders | Trends, analysis |
| Quarterly Business Review | Quarterly | Leadership | Strategic review |

### 8.2 Key Performance Indicators

| KPI | Target | Measurement |
|-----|--------|-------------|
| First Response Time | 95% within SLA | Ticket system |
| First Contact Resolution | > 70% | Ticket analysis |
| Customer Satisfaction | > 4.0/5 | Post-resolution survey |
| System Availability | 99.9% | Monitoring tools |
| Mean Time to Resolve (MTTR) | Per priority SLA | Ticket analysis |
| Escalation Rate | < 20% | Ticket tracking |

---

## 9. CONTINUOUS IMPROVEMENT

### 9.1 Improvement Process

| Activity | Frequency | Output |
|----------|-----------|--------|
| Ticket Analysis | Weekly | Improvement opportunities |
| User Feedback Review | Monthly | Usability enhancements |
| Process Review | Quarterly | SOP updates |
| Technology Review | Bi-annual | Tool evaluation |
| Training Needs Analysis | Quarterly | Training updates |

---

## 10. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T34-CHANGE-MGMT | Change Support |
| CR-002 | ANNEX-T38-TRAINING-PLAN | User Support |
| CR-003 | ANNEX-T35-DEPLOYMENT-PLAN | Hypercare Support |
| CR-004 | ANNEX-T37-BACKUP-RECOVERY | DR Support |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
