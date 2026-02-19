# ANNEX-T32-TESTING-STRATEGY-TSH2607.md

# ANNEX T32: TESTING STRATEGY
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T32  
**Version:** 1.0  
**Date:** February 2026  

---

## TESTING LEVELS

### 1. Unit Testing
- Scope: Individual components/functions
- Responsibility: Developers
- Coverage Target: >80%
- Tools: JUnit, Jest

### 2. Integration Testing
- Scope: API and service integration
- Responsibility: QA Team
- Focus: USPFS, Azure AD, Payment Gateway
- Tools: Postman, REST Assured

### 3. System Testing
- Scope: End-to-end workflows
- Responsibility: QA Team
- Types: Functional, Regression, Performance

### 4. UAT (User Acceptance Testing)
- Scope: Business scenarios
- Responsibility: MCMC Users
- Duration: 4 weeks

### 5. Security Testing
- VAPT (Vulnerability Assessment & Penetration Testing)
- Code Security Review
- Tools: SonarQube, Burp Suite, OWASP ZAP

### Test Environments

| Environment | Purpose | Data |
|-------------|---------|------|
| DEV | Development | Synthetic |
| SIT | System Integration | Anonymized |
| UAT | User Acceptance | MCMC test data |
| PRE-PROD | Production-like | Anonymized |
| PROD | Production | Live |

---

**END OF ANNEX T32**
