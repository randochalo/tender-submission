# DOC54-PM-SCHEDULE-TSH2607.md
# Preventive Maintenance Schedule
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC54-PM-SCHEDULE-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 MAINTENANCE PHILOSOPHY

Preventive maintenance is conducted to ensure optimal system performance, prevent unexpected failures, and extend equipment lifespan. All maintenance follows manufacturer recommendations and industry best practices.

## 2.0 MAINTENANCE SCHEDULE

### 2.1 Daily Maintenance

| Time | Activity | Duration | Responsible |
|------|----------|----------|-------------|
| 08:00 | System health check | 15 min | On-call Engineer |
| 08:00 | Review overnight alerts | 15 min | On-call Engineer |
| 08:00 | Backup verification | 10 min | DBA |
| 18:00 | Daily backup execution | 30 min | Automated |

### 2.2 Weekly Maintenance

| Day | Time | Activity | Duration | Responsible |
|-----|------|----------|----------|-------------|
| Sunday | 02:00 | OS patching (if required) | 2 hours | SysAdmin |
| Sunday | 04:00 | Database maintenance | 1 hour | DBA |
| Sunday | 05:00 | Log rotation and cleanup | 30 min | SysAdmin |
| Sunday | 06:00 | Security scan | 1 hour | Security |
| Friday | 17:00 | Weekly report generation | 30 min | Automated |

### 2.3 Monthly Maintenance

| Day | Activity | Duration | Responsible |
|-----|----------|----------|-------------|
| First Saturday | Hardware health check | 2 hours | Infrastructure |
| First Saturday | Firmware updates (if required) | 2 hours | Infrastructure |
| Second Saturday | Security patch deployment | 4 hours | Security |
| Third Saturday | Database optimization | 3 hours | DBA |
| Third Saturday | Application updates | 2 hours | App Team |
| Last Friday | Capacity review | 1 hour | Infrastructure |
| Last Friday | Disaster recovery drill | 2 hours | DR Team |

### 2.4 Quarterly Maintenance

| Quarter | Month | Activity | Duration |
|---------|-------|----------|----------|
| Q1 | March | Full system audit | 8 hours |
| Q2 | June | Penetration testing | 40 hours |
| Q3 | September | DR site failover test | 8 hours |
| Q4 | December | Year-end maintenance | 16 hours |

### 2.5 Annual Maintenance

| Month | Activity | Duration |
|-------|----------|----------|
| January | SSL certificate renewal | 2 hours |
| March | Comprehensive security audit | 1 week |
| June | Hardware lifecycle review | 1 week |
| September | Disaster recovery exercise | 2 days |
| December | Annual maintenance window | 3 days |

---

## 3.0 MAINTENANCE PROCEDURES

### 3.1 Daily Health Check Procedure

```bash
#!/bin/bash
# Daily health check script

echo "=== UCMS Daily Health Check ==="
echo "Date: $(date)"

# Check application status
echo "[1/6] Checking application..."
curl -f http://localhost:3000/health || echo "WARNING: Application unhealthy"

# Check database
echo "[2/6] Checking database..."
pg_isready -h localhost -p 5432 || echo "WARNING: Database unavailable"

# Check disk space
echo "[3/6] Checking disk space..."
df -h | grep -E "(Filesystem|/dev/)"

# Check memory
echo "[4/6] Checking memory..."
free -h

# Check load average
echo "[5/6] Checking load..."
uptime

# Check recent errors
echo "[6/6] Checking logs..."
tail -50 /var/log/ucms/error.log | grep ERROR

echo "=== Health Check Complete ==="
```

### 3.2 Database Maintenance Procedure

```sql
-- Monthly database maintenance
-- Run during maintenance window

-- 1. Update statistics
VACUUM ANALYZE;

-- 2. Check for bloated tables
SELECT schemaname, tablename, 
       pg_size_pretty(pg_total_relation_size(schemaname||'.'||tablename)) as size
FROM pg_tables 
WHERE schemaname = 'public'
ORDER BY pg_total_relation_size(schemaname||'.'||tablename) DESC;

-- 3. Reindex if needed
REINDEX INDEX CONCURRENTLY idx_claims_status;
REINDEX INDEX CONCURRENTLY idx_applicants_ic;

-- 4. Cleanup old sessions
DELETE FROM t_sessions WHERE expiry < NOW() - INTERVAL '7 days';

-- 5. Archive old audit logs
-- (Move to archive table)
```

### 3.3 Security Maintenance Checklist

| # | Check | Method | Frequency |
|---|-------|--------|-----------|
| 1 | SSL certificate expiry | Check date | Daily |
| 2 | Security patches | Vulnerability scan | Weekly |
| 3 | User access review | Audit logs | Monthly |
| 4 | Password policy compliance | User audit | Quarterly |
| 5 | Firewall rules review | Rule audit | Quarterly |
| 6 | Penetration testing | External test | Annually |

---

## 4.0 MAINTENANCE WINDOWS

### 4.1 Standard Maintenance Window

| Window | Time | Duration | Activities |
|--------|------|----------|------------|
| Weekly | Sunday 02:00-06:00 | 4 hours | Patching, optimization |
| Monthly | First Saturday 00:00-06:00 | 6 hours | Updates, health checks |
| Quarterly | Saturday 00:00-08:00 | 8 hours | Major updates |

### 4.2 Emergency Maintenance

Emergency maintenance may be required for:
- Critical security patches
- System instability
- Hardware failures
- Data corruption issues

**Emergency Process:**
1. Assess urgency and impact
2. Notify stakeholders (minimum 4 hours notice if possible)
3. Execute maintenance
4. Verify system stability
5. Communicate completion

---

## 5.0 MAINTENANCE RECORDS

| Maintenance ID | Date | Type | Activity | Performed By | Status | Notes |
|----------------|------|------|----------|--------------|--------|-------|
| PM-YYYY-001 | | Daily | Health check | | □ Complete | |
| PM-YYYY-002 | | Weekly | Patching | | □ Complete | |
| PM-YYYY-003 | | Monthly | Optimization | | □ Complete | |
| PM-YYYY-004 | | Quarterly | DR Test | | □ Complete | |

---

## 6.0 SIGN-OFFS

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Maintenance Lead | | | |
| Technical Manager | | | |
| MCMC Representative | | | |

---

*Document Control: Update when maintenance procedures change.*
