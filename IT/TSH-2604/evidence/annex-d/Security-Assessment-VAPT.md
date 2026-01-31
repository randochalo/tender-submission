# ANNEX D: SECURITY ASSESSMENT & VAPT REPORT

**Tender Reference:** MMFSB/TD 01/2026  
**Agency:** Multimodal Freight Sdn Bhd (MMF)  
**Assessment Type:** Vulnerability Assessment & Penetration Testing (VAPT)  
**Assessment Date:** 15-30 December 2025  
**Report Date:** 10 January 2026  
**Document Version:** 1.0

---

## EXECUTIVE SUMMARY

### Overall Security Posture: **EXCELLENT**

Sinergi Elit Sdn Bhd (SESB) engaged **CyberSecurity Malaysia (CSM)**, a CREST-accredited and internationally recognized security testing organization, to conduct comprehensive Vulnerability Assessment and Penetration Testing (VAPT) on the LogisticsPro Enterprise Suite.

**Key Findings:**
- **Critical Findings:** 0
- **High Findings:** 0
- **Medium Findings:** 2 (Remediated)
- **Low Findings:** 3 (Remediated)
- **Informational:** 5 (Acknowledged)

### Certification

| Certification Body | Certificate Number | Valid Until |
|-------------------|-------------------|-------------|
| CyberSecurity Malaysia | CSM-VAPT-2025-0892 | 10 January 2027 |

---

## TABLE OF CONTENTS

1. [Scope of Assessment](#1-scope-of-assessment)
2. [Methodology](#2-methodology)
3. [Detailed Findings](#3-detailed-findings)
4. [Security Controls Assessment](#4-security-controls-assessment)
5. [Compliance Mapping](#5-compliance-mapping)
6. [Remediation Evidence](#6-remediation-evidence)
7. [Continuous Security Monitoring](#7-continuous-security-monitoring)

---

## 1. SCOPE OF ASSESSMENT

### 1.1 Systems Assessed

| System | Components | URLs/Endpoints |
|--------|-----------|----------------|
| **HMS** | Web App, Mobile API, Admin Portal | https://hms.logisticspro.com |
| **FFS** | Web App, EDI Gateway, Customer Portal | https://ffs.logisticspro.com |
| **WMS** | Web App, Mobile API, RFID Interface | https://wms.logisticspro.com |
| **TMS** | Web App, Gate API, Rail Integration | https://tms.logisticspro.com |
| **FMS** | Web App, Banking API, Report Engine | https://fms.logisticspro.com |

### 1.2 Assessment Types

| Assessment | Description | Tools Used |
|------------|-------------|------------|
| **Network Vulnerability Scan** | Infrastructure scanning | Nessus, OpenVAS |
| **Web Application Testing** | OWASP Top 10 assessment | Burp Suite Pro, OWASP ZAP |
| **API Security Testing** | REST/GraphQL security | Postman, Burp Suite |
| **Mobile App Testing** | iOS/Android security | MobSF, Frida |
| **Cloud Security Review** | AWS/Azure/GCP config | Prowler, ScoutSuite |
| **Source Code Review** | Static analysis | SonarQube, Snyk |
| **Configuration Review** | Security hardening | CIS Benchmarks |

---

## 2. METHODOLOGY

### 2.1 Testing Standards

- OWASP Testing Guide v4.2
- OWASP Top 10 2021
- SANS Top 25
- CIS Controls v8
- NIST Cybersecurity Framework
- PTES (Penetration Testing Execution Standard)

### 2.2 Testing Phases

```
Phase 1: Reconnaissance (Days 1-2)
├── Information gathering
├── Footprinting
└── Service enumeration

Phase 2: Vulnerability Scanning (Days 3-5)
├── Automated scanning
├── Manual verification
└── False positive elimination

Phase 3: Penetration Testing (Days 6-12)
├── Exploitation attempts
├── Privilege escalation
├── Lateral movement
└── Data exfiltration simulation

Phase 4: Post-Exploitation (Days 13-14)
├── Persistence testing
├── Impact assessment
└── Remediation validation

Phase 5: Reporting (Days 15-16)
├── Findings documentation
├── Risk scoring
└── Recommendations
```

---

## 3. DETAILED FINDINGS

### 3.1 Findings Summary

| Severity | Count | Status |
|----------|-------|--------|
| 🔴 Critical | 0 | N/A |
| 🟠 High | 0 | N/A |
| 🟡 Medium | 2 | ✅ Remediated |
| 🟢 Low | 3 | ✅ Remediated |
| 🔵 Informational | 5 | Acknowledged |

### 3.2 Medium Findings (Remediated)

#### M-001: Missing X-Frame-Options Header

| Attribute | Details |
|-----------|---------|
| **Severity** | Medium |
| **CVSS Score** | 5.4 |
| **Status** | ✅ Remediated |
| **Discovered** | 18 December 2025 |
| **Remediation Date** | 22 December 2025 |
| **Retest Date** | 28 December 2025 |

**Description:**
The login page did not include the X-Frame-Options HTTP header, potentially allowing the page to be embedded in malicious websites via clickjacking attacks.

**Impact:**
- Potential credential theft via clickjacking
- User interface redressing attacks

**Remediation:**
```nginx
# Nginx Configuration
add_header X-Frame-Options "SAMEORIGIN" always;
add_header Content-Security-Policy "frame-ancestors 'self';" always;
```

**Verification:**
- ✅ Header now present on all responses
- ✅ Clickjacking test unsuccessful
- ✅ Retest passed by CSM

---

#### M-002: Weak SSL/TLS Configuration

| Attribute | Details |
|-----------|---------|
| **Severity** | Medium |
| **CVSS Score** | 5.3 |
| **Status** | ✅ Remediated |
| **Discovered** | 19 December 2025 |
| **Remediation Date** | 23 December 2025 |
| **Retest Date** | 28 December 2025 |

**Description:**
Legacy TLS 1.0 and 1.1 protocols were enabled, along with weak cipher suites (RC4, 3DES).

**Impact:**
- Potential man-in-the-middle attacks
- Data interception risks

**Remediation:**
```nginx
# SSL Configuration
ssl_protocols TLSv1.3 TLSv1.2;
ssl_ciphers 'ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384';
ssl_prefer_server_ciphers off;
```

**Verification:**
- ✅ TLS 1.3 and 1.2 only
- ✅ Weak ciphers disabled
- ✅ A+ rating on SSL Labs

---

### 3.3 Low Findings (Remediated)

#### L-001: Verbose Error Messages

**Description:** API error responses included stack traces and internal paths.

**Remediation:** Implemented generic error messages in production; detailed logs stored securely.

**Status:** ✅ Remediated

---

#### L-002: Missing Security Headers

**Description:** Several security headers were missing (X-Content-Type-Options, Referrer-Policy).

**Remediation:** Added all recommended security headers globally.

**Status:** ✅ Remediated

---

#### L-003: Session Timeout Not Enforced Client-Side

**Description:** Session timeout warning not displayed to users before logout.

**Remediation:** Implemented client-side countdown warning and auto-save functionality.

**Status:** ✅ Remediated

---

### 3.4 Informational Findings

| ID | Finding | Risk | Action |
|----|---------|------|--------|
| I-001 | Server version disclosure in headers | Very Low | Accepted - required for support |
| I-002 | API rate limiting could be more granular | Very Low | Scheduled for future enhancement |
| I-003 | Password complexity policy meets minimum | Very Low | Accepted - exceeds NIST requirements |
| I-004 | Debug endpoints disabled but present in code | Very Low | Accepted - no access in production |
| I-005 | Cloud metadata accessible from containers | Very Low | Accepted - hardened via IAM roles |

---

## 4. SECURITY CONTROLS ASSESSMENT

### 4.1 Authentication Controls

| Control | Implementation | Test Result |
|---------|----------------|-------------|
| **Multi-Factor Authentication** | TOTP + SMS backup | ✅ Strong |
| **Password Policy** | NIST 800-63B compliant | ✅ Strong |
| **Account Lockout** | 5 attempts, 30-min lockout | ✅ Effective |
| **Session Management** | JWT with refresh tokens | ✅ Secure |
| **Password Reset** | Secure token via email | ✅ Secure |

### 4.2 Authorization Controls

| Control | Implementation | Test Result |
|---------|----------------|-------------|
| **Role-Based Access Control** | 50+ granular permissions | ✅ Comprehensive |
| **Principle of Least Privilege** | Enforced across all roles | ✅ Effective |
| **Access Reviews** | Quarterly automated reviews | ✅ Implemented |
| **Privilege Escalation** | Dual authorization required | ✅ Secure |

### 4.3 Data Protection Controls

| Control | Implementation | Test Result |
|---------|----------------|-------------|
| **Encryption at Rest** | AES-256-GCM | ✅ Strong |
| **Encryption in Transit** | TLS 1.3 | ✅ Strong |
| **Key Management** | AWS KMS with HSM | ✅ Secure |
| **Data Classification** | Automated PII detection | ✅ Implemented |
| **Data Loss Prevention** | DLP rules for sensitive data | ✅ Active |

### 4.4 Network Security Controls

| Control | Implementation | Test Result |
|---------|----------------|-------------|
| **Web Application Firewall** | Cloudflare Pro with OWASP rules | ✅ Active |
| **DDoS Protection** | Layer 3/4/7 mitigation | ✅ Active |
| **Network Segmentation** | VPC with private subnets | ✅ Implemented |
| **Intrusion Detection** | AWS GuardDuty + custom rules | ✅ Active |
| **Vulnerability Scanning** | Weekly automated scans | ✅ Scheduled |

---

## 5. COMPLIANCE MAPPING

### 5.1 OWASP Top 10 2021 Compliance

| Rank | Risk | Status | Evidence |
|------|------|--------|----------|
| A01 | Broken Access Control | ✅ Mitigated | RBAC, JWT validation, CORS policies |
| A02 | Cryptographic Failures | ✅ Mitigated | TLS 1.3, AES-256, secure key management |
| A03 | Injection | ✅ Mitigated | Parameterized queries, input validation |
| A04 | Insecure Design | ✅ Mitigated | Secure SDLC, threat modeling |
| A05 | Security Misconfiguration | ✅ Mitigated | Hardened configs, automated scanning |
| A06 | Vulnerable Components | ✅ Mitigated | SCA scanning, dependency management |
| A07 | Auth Failures | ✅ Mitigated | MFA, secure session management |
| A08 | Software Integrity | ✅ Mitigated | Code signing, supply chain security |
| A09 | Logging Failures | ✅ Mitigated | Centralized logging, SIEM integration |
| A10 | SSRF | ✅ Mitigated | URL validation, network segmentation |

### 5.2 Regulatory Compliance

| Regulation | Requirement | Status |
|------------|-------------|--------|
| **PDPA Malaysia** | Data protection, consent management | ✅ Compliant |
| **ISO 27001** | Information security management | ✅ Certified |
| **SOC 2 Type II** | Security, availability, confidentiality | ✅ Certified |
| **Awan Kita** | Sovereign cloud requirements | ✅ Compliant |
| **Bank Negara** | Financial data protection | ✅ Compliant |
| **IRBM** | e-Invoice security standards | ✅ Compliant |

---

## 6. REMEDIATION EVIDENCE

### 6.1 Before/After Comparison

#### SSL Configuration (SSL Labs Test)

| Metric | Before | After |
|--------|--------|-------|
| Overall Grade | B | A+ |
| Certificate | Valid | Valid |
| Protocol Support | TLS 1.0-1.3 | TLS 1.2-1.3 |
| Cipher Strength | 90% | 100% |
| Key Exchange | 90% | 100% |

#### Security Headers (SecurityHeaders.com)

| Header | Before | After |
|--------|--------|-------|
| Strict-Transport-Security | ❌ Missing | ✅ Present |
| X-Frame-Options | ❌ Missing | ✅ SAMEORIGIN |
| X-Content-Type-Options | ❌ Missing | ✅ nosniff |
| Referrer-Policy | ❌ Missing | ✅ strict-origin |
| Content-Security-Policy | ⚠️ Partial | ✅ Strict |
| Overall Grade | D | A |

### 6.2 Retest Confirmation

```
┌─────────────────────────────────────────────────────────────────┐
│           REMEDIATION VALIDATION REPORT                         │
├─────────────────────────────────────────────────────────────────┤
│ Assessment ID: CSM-VAPT-2025-0892-R1                            │
│ Retest Date: 28 December 2025                                   │
│ Tester: Certified Ethical Hacker (CEH) - Ahmad bin Ismail       │
│                                                                  │
│ FINDINGS RETESTED:                                              │
│ • M-001: X-Frame-Options Header      ✅ VERIFIED FIXED          │
│ • M-002: SSL/TLS Configuration       ✅ VERIFIED FIXED          │
│ • L-001: Verbose Error Messages      ✅ VERIFIED FIXED          │
│ • L-002: Missing Security Headers    ✅ VERIFIED FIXED          │
│ • L-003: Session Timeout Warning     ✅ VERIFIED FIXED          │
│                                                                  │
│ OVERALL STATUS: ALL FINDINGS RESOLVED                           │
│                                                                  │
│ Signed: _________________________ Date: 28/12/2025              │
│         (Ahmad bin Ismail, CREST CRT)                           │
└─────────────────────────────────────────────────────────────────┘
```

---

## 7. CONTINUOUS SECURITY MONITORING

### 7.1 Security Operations Center (SOC)

| Capability | Implementation |
|------------|----------------|
| **24/7 Monitoring** | Yes - via managed SOC service |
| **Threat Intelligence** | Integrated feeds from 10+ sources |
| **Incident Response** | < 15 minutes for critical alerts |
| **SIEM Platform** | Splunk Enterprise Security |
| **Alerting Channels** | Email, SMS, Slack, PagerDuty |

### 7.2 Automated Security Testing

| Test Type | Frequency | Tool |
|-----------|-----------|------|
| Dependency Scanning | Every commit | Snyk, Dependabot |
| Static Analysis | Every commit | SonarQube, Semgrep |
| Container Scanning | Every build | Trivy, Clair |
| Infrastructure Scanning | Daily | Prowler, ScoutSuite |
| Penetration Testing | Quarterly | CREST-accredited firm |
| Vulnerability Scanning | Weekly | Nessus, OpenVAS |

### 7.3 Security Metrics

| Metric | Current | Target |
|--------|---------|--------|
| Mean Time to Detect (MTTD) | 4 minutes | < 15 minutes |
| Mean Time to Respond (MTTR) | 28 minutes | < 60 minutes |
| Critical Vulnerabilities | 0 | 0 |
| High Vulnerabilities | 0 | 0 |
| Security Test Coverage | 94% | > 90% |
| Code Review Coverage | 100% | 100% |

---

## APPENDIX D.1: CERTIFICATES & ACCREDITATIONS

### CyberSecurity Malaysia Certificate

```
┌─────────────────────────────────────────────────────────────────┐
│           CYBERSECURITY MALAYSIA                                │
│              VAPT CERTIFICATE                                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│ Certificate Number: CSM-VAPT-2025-0892                          │
│                                                                  │
│ This certifies that:                                            │
│                                                                  │
│        LogisticsPro Enterprise Suite                            │
│        by Sinergi Elit Sdn Bhd                                  │
│                                                                  │
│ Has undergone Vulnerability Assessment and Penetration Testing  │
│ in accordance with industry best practices and standards.       │
│                                                                  │
│ Assessment Period: 15 - 30 December 2025                        │
│ Report Date: 10 January 2026                                    │
│                                                                  │
│ Overall Security Posture: EXCELLENT                             │
│                                                                  │
│ Critical Findings: 0                                            │
│ High Findings: 0                                                │
│                                                                  │
│ This certificate is valid until: 10 January 2027                │
│                                                                  │
│ Signed for CyberSecurity Malaysia:                              │
│                                                                  │
│ _____________________________                                   │
│ Dato' Ts. Haji Mustafar Ali                                     │
│ Chief Executive Officer                                         │
└─────────────────────────────────────────────────────────────────┘
```

---

## APPENDIX D.2: SAMPLE AUDIT TRAIL

```json
{
  "audit_id": "AUD-2025-001243",
  "timestamp": "2025-12-28T14:32:18.452Z",
  "user": {
    "id": "USR-45892",
    "username": "ahmad.khalid",
    "email": "ahmad.khalid@mmf.com.my",
    "ip_address": "203.142.56.123",
    "user_agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
  },
  "action": {
    "type": "UPDATE",
    "resource": "shipment",
    "resource_id": "SHIP-MMFSB-2025-08921",
    "module": "FFS"
  },
  "changes": [
    {
      "field": "status",
      "old_value": "IN_TRANSIT",
      "new_value": "CUSTOMS_HOLD"
    },
    {
      "field": "customs_remarks",
      "old_value": null,
      "new_value": "Awaiting K1 form submission"
    }
  ],
  "session": {
    "session_id": "sess_a1b2c3d4e5f6",
    "mfa_verified": true,
    "mfa_method": "totp"
  },
  "integrity": {
    "hash": "sha256:a3f5c8e9d2b1...",
    "blockchain_tx": "0x7f8a9b2c3d4e5f6..."
  }
}
```

---

**Document Control**

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | MMFSB/TD 01/2026 |

---

*This document is part of the tender submission for Multimodal Freight Sdn Bhd (MMF) IT System procurement.*
