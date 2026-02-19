# DOC40-VAPT-TSH2607.md
# Vulnerability Assessment & Penetration Testing (VAPT) Report Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC40-VAPT-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Classification | CONFIDENTIAL |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This template documents Vulnerability Assessment and Penetration Testing activities. All findings should be handled according to MCMC security policies and Malaysia's security guidelines.

---

## VAPT REPORT

### SECTION A: ENGAGEMENT DETAILS

| Field | Information |
|-------|-------------|
| VAPT Report ID | VAPT-UCMS-[YYYY]-[###] |
| Assessment Type | □ Vulnerability Assessment □ Penetration Test □ Both |
| Assessment Date | DD/MM/YYYY to DD/MM/YYYY |
| Report Date | DD/MM/YYYY |
| Target System | UCMS Production/Staging |
| Target URL/IP | |
| Scope Definition | |

#### Assessment Team

| Role | Name | Organization | Certification |
|------|------|--------------|---------------|
| Lead Penetration Tester | | | CEH/OSCP/GPEN |
| Security Analyst | | | |
| Quality Reviewer | | | |

#### Client Representatives

| Role | Name | Organization |
|------|------|--------------|
| Security Officer | | MCMC |
| Technical Lead | | |
| Project Manager | | |

### SECTION B: SCOPE AND METHODOLOGY

#### B.1 Assessment Scope

| Component | In Scope | Testing Type |
|-----------|----------|--------------|
| Web Application (UCMS Portal) | □ Yes □ No | Black Box / Grey Box / White Box |
| API Endpoints | □ Yes □ No | Authenticated / Unauthenticated |
| Mobile Application | □ Yes □ No | iOS / Android |
| Network Infrastructure | □ Yes □ No | Internal / External |
| Database Layer | □ Yes □ No | Direct / Application |
| Source Code Review | □ Yes □ No | Automated / Manual |
| Cloud Configuration | □ Yes □ No | AWS/Azure/GCP |

#### B.2 Testing Methodology

| Phase | Activities | Tools Used |
|-------|------------|------------|
| Reconnaissance | Information gathering, footprinting | Nmap, Shodan, Maltego |
| Scanning | Port scanning, service enumeration | Nessus, OpenVAS, Nikto |
| Enumeration | User accounts, shares, applications | Dirb, Gobuster, Enum4linux |
| Vulnerability Analysis | Vulnerability identification | Nessus, Burp Suite, OWASP ZAP |
| Exploitation | Attempted exploitation | Metasploit, SQLMap, custom scripts |
| Post-Exploitation | Privilege escalation, lateral movement | Various |
| Reporting | Documentation of findings | Custom templates |

#### B.3 Standards and Frameworks

| Standard/Framework | Reference |
|-------------------|-----------|
| OWASP Top 10 | 2021 Edition |
| OWASP Testing Guide | v4.2 |
| PTES | Penetration Testing Execution Standard |
| NIST SP 800-115 | Technical Guide to Information Security Testing |
| CIS Benchmarks | Applicable versions |
| CVSS | v3.1 for scoring |

---

### SECTION C: EXECUTIVE SUMMARY

#### C.1 Risk Summary

| Risk Level | Count | Description |
|------------|-------|-------------|
| Critical | | Immediate action required |
| High | | Address within 30 days |
| Medium | | Address within 90 days |
| Low | | Address as resources allow |
| Informational | | Best practice recommendations |
| **TOTAL** | | |

#### C.2 Risk Rating Matrix

```
                    IMPACT
              Low    Medium    High   Critical
           ┌────────┬────────┬────────┬────────┐
    High   │ Medium │ High   │Critical│Critical│
LIKELIHOOD ├────────┼────────┼────────┼────────┤
    Medium │ Low    │ Medium │ High   │Critical│
           ├────────┼────────┼────────┼────────┤
    Low    │ Low    │ Low    │ Medium │ High   │
           └────────┴────────┴────────┴────────┘
```

#### C.3 Key Findings Summary

| Finding ID | Title | Severity | Status |
|------------|-------|----------|--------|
| | | | |
| | | | |
| | | | |

#### C.4 Remediation Priority

| Priority | Finding IDs | Timeline |
|----------|-------------|----------|
| Immediate (P1) | | 24-48 hours |
| Urgent (P2) | | 1-2 weeks |
| High (P3) | | 30 days |
| Medium (P4) | | 90 days |
| Low (P5) | | Next release |

---

### SECTION D: DETAILED FINDINGS

#### Finding Template (Repeat for Each Finding)

---

##### FINDING X: [Vulnerability Title]

| Attribute | Details |
|-----------|---------|
| Finding ID | VAPT-XXX |
| Severity | □ Critical □ High □ Medium □ Low □ Informational |
| CVSS Score | X.X (Vector: _______) |
| Category | □ Injection □ Authentication □ Authorization □ Cryptographic □ Configuration □ Other |
| OWASP Category | |
| Affected Component | |
| Affected URL/Endpoint | |
| First Discovered | DD/MM/YYYY |
| Last Verified | DD/MM/YYYY |

**Description:**
[Detailed description of the vulnerability]

**Evidence:**
```
[Proof of concept code, screenshots, or command output]
```

**Impact:**
[Description of potential impact if exploited]

**Affected Systems:**
- [List of affected systems/URLs]

**Remediation:**
[Detailed steps to remediate the vulnerability]

**References:**
- [CVE IDs, advisories, or reference links]

**Verification:**
[How to verify the fix]

---

### SECTION E: VULNERABILITY DETAILS BY CATEGORY

#### E.1 Injection Flaws

| Finding ID | Title | Severity | CWE |
|------------|-------|----------|-----|
| | SQL Injection | | CWE-89 |
| | Command Injection | | CWE-78 |
| | LDAP Injection | | CWE-90 |
| | XPath Injection | | CWE-91 |
| | Code Injection | | CWE-94 |

#### E.2 Authentication Issues

| Finding ID | Title | Severity | CWE |
|------------|-------|----------|-----|
| | Weak Password Policy | | CWE-521 |
| | Brute Force Possible | | CWE-307 |
| | Session Fixation | | CWE-384 |
| | Insecure Session Management | | CWE-613 |
| | MFA Bypass | | CWE-287 |

#### E.3 Authorization Issues

| Finding ID | Title | Severity | CWE |
|------------|-------|----------|-----|
| | IDOR (Insecure Direct Object Ref) | | CWE-639 |
| | Privilege Escalation | | CWE-250 |
| | Missing Function Level Access | | CWE-285 |
| | Path Traversal | | CWE-22 |

#### E.4 Cryptographic Issues

| Finding ID | Title | Severity | CWE |
|------------|-------|----------|-----|
| | Weak SSL/TLS Configuration | | CWE-326 |
| | Insecure Cipher Suites | | CWE-327 |
| | Weak Hash Algorithm | | CWE-328 |
| | Hardcoded Credentials | | CWE-798 |
| | Insecure Randomness | | CWE-338 |

#### E.5 Configuration Issues

| Finding ID | Title | Severity | CWE |
|------------|-------|----------|-----|
| | Missing Security Headers | | CWE-693 |
| | Information Disclosure | | CWE-200 |
| | Default Credentials | | CWE-798 |
| | Unnecessary Services | | CWE-200 |
| | Verbose Error Messages | | CWE-209 |

---

### SECTION F: COMPLIANCE MAPPING

| Requirement | Standard | Status | Finding IDs |
|-------------|----------|--------|-------------|
| Input Validation | OWASP ASVS L2 | □ Pass □ Fail | |
| Authentication | OWASP ASVS L2 | □ Pass □ Fail | |
| Session Management | OWASP ASVS L2 | □ Pass □ Fail | |
| Access Control | OWASP ASVS L2 | □ Pass □ Fail | |
| Cryptography | OWASP ASVS L2 | □ Pass □ Fail | |
| Error Handling | OWASP ASVS L2 | □ Pass □ Fail | |
| Data Protection | OWASP ASVS L2 | □ Pass □ Fail | |
| Communication Security | OWASP ASVS L2 | □ Pass □ Fail | |
| System Configuration | OWASP ASVS L2 | □ Pass □ Fail | |
| Database Security | OWASP ASVS L2 | □ Pass □ Fail | |
| File Management | OWASP ASVS L2 | □ Pass □ Fail | |
| Memory Management | OWASP ASVS L2 | □ Pass □ Fail | |

---

### SECTION G: TECHNICAL FINDINGS

#### G.1 Network Scan Results

| Host | Port | Service | Version | Finding | Severity |
|------|------|---------|---------|---------|----------|
| | | | | | |

#### G.2 Web Application Findings

| URL | Parameter | Vulnerability | Severity | Evidence |
|-----|-----------|---------------|----------|----------|
| | | | | |

#### G.3 SSL/TLS Assessment

| Host:Port | Protocol | Cipher | Grade | Findings |
|-----------|----------|--------|-------|----------|
| | | | | |

---

### SECTION H: REMEDIATION ROADMAP

#### H.1 Immediate Actions (24-48 hours)

| # | Action | Owner | Status |
|---|--------|-------|--------|
| 1 | | | □ Open □ In Progress □ Complete |
| 2 | | | □ Open □ In Progress □ Complete |

#### H.2 Short-term Actions (1-4 weeks)

| # | Action | Owner | Target Date | Status |
|---|--------|-------|-------------|--------|
| 1 | | | | □ Open □ In Progress □ Complete |
| 2 | | | | □ Open □ In Progress □ Complete |

#### H.3 Long-term Actions (1-6 months)

| # | Action | Owner | Target Date | Status |
|---|--------|-------|-------------|--------|
| 1 | | | | □ Open □ In Progress □ Complete |
| 2 | | | | □ Open □ In Progress □ Complete |

---

### SECTION I: RETESTING

#### I.1 Retest Results

| Original Finding | Retest Date | Status | Evidence |
|------------------|-------------|--------|----------|
| | | □ Fixed □ Partial □ Unchanged □ Worse | |
| | | □ Fixed □ Partial □ Unchanged □ Worse | |

#### I.2 Retest Summary

| Metric | Value |
|--------|-------|
| Total Findings Retested | |
| Fully Remediated | |
| Partially Remediated | |
| Unchanged | |
| New Issues Introduced | |
| Overall Risk Reduction | % |

---

### SECTION J: APPENDICES

| Appendix | Description | Included |
|----------|-------------|----------|
| A | Detailed vulnerability scan output | □ Yes □ No |
| B | Penetration test logs | □ Yes □ No |
| C | Screenshots and evidence | □ Yes □ No |
| D | Tool configuration and outputs | □ Yes □ No |
| E | Scope verification documents | □ Yes □ No |
| F | Legal and authorization letters | □ Yes □ No |

---

### SECTION K: CERTIFICATION AND SIGN-OFF

#### Assessment Team

| Name | Role | Signature | Date |
|------|------|-----------|------|
| | Lead Penetration Tester | | |
| | Security Analyst | | |
| | Quality Reviewer | | |

#### Client Acknowledgment

| Name | Role | Signature | Date |
|------|------|-----------|------|
| | Security Officer | | |
| | Project Manager | | |

---

**Confidentiality Statement:**
This report contains sensitive security information. Distribution is restricted to authorized personnel only. This document is classified as CONFIDENTIAL.

**Disclaimer:**
The assessment was performed within defined scope and time constraints. New vulnerabilities may emerge after the assessment date. Regular security testing is recommended.

---

**Document Control:** Original - MCMC Security | Copy - Project Office | Copy - Vendor (sanitized)
