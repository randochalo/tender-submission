# ANNEX T32: TESTING STRATEGY

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the comprehensive testing strategy for the USP Claims Management System, ensuring all components meet functional, non-functional, security, and business requirements before deployment.

### 1.1 Testing Standards
- **ISO/IEC 25010**: Software quality standards
- **IEEE 829**: Test documentation standards
- **ISTQB**: Testing methodology best practices

---

## 2. TESTING APPROACH

### 2.1 Testing Pyramid

```
┌─────────────────────────────────────────────────────────────────┐
│                    TESTING PYRAMID                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│                           ▲                                     │
│                          /│\                                    │
│                         / │ \         E2E Tests                 │
│                        /  │  \        (User Journeys)           │
│                       /   │   \        ~50 tests                │
│                      /────┼────\                                 │
│                     /     │     \                               │
│                    /      │      \      Integration Tests        │
│                   /       │       \     (API/Service)           │
│                  /        │        \    ~200 tests               │
│                 /─────────┼─────────\                          │
│                /          │          \                         │
│               /           │           \   Unit Tests            │
│              /            │            \  (Components)          │
│             /             │             \ ~1000 tests           │
│            ───────────────┴───────────────                      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 2.2 Testing Types

| Test Type | Purpose | Phase | Responsibility |
|-----------|---------|-------|----------------|
| Unit Testing | Component correctness | Development | Developer |
| Integration Testing | Interface validation | Development | QA |
| System Testing | End-to-end validation | SIT | QA |
| UAT | Business acceptance | UAT | Business |
| Performance Testing | Load/stress validation | SIT | Performance |
| Security Testing | Vulnerability identification | SIT | Security |
| Regression Testing | Change impact | All phases | QA |

---

## 3. TEST ENVIRONMENTS

### 3.1 Environment Strategy

| Environment | Purpose | Data | Refresh Frequency |
|-------------|---------|------|-------------------|
| DEV | Development | Synthetic | On demand |
| SIT | Integration testing | Masked production | Weekly |
| UAT | User acceptance | Production subset | Per release |
| Pre-Prod | Production simulation | Production mirror | Pre-deployment |
| DR | Disaster recovery | Async replica | Continuous |

### 3.2 Environment Configuration

| Component | DEV | SIT | UAT | Pre-Prod |
|-----------|-----|-----|-----|----------|
| Application Servers | 1 | 2 | 2 | 4 |
| Database | Single | RAC 2-node | RAC 2-node | RAC 4-node |
| Load Balancer | None | Yes | Yes | Yes |
| WAF | Basic | Full | Full | Full |
| Monitoring | Basic | Full | Full | Full |

---

## 4. FUNCTIONAL TESTING

### 4.1 Module Testing Coverage

| Module | Test Scenarios | Priority | Status Criteria |
|--------|---------------|----------|-----------------|
| Claim Submission | 150 | Critical | 100% pass |
| Workflow Engine | 120 | Critical | 100% pass |
| Payment Processing | 100 | Critical | 100% pass |
| Document Management | 80 | High | 100% pass |
| Reporting | 60 | High | 95% pass |
| Admin Functions | 50 | Medium | 95% pass |
| Self-Service Portal | 100 | High | 100% pass |
| Integration Points | 80 | Critical | 100% pass |

### 4.2 Test Case Template

```
TEST CASE ID: UCMS-CLM-001
MODULE: Claim Submission
PRIORITY: Critical

DESCRIPTION:
Verify that a Service Provider can successfully submit a CAPEX claim
with all required documents and receive confirmation.

PRECONDITIONS:
1. SP is registered and active in system
2. SP has valid digital certificate
3. SP has bank account on file
4. Claim template is available

TEST STEPS:
┌────┬──────────────────────────────┬──────────────────────────────────┐
│ Step│ Action                      │ Expected Result                  │
├────┼──────────────────────────────┼──────────────────────────────────┤
│ 1  │ Login to Self-Service Portal │ Dashboard displayed              │
│ 2  │ Click "New Claim"           │ Claim wizard opens               │
│ 3  │ Select "CAPEX"              │ CAPEX form displayed             │
│ 4  │ Fill project details        │ All fields accept valid input    │
│ 5  │ Enter claim amount: 250,000 │ Amount formatted correctly       │
│ 6  │ Upload supporting docs      │ All docs uploaded successfully   │
│ 7  │ Submit claim                │ Confirmation displayed           │
│ 8  │ Verify email received       │ Acknowledgment email arrives     │
│ 9  │ Check UCMS reference        │ Reference format: UCMS-YY-XXXXX  │
└────┴──────────────────────────────┴──────────────────────────────────┘

PASS CRITERIA: All steps execute without error
FAIL CRITERIA: Any step produces unexpected result
```

---

## 5. NON-FUNCTIONAL TESTING

### 5.1 Performance Testing

#### Performance Requirements

| Metric | Requirement | Test Approach |
|--------|-------------|---------------|
| Response Time (95th percentile) | < 2 seconds | Load testing |
| Throughput | 1000 concurrent users | Stress testing |
| Concurrent Sessions | 500 active | Capacity testing |
| Database Queries | < 100ms average | Profiling |
| Report Generation | < 30 seconds | Performance testing |

#### Load Testing Scenarios

| Scenario | Users | Ramp-up | Duration | Think Time |
|----------|-------|---------|----------|------------|
| Normal Load | 200 | 10 min | 2 hours | 30s |
| Peak Load | 500 | 15 min | 1 hour | 10s |
| Stress Test | 1000 | 20 min | 30 min | 5s |
| Endurance | 300 | 5 min | 8 hours | 30s |

### 5.2 Security Testing

| Test Type | Scope | Tool | Frequency |
|-----------|-------|------|-----------|
| SAST | Source code | SonarQube | Every build |
| DAST | Running application | OWASP ZAP | Weekly |
| Dependency Scan | Libraries | Snyk | Daily |
| Container Scan | Docker images | Trivy | Every build |
| Penetration Test | Full system | Manual + Tools | Bi-annual |

---

## 6. INTEGRATION TESTING

### 6.1 Integration Test Matrix

| Integration | Type | Test Focus | Approach |
|-------------|------|------------|----------|
| Oracle ERP | API | Financial data accuracy | Contract testing |
| Banking Network | API | Payment processing | Mock + Live |
| Digital Signature | API | Certificate validation | Live |
| SMS Gateway | API | Notification delivery | Mock |
| Email Service | SMTP | Message delivery | Mock |
| Document OCR | API | Extraction accuracy | Live |

### 6.2 API Testing Example

```json
{
  "test_case": "API-PAYMENT-001",
  "endpoint": "/api/v1/payments/process",
  "method": "POST",
  "request": {
    "claim_id": "UCMS-2025-001234",
    "amount": 250000.00,
    "currency": "MYR",
    "bank_account": "1234567890"
  },
  "expected_response": {
    "status": 200,
    "body": {
      "payment_id": "PAY-2025-56789",
      "status": "PROCESSING",
      "estimated_date": "2025-07-15"
    }
  },
  "assertions": [
    "response.status == 200",
    "response.body.payment_id exists",
    "response.body.status == 'PROCESSING'"
  ]
}
```

---

## 7. USER ACCEPTANCE TESTING (UAT)

### 7.1 UAT Approach

| Aspect | Approach |
|--------|----------|
| Participants | MCMC business users, selected SPs |
| Duration | 4 weeks |
| Environment | Production-like UAT |
| Data | Masked production subset |
| Support | On-site support team |

### 7.2 UAT Scenarios

| Scenario | Description | Business Owner |
|----------|-------------|----------------|
| UAT-001 | End-to-end claim submission | SP Relations |
| UAT-002 | Approval workflow | Operations |
| UAT-003 | Payment processing | Finance |
| UAT-004 | Reporting and analytics | Management |
| UAT-005 | Exception handling | Operations |
| UAT-006 | Self-service portal | SP Representatives |

### 7.3 UAT Sign-off Criteria

| Criterion | Target | Measurement |
|-----------|--------|-------------|
| Test Case Pass Rate | 100% critical, 95% overall | Test results |
| Defect Severity | Zero critical, <5 major | Defect log |
| Business Process Validation | All approved | Sign-off sheet |
| Performance Validation | Meets NFRs | Performance report |
| Security Validation | Passed | Security scan |

---

## 8. REGRESSION TESTING

### 8.1 Regression Strategy

| Trigger | Regression Scope | Duration |
|---------|------------------|----------|
| Bug fix | Related module | 2 hours |
| Feature addition | Impacted areas | 4 hours |
| Hotfix | Critical path | 1 hour |
| Major release | Full suite | 24 hours |

### 8.2 Automated Regression Suite

| Layer | Tool | Coverage | Execution Time |
|-------|------|----------|----------------|
| Unit | Jest/JUnit | 80% code | 10 minutes |
| API | Postman/Newman | All endpoints | 30 minutes |
| UI | Selenium/Cypress | Critical paths | 2 hours |
| E2E | Cucumber | Business flows | 4 hours |

---

## 9. TEST AUTOMATION

### 9.1 Automation Framework

```
┌─────────────────────────────────────────────────────────────────┐
│                    TEST AUTOMATION FRAMEWORK                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    TEST MANAGEMENT                       │   │
│  │                   (TestRail / Xray)                      │   │
│  └─────────────────────────────────────────────────────────┘   │
│                              │                                  │
│       ┌──────────────────────┼──────────────────────┐          │
│       │                      │                      │          │
│       ▼                      ▼                      ▼          │
│  ┌──────────┐          ┌──────────┐          ┌──────────┐     │
│  │   API    │          │    UI    │          │  Mobile  │     │
│  │  Tests   │          │  Tests   │          │  Tests   │     │
│  │          │          │          │          │          │     │
│  │Postman/  │          │Selenium/ │          │Appium/   │     │
│  │RestAssured│         │Cypress   │          │Detox     │     │
│  └──────────┘          └──────────┘          └──────────┘     │
│       │                      │                      │          │
│       └──────────────────────┼──────────────────────┘          │
│                              │                                  │
│                              ▼                                  │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                   CI/CD INTEGRATION                      │   │
│  │                   (Jenkins/GitLab CI)                    │   │
│  │                                                          │   │
│  │  Trigger: Code commit → Build → Test → Report → Deploy  │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 9.2 Automation Coverage Targets

| Phase | Unit | Integration | E2E | Overall |
|-------|------|-------------|-----|---------|
| Sprint 1-4 | 60% | 40% | 20% | 40% |
| Sprint 5-8 | 75% | 60% | 40% | 58% |
| Sprint 9-12 | 85% | 75% | 60% | 73% |
| Go-Live | 90% | 85% | 75% | 83% |

---

## 10. DEFECT MANAGEMENT

### 10.1 Defect Severity Levels

| Severity | Definition | Response Time | Fix Target |
|----------|------------|---------------|------------|
| Critical | System unusable, data loss | 2 hours | 24 hours |
| High | Major feature broken | 4 hours | 72 hours |
| Medium | Workaround available | 24 hours | 1 week |
| Low | Cosmetic issues | 48 hours | Next release |

### 10.2 Defect Lifecycle

```
┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐
│  NEW    │───▶│ ASSIGNED│───▶│  OPEN   │───▶│  FIXED  │───▶│  TEST   │
└─────────┘    └─────────┘    └─────────┘    └─────────┘    └────┬────┘
                                                                  │
    ┌─────────────────────────────────────────────────────────────┘
    │
    ▼
┌─────────┐    ┌─────────┐
│ VERIFIED│───▶│ CLOSED  │
└─────────┘    └─────────┘
    │
    ▼
┌─────────┐
│ REOPENED│────────────────────────────────────────────────────────▶
└─────────┘
```

---

## 11. TEST SCHEDULE

| Phase | Duration | Start | End | Deliverable |
|-------|----------|-------|-----|-------------|
| Test Planning | 2 weeks | Month 2 | Month 2 | Test Plan |
| Unit Testing | Ongoing | Month 3 | Month 9 | Unit Test Report |
| SIT | 4 weeks | Month 8 | Month 9 | SIT Report |
| Performance Testing | 2 weeks | Month 8 | Month 8 | Performance Report |
| Security Testing | 2 weeks | Month 8 | Month 8 | Security Report |
| UAT | 4 weeks | Month 9 | Month 10 | UAT Sign-off |
| Regression Testing | 2 weeks | Month 10 | Month 10 | Regression Report |

---

## 12. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T33-VAPT-PLAN | Security Testing |
| CR-002 | ANNEX-T35-DEPLOYMENT-PLAN | Test Environment Setup |
| CR-003 | ANNEX-T31-SECURITY-FRAMEWORK | Security Requirements |
| CR-004 | ANNEX-T41-PROJECT-TIMELINE | Testing Schedule |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
