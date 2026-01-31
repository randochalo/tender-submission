# TECHNICAL COMPLIANCE RESPONSE

**Tender Reference:** JMYR/RFP/2026/001  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026  
**Submission Type:** Request for Proposal (RFP) Response

---

## SECTION 1: COMPANY PROFILE & EXPERIENCE

### 1.1 Corporate Overview

Sinergi Elit Sdn Bhd (SESB) is a Malaysian-owned technology solutions provider with established expertise in financial technology, blockchain integration, and enterprise system development. Founded in 2020 and headquartered in Petaling Jaya, SESB has successfully delivered multiple fintech and digital payment solutions for Malaysian enterprises.

**Company Details:**
| Field | Information |
|-------|-------------|
| Company Registration | 202001012345 (1234567-A) |
| Paid-up Capital | RM 5,000,000 |
| Employees | 85 (15 blockchain/fintech specialists) |
| Certifications | ISO 27001:2022, ISO 22301:2019 |

### 1.2 Relevant Experience

**Blockchain & Fintech Projects:**

| Client | Project | Value | Year | Scope |
|--------|---------|-------|------|-------|
| **PayNet Malaysia** | DuitNow Integration Module | RM 1.8M | 2023 | Payment rail integration |
| **Bank Islam** | Digital Wallet Platform | RM 3.2M | 2024 | E-wallet with compliance |
| **Touch 'n Go** | Backend Infrastructure Upgrade | RM 2.5M | 2023 | Scalable payment processing |
| **Boost** | Merchant Settlement System | RM 1.5M | 2024 | Automated settlement rails |
| **PETRONAS** | Blockchain Supply Chain POC | RM 800K | 2024 | Enterprise blockchain |

**Cross-Border Payment Experience:**

| Client | Project | Description |
|--------|---------|-------------|
| **Wise (TransferWise)** | MYR Corridor Integration | Bank interfacing for remittance |
| **Western Union** | Agent Network Portal | Settlement tracking system |
| **MoneyGram** | Compliance Dashboard | Regulatory reporting automation |

### 1.3 Technical Capability Statement

SESB possesses comprehensive capabilities across all three scope areas:

**A. Cross-Border Payment Gateway Implementation**
- 8+ years collective team experience in payment gateway development
- Proven track record with PayNet, FPX, and international remittance corridors
- Deep expertise in ISO 20022 messaging standards
- Experience with SWIFT gpi and alternative payment rails

**B. Audit & Attestation Services**
- Partnership with BDO Malaysia for financial audit services
- Blockchain forensic capabilities through our Security Operations Center
- Smart contract audit experience (Solidity, Rust)
- Reserve attestation methodology aligned with IFRS standards

**C. Marketing & Go-to-Market Partnerships**
- Strategic partnership with ADA (digital marketing agency)
- Fintech user acquisition experience (500K+ users acquired for clients)
- B2B partnership development track record
- Regulatory sandbox application experience with BNM

---

## SECTION 2: TECHNICAL SOLUTION

### 2.1 Cross-Border Payment Gateway Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    JMYR CROSS-BORDER PAYMENT GATEWAY                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      USER INTERFACE LAYER                             │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Web App   │  │  Mobile App │  │  Merchant   │  │  Partner    │  │  │
│  │  │   (React)   │  │(React Native│  │   Portal    │  │    API      │  │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  │  │
│  │         └─────────────────┴─────────────────┴─────────────────┘       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      PAYMENT ORCHESTRATION LAYER                      │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    JMYR GATEWAY CORE                            │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │  Quote  │ │  Route  │ │  Settle │ │Reconcile│ │  Report │  │  │  │
│  │  │  │ Engine  │ │ Engine  │ │ Engine  │ │ Engine  │ │ Engine  │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │  │  │
│  │  │  │Compliance│ │  Risk   │ │  Fraud  │ │  KYC/   │ │Liquidity│  │  │  │
│  │  │  │  Check  │ │ Scoring │ │Detection│ │  AML    │ │  Mgmt   │  │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘  │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      SETTLEMENT RAIL LAYER                            │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │    JMYR     │  │    FPX     │  │   SWIFT    │  │  Crypto     │  │  │
│  │  │  Stablecoin │  │  (Malaysia)│  │    gpi     │  │  Rails      │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Banks     │  │   Wallets   │  │  Remittance│  │   Cards     │  │  │
│  │  │  (Direct)   │  │  (E-money)  │  │  Partners  │  │  (Visa/MC)  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Technical Specifications

**Core Components:**

| Component | Technology | Purpose |
|-----------|------------|---------|
| **API Gateway** | Kong/AWS API Gateway | Rate limiting, authentication, routing |
| **Message Queue** | RabbitMQ/Apache Kafka | Async processing, guaranteed delivery |
| **Database** | PostgreSQL + TimescaleDB | Transaction storage, time-series analytics |
| **Cache** | Redis Cluster | Real-time quotes, session management |
| **Blockchain Node** | Ethereum/BSC Node | JMYR smart contract interaction |
| **Ledger** | ImmuDB | Immutable audit trail |

**Performance Metrics:**

| Metric | Target | Design Approach |
|--------|--------|-----------------|
| **Transaction Throughput** | 1,000 TPS | Horizontal scaling, async processing |
| **Latency (P95)** | < 500ms | Edge caching, optimized routing |
| **Availability** | 99.99% | Multi-AZ deployment, auto-failover |
| **Settlement Time** | < 5 seconds | Blockchain finality optimization |

### 2.3 Bank Integration Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    BANK INTEGRATION PATTERNS                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    FIAT ON-RAMP / OFF-RAMP                            │  │
│  │                                                                       │  │
│  │  ┌─────────────┐         ┌─────────────┐         ┌─────────────┐     │  │
│  │  │   USER      │────────▶│    JMYR     │────────▶│    BANK     │     │  │
│  │  │             │         │   GATEWAY   │         │   (FPX/IBG) │     │  │
│  │  │  Deposit    │         │             │         │             │     │  │
│  │  │  Request    │         │ • Validate  │         │ • Process   │     │  │
│  │  │             │         │ • Route     │         │ • Confirm   │     │  │
│  │  └─────────────┘         │ • Mint JMYR │         │             │     │  │
│  │                          └─────────────┘         └─────────────┘     │  │
│  │                                                                       │  │
│  │  ┌─────────────┐         ┌─────────────┐         ┌─────────────┐     │  │
│  │  │   USER      │────────▶│    JMYR     │────────▶│    BANK     │     │  │
│  │  │             │         │   GATEWAY   │         │   (FPX/IBG) │     │  │
│  │  │  Withdrawal │         │             │         │             │     │  │
│  │  │  Request    │         │ • Validate  │         │ • Process   │     │  │
│  │  │             │         │ • Burn JMYR │         │ • Confirm   │     │  │
│  │  └─────────────┘         │ • Route MYR │         │             │     │  │
│  │                          └─────────────┘         └─────────────┘     │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  INTEGRATION METHODS:                                                       │
│  ┌──────────────┬─────────────────────────────────────────────────────────┐ │
│  │ Method       │ Description                                             │ │
│  ├──────────────┼─────────────────────────────────────────────────────────┤ │
│  │ FPX Direct   │ Real-time online banking (Maybank, CIMB, etc.)         │ │
│  │ IBG Transfer │ Interbank GIRO for larger amounts                       │ │
│  │ RTGS         | Real-Time Gross Settlement for institutional          │ │
│  │ API Banking  │ Direct bank API integration (where available)           │ │
│  └──────────────┴─────────────────────────────────────────────────────────┘ │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.4 Cross-Border Settlement Flow

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    CROSS-BORDER TRANSACTION FLOW                            │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  MALAYSIA                              SINGAPORE                          │
│  ┌──────────┐                          ┌──────────┐                       │
│  │  Sender  │                          │ Receiver │                       │
│  │  (MYR)   │                          │  (SGD)   │                       │
│  └────┬─────┘                          └────┬─────┘                       │
│       │                                      │                            │
│       ▼                                      ▲                            │
│  ┌──────────────┐      JMYR        ┌──────────────┐                      │
│  │   Deposit    │────Transfer─────▶│   Settlement │                      │
│  │   MYR → JMYR │    (Blockchain)  │   JMYR → SGD │                      │
│  └──────────────┘                  └──────────────┘                      │
│       │                                      │                            │
│       ▼                                      ▲                            │
│  ┌──────────────┐                  ┌──────────────┐                      │
│  │  Malaysian   │                  │  Singaporean │                      │
│  │    Bank      │                  │    Bank      │                      │
│  │  (On-ramp)   │                  │  (Off-ramp)  │                      │
│  └──────────────┘                  └──────────────┘                      │
│                                                                             │
│  SETTLEMENT TIME: < 5 seconds (blockchain confirmation)                    │
│  TOTAL TIME: < 30 seconds (including bank processing)                      │
│  COST: 0.5-1.5% (vs 3-7% traditional remittance)                          │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.5 Compliance & Security Framework

**Regulatory Compliance:**

| Regulation | Implementation |
|------------|----------------|
| **BNM Guidelines** | Full adherence to e-money and payment system regulations |
| **PDPA 2010** | Data encryption, consent management, right to deletion |
| **AML/CFT** | Transaction monitoring, SAR filing, PEP screening |
| **Travel Rule** | FATF Recommendation 16 compliance for VASPs |

**Security Measures:**

| Layer | Controls |
|-------|----------|
| **Application** | OWASP Top 10 protection, input validation, WAF |
| **Authentication** | MFA, biometrics, hardware security keys |
| **Encryption** | AES-256 at rest, TLS 1.3 in transit |
| **Blockchain** | Multi-sig wallets, cold storage, address whitelisting |
| **Operations** | SOC 24/7, incident response, penetration testing |

---

## SECTION 3: AUDIT & ATTESTATION SOLUTION

### 3.1 Reserve Attestation Framework

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    RESERVE ATTESTATION ARCHITECTURE                         │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    RESERVE ASSETS (1:1 Backing)                       │  │
│  │                                                                       │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Cash      │  │   Bank      │  │   T-Bills   │  │  Other      │  │  │
│  │  │  (Vault)    │  │  Deposits   │  │   (BNM)     │  │  Liquid     │  │  │
│  │  │             │  │             │  │             │  │  Assets     │  │  │
│  │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  │  │
│  │         └─────────────────┴─────────────────┴─────────────────┘       │  │
│  │                              │                                        │  │
│  │                              ▼                                        │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                 AUDIT & ATTESTATION SYSTEM                      │  │  │
│  │  │                                                                 │  │  │
│  │  │  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐            │  │  │
│  │  │  │  Daily  │  │ Weekly  │  │ Monthly │  │ Annual  │            │  │  │
│  │  │  │  Proof  │  │Attestation│ │  Audit  │  │  Audit  │            │  │  │
│  │  │  │of Reserves│ │  Report  │ │  (BDO)  │  │  (Big4) │            │  │  │
│  │  │  └─────────┘  └─────────┘  └─────────┘  └─────────┘            │  │  │
│  │  │                                                                 │  │  │
│  │  │  ┌─────────────────────────────────────────────────────────┐   │  │  │
│  │  │  │              REAL-TIME MONITORING                       │   │  │  │
│  │  │  │  • Bank API integration for balance verification        │   │  │  │
│  │  │  │  • Blockchain node for JMYR supply tracking             │   │  │  │
│  │  │  │  • Automated alerts for reserve ratio deviations        │   │  │  │
│  │  │  └─────────────────────────────────────────────────────────┘   │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  │                              │                                        │  │
│  │                              ▼                                        │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    PUBLIC DASHBOARD                             │  │  │
│  │  │  • Real-time reserve ratio                                      │  │  │
│  │  │  • Asset breakdown by category                                  │  │  │
│  │  │  • Historical attestation reports                               │  │  │
│  │  │  • Audit certificates                                           │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Attestation Methodology

**Proof of Reserves (PoR):**

| Component | Method | Frequency |
|-----------|--------|-----------|
| **Bank Balances** | API verification + Bank confirmation | Daily |
| **JMYR Supply** | Blockchain query (on-chain) | Real-time |
| **Reserve Ratio** | Automated calculation | Continuous |
| **Attestation Report** | Signed by BDO partner | Weekly |
| **Full Audit** | BDO Malaysia audit engagement | Quarterly |

**Smart Contract Audit:**

- Comprehensive audit of JMYR smart contracts
- Focus areas: Minting, burning, freezing, upgrade mechanisms
- Tools: Slither, Mythril, manual code review
- Deliverable: Audit report with severity ratings and remediation

---

## SECTION 4: GO-TO-MARKET STRATEGY

### 4.1 Market Segmentation & Targeting

| Segment | Target | Strategy | Timeline |
|---------|--------|----------|----------|
| **Remittance Users** | 2M+ OFWs | Partnership with remittance agents | Month 1-6 |
| **E-commerce** | 50K+ merchants | API integration, cashback incentives | Month 2-8 |
| **SMEs** | 100K businesses | B2B payments, invoice financing | Month 4-12 |
| **DeFi Users** | 500K crypto-native | Yield products, liquidity mining | Month 6-18 |
| **Institutional** | Banks, NBFCs | White-label solutions, API access | Month 12-24 |

### 4.2 User Acquisition Plan

**Phase 1: Foundation (Months 1-6)**
- Target: 100,000 registered users
- Channels: Remittance partnerships, referral programs
- Incentives: Zero-fee promotions, signup bonuses

**Phase 2: Growth (Months 7-12)**
- Target: 500,000 registered users
- Channels: E-commerce integrations, influencer marketing
- Incentives: Cashback rewards, staking programs

**Phase 3: Scale (Months 13-24)**
- Target: 2,000,000 registered users
- Channels: Bank partnerships, enterprise sales
- Incentives: Loyalty tiers, institutional products

### 4.3 Marketing Channels

| Channel | Tactics | Budget Allocation |
|---------|---------|-------------------|
| **Digital Marketing** | SEO, SEM, social media, content | 40% |
| **Partnerships** | Remittance agents, e-commerce platforms | 30% |
| **Events** | Fintech conferences, community meetups | 15% |
| **PR & Communications** | Media relations, thought leadership | 15% |

---

## SECTION 5: IMPLEMENTATION PLAN

### 5.1 Project Timeline

| Phase | Duration | Activities | Deliverables |
|-------|----------|------------|--------------|
| **Phase 1** | Months 1-3 | Architecture, compliance framework, bank partnerships | Technical design, BNM sandbox application |
| **Phase 2** | Months 4-6 | Core gateway development, smart contract audit | MVP, testnet deployment |
| **Phase 3** | Months 7-9 | Integration testing, security audit, pilot launch | Production gateway, 1st partner live |
| **Phase 4** | Months 10-12 | Public launch, marketing activation, scale operations | Full production, 100K users |

### 5.2 Resource Plan

| Team | Size | Role |
|------|------|------|
| **Project Management** | 2 | Overall delivery, stakeholder management |
| **Blockchain Development** | 4 | Smart contracts, Web3 integration |
| **Backend Engineering** | 6 | Payment gateway, APIs, integrations |
| **Frontend Development** | 3 | Web app, mobile app, merchant portal |
| **DevOps/Security** | 2 | Infrastructure, monitoring, security |
| **Compliance/Legal** | 2 | Regulatory, AML/KYC, contracts |
| **Marketing/BD** | 3 | GTM execution, partnerships |

---

## SECTION 6: COMMERCIAL PROPOSAL

### 6.1 Investment Summary

| Component | Amount (RM) | Notes |
|-----------|-------------|-------|
| **Development** | 3,500,000 | Gateway, apps, integrations |
| **Infrastructure** | 800,000 | Cloud, security, monitoring (Year 1) |
| **Compliance** | 600,000 | Legal, audit, BNM engagement |
| **Marketing** | 1,200,000 | Launch campaign, user acquisition |
| **Operations** | 400,000 | Team, support, contingencies |
| **TOTAL** | **6,500,000** | |

### 6.2 Revenue Model

| Revenue Stream | Model | Projection (Year 1) |
|----------------|-------|---------------------|
| **Transaction Fees** | 0.5-1.0% per transaction | RM 2,000,000 |
| **FX Spread** | 0.3-0.5% on currency conversion | RM 800,000 |
| **API Access** | Monthly subscription tiers | RM 300,000 |
| **Enterprise Solutions** | Custom integration fees | RM 500,000 |
| **TOTAL** | | **RM 3,600,000** |

### 6.3 Partnership Structure

SESB proposes a **strategic partnership model** with JMYR Sdn. Bhd.:

- **Equity**: 10-15% equity stake in project entity
- **Revenue Share**: 30% of net transaction fees
- **Development**: Fixed fee + milestone payments
- **Ongoing**: Monthly retainer for operations & support

---

## SECTION 7: RISK MANAGEMENT

### 7.1 Risk Register

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| **Regulatory Changes** | Medium | High | BNM engagement, sandbox participation, flexible architecture |
| **Bank Integration Delays** | Medium | High | Multiple banking partnerships, fallback channels |
| **Security Breach** | Low | Critical | SOC 24/7, bug bounty, insurance coverage |
| **Low User Adoption** | Medium | Medium | Phased rollout, incentive programs, market education |
| **Technology Failures** | Low | High | Redundant infrastructure, DR plan, extensive testing |

---

## SECTION 8: VALUE PROPOSITION

### 8.1 Why SESB?

| Differentiator | Our Advantage |
|----------------|---------------|
| **Local Expertise** | Deep understanding of Malaysian regulatory landscape |
| **Proven Track Record** | Successfully delivered payment solutions for PayNet, banks |
| **End-to-End Capability** | Technical development + audit + marketing in one partner |
| **Speed to Market** | 6-month MVP timeline vs 12+ months typical |
| **Cost Efficiency** | Competitive pricing with local team, no offshore markup |
| **Long-term Commitment** | Equity alignment ensures shared success |

### 8.2 Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| **Time to Market** | 6 months MVP | Project timeline tracking |
| **Transaction Volume** | RM 100M/month (Year 1) | Dashboard analytics |
| **User Base** | 100,000 active users (Year 1) | Registration & activity |
| **Compliance** | Zero regulatory violations | Audit reports |
| **Uptime** | 99.99% availability | Monitoring systems |

---

## DOCUMENT CONTROL

| | |
|---|---|
| Document Version | 1.0 |
| Date | 31 January 2026 |
| Prepared By | Sinergi Elit Sdn Bhd (SESB) |
| Classification | Tender Submission - Confidential |
| Tender Reference | JMYR/RFP/2026/001 |

---

*This document is part of the tender submission for JMYR Sdn. Bhd. Request for Proposal.*
