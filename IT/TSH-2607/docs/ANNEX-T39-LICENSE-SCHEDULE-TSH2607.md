# ANNEX T39: LICENSE SCHEDULE

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex provides a comprehensive license schedule for all software and tools required for the USP Claims Management System, including quantities, metrics, and pricing structure.

### 1.1 License Principles
- **Perpetual Licenses**: Core platform components
- **Subscription Licenses**: Cloud services and utilities
- **Concurrent User Model**: Application server licenses
- **Processor-Based**: Database and middleware licenses

---

## 2. LICENSE INVENTORY

### 2.1 Oracle Database Licenses

| Component | Edition | Metric | Qty | Unit | Notes |
|-----------|---------|--------|-----|------|-------|
| Oracle Database | Enterprise Edition | Processor | 4 | Per Processor | Production RAC |
| Oracle Database | Enterprise Edition | Processor | 2 | Per Processor | DR Site |
| Oracle Database | Enterprise Edition | Processor | 2 | Per Processor | Non-Production |
| Partitioning | Option | Processor | 4 | Per Processor | Production only |
| Advanced Security | Option | Processor | 4 | Per Processor | TDE, Data Redaction |
| Active Data Guard | Option | Processor | 4 | Per Processor | DR replication |
| Real Application Clusters | Option | Processor | 4 | Per Processor | Production RAC |
| Diagnostic Pack | Option | Processor | 8 | Per Processor | All environments |
| Tuning Pack | Option | Processor | 8 | Per Processor | All environments |

**Processor Calculation:**
- Production: 4 servers × 2 processors × 0.5 (Intel core factor) = 4 processors
- DR: 2 servers × 2 processors × 0.5 = 2 processors
- Non-Prod: 2 servers × 2 processors × 0.5 = 2 processors

### 2.2 Oracle Middleware Licenses

| Component | Edition | Metric | Qty | Notes |
|-----------|---------|--------|-----|-------|
| Oracle WebLogic Server | Enterprise Edition | Processor | 4 | Application server |
| Oracle Internet Directory | - | Processor | 2 | LDAP directory |
| Oracle Identity Management | Suite | User | 200 | Identity & access |
| Oracle Analytics Server | Enterprise | Processor | 2 | Reporting & analytics |
| Oracle APEX | - | Included with DB | - | Application development |

### 2.3 Oracle Development Tools

| Component | Metric | Qty | Environment |
|-----------|--------|-----|-------------|
| Oracle JDeveloper | Named User Plus | 10 | Development team |
| SQL Developer | Free | Unlimited | All environments |
| ORDS (Oracle REST Data Services) | Included | - | All environments |

### 2.4 Third-Party Licenses

| Vendor | Product | Purpose | Metric | Qty |
|--------|---------|---------|--------|-----|
| Microsoft | Windows Server | Application OS | Core | 32 |
| Microsoft | Office 365 | Documentation | User | 50 |
| VMware | vSphere | Virtualization | CPU | 16 |
| Veritas | NetBackup | Backup software | Front-end TB | 50 |
| CrowdStrike | Falcon | EDR Security | Endpoint | 100 |
| Splunk | Enterprise | SIEM/Log Management | GB/day | 50 |

---

## 3. USER LICENSE METRICS

### 3.1 Named User Plus (NUP) Breakdown

| User Category | Count | License Type |
|---------------|-------|--------------|
| Internal MCMC Users | 50 | Named User Plus |
| External Service Providers | 150 | Application Express |
| System Accounts | 20 | Named User Plus |
| Total NUP Required | 70 | (Minimum 25 per processor applies) |

### 3.2 Application User Tiers

| Tier | Users | Features | Concurrent Sessions |
|------|-------|----------|---------------------|
| Administrator | 10 | Full system access | 20 |
| Power User | 30 | Claims processing | 60 |
| Standard User | 100 | View and submit | 100 |
| Read-Only | 60 | Reports only | 30 |

---

## 4. CLOUD SERVICE SUBSCRIPTIONS

### 4.1 Oracle Cloud Infrastructure (OCI)

| Service | Shape | OCPU/Month | Storage | Purpose |
|---------|-------|------------|---------|---------|
| Compute VM | VM.Standard2.4 | 4 | 500 GB | App servers |
| Compute BM | BM.Standard2.52 | 2 | 2 TB | DB servers |
| Block Volume | - | - | 10 TB | Data storage |
| Object Storage | - | - | 50 TB | Documents/Archives |
| Load Balancer | 400 Mbps | - | - | Traffic distribution |
| DNS | - | - | - | DNS management |

### 4.2 SaaS Subscriptions

| Service | Provider | Tier | Users | Period |
|---------|----------|------|-------|--------|
| Email Service | AWS SES | Enterprise | Unlimited | Monthly |
| SMS Gateway | Twilio | Business | 10K msgs/mo | Monthly |
| Monitoring | Datadog | Pro | 100 hosts | Monthly |
| Collaboration | Slack | Business+ | 50 users | Annual |
| Documentation | Confluence | Standard | 50 users | Annual |

---

## 5. SECURITY & COMPLIANCE LICENSES

| Product | Vendor | Metric | Qty | Purpose |
|---------|--------|--------|-----|---------|
| Digital Certificates | DigiCert | Certificate | 10 | SSL/TLS |
| PKI Tokens | MSC Trustgate | Token | 200 | User authentication |
| Vulnerability Scanner | Qualys | Asset | 50 | Security scanning |
| Code Analysis | SonarQube | Lines of Code | 500K | Code quality |
| Secrets Management | HashiCorp Vault | Instance | 2 | Secret storage |

---

## 6. DEVELOPMENT & TESTING LICENSES

| Category | Product | License | Qty | Notes |
|----------|---------|---------|-----|-------|
| IDE | IntelliJ IDEA Ultimate | Commercial | 10 | Java development |
| IDE | Visual Studio Professional | Commercial | 5 | Integration dev |
| Testing | JMeter | Open Source | Unlimited | Performance testing |
| Testing | Selenium | Open Source | Unlimited | UI testing |
| API Testing | Postman Enterprise | Team | 10 | API development |
| Version Control | GitLab Enterprise | User | 50 | Source control |
| CI/CD | Jenkins | Open Source | Unlimited | Build automation |

---

## 7. LICENSE SUMMARY

### 7.1 By Category

| Category | License Count | Coverage |
|----------|---------------|----------|
| Database | 32 processor licenses | Production, DR, Non-Prod |
| Middleware | 10 processor + 200 user | App server, IAM, Analytics |
| Operating System | 32 cores | All servers |
| Security | 350 endpoints/tokens | EDR, Auth, Certificates |
| Development | 75 user licenses | Dev team tools |
| Cloud Services | 7 services | OCI + SaaS |

### 7.2 License Compliance Framework

```
┌─────────────────────────────────────────────────────────────────┐
│              LICENSE MANAGEMENT FRAMEWORK                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  LICENSE TRACKING                                               │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ • Automated discovery of deployed licenses              │   │
│  │ • Quarterly reconciliation against entitlements         │   │
│  │ • Usage trend analysis and forecasting                  │   │
│  │ • Alert threshold: 80% of entitlement                   │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  COMPLIANCE MONITORING                                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ • Annual license compliance audit                       │   │
│  │ • Oracle LMS (License Management Services) ready        │   │
│  │ • Documentation of all deployments                      │   │
│  │ • True-up calculations for growth                       │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  OPTIMIZATION                                                   │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ • Regular review of unused licenses                     │   │
│  │ • Consolidation opportunities identification            │   │
│  │ • License mobility for DR/backup scenarios              │   │
│  │ • Cloud burst licensing for peak loads                  │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 8. LICENSE TERMS & CONDITIONS

### 8.1 Standard Terms

| Aspect | Terms |
|--------|-------|
| License Metric | As specified per product |
| License Type | Perpetual with annual support |
| Support Period | 1 year initial, renewable |
| Support Hours | 24x7 for production |
| Updates | Included during support period |
| Usage Rights | Production + DR + Non-Production |
| Audit Rights | Vendor audit with 45 days notice |

### 8.2 Special Provisions

| Provision | Description |
|-----------|-------------|
| Disaster Recovery | DR licenses at 50% of production |
| Test/Development | Non-production at 50% of production |
| Education | Training environment included |
| Migration | License migration assistance included |

---

## 9. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T41-PROJECT-TIMELINE | License Procurement |
| CR-002 | ANNEX-T35-DEPLOYMENT-PLAN | Environment Sizing |
| CR-003 | ANNEX-T31-SECURITY-FRAMEWORK | Security Tool Requirements |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
