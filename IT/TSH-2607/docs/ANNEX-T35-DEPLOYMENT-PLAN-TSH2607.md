# ANNEX T35: DEPLOYMENT PLAN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the deployment plan for the USP Claims Management System, detailing the approach, environment strategy, cutover procedures, and rollback plans for successful system implementation.

### 1.1 Deployment Principles
- **Minimal Disruption**: Zero-downtime deployment where possible
- **Phased Rollout**: Gradual feature activation
- **Rollback Ready**: Always maintain rollback capability
- **Validation Gates**: Quality gates at each phase

---

## 2. DEPLOYMENT STRATEGY

### 2.1 Deployment Model

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DEPLOYMENT STRATEGY - PHASED ROLLOUT                     │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  PHASE 1: INFRASTRUCTURE & CORE (Month 10)                                 │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Server provisioning    • Database setup    • Network config     │   │
│  │  • Security hardening     • Monitoring setup                       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  PHASE 2: PILOT DEPLOYMENT (Month 11 - Week 1-2)                          │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Limited users (10)     • Non-production data    • Core features │   │
│  │  • Intensive monitoring   • Feedback collection                    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  PHASE 3: SOFT LAUNCH (Month 11 - Week 3-4)                               │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Single department      • Live data              • Full support  │   │
│  │  • Parallel run option    • Performance tuning                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  PHASE 4: FULL PRODUCTION (Month 12)                                       │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • All users onboarded    • All features enabled   • Old system    │   │
│  │  • SP portal activated    • Go-live complete        decommissioned │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Deployment Environments

| Environment | Purpose | Configuration | Data |
|-------------|---------|---------------|------|
| Development | Active development | Single node | Synthetic |
| SIT | Integration testing | 2-node cluster | Masked prod |
| UAT | User acceptance | 2-node cluster | Production subset |
| Pre-Prod | Final validation | Production mirror | Production mirror |
| Production | Live system | 4-node RAC cluster | Live |
| DR | Disaster recovery | Warm standby | Async replica |

---

## 3. DEPLOYMENT ARCHITECTURE

### 3.1 High-Availability Deployment

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    PRODUCTION DEPLOYMENT ARCHITECTURE                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│                              [Load Balancer]                                │
│                              (Active-Active)                                │
│                                    │                                        │
│                    ┌───────────────┼───────────────┐                        │
│                    ▼               ▼               ▼                        │
│              ┌──────────┐   ┌──────────┐   ┌──────────┐                    │
│              │  App     │   │  App     │   │  App     │                    │
│              │ Server 1 │   │ Server 2 │   │ Server 3 │                    │
│              │ (Active) │   │ (Active) │   │ (Standby)│                    │
│              └────┬─────┘   └────┬─────┘   └──────────┘                    │
│                   │              │                                          │
│                   └──────────────┘                                          │
│                          │                                                  │
│                          ▼                                                  │
│              ┌─────────────────────────┐                                   │
│              │    Oracle RAC Cluster   │                                   │
│              │  ┌─────┐ ┌─────┐ ┌─────┐                                   │
│              │  │Node1│ │Node2│ │Node3│                                   │
│              │  └──┬──┘ └──┬──┘ └──┬──┘                                   │
│              │     └───────┼───────┘                                      │
│              │        Shared Storage                                       │
│              └─────────────────────────┘                                   │
│                          │                                                  │
│                          ▼                                                  │
│              ┌─────────────────────────┐                                   │
│              │    Backup & Archive     │                                   │
│              └─────────────────────────┘                                   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Zero-Downtime Deployment

| Component | Strategy | Downtime |
|-----------|----------|----------|
| Application | Rolling deployment | Zero |
| Database | Oracle Rolling Patch | < 5 min |
| Configuration | Blue-green switch | Zero |
| Static Content | CDN cache refresh | Zero |

---

## 4. DEPLOYMENT PHASES

### 4.1 Phase 1: Infrastructure Deployment (Month 10)

| Task | Duration | Dependencies | Owner |
|------|----------|--------------|-------|
| Server provisioning | 1 week | Purchase order | Infrastructure |
| OS installation & hardening | 1 week | Server ready | Infrastructure |
| Network configuration | 3 days | OS ready | Network |
| Database installation | 1 week | OS + Network | DBA |
| Security configuration | 1 week | All above | Security |
| Monitoring setup | 3 days | All above | Operations |

### 4.2 Phase 2: Application Deployment (Month 11)

| Step | Activity | Validation |
|------|----------|------------|
| 2.1 | Deploy base application | Smoke tests pass |
| 2.2 | Configure integrations | Connectivity verified |
| 2.3 | Load master data | Data validation complete |
| 2.4 | Security validation | VAPT clearance |
| 2.5 | Performance baseline | NFRs met |
| 2.6 | Pilot user access | Pilot acceptance |

### 4.3 Phase 3: Data Migration

```
┌─────────────────────────────────────────────────────────────────┐
│                    DATA MIGRATION STRATEGY                      │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  LEGACY SYSTEM                        UCMS                      │
│  ┌──────────────┐                     ┌──────────────┐         │
│  │  Historical  │                     │  New Claims  │         │
│  │  Claims      │                     │  (Go-live+)  │         │
│  │  (Read-only) │                     │  (Active)    │         │
│  └──────────────┘                     └──────────────┘         │
│         │                                    ▲                  │
│         │                                    │                  │
│         └──────────────┬─────────────────────┘                  │
│                        │                                        │
│                        ▼                                        │
│              ┌───────────────────┐                             │
│              │  ETL Pipeline     │                             │
│              │  • Extract        │                             │
│              │  • Transform      │                             │
│              │  • Validate       │                             │
│              │  • Load           │                             │
│              └───────────────────┘                             │
│                                                                 │
│  MIGRATION APPROACH:                                           │
│  • Historical claims: Read-only archive                        │
│  • Active claims: Full migration with validation               │
│  • Master data: Complete migration                             │
│  • Audit logs: Preserved with integrity                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 4.4 Phase 4: Cutover

| Activity | Start Time | Duration | Responsible |
|----------|------------|----------|-------------|
| Pre-cutover checklist | D-1 18:00 | 2 hours | PM |
| Final data sync | D-Day 00:00 | 4 hours | DBA |
| Application switchover | D-Day 04:00 | 30 min | Infrastructure |
| Smoke testing | D-Day 04:30 | 1 hour | QA |
| User acceptance | D-Day 06:00 | 2 hours | Business |
| Go-live declaration | D-Day 08:00 | - | Sponsor |

---

## 5. DEPLOYMENT CHECKLISTS

### 5.1 Pre-Deployment Checklist

| # | Item | Status | Sign-off |
|---|------|--------|----------|
| 1 | All code committed and tagged | ☐ | Dev Lead |
| 2 | All tests passed | ☐ | QA Lead |
| 3 | Security scan clear | ☐ | Security |
| 4 | Performance tests passed | ☐ | Perf Lead |
| 5 | UAT sign-off obtained | ☐ | Business |
| 6 | Rollback plan documented | ☐ | Tech Lead |
| 7 | Communication sent to users | ☐ | Change Mgr |
| 8 | Support team on standby | ☐ | Support Mgr |
| 9 | Backup verified | ☐ | DBA |
| 10 | Monitoring active | ☐ | Operations |

### 5.2 Deployment Execution Checklist

| Step | Task | Command/Action | Verify |
|------|------|----------------|--------|
| 1 | Stop application services | `systemctl stop ucms-app` | Services stopped |
| 2 | Database backup | RMAN backup script | Backup complete |
| 3 | Deploy application | Ansible playbook | Deployment log |
| 4 | Database migration | Flyway migrate | Schema version |
| 5 | Start services | `systemctl start ucms-app` | Health check |
| 6 | Verify deployment | Smoke tests | All pass |
| 7 | Enable user access | Update LB config | Users can login |
| 8 | Monitor metrics | Dashboard review | Normal ranges |

---

## 6. ROLLBACK PLAN

### 6.1 Rollback Triggers

| Condition | Severity | Action |
|-----------|----------|--------|
| Critical functionality broken | Critical | Immediate rollback |
| Data integrity issues | Critical | Immediate rollback |
| Security breach | Critical | Immediate rollback |
| Performance < 50% of baseline | High | Evaluate for 1 hour |
| > 20% features non-functional | High | Evaluate for 2 hours |
| User acceptance < 60% | Medium | Mitigation plan |

### 6.2 Rollback Procedures

```
┌─────────────────────────────────────────────────────────────────┐
│                    ROLLBACK PROCEDURE                           │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  AUTOMATIC ROLLBACK (Health Check Failure)                     │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  1. Health check fails 3 consecutive times              │   │
│  │  2. Automatic traffic diversion to previous version     │   │
│  │  3. Alert operations team                               │   │
│  │  4. Investigation begins                                │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  MANUAL ROLLBACK (Decision-based)                              │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  1. Incident commander decides rollback                 │   │
│  │  2. Communication to stakeholders                       │   │
│  │  3. Stop new transactions                               │   │
│  │  4. Complete in-flight transactions                     │   │
│  │  5. Database rollback (if needed)                       │   │
│  │  6. Application rollback                                │   │
│  │  7. Verify rollback success                             │   │
│  │  8. Resume operations                                   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ROLLBACK TIME TARGETS:                                        │
│  • Application only: 15 minutes                                │
│  • Application + Database: 1 hour                              │
│  • Full environment: 4 hours                                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 7. POST-DEPLOYMENT ACTIVITIES

### 7.1 Hypercare Support

| Period | Support Level | Staffing | Focus |
|--------|---------------|----------|-------|
| Week 1 | 24/7 | Full team | Stability |
| Week 2-4 | 16/5 | Core team | Issue resolution |
| Month 2 | Business hours | Standard | Optimization |
| Month 3+ | Normal operations | Standard | Enhancement |

### 7.2 Validation Activities

| Day | Activity | Success Criteria |
|-----|----------|------------------|
| D+1 | Transaction volume check | ≥ 80% of normal |
| D+3 | User feedback collection | < 10 critical issues |
| D+7 | Performance review | All NFRs met |
| D+14 | Stability assessment | < 5 incidents/day |
| D+30 | Success evaluation | ≥ 90% user satisfaction |

---

## 8. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T34-CHANGE-MGMT | Change Readiness |
| CR-002 | ANNEX-T37-BACKUP-RECOVERY | Backup Procedures |
| CR-003 | ANNEX-T40-SUPPORT-PLAN | Hypercare Support |
| CR-004 | ANNEX-T41-PROJECT-TIMELINE | Deployment Schedule |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
