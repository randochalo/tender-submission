# ANNEX T31: SECURITY FRAMEWORK

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive security framework for the USP Claims Management System, ensuring protection of sensitive data, financial transactions, and system operations against cyber threats while maintaining compliance with Malaysian regulations.

### 1.1 Compliance Requirements
- **KRISA Section 10**: Information security requirements
- **PDPA 2010**: Personal data protection
- **ISO 27001**: Information security management
- **NIST Cybersecurity Framework**: Security controls
- **Bank Negara Guidelines**: Financial system security

---

## 2. SECURITY ARCHITECTURE

### 2.1 Defense in Depth

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DEFENSE IN DEPTH ARCHITECTURE                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Layer 7: Data Layer                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Encryption at Rest (AES-256)  • Database Activity Monitoring     │   │
│  │  • Data Masking  • Tokenization  • Backup Encryption                │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 6: Application Layer                                                 │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Input Validation  • Output Encoding  • Session Management        │   │
│  │  • Secure Coding  • WAF  • RASP                                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 5: API & Integration Layer                                           │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • API Gateway  • Rate Limiting  • Authentication  • mTLS           │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 4: Host Layer                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Hardening  • EDR  • Antivirus  • Patch Management                │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 3: Network Layer                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Firewall  • IDS/IPS  • Network Segmentation  • VPN               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 2: Endpoint Layer                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Device Management  • DLP  • Certificate Pinning                  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  Layer 1: Physical Layer                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Access Control  • Surveillance  • Environmental Controls         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Security Zones

| Zone | Description | Trust Level | Access |
|------|-------------|-------------|--------|
| Internet | Public access | Untrusted | Public |
| DMZ | Reverse proxy, WAF | Low | Restricted |
| Application | Web servers, APIs | Medium | Authenticated |
| Data | Database, file storage | High | Service accounts |
| Management | Monitoring, backup | Critical | Admin only |

---

## 3. ACCESS CONTROL

### 3.1 Identity and Access Management

| Component | Technology | Purpose |
|-----------|------------|---------|
| Identity Provider | Oracle IDCS | Centralized identity |
| Directory | Active Directory | User synchronization |
| MFA | Oracle Authenticator + PKI | Strong authentication |
| PAM | CyberArk | Privileged access |
| SSO | SAML 2.0 / OIDC | Seamless access |

### 3.2 Role-Based Access Control (RBAC)

| Role | System Access | Data Access | Approval Limit |
|------|--------------|-------------|----------------|
| System Admin | Full | All | None (operations) |
| Security Admin | Security functions | Security logs | None |
| CEO | Dashboard, Reports | All | Unlimited |
| Director | All modules | Department | RM 5M |
| Manager | Operational | Team data | RM 1M |
| Officer | Claim processing | Assigned | RM 100K |
| Auditor | Read-only audit | Audit data | View only |
| SP User | Self-service portal | Own data | Submit only |

### 3.3 Authentication Matrix

| User Type | Primary Auth | Secondary Auth | Session |
|-----------|--------------|----------------|---------|
| Internal Staff | AD + Password | OTP/Hardware token | 8 hours |
| Privileged Users | AD + Password | Hardware token + OTP | 4 hours |
| Service Providers | PKI Certificate | OTP | 30 minutes |
| API Clients | Client Certificate | API Key | Token-based |

---

## 4. DATA SECURITY

### 4.1 Data Classification

| Classification | Examples | Handling |
|----------------|----------|----------|
| Critical | Banking details, approval chains | Encryption + Access log |
| Confidential | Claim amounts, SP financials | Encryption + Need-to-know |
| Internal | Process docs, policies | Access controlled |
| Public | Published reports | Open access |

### 4.2 Encryption Standards

| State | Algorithm | Key Management |
|-------|-----------|----------------|
| Data at Rest | AES-256-GCM | Oracle TDE + HSM |
| Data in Transit | TLS 1.3 | Auto-rotating certs |
| Data in Use | Memory encryption | Secure enclaves |
| Backups | AES-256 | Separate key hierarchy |

### 4.3 Data Masking

| Environment | Masking Strategy | Data Subset |
|-------------|------------------|-------------|
| Production | None (live data) | 100% |
| UAT | Dynamic masking | 10% sample |
| Development | Static masking | Synthetic |
| Training | Fully anonymized | Synthetic |

---

## 5. APPLICATION SECURITY

### 5.1 Secure Development Lifecycle

| Phase | Security Activity | Deliverable |
|-------|-------------------|-------------|
| Requirements | Threat modeling | Threat model document |
| Design | Security architecture review | Approved architecture |
| Development | Secure coding standards | Code with SAST scans |
| Testing | DAST, penetration testing | Vulnerability report |
| Deployment | Security configuration review | Hardened environment |
| Operations | Continuous monitoring | Security metrics |

### 5.2 OWASP Top 10 Mitigations

| Risk | Mitigation | Verification |
|------|------------|--------------|
| Injection | Parameterized queries | SAST + DAST |
| Broken Auth | MFA + session management | Pen test |
| Sensitive Data Exposure | Encryption + TLS 1.3 | SSL scan |
| XXE | Disable external entities | SAST |
| Broken Access Control | RBAC + ABAC | Pen test |
| Security Misconfiguration | Hardening guides | CIS scan |
| XSS | Output encoding + CSP | DAST |
| Insecure Deserialization | Input validation | SAST |
| Vulnerable Components | SBOM + dependency scan | SCA |
| Insufficient Logging | Comprehensive audit | Log review |

---

## 6. NETWORK SECURITY

### 6.1 Network Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         NETWORK SECURITY ARCHITECTURE                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│    Internet                                                                 │
│       │                                                                     │
│       ▼                                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                         DMZ ZONE                                    │   │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐            │   │
│  │  │   WAF    │  │   CDN    │  │   Load   │  │  Reverse │            │   │
│  │  │          │  │          │  │ Balancer │  │  Proxy   │            │   │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘            │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│       │                                                                     │
│       ▼                                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      INTERNAL FIREWALL                              │   │
│  │              (Stateful inspection + Application aware)              │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│       │                                                                     │
│       ▼                                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      APPLICATION ZONE                               │   │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐            │   │
│  │  │  App     │  │  App     │  │   API    │  │   Job    │            │   │
│  │  │ Server 1 │  │ Server 2 │  │ Gateway  │  │ Scheduler│            │   │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘            │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│       │                                                                     │
│       ▼                                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                        DATABASE ZONE                                │   │
│  │  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐     │   │
│  │  │  Oracle Primary │  │  Oracle Standby │  │  Oracle DR      │     │   │
│  │  │  (RAC)          │  │  (Active)       │  │  (Remote)       │     │   │
│  │  └─────────────────┘  └─────────────────┘  └─────────────────┘     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Network Controls

| Control | Implementation | Purpose |
|---------|----------------|---------|
| Firewall | Palo Alto / Fortinet | Traffic filtering |
| IDS/IPS | Snort / Suricata | Threat detection |
| DLP | Symantec / Forcepoint | Data loss prevention |
| VPN | IPsec / SSL VPN | Secure remote access |
| NAC | Cisco ISE | Device authentication |

---

## 7. SECURITY MONITORING

### 7.1 Security Operations Center (SOC)

| Function | Tool | Coverage |
|----------|------|----------|
| SIEM | Oracle Cloud SIEM / Splunk | 24/7 |
| Threat Intel | MISP + Commercial feeds | Continuous |
| Vulnerability Management | Qualys / Nessus | Weekly |
| EDR | CrowdStrike / SentinelOne | Real-time |
| UEBA | Oracle CASB | Real-time |

### 7.2 Security Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| MTTD (Mean Time to Detect) | < 15 minutes | SIEM alerts |
| MTTR (Mean Time to Respond) | < 1 hour | Incident tracking |
| Vulnerability Patch Time | < 7 days (critical) | Scan results |
| Failed Login Attempts | < 0.1% of logins | Auth logs |
| Security Incidents | Zero critical | Incident register |

---

## 8. INCIDENT RESPONSE

### 8.1 Incident Classification

| Severity | Criteria | Response Time |
|----------|----------|---------------|
| Critical | Data breach, system compromise | 15 minutes |
| High | Ransomware, unauthorized access | 1 hour |
| Medium | Malware, policy violation | 4 hours |
| Low | Phishing attempts, scans | 24 hours |

### 8.2 Response Procedure

```
┌─────────────────────────────────────────────────────────────────┐
│              INCIDENT RESPONSE WORKFLOW                         │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. DETECTION                                                   │
│     ↓ Alert from SIEM / User report / External notification     │
│                                                                 │
│  2. TRIAGE                                                      │
│     ↓ Classify severity  →  Assign incident commander           │
│                                                                 │
│  3. CONTAINMENT                                                 │
│     ↓ Isolate affected systems  →  Preserve evidence            │
│                                                                 │
│  4. ERADICATION                                                 │
│     ↓ Remove threat  →  Patch vulnerabilities                   │
│                                                                 │
│  5. RECOVERY                                                    │
│     ↓ Restore services  →  Verify integrity                     │
│                                                                 │
│  6. POST-INCIDENT                                               │
│     ↓ Root cause analysis  →  Lessons learned  →  Update controls│
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 9. COMPLIANCE & AUDIT

### 9.1 Compliance Mapping

| Requirement | Control | Evidence |
|-------------|---------|----------|
| KRISA 10.1 | Access control logs | Audit reports |
| KRISA 10.2 | Encryption standards | Configuration |
| PDPA 4.1 | Data protection | Policy docs |
| ISO 27001 A.9 | Access management | Access reviews |
| BNM RMIT | Incident reporting | Incident logs |

### 9.2 Audit Schedule

| Audit Type | Frequency | Scope |
|------------|-----------|-------|
| Internal | Quarterly | All controls |
| External | Annual | ISO 27001 |
| Penetration | Bi-annual | Full system |
| Vulnerability | Weekly | Automated |
| Compliance | Annual | KRISA/PDPA |

---

## 10. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T33-VAPT-PLAN | Testing Details |
| CR-002 | ANNEX-T26-AUDIT-TRAIL | Audit Logging |
| CR-003 | ANNEX-T29-INTEGRATION-ARCH | API Security |
| CR-004 | ANNEX-T37-BACKUP-RECOVERY | Data Protection |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
