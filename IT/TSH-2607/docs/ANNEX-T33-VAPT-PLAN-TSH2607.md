# ANNEX T33: VAPT PLAN

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the Vulnerability Assessment and Penetration Testing (VAPT) plan for the USP Claims Management System, ensuring comprehensive security validation before production deployment and on an ongoing basis.

### 1.1 Compliance Requirements
- **KRISA Section 10**: Security assessment requirements
- **NIST SP 800-115**: Technical Guide to Information Security Testing
- **OWASP Testing Guide**: Web application security testing
- **PTES (Penetration Testing Execution Standard)**: Testing methodology

---

## 2. VAPT SCOPE

### 2.1 Assessment Scope

| Component | In-Scope | Approach | Frequency |
|-----------|----------|----------|-----------|
| Web Application | Yes | Black box + Grey box | Bi-annual |
| Mobile Application | Yes | Black box + Grey box | Bi-annual |
| APIs | Yes | Black box + Grey box | Bi-annual |
| Network Infrastructure | Yes | Grey box | Annual |
| Database Layer | Yes | Grey box | Annual |
| Cloud Infrastructure | Yes | Grey box | Annual |
| Source Code | Yes | White box | Quarterly |
| Third-party Libraries | Yes | SCA | Continuous |

### 2.2 Out-of-Scope
- Physical security (separate assessment)
- Social engineering (separate engagement)
- DoS/DDoS testing (controlled environment only)
- Production data manipulation

---

## 3. VAPT METHODOLOGY

### 3.1 Testing Phases

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    VAPT EXECUTION METHODOLOGY                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Phase 1: PRE-ENGAGEMENT                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Scope definition    • Rules of engagement   • Legal agreements    │   │
│  │ • Emergency contacts  • Testing windows       • Success criteria    │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  Phase 2: RECONNAISSANCE                                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Information gathering    • Footprinting    • Service enumeration  │   │
│  │ • Network mapping          • Technology identification              │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  Phase 3: VULNERABILITY ANALYSIS                                            │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Automated scanning    • Manual verification    • Vulnerability    │   │
│  │ • Configuration review  • Architecture review      validation       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  Phase 4: EXPLOITATION                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Vulnerability exploitation    • Privilege escalation              │   │
│  │ • Lateral movement attempts     • Data access testing               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  Phase 5: POST-EXPLOITATION                                                 │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Persistence testing    • Pivot testing    • Impact assessment     │   │
│  │ • Data exfiltration simulation    • Clean-up verification         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│                                    ▼                                        │
│  Phase 6: REPORTING                                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │ • Executive summary    • Technical findings    • Risk ratings       │   │
│  │ • Remediation guidance    • Retest validation                       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. VULNERABILITY ASSESSMENT

### 4.1 Automated Scanning Tools

| Category | Tool | Purpose |
|----------|------|---------|
| Web App Scanner | Burp Suite Pro, OWASP ZAP | Web vulnerability detection |
| Network Scanner | Nessus, OpenVAS | Network vulnerability assessment |
| Mobile Scanner | MobSF, Burp Mobile | Mobile app security |
| API Scanner | Postman + Burp, OWASP API Security | API vulnerability testing |
| Container Scanner | Trivy, Clair | Container image scanning |
| SAST | SonarQube, Checkmarx | Source code analysis |
| SCA | Snyk, OWASP Dependency Check | Dependency vulnerability |
| DAST | Burp Suite, OWASP ZAP | Runtime vulnerability scanning |

### 4.2 Manual Testing Areas

| Area | Technique | CWE Categories |
|------|-----------|----------------|
| Authentication | Session management testing | CWE-287, CWE-306 |
| Authorization | Role-based access testing | CWE-285, CWE-862 |
| Input Validation | Fuzzing, injection testing | CWE-20, CWE-89 |
| Business Logic | Workflow bypass attempts | CWE-840 |
| Cryptography | Weak algorithm detection | CWE-326, CWE-327 |
| Configuration | Security misconfiguration | CWE-16, CWE-2 |

---

## 5. PENETRATION TESTING

### 5.1 Web Application Penetration Testing

#### OWASP Top 10 Validation

| # | Vulnerability | Test Method | Tools |
|---|---------------|-------------|-------|
| 1 | Broken Access Control | Horizontal/vertical privilege escalation | Burp, Custom scripts |
| 2 | Cryptographic Failures | TLS analysis, key management review | SSL Labs, TestSSL |
| 3 | Injection | SQLi, NoSQLi, Command injection | SQLMap, Manual |
| 4 | Insecure Design | Business logic flaws | Manual analysis |
| 5 | Security Misconfiguration | Banner grabbing, stack tracing | Nmap, Nikto |
| 6 | Vulnerable Components | Version detection, CVE matching | Snyk, Retire.js |
| 7 | Auth Failures | Brute force, session fixation | Hydra, Burp |
| 8 | Data Integrity | Serialization attacks | ysoserial, Manual |
| 9 | Logging Failures | Audit bypass attempts | Manual verification |
| 10 | SSRF | Internal resource access | Burp Collaborator |

### 5.2 API Penetration Testing

| Test Category | Test Cases | OWASP API Top 10 |
|---------------|------------|------------------|
| Authentication | JWT manipulation, OAuth flaws | API1, API2 |
| Authorization | Object level access control | API1, API5 |
| Input Validation | Mass assignment, injection | API8, API9 |
| Rate Limiting | Resource exhaustion | API4 |
| Business Logic | Workflow bypass | API6 |

### 5.3 Network Penetration Testing

| Layer | Tests | Tools |
|-------|-------|-------|
| Network | Port scanning, service enumeration | Nmap, Masscan |
| Transport | TLS/SSL analysis | TestSSL, SSLyze |
| Application | Protocol-specific attacks | Hydra, Medusa |
| Wireless | WiFi security (if applicable) | Aircrack-ng |

---

## 6. TEST SCENARIOS

### 6.1 Critical Security Test Scenarios

| Scenario ID | Description | Expected Result | Risk |
|-------------|-------------|-----------------|------|
| VAPT-001 | Unauthorized claim approval | Access denied | Critical |
| VAPT-002 | SQL injection in claim search | Safe parameterization | Critical |
| VAPT-003 | XSS in document upload filename | Output encoding | High |
| VAPT-004 | Privilege escalation to admin | Role validation | Critical |
| VAPT-005 | Payment amount manipulation | Server-side validation | Critical |
| VAPT-006 | Session hijacking | Secure session management | High |
| VAPT-007 | IDOR - View other SP claims | Authorization check | Critical |
| VAPT-008 | File upload malware execution | File type validation | High |
| VAPT-009 | API key exposure | Secure storage | High |
| VAPT-010 | Sensitive data in logs | Data masking | Medium |

### 6.2 Financial Transaction Security

| Test | Objective | Approach |
|------|-----------|----------|
| Amount Tampering | Prevent payment modification | Request/response manipulation |
| Duplicate Submission | Prevent double payments | Replay attack testing |
| Race Condition | Prevent concurrent processing | Timing-based testing |
| Workflow Bypass | Enforce approval process | Direct API endpoint access |

---

## 7. RISK RATING MATRIX

### 7.1 CVSS v3.1 Scoring

| Severity | Score Range | Response Time | Remediation |
|----------|-------------|---------------|-------------|
| Critical | 9.0 - 10.0 | 24 hours | Immediate fix + hotfix |
| High | 7.0 - 8.9 | 72 hours | Next release |
| Medium | 4.0 - 6.9 | 2 weeks | Planned fix |
| Low | 0.1 - 3.9 | 1 month | Next maintenance |
| Informational | 0.0 | N/A | Best practice |

### 7.2 Risk Calculation

```
Risk Score = Likelihood × Impact × Asset Value

Likelihood Scale:
5 = Very High (Exploit code publicly available)
4 = High (Attack path known, no exploit yet)
3 = Medium (Requires significant effort)
2 = Low (Difficult to exploit)
1 = Very Low (Theoretical only)

Impact Scale:
5 = Critical (System compromise, data breach)
4 = High (Significant functionality loss)
3 = Medium (Limited functionality impact)
2 = Low (Minor issue)
1 = Very Low (Cosmetic)
```

---

## 8. VAPT SCHEDULE

### 8.1 Testing Calendar

| Phase | Type | Timing | Duration | Environment |
|-------|------|--------|----------|-------------|
| Pre-SIT | Vulnerability Assessment | Month 7 | 1 week | SIT |
| Pre-SIT | Penetration Testing | Month 7 | 2 weeks | SIT |
| Pre-UAT | Vulnerability Assessment | Month 9 | 1 week | UAT |
| Pre-UAT | Penetration Testing | Month 9 | 2 weeks | UAT |
| Pre-Prod | Full VAPT | Month 10 | 3 weeks | Pre-Prod |
| Post-Launch | Re-test | Month 12 | 1 week | Production (controlled) |
| Ongoing | Quarterly Scans | Quarterly | 3 days | Production |
| Annual | Full VAPT | Annually | 4 weeks | Production (maintenance window) |

### 8.2 Test Environment Requirements

| Requirement | Specification |
|-------------|---------------|
| Access | VPN + Internal network access |
| Credentials | Test accounts for all roles |
| Tools | Approved security tools only |
| Time Window | Business hours + Maintenance windows |
| Exclusions | Production payment gateways (mock only) |
| Monitoring | Security team notified of testing |

---

## 9. DELIVERABLES

### 9.1 VAPT Report Structure

```
1. EXECUTIVE SUMMARY
   1.1 Assessment Overview
   1.2 Risk Summary (Charts/Graphs)
   1.3 Key Findings
   1.4 Recommendations Summary

2. TECHNICAL FINDINGS
   2.1 Critical Findings
   2.2 High Findings
   2.3 Medium Findings
   2.4 Low Findings
   2.5 Informational Findings

3. METHODOLOGY
   3.1 Scope
   3.2 Tools Used
   3.3 Testing Approach
   3.4 Limitations

4. DETAILED FINDINGS
   For each finding:
   • Title
   • Severity (CVSS Score)
   • CWE Reference
   • Description
   • Evidence (Screenshots/Logs)
   • Impact
   • Remediation Steps
   • References

5. APPENDICES
   5.1 Test Credentials
   5.2 Tool Output Samples
   5.3 Retest Results
```

### 9.2 Remediation Tracking

| Finding ID | Severity | Assigned To | Due Date | Status |
|------------|----------|-------------|----------|--------|
| V-001 | Critical | Security Team | +24h | Open |
| V-002 | High | Dev Team A | +72h | In Progress |
| V-003 | Medium | Dev Team B | +2w | Open |

---

## 10. REMEDIATION & RETEST

### 10.1 Remediation Process

```
┌─────────────────────────────────────────────────────────────────┐
│              VULNERABILITY REMEDIATION WORKFLOW                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │  Report     │───▶│  Triage     │───▶│  Assign     │         │
│  │  Received   │    │  & Prioritize│    │  Owner      │         │
│  └─────────────┘    └─────────────┘    └──────┬──────┘         │
│                                               │                 │
│                    ┌──────────────────────────┘                 │
│                    ▼                                            │
│         ┌─────────────────┐     ┌─────────────┐                 │
│         │  Develop Fix    │────▶│  Test Fix   │                 │
│         │  (Dev + Security)│    │  (QA + Sec) │                 │
│         └─────────────────┘     └──────┬──────┘                 │
│                                        │                        │
│                    ┌───────────────────┘                        │
│                    ▼                                            │
│         ┌─────────────────┐     ┌─────────────┐                 │
│         │  Deploy to      │────▶│  Retest     │                 │
│         │  Environment    │     │  (VAPT Team)│                 │
│         └─────────────────┘     └──────┬──────┘                 │
│                                        │                        │
│                    ┌───────────────────┘                        │
│                    ▼                                            │
│         ┌─────────────────┐     ┌─────────────┐                 │
│         │  Pass?          │────▶│  Close      │                 │
│         │  → Close        │     │  Finding    │                 │
│         │  → Fail         │     │             │                 │
│         └─────────────────┘     └─────────────┘                 │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 10.2 Retest Criteria

| Severity | Retest Required | Evidence |
|----------|-----------------|----------|
| Critical | Yes | Screenshot + Verification |
| High | Yes | Screenshot + Verification |
| Medium | Yes (sample) | Screenshot |
| Low | No (spot check) | Developer confirmation |

---

## 11. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T31-SECURITY-FRAMEWORK | Security Controls |
| CR-002 | ANNEX-T32-TESTING-STRATEGY | Security Testing |
| CR-003 | ANNEX-T35-DEPLOYMENT-PLAN | Security Gates |
| CR-004 | ANNEX-T41-PROJECT-TIMELINE | VAPT Schedule |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
