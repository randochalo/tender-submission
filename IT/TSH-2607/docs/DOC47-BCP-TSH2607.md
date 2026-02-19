# DOC47-BCP-TSH2607.md
# Business Continuity Plan
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC47-BCP-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Classification | Confidential |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Business Continuity Plan (BCP) establishes procedures to ensure the continuity of USP Claims Management System (UCMS) operations during and after disruptive incidents.

### 1.2 Scope
This plan covers:
- System availability disruptions
- Data center failures
- Cybersecurity incidents
- Natural disasters
- Pandemic situations
- Critical staff unavailability

### 1.3 Objectives

| Objective | Target |
|-----------|--------|
| Recovery Time Objective (RTO) | 4 hours |
| Recovery Point Objective (RPO) | 1 hour |
| Maximum Tolerable Downtime (MTD) | 8 hours |
| Minimum Service Level During Crisis | 50% capacity |

---

## 2.0 BUSINESS IMPACT ANALYSIS

### 2.1 Critical Business Functions

| Function | Criticality | Max Downtime | Impact if Unavailable |
|----------|-------------|--------------|----------------------|
| Claim Submission | Critical | 4 hours | Public cannot apply for USP |
| Claim Processing | Critical | 4 hours | Backlog, delayed payments |
| Payment Processing | Critical | 8 hours | Financial impact on beneficiaries |
| Reporting | High | 24 hours | Management decisions affected |
| User Management | Medium | 48 hours | New user onboarding delayed |
| Document Management | High | 8 hours | Cannot verify claims |

### 2.2 Peak Usage Periods

| Period | Expected Load | Criticality |
|--------|---------------|-------------|
| Month-end | 150% normal | High |
| Quarter-end | 200% normal | Critical |
| Financial year-end | 250% normal | Critical |
| Post-announcement | 300% normal | Critical |

---

## 3.0 CONTINUITY STRATEGIES

### 3.1 System Resilience

```
┌─────────────────────────────────────────────────────────────────┐
│                    CONTINUITY ARCHITECTURE                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  PRIMARY SITE                    DISASTER RECOVERY SITE         │
│  ┌─────────────────┐             ┌─────────────────┐           │
│  │  Production DB  │◄───────────►│  Replica DB     │           │
│  │  (Read-Write)   │  Sync Repl  │  (Read-Standby) │           │
│  └─────────────────┘             └─────────────────┘           │
│         │                                │                      │
│  ┌─────────────────┐             ┌─────────────────┐           │
│  │  Application    │             │  Application    │           │
│  │  Servers (x4)   │             │  Servers (x2)   │           │
│  └─────────────────┘             └─────────────────┘           │
│         │                                │                      │
│         └──────────────┬─────────────────┘                      │
│                        │                                        │
│                 ┌─────────────┐                                │
│                 │   Load      │                                │
│                 │  Balancer   │                                │
│                 │  (Global)   │                                │
│                 └─────────────┘                                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2 Recovery Strategies

| Scenario | Strategy | RTO |
|----------|----------|-----|
| Single server failure | Auto-failover to standby | < 5 min |
| Database failure | Promote replica to primary | < 30 min |
| Data center failure | Activate DR site | < 4 hours |
| Regional disaster | Activate cold DR site | < 24 hours |
| Cyber attack (ransomware) | Restore from offline backup | < 8 hours |
| Data corruption | Point-in-time recovery | < 4 hours |

---

## 4.0 EMERGENCY RESPONSE

### 4.1 Incident Classification

| Level | Description | Examples | Response Time |
|-------|-------------|----------|---------------|
| P1 - Critical | Complete system outage | All users cannot access | Immediate |
| P2 - High | Major functionality impaired | Payment processing down | 30 minutes |
| P3 - Medium | Partial functionality impaired | Some reports unavailable | 2 hours |
| P4 - Low | Minor issues | Cosmetic issues | 4 hours |

### 4.2 Emergency Contacts

| Role | Name | Primary Contact | Alternate Contact |
|------|------|-----------------|-------------------|
| BCP Coordinator | | | |
| Technical Lead | | | |
| MCMC Liaison | | | |
| Infrastructure Lead | | | |
| Database Admin | | | |
| Security Officer | | | |

### 4.3 Communication Plan

| Stakeholder | Communication Method | Frequency During Crisis |
|-------------|---------------------|------------------------|
| MCMC Management | Phone + Email | Every 30 min |
| System Users | Email + Portal Banner | Every hour |
| Service Providers | Email + SMS | Every 2 hours |
| Public | Website + Social Media | As needed |
| Media | Press Release | If required |

---

## 5.0 ACTIVATION PROCEDURES

### 5.1 Activation Triggers

Activate BCP when:
- Primary site is expected to be down > 2 hours
- Critical data loss is confirmed
- Cyber attack affects system integrity
- Natural disaster affects primary location
- Pandemic reduces staff below 50%

### 5.2 Activation Steps

1. **Declare Incident** (0-15 min)
   - Incident detected and reported
   - BCP Coordinator notified
   - Initial assessment conducted

2. **Assess Impact** (15-30 min)
   - Determine scope of impact
   - Classify incident severity
   - Decide on BCP activation

3. **Activate Teams** (30-60 min)
   - Alert response teams
   - Establish command center
   - Begin stakeholder communication

4. **Implement Recovery** (1-4 hours)
   - Execute recovery procedures
   - Failover to alternate systems
   - Verify service restoration

5. **Resume Operations** (4+ hours)
   - Return to normal operations
   - Monitor system stability
   - Document lessons learned

---

## 6.0 RECOVERY PROCEDURES

### 6.1 Database Failover Procedure

```bash
# Step 1: Verify primary is down
pg_isready -h primary-db -p 5432
# If no response, proceed

# Step 2: Promote replica to primary
ssh dr-db-server
sudo -u postgres pg_ctl promote -D /var/lib/postgresql/15/main

# Step 3: Update application configuration
# Edit connection strings to point to DR database

# Step 4: Restart application servers
pm2 restart all

# Step 5: Verify connectivity
psql -h dr-db -U ucms_app -d ucms_prod -c "SELECT 1;"

# Step 6: Update DNS/load balancer
# Point to DR application servers
```

### 6.2 Application Failover Procedure

```bash
# Step 1: Disable primary in load balancer
# Access load balancer admin console
# Remove primary servers from pool

# Step 2: Enable DR application servers
# Add DR servers to load balancer pool

# Step 3: Verify health checks
# Ensure all DR servers show healthy

# Step 4: Monitor traffic
# Watch for successful requests
```

### 6.3 Work-from-Home Activation

When physical office access is restricted:

1. Activate VPN infrastructure
2. Increase VPN capacity if needed
3. Distribute VPN credentials
4. Verify remote access to UCMS
5. Establish virtual command center
6. Implement secure communication channels

---

## 7.0 ALTERNATE PROCESSING PROCEDURES

### 7.1 Manual Claim Processing (Paper-Based)

If system is unavailable for > 24 hours:

1. **Claim Intake**
   - Accept paper claim forms
   - Assign temporary reference numbers
   - Store securely

2. **Verification**
   - Manual verification of documents
   - Phone verification where possible
   - Record decisions on paper

3. **Approval**
   - Physical approval signatures
   - Maintain approval log
   - Secure storage of records

4. **Data Entry (Post-Recovery)**
   - Back-enter all paper claims
   - Maintain audit trail
   - Reconcile totals

### 7.2 Communication Alternatives

| Normal Channel | Alternative During Disruption |
|----------------|------------------------------|
| UCMS Portal | Email + Phone hotline |
| Email notifications | SMS + Phone calls |
| Online reporting | Manual report compilation |
| Document upload | Physical document submission |

---

## 8.0 TESTING AND MAINTENANCE

### 8.1 Testing Schedule

| Test Type | Frequency | Last Conducted | Next Scheduled |
|-----------|-----------|----------------|----------------|
| Tabletop Exercise | Quarterly | | |
| Failover Test | Semi-annually | | |
| Full DR Test | Annually | | |
| Pandemic Drill | Annually | | |

### 8.2 Test Objectives

- Validate recovery procedures
- Verify contact information
- Test communication channels
- Identify gaps and improvements
- Train new team members

### 8.3 Plan Maintenance

| Activity | Frequency | Owner |
|----------|-----------|-------|
| Review and update contacts | Quarterly | BCP Coordinator |
| Update system documentation | Monthly | Technical Lead |
| Review RTO/RPO metrics | Quarterly | Infrastructure Lead |
| Plan review and approval | Annually | MCMC Management |

---

## 9.0 TRAINING REQUIREMENTS

### 9.1 BCP Awareness Training

| Audience | Content | Frequency |
|----------|---------|-----------|
| All Staff | General awareness | Annually |
| Response Team | Detailed procedures | Quarterly |
| IT Team | Technical recovery | Quarterly |
| Management | Decision-making | Annually |

---

## 10.0 APPENDICES

### Appendix A: Contact Directory
[Complete contact list with alternates]

### Appendix B: System Documentation
[Architecture diagrams, configurations]

### Appendix C: Recovery Runbooks
[Step-by-step recovery procedures]

### Appendix D: Vendor Contacts
[Third-party support contacts]

### Appendix E: Alternate Site Details
[DR site location, access procedures]

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| BCP Coordinator | | | |
| Technical Lead | | | |
| MCMC Representative | | | |

---

*Document Control: This BCP is reviewed quarterly and updated annually. All changes require approval from the BCP Coordinator and MCMC Representative.*
