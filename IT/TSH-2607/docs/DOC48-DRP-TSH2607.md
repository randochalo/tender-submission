# DOC48-DRP-TSH2607.md
# Disaster Recovery Plan
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC48-DRP-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Classification | Confidential |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Disaster Recovery Plan (DRP) provides detailed procedures for recovering UCMS infrastructure, applications, and data following a catastrophic event.

### 1.2 Recovery Objectives

| Metric | Objective | Measurement |
|--------|-----------|-------------|
| Recovery Time Objective (RTO) | 4 hours | Time to restore service |
| Recovery Point Objective (RPO) | 1 hour | Maximum data loss |
| Recovery Level Objective (RLO) | Full system | Scope of recovery |

### 1.3 Disaster Scenarios Covered

- Data center destruction
- Major natural disasters (flood, earthquake)
- Extended power outages
- Critical infrastructure failures
- Catastrophic cyber attacks
- Terrorism or sabotage

---

## 2.0 DISASTER RECOVERY INFRASTRUCTURE

### 2.1 DR Site Architecture

| Component | Primary Site | DR Site | Replication |
|-----------|--------------|---------|-------------|
| Application Servers | 4 nodes | 2 nodes | Configuration sync |
| Database Server | Primary | Standby | Streaming replication |
| Storage | 10 TB | 10 TB | Async replication |
| Network | 1 Gbps | 1 Gbps | Independent |
| Internet | Dual ISP | Dual ISP | Separate links |

### 2.2 DR Site Location

| Attribute | Details |
|-----------|---------|
| Site Address | [DR Site Address] |
| Distance from Primary | > 50 km |
| Geographic Region | Separate seismic zone |
| Access Method | VPN + Physical |
| 24/7 Availability | Yes |

---

## 3.0 DISASTER DECLARATION

### 3.1 Declaration Authority

| Role | Authority | Contact |
|------|-----------|---------|
| MCMC CIO | Can declare disaster | |
| Project Sponsor | Can declare disaster | |
| BCP Coordinator | Can recommend declaration | |

### 3.2 Declaration Criteria

Declare disaster when:
- Primary site is physically inaccessible
- Infrastructure damage exceeds 50%
- Estimated downtime > 8 hours
- Data corruption affecting > 25% of data
- Cyber attack with no recovery path at primary

### 3.3 Declaration Process

1. Incident reported to on-call engineer
2. Assessment team dispatched (if safe)
3. Damage assessment completed
4. Declaration authority notified
5. Formal disaster declaration made
6. DR team activated
7. Customers notified within 1 hour

---

## 4.0 RECOVERY PROCEDURES

### 4.1 Phase 1: Immediate Response (0-1 hour)

| Step | Action | Owner | Status |
|------|--------|-------|--------|
| 1 | Acknowledge disaster declaration | DR Lead | □ |
| 2 | Activate DR team | DR Lead | □ |
| 3 | Establish command center | DR Lead | □ |
| 4 | Notify stakeholders | Communications | □ |
| 5 | Assess DR site readiness | Infrastructure | □ |
| 6 | Begin recovery procedures | Technical Team | □ |

### 4.2 Phase 2: Infrastructure Recovery (1-2 hours)

```bash
#!/bin/bash
# Phase 2 Recovery Script

echo "=== UCMS DR RECOVERY - PHASE 2 ==="
echo "$(date): Starting infrastructure recovery"

# 1. Verify DR site infrastructure
echo "[1/5] Verifying DR site..."
ping -c 3 dr-gateway || exit 1

# 2. Activate DR database
echo "[2/5] Activating DR database..."
ssh postgres@dr-db "sudo -u postgres pg_ctl promote -D /var/lib/postgresql/15/main"

# 3. Verify database is writable
echo "[3/5] Verifying database..."
psql -h dr-db -U ucms_app -d ucms_prod -c "CREATE TABLE dr_test (id int); DROP TABLE dr_test;"

# 4. Start application servers
echo "[4/5] Starting application servers..."
ssh app@dr-app-01 "pm2 start /opt/ucms/app.js"
ssh app@dr-app-02 "pm2 start /opt/ucms/app.js"

# 5. Verify application health
echo "[5/5] Verifying application..."
curl -f http://dr-app-01:3000/health || exit 1
curl -f http://dr-app-02:3000/health || exit 1

echo "$(date): Phase 2 complete"
```

### 4.3 Phase 3: Service Restoration (2-4 hours)

| Step | Action | Target Time |
|------|--------|-------------|
| 1 | Update DNS to point to DR | +2:00 |
| 2 | Activate load balancer rules | +2:15 |
| 3 | Enable SSL certificates | +2:30 |
| 4 | Verify external connectivity | +2:45 |
| 5 | Activate monitoring | +3:00 |
| 6 | Conduct smoke tests | +3:30 |
| 7 | Open service to users | +4:00 |

### 4.4 Phase 4: Data Synchronization

If any data was processed manually during outage:

1. Collect all manual transaction records
2. Prepare data import scripts
3. Validate data integrity
4. Import to recovered system
5. Reconcile totals
6. Verify audit trail completeness

---

## 5.0 FAILBACK PROCEDURES

### 5.1 Failback Preparation

1. Verify primary site is fully restored
2. Ensure primary infrastructure is stable
3. Schedule maintenance window
4. Notify users of brief maintenance
5. Prepare synchronization scripts

### 5.2 Failback Execution

```bash
#!/bin/bash
# Failback Script

echo "=== UCMS FAILBACK PROCEDURE ==="

# 1. Stop DR site writes
echo "[1/7] Putting DR in maintenance mode..."
curl -X POST http://dr-lb/admin/maintenance-on

# 2. Export data from DR
echo "[2/7] Exporting data from DR..."
pg_dump -h dr-db -Fc ucms_prod > /tmp/ucms_dr_export.dump

# 3. Import to primary
echo "[3/7] Importing to primary..."
pg_restore -h primary-db -d ucms_prod /tmp/ucms_dr_export.dump

# 4. Re-establish replication
echo "[4/7] Re-establishing replication..."
# Configure primary as master, DR as replica

# 5. Verify data consistency
echo "[5/7] Verifying consistency..."
# Run checksum comparisons

# 6. Switch traffic to primary
echo "[6/7] Switching traffic..."
# Update DNS/load balancer

# 7. Verify operations
echo "[7/7] Verification..."
curl -f https://ucms.mcmc.gov.my/health

echo "Failback complete"
```

---

## 6.0 ROLES AND RESPONSIBILITIES

### 6.1 DR Team Structure

| Role | Responsibilities | Primary | Alternate |
|------|------------------|---------|-----------|
| DR Lead | Overall coordination | | |
| Infrastructure Lead | Hardware, network recovery | | |
| Database Admin | Database recovery | | |
| Application Lead | Application restoration | | |
| Security Lead | Security verification | | |
| Communications | Stakeholder updates | | |

### 6.2 External Support

| Vendor | Service | Contact | Escalation |
|--------|---------|---------|------------|
| Cloud Provider | Infrastructure | | |
| Database Vendor | PostgreSQL support | | |
| Network Provider | Connectivity | | |
| Security Vendor | Incident response | | |

---

## 7.0 TESTING AND VALIDATION

### 7.1 DR Test Types

| Test Type | Frequency | Duration | Scope |
|-----------|-----------|----------|-------|
| Documentation Review | Quarterly | 2 hours | Review procedures |
| Tabletop Walkthrough | Quarterly | 4 hours | Simulate scenario |
| Component Test | Semi-annually | 8 hours | Test individual systems |
| Full DR Simulation | Annually | 24 hours | Complete failover |

### 7.2 Test Success Criteria

- RTO met: < 4 hours
- RPO met: < 1 hour data loss
- All critical functions operational
- No data corruption
- Security controls effective
- Users can access system

### 7.3 Post-Test Activities

1. Document test results
2. Identify gaps and issues
3. Update DRP as needed
4. Retrain team if required
5. Schedule next test

---

## 8.0 APPENDICES

### Appendix A: Network Diagrams
[DR site network architecture]

### Appendix B: System Configurations
[DR server configurations]

### Appendix C: Recovery Scripts
[Automated recovery scripts]

### Appendix D: Vendor Contacts
[24/7 support contacts]

### Appendix E: DR Site Access
[Physical access procedures]

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| DR Lead | | | |
| Infrastructure Lead | | | |
| MCMC Representative | | | |

---

*Document Control: This DRP is tested annually and updated as required. All changes require approval from the DR Lead and MCMC Representative.*
