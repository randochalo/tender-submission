# ANNEX F: IMPLEMENTATION PLAN & METHODOLOGY

**Tender Reference:** JMYR/RFP/2026/001  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Project:** JMYR Cross-Border Payment Gateway  
**Date:** 31 January 2026

---

## 1. PROJECT METHODOLOGY

### 1.1 Agile-Phased Approach

SESB employs an **Agile-Phased methodology** combining the flexibility of Agile sprints with structured phase gates appropriate for financial services delivery.

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AGILE-PHASED METHODOLOGY                                 │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐     │
│  │   PHASE 1   │──▶│   PHASE 2   │──▶│   PHASE 3   │──▶│   PHASE 4   │     │
│  │ Foundation  │   │    Build    │   │    Pilot    │   │    Scale    │     │
│  │   (M1-3)    │   │   (M4-6)    │   │   (M7-9)    │   │  (M10-12)   │     │
│  └─────────────┘   └─────────────┘   └─────────────┘   └─────────────┘     │
│        │                 │                 │                 │              │
│        ▼                 ▼                 ▼                 ▼              │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Within each phase: 2-week sprints with demo, retro, planning       │   │
│  │  Phase gates: Compliance review, security audit, go/no-go decision  │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Phase Overview

| Phase | Timeline | Focus | Key Deliverable |
|-------|----------|-------|-----------------|
| **Phase 1** | Months 1-3 | Architecture, compliance, partnerships | Technical design, sandbox approval |
| **Phase 2** | Months 4-6 | Core development, smart contracts | MVP on testnet |
| **Phase 3** | Months 7-9 | Testing, audit, pilot | Production launch with 1 partner |
| **Phase 4** | Months 10-12 | Public launch, marketing | Full production, 100K users |

---

## 2. DETAILED PROJECT TIMELINE

### 2.1 Phase 1: Foundation (Months 1-3)

```
Month 1                    Month 2                    Month 3
├─ Week 1-2 ─┼─ Week 3-4 ─┼─ Week 5-6 ─┼─ Week 7-8 ─┼─ Week 9-10 ┼─ Week 11-12 ┤
     │             │             │             │             │              │
  ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐
  │Kick- │    │Arch  │    │Bank  │    │BNM   │    │Sec   │    │Phase │
  │off   │    │Design│    │Partnr│    │Sandbx│    │Audit │    │Gate  │
  │      │    │      │    │Disc  │    │App   │    │Plan  │    │1     │
  └──────┘    └──────┘    └──────┘    └──────┘    └──────┘    └──────┘

Activities:
• Project mobilization              • Technical architecture finalization
• Team onboarding                   • Bank partnership MoUs
• Requirements workshops            • BNM sandbox application
• Compliance framework design       • Security audit planning
```

**Phase 1 Deliverables:**
- Technical Architecture Document
- BNM Sandbox Application (submitted)
- Bank Partnership Letters of Intent (3+)
- Compliance Framework Document
- Security Audit Scope

### 2.2 Phase 2: Build (Months 4-6)

```
Month 4                    Month 5                    Month 6
├─ Week 13-14─┼─ Week 15-16┼─ Week 17-18┼─ Week 19-20┼─ Week 21-22┼─ Week 23-24┤
      │             │             │             │             │              │
  ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐
  │Smart │    │Bank  │    │KYC   │    │Gateway│   │Test  │    │MVP   │
  │Contrt│    │API   │    │Integr│    │Core  │    │Complete│   │Demo  │
  │Dev   │    │Dev   │    │      │    │      │    │      │    │      │
  └──────┘    └──────┘    └──────┘    └──────┘    └──────┘    └──────┘

Activities:
• Smart contract development        • Bank API integration
• Security audit (ongoing)          • KYC provider integration
• Payment gateway core              • End-to-end testing
• Testnet deployment                • MVP demonstration
```

**Phase 2 Deliverables:**
- Deployed Smart Contracts (testnet)
- Core Payment Gateway (testnet)
- Bank API Integration (test environment)
- KYC/AML Integration
- Security Audit Report (draft)

### 2.3 Phase 3: Pilot (Months 7-9)

```
Month 7                    Month 8                    Month 9
├─ Week 25-26┼─ Week 27-28┼─ Week 29-30┼─ Week 31-32┼─ Week 33-34┼─ Week 35-36┤
      │             │             │             │             │              │
  ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐
  │Prod  │    │Sec   │    │BNM   │    │Pilot │    │Pilot │    │Phase │
  │Deploy│    │Audit │    │Approvl│   │Launch│    │Opt   │    │Gate  │
  │Prep  │    │Final │    │      │    │      │    │      │    │3     │
  └──────┘    └──────┘    └──────┘    └──────┘    └──────┘    └──────┘

Activities:
• Production environment setup      • Final security audit
• Penetration testing               • BNM sandbox graduation
• Pilot partner onboarding          • Limited user pilot (1,000 users)
• Bug fixes and optimization        • Performance tuning
```

**Phase 3 Deliverables:**
- Production Environment Live
- Security Audit Certificate
- BNM Regulatory Approval
- Pilot Program Live (1 partner, 1,000 users)
- Performance Benchmarks Met

### 2.4 Phase 4: Scale (Months 10-12)

```
Month 10                   Month 11                   Month 12
├─ Week 37-38┼─ Week 39-40┼─ Week 41-42┼─ Week 43-44┼─ Week 45-46┼─ Week 47-48┤
      │             │             │             │             │              │
  ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐    ┌──────┐
  │Public│    │Market│    │Partner│   │Scale │    │Stabil│    │Proj  │
  │Launch│    │Campgn│    │Onbord│    │Ops   │    │      │    │Close │
  │      │    │      │    │      │    │      │    │      │    │      │
  └──────┘    └──────┘    └──────┘    └──────┘    └──────┘    └──────┘

Activities:
• Public launch announcement        • Marketing campaign execution
• Additional bank integrations      • Merchant onboarding
• User acquisition campaigns        • Operations stabilization
• 24/7 support activation           • Project handover
```

**Phase 4 Deliverables:**
- Public Launch (100,000 users target)
- Marketing Campaign Live
- 3+ Bank Partners Integrated
- 24/7 Operations Active
- Final Project Documentation

---

## 3. PROJECT TEAM STRUCTURE

### 3.1 Organization Chart

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                         PROJECT ORGANIZATION                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│                    ┌─────────────────────┐                                  │
│                    │   PROJECT SPONSOR   │                                  │
│                    │  (JMYR + SESB Exec) │                                  │
│                    └──────────┬──────────┘                                  │
│                               │                                             │
│                    ┌──────────▼──────────┐                                  │
│                    │   PROJECT BOARD     │                                  │
│                    │ (Monthly Governance)│                                  │
│                    └──────────┬──────────┘                                  │
│                               │                                             │
│         ┌─────────────────────┼─────────────────────┐                       │
│         │                     │                     │                       │
│  ┌──────▼──────┐     ┌────────▼────────┐   ┌──────▼──────┐                │
│  │  PROJECT    │     │   TECHNICAL     │   │  BUSINESS   │                │
│  │  MANAGER    │     │   LEAD          │   │  LEAD       │                │
│  │ (Delivery)  │     │ (Architecture)  │   │ (GTM/Ops)   │                │
│  └──────┬──────┘     └────────┬────────┘   └──────┬──────┘                │
│         │                     │                     │                       │
│    ┌────┴────┐          ┌─────┴─────┐        ┌────┴────┐                  │
│    │         │          │           │        │         │                  │
│ ┌──▼──┐   ┌─▼──┐    ┌──▼──┐     ┌──▼──┐  ┌──▼──┐   ┌─▼──┐               │
│ │PMO  │   │QA  │    │Block│     │App  │  │Markt│   │Ops │               │
│ │     │   │    │    │chain│     │Dev  │  │     │   │    │               │
│ └─────┘   └────┘    └─────┘     └─────┘  └─────┘   └────┘               │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Key Personnel

| Role | Name/Profile | Responsibility |
|------|--------------|----------------|
| **Project Manager** | 15+ years fintech delivery | Overall delivery, stakeholder management |
| **Technical Lead** | Blockchain architect, 10 years | Solution architecture, technical decisions |
| **Blockchain Lead** | Solidity expert, 6 years | Smart contract development, security |
| **Backend Lead** | Payment systems, 8 years | Gateway development, bank integrations |
| **Security Lead** | CISSP, former bank CISO | Security architecture, audit coordination |
| **Compliance Lead** | ex-BNM, 12 years | Regulatory engagement, compliance framework |
| **Marketing Lead** | Fintech growth, 8 years | GTM strategy, user acquisition |

### 3.3 Team Size by Phase

| Phase | Team Size | Key Additions |
|-------|-----------|---------------|
| **Phase 1** | 12 | Core team, compliance specialists |
| **Phase 2** | 20 | + Blockchain devs, backend engineers |
| **Phase 3** | 18 | + QA, security auditors, support |
| **Phase 4** | 25 | + Marketing, operations, partnerships |

---

## 4. RISK MANAGEMENT

### 4.1 Risk Register

| Risk | Prob | Impact | Mitigation | Owner |
|------|------|--------|------------|-------|
| **BNM Approval Delay** | Med | High | Early engagement, sandbox application, alternative plans | Compliance Lead |
| **Bank Integration Issues** | Med | High | Multiple banking partners, fallback channels, early testing | Technical Lead |
| **Smart Contract Vulnerability** | Low | Critical | Multiple audits, bug bounty, formal verification | Security Lead |
| **Low User Adoption** | Med | Med | Phased incentives, partnerships, market education | Marketing Lead |
| **Talent Attrition** | Low | Med | Competitive packages, knowledge documentation, cross-training | Project Manager |

### 4.2 Contingency Plans

| Scenario | Response |
|----------|----------|
| **Schedule Slippage** | Add resources, reduce scope, extend timeline with approval |
| **Budget Overrun** | Phase implementation, defer non-critical features |
| **Security Incident** | Activate incident response, pause transactions, forensic investigation |
| **Regulatory Change** | Compliance review, architecture adjustment, BNM consultation |

---

## 5. QUALITY ASSURANCE

### 5.1 Testing Strategy

| Test Type | Approach | Tools |
|-----------|----------|-------|
| **Unit Testing** | 80%+ code coverage | Jest, Hardhat |
| **Integration Testing** | API contract testing | Postman, Newman |
| **Security Testing** | Penetration test, SAST/DAST | Burp Suite, SonarQube |
| **Smart Contract Audit** | Internal + External audit | Slither, Mythril, CertiK |
| **Performance Testing** | Load testing to 1000 TPS | k6, Artillery |
| **UAT** | Pilot user acceptance testing | Manual + automated |

### 5.2 Quality Gates

| Gate | Criteria | Sign-off |
|------|----------|----------|
| **G1: Design** | Architecture approved, security review complete | CTO |
| **G2: Development** | Code review passed, unit tests >80% | Tech Lead |
| **G3: Security** | Pen test passed, critical vulnerabilities resolved | CISO |
| **G4: Pilot** | UAT passed, BNM approval obtained | Project Board |
| **G5: Launch** | All systems GO, marketing ready, support staffed | Steering Committee |

---

## 6. CHANGE MANAGEMENT

### 6.1 Communication Plan

| Stakeholder | Frequency | Channel | Content |
|-------------|-----------|---------|---------|
| **JMYR Executive** | Weekly | Email + Meeting | Progress, risks, decisions |
| **Project Team** | Daily | Standup + Slack | Tasks, blockers, coordination |
| **Bank Partners** | Bi-weekly | Email + Calls | Integration status |
| **BNM** | As required | Formal submissions | Regulatory updates |

### 6.2 Training Plan

| Audience | Training | Timing |
|----------|----------|--------|
| **Operations Team** | System operation, incident response | Month 8 |
| **Customer Support** | Product knowledge, troubleshooting | Month 9 |
| **End Users** | App tutorials, FAQ, help center | Month 10 |
| **Merchants** | API integration, portal usage | Month 10-11 |

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Tender Reference | JMYR/RFP/2026/001 |

---

*This document is part of the tender submission for JMYR Sdn. Bhd.*
