# DOC32-CONFIG-SETUP-TSH2607.md
# Configuration Setup Report Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC32-CONFIG-SETUP-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This Configuration Setup Report documents all system configurations, parameter settings, and customizations implemented during the UCMS deployment. Complete this report for each environment (Development, UAT, Staging, Production).

---

## CONFIGURATION SETUP REPORT

### SECTION A: GENERAL INFORMATION

| Field | Details |
|-------|---------|
| Report Reference | CSR-UCMS-[ENV]-[YYYY]-[###] |
| Environment | □ Production □ Staging □ UAT □ Development |
| Configuration Date | DD/MM/YYYY |
| Configuration Engineer | |
| Reviewed By | |
| Approved By | |
| Related Site | |
| System Version | |

### SECTION B: SERVER CONFIGURATION

#### B.1 Operating System Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| OS Version | | □ Verified |
| Hostname | | □ Verified |
| Timezone | Asia/Kuala_Lumpur | □ Verified |
| NTP Servers | | □ Verified |
| System Language | en_US.UTF-8 | □ Verified |
| Keyboard Layout | US | □ Verified |
| Swap Space | _______ GB | □ Verified |
| SELinux/AppArmor | □ Enforcing □ Permissive □ Disabled | □ Verified |
| Firewall Status | □ Enabled □ Disabled | □ Verified |

#### B.2 Network Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| IP Address | | □ Verified |
| Subnet Mask | | □ Verified |
| Default Gateway | | □ Verified |
| Primary DNS | | □ Verified |
| Secondary DNS | | □ Verified |
| Hostname (FQDN) | | □ Verified |
| Network Interface | | □ Verified |
| MAC Address | | □ Verified |
| VLAN | | □ Verified |

#### B.3 Disk and Storage Configuration

| Mount Point | Size | Filesystem | Options | Verification |
|-------------|------|------------|---------|--------------|
| / | _______ GB | | | □ Verified |
| /boot | _______ GB | | | □ Verified |
| /var | _______ GB | | | □ Verified |
| /var/log | _______ GB | | | □ Verified |
| /tmp | _______ GB | | | □ Verified |
| /opt/ucms | _______ GB | | | □ Verified |
| /data | _______ GB | | | □ Verified |
| /backup | _______ GB | | | □ Verified |

#### B.4 Security Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| SSH Port | 22 / Custom: ___ | □ Verified |
| Root Login | □ Enabled □ Disabled | □ Verified |
| Password Auth | □ Enabled □ Disabled | □ Verified |
| Key-Based Auth | □ Enabled □ Disabled | □ Verified |
| Fail2Ban | □ Enabled □ Disabled | □ Verified |
| Automatic Updates | □ Enabled □ Disabled | □ Verified |
| AIDE/Tripwire | □ Enabled □ Disabled | □ Verified |

### SECTION C: DATABASE CONFIGURATION

#### C.1 PostgreSQL Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Version | | □ Verified |
| Port | 5432 | □ Verified |
| Data Directory | | □ Verified |
| Max Connections | _______ | □ Verified |
| Shared Buffers | _______ MB | □ Verified |
| Work Mem | _______ MB | □ Verified |
| Maintenance Work Mem | _______ MB | □ Verified |
| WAL Level | replica / logical | □ Verified |
| Archive Mode | □ On □ Off | □ Verified |
| Logging Collector | □ On □ Off | □ Verified |

#### C.2 Database Parameters

| Parameter | Value | Verification |
|-----------|-------|--------------|
| Database Name | ucms_db | □ Verified |
| Application User | ucms_app | □ Verified |
| Read User | ucms_read | □ Verified |
| Admin User | ucms_admin | □ Verified |
| Default Encoding | UTF8 | □ Verified |
| Default Locale | en_US.UTF-8 | □ Verified |
| Timezone | Asia/Kuala_Lumpur | □ Verified |

#### C.3 Connection Pooling (PgBouncer)

| Parameter | Value | Verification |
|-----------|-------|--------------|
| Listen Port | 6432 | □ Verified |
| Pool Mode | transaction / session | □ Verified |
| Max Client Conn | _______ | □ Verified |
| Default Pool Size | _______ | □ Verified |
| Reserve Pool Size | _______ | □ Verified |

#### C.4 Backup Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Backup Tool | pg_dump / pgBackRest / Barman | □ Verified |
| Backup Schedule | Daily at _____ | □ Verified |
| Retention Policy | _______ days | □ Verified |
| Archive Destination | | □ Verified |
| Compression | □ Yes □ No | □ Verified |
| Encryption | □ Yes □ No | □ Verified |

### SECTION D: APPLICATION CONFIGURATION

#### D.1 Web Server Configuration (Nginx/Apache)

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Web Server | Nginx / Apache | □ Verified |
| Version | | □ Verified |
| Listen Port (HTTP) | 80 | □ Verified |
| Listen Port (HTTPS) | 443 | □ Verified |
| Server Tokens | □ On □ Off | □ Verified |
| Gzip Compression | □ On □ Off | □ Verified |
| Client Max Body Size | _______ MB | □ Verified |
| Worker Processes | _______ | □ Verified |
| Worker Connections | _______ | □ Verified |

#### D.2 Application Server Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Runtime | Node.js / .NET / Java | □ Verified |
| Version | | □ Verified |
| Application Port | _______ | □ Verified |
| Node Environment | production / staging / development | □ Verified |
| Log Level | info / debug / error | □ Verified |
| Max Memory | _______ MB | □ Verified |
| Cluster Workers | _______ | □ Verified |

#### D.3 Application Parameters

| Parameter | Value | Verification |
|-----------|-------|--------------|
| Application Name | UCMS | □ Verified |
| Application URL | https://______ | □ Verified |
| API Base URL | https://______/api/v1 | □ Verified |
| Session Timeout | _______ minutes | □ Verified |
| JWT Expiry | _______ minutes | □ Verified |
| File Upload Limit | _______ MB | □ Verified |
| Allowed File Types | | □ Verified |
| Default Language | en / ms | □ Verified |
| Date Format | DD/MM/YYYY | □ Verified |
| Currency | MYR | □ Verified |

### SECTION E: SECURITY CONFIGURATION

#### E.1 SSL/TLS Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Certificate Provider | | □ Verified |
| Certificate Type | DV / OV / EV / Wildcard | □ Verified |
| TLS Version | 1.2 / 1.3 | □ Verified |
| Cipher Suites | | □ Verified |
| HSTS Enabled | □ Yes □ No | □ Verified |
| Certificate Expiry | DD/MM/YYYY | □ Verified |
| Auto-Renewal | □ Yes □ No | □ Verified |

#### E.2 Authentication Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Auth Method | Local / LDAP / SAML / OAuth | □ Verified |
| MFA Required | □ Yes □ No | □ Verified |
| MFA Method | TOTP / SMS / Hardware | □ Verified |
| Password Policy | □ Standard □ Strict □ Custom | □ Verified |
| Min Password Length | _______ characters | □ Verified |
| Password Complexity | | □ Verified |
| Max Login Attempts | _______ | □ Verified |
| Lockout Duration | _______ minutes | □ Verified |
| Session Timeout | _______ minutes | □ Verified |

#### E.3 Access Control Configuration

| Role | Permissions | Verification |
|------|-------------|--------------|
| SYS_ADMIN | Full System Access | □ Verified |
| MCMC_ADMIN | Configuration, Reports | □ Verified |
| MCMC_OFFICER | Review, Approve Claims | □ Verified |
| MCMC_VIEWER | Read-Only Access | □ Verified |
| PROVIDER_ADMIN | Provider Configuration | □ Verified |
| PROVIDER_USER | Submit Claims | □ Verified |
| PUBLIC_USER | Self-Service Portal | □ Verified |

#### E.4 Audit Configuration

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Audit Logging | □ Enabled □ Disabled | □ Verified |
| Logged Events | Login, Logout, CRUD, Export | □ Verified |
| Log Retention | _______ days | □ Verified |
| Log Encryption | □ Yes □ No | □ Verified |
| SIEM Integration | □ Yes □ No | □ Verified |

### SECTION F: INTEGRATION CONFIGURATION

#### F.1 MyIDENTITY Integration

| Parameter | Value | Verification |
|-----------|-------|--------------|
| Integration Type | REST API | □ Verified |
| Endpoint URL | | □ Verified |
| Authentication | OAuth 2.0 | □ Verified |
| Client ID | [REDACTED] | □ Verified |
| Timeout | _______ seconds | □ Verified |
| Retry Attempts | _______ | □ Verified |
| Status | □ Active □ Inactive | □ Verified |

#### F.2 Email/SMS Gateway

| Parameter | Value | Verification |
|-----------|-------|--------------|
| SMTP Server | | □ Verified |
| SMTP Port | 587 / 465 | □ Verified |
| Encryption | STARTTLS / SSL | □ Verified |
| From Address | | □ Verified |
| SMS Gateway | | □ Verified |
| SMS API Key | [REDACTED] | □ Verified |
| Status | □ Active □ Inactive | □ Verified |

#### F.3 Payment Gateway

| Parameter | Value | Verification |
|-----------|-------|--------------|
| Provider | | □ Verified |
| Environment | Sandbox / Production | □ Verified |
| Merchant ID | [REDACTED] | □ Verified |
| API Endpoint | | □ Verified |
| Webhook URL | | □ Verified |
| Status | □ Active □ Inactive | □ Verified |

### SECTION G: MONITORING CONFIGURATION

#### G.1 System Monitoring

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Monitoring Tool | Prometheus / Grafana / Zabbix | □ Verified |
| Collection Interval | _______ seconds | □ Verified |
| Retention Period | _______ days | □ Verified |
| Alert Channels | Email / SMS / Slack / PagerDuty | □ Verified |
| Dashboard URL | | □ Verified |

#### G.2 Log Management

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Log Aggregation | ELK / Splunk / Fluentd | □ Verified |
| Log Levels Captured | INFO, WARN, ERROR, FATAL | □ Verified |
| Log Rotation | Daily / Size-based | □ Verified |
| Retention Period | _______ days | □ Verified |
| Centralized Storage | □ Yes □ No | □ Verified |

### SECTION H: BACKUP AND RECOVERY CONFIGURATION

| Parameter | Setting | Verification |
|-----------|---------|--------------|
| Backup Schedule | Daily at _____ | □ Verified |
| Full Backup | Weekly on _____ | □ Verified |
| Incremental Backup | Daily | □ Verified |
| Backup Destination | Local / NAS / Cloud | □ Verified |
| Retention (Local) | _______ days | □ Verified |
| Retention (Offsite) | _______ days | □ Verified |
| Encryption | AES-256 | □ Verified |
| Compression | □ Yes □ No | □ Verified |
| Last Backup Test | DD/MM/YYYY | □ Verified |
| RTO Target | _______ hours | □ Verified |
| RPO Target | _______ hours | □ Verified |

### SECTION I: CUSTOM CONFIGURATIONS

#### I.1 Custom Scripts

| Script Name | Purpose | Location | Verification |
|-------------|---------|----------|--------------|
| | | | □ Verified |
| | | | □ Verified |
| | | | □ Verified |

#### I.2 Cron Jobs / Scheduled Tasks

| Schedule | Command/Script | Purpose | Verification |
|----------|----------------|---------|--------------|
| | | | □ Verified |
| | | | □ Verified |
| | | | □ Verified |

#### I.3 Environment Variables

| Variable | Value | Purpose | Verification |
|----------|-------|---------|--------------|
| UCMS_ENV | | Environment identification | □ Verified |
| UCMS_DB_HOST | | Database host | □ Verified |
| UCMS_DB_PORT | | Database port | □ Verified |
| UCMS_REDIS_HOST | | Cache host | □ Verified |
| UCMS_LOG_LEVEL | | Logging level | □ Verified |
| | | | □ Verified |
| | | | □ Verified |

### SECTION J: CONFIGURATION VERIFICATION CHECKLIST

| # | Verification Item | Status | Remarks |
|---|-------------------|--------|---------|
| 1 | All services started successfully | □ Pass □ Fail | |
| 2 | No errors in system logs | □ Pass □ Fail | |
| 3 | Database connections working | □ Pass □ Fail | |
| 4 | Application accessible via HTTP | □ Pass □ Fail | |
| 5 | Application accessible via HTTPS | □ Pass □ Fail | |
| 6 | SSL certificate valid | □ Pass □ Fail | |
| 7 | Authentication working | □ Pass □ Fail | |
| 8 | Authorization rules enforced | □ Pass □ Fail | |
| 9 | External integrations responding | □ Pass □ Fail | |
| 10 | Email notifications working | □ Pass □ Fail | |
| 11 | File upload/download working | □ Pass □ Fail | |
| 12 | Backup job configured and tested | □ Pass □ Fail | |
| 13 | Monitoring agents reporting | □ Pass □ Fail | |
| 14 | Log aggregation working | □ Pass □ Fail | |
| 15 | Security scans completed | □ Pass □ Fail | |

### SECTION K: APPROVALS

#### Configured By

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Signature | |
| Date | |

#### Verified By

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Signature | |
| Date | |

#### Approved By

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Signature | |
| Date | |

### SECTION L: APPENDICES

| Appendix | Description | Included |
|----------|-------------|----------|
| A | Configuration Files (sanitized) | □ Yes □ No |
| B | Network Diagram | □ Yes □ No |
| C | Security Scan Results | □ Yes □ No |
| D | Performance Test Results | □ Yes □ No |
| E | Backup Test Results | □ Yes □ No |

### SECTION M: CONFIGURATION CHANGE LOG

| Version | Date | Changes | Changed By | Approved By |
|---------|------|---------|------------|-------------|
| 1.0 | | Initial configuration | | |
| | | | | |
| | | | | |
| | | | | |

---

**Confidentiality Notice:** This document contains system configuration details that are sensitive. Store securely and restrict access to authorized personnel.

**Document Control:** Original - Project Office | Copy - Technical Team | Copy - Security Team
