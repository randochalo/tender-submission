# ANNEX E: PROPOSED IT ARCHITECTURE & SECURITY FRAMEWORK

**Tender Reference:** JMYR/RFP/2026/001  
**Company:** Sinergi Elit Sdn Bhd (SESB)  
**Date:** 31 January 2026

---

## 1. SYSTEM ARCHITECTURE OVERVIEW

### 1.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    JMYR PAYMENT GATEWAY ARCHITECTURE                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         CLIENT LAYER                                  │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │   Web App   │  │  iOS App    │  │ Android App │  │  Merchant   │  │  │
│  │  │   React     │  │   Swift     │  │    Kotlin   │  │    SDK      │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼ CDN/WAF                                │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         GATEWAY LAYER                                 │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                      API GATEWAY (Kong/AWS)                     │  │  │
│  │  │  • Rate Limiting • Authentication • SSL/TLS • Load Balancing   │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      MICROSERVICES LAYER                              │  │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐         │  │
│  │  │  User   │ │  Quote  │ │Transaction│ │ Settlement │ │ Compliance │ │  │
│  │  │ Service │ │ Service │ │ Service  │ │  Service   │ │  Service   │ │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘         │  │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐         │  │
│  │  │  KYC    │ │  Wallet │ │ Notification │ │ Analytics │ │  Audit   │ │  │
│  │  │ Service │ │ Service │ │   Service    │ │  Service  │ │  Service │ │  │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘         │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         DATA LAYER                                    │  │
│  │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │  │
│  │  │ PostgreSQL  │  │    Redis    │  │  ImmuDB     │  │ClickHouse   │  │  │
│  │  │(Primary DB) │  │   (Cache)   │  │(Audit Log)  │  │(Analytics)  │  │  │
│  │  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                    │                                        │
│                                    ▼                                        │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                      BLOCKCHAIN LAYER                                 │  │
│  │  ┌─────────────────────────────────────────────────────────────────┐  │  │
│  │  │                    JMYR SMART CONTRACTS                         │  │  │
│  │  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐               │  │  │
│  │  │  │  Mint   │ │  Burn   │ │ Transfer │ │  Freeze │               │  │  │
│  │  │  │ Contract│ │ Contract│ │ Contract │ │ Contract│               │  │  │
│  │  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘               │  │  │
│  │  │                                                                  │  │  │
│  │  │  Network: Ethereum L2 / BSC (TBD based on gas/performance)      │  │  │
│  │  │  Standard: ERC-20 with upgradeable proxy pattern                 │  │  │
│  │  └─────────────────────────────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 1.2 Technology Stack

| Component | Technology | Justification |
|-----------|------------|---------------|
| **API Gateway** | Kong or AWS API Gateway | Enterprise-grade, rate limiting, authentication |
| **Microservices** | Node.js / Go | High performance, async processing |
| **Database** | PostgreSQL + TimescaleDB | ACID compliance, time-series support |
| **Cache** | Redis Cluster | Sub-millisecond response, session management |
| **Message Queue** | Apache Kafka | High throughput, guaranteed delivery |
| **Blockchain** | Ethereum L2 / BSC | Ecosystem maturity, lower gas costs |
| **Smart Contracts** | Solidity + OpenZeppelin | Security-audited libraries |
| **Infrastructure** | AWS / Azure | Compliance certifications, scalability |

---

## 2. BLOCKCHAIN ARCHITECTURE

### 2.1 Smart Contract Design

```solidity
// Simplified JMYR Token Contract Structure

contract JMYRToken is ERC20Upgradeable, PausableUpgradeable, AccessControlUpgradeable {
    // Roles
    bytes32 public constant MINTER_ROLE = keccak256("MINTER_ROLE");
    bytes32 public constant BURNER_ROLE = keccak256("BURNER_ROLE");
    bytes32 public constant FREEZER_ROLE = keccak256("FREEZER_ROLE");
    bytes32 public constant PAUSER_ROLE = keccak256("PAUSER_ROLE");
    
    // State
    mapping(address => bool) public frozen;
    uint256 public maxSupply;
    
    // Events
    event Mint(address indexed to, uint256 amount, bytes32 indexed reference);
    event Burn(address indexed from, uint256 amount, bytes32 indexed reference);
    event Freeze(address indexed account);
    event Unfreeze(address indexed account);
    
    // Core Functions
    function mint(address to, uint256 amount, bytes32 reference) external onlyRole(MINTER_ROLE);
    function burn(address from, uint256 amount, bytes32 reference) external onlyRole(BURNER_ROLE);
    function freeze(address account) external onlyRole(FREEZER_ROLE);
    function unfreeze(address account) external onlyRole(FREEZER_ROLE);
}
```

### 2.2 Multi-Signature Wallet Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    MULTI-SIG WALLET STRUCTURE                               │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  OPERATION TYPES:                                                           │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  Tier 1: Daily Operations (2-of-4)                                  │   │
│  │    • Routine minting/burning (within daily limits)                  │   │
│  │    • Standard transfers                                             │   │
│  │                                                                     │   │
│  │  Tier 2: Significant Operations (3-of-5)                            │   │
│  │    • Large minting/burning (above daily limits)                     │   │
│  │    • Contract upgrades                                              │   │
│  │    • Parameter changes                                              │   │
│  │                                                                     │   │
│  │  Tier 3: Emergency Operations (4-of-6)                              │   │
│  │    • Contract pause/unpause                                         │   │
│  │    • Emergency fund recovery                                        │   │
│  │    • Key rotation                                                   │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│  SIGNER COMPOSITION:                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • 2 SESB Technical Directors                                       │   │
│  │  • 2 JMYR Executives                                                │   │
│  │  • 1 External Security Auditor                                      │   │
│  │  • 1 BDO Representative (for Tier 2 & 3)                            │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. SECURITY ARCHITECTURE

### 3.1 Defense in Depth

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       SECURITY LAYERS                                       │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  LAYER 1: PERIMETER                                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • AWS WAF / Cloudflare                                              │   │
│  │  • DDoS Protection (AWS Shield Advanced)                             │   │
│  │  • Geo-blocking (allow MY only for admin)                            │   │
│  │  • Rate limiting per IP/user                                         │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 2: NETWORK                                                         │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • VPC with private subnets                                          │   │
│  │  • Security groups (least privilege)                                 │   │
│  │  • Network ACLs                                                      │   │
│  │  • VPC Flow Logs                                                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 3: APPLICATION                                                     │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Input validation & sanitization                                   │   │
│  │  • OWASP Top 10 protection                                           │   │
│  │  • CSRF, XSS, SQL injection prevention                               │   │
│  │  • API authentication (JWT + API keys)                               │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 4: DATA                                                            │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • AES-256 encryption at rest                                        │   │
│  │  • TLS 1.3 in transit                                                │   │
│  │  • Field-level encryption for PII                                    │   │
│  │  • Database activity monitoring                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 5: BLOCKCHAIN                                                      │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Multi-signature requirements                                      │   │
│  │  • Cold storage for reserves                                         │   │
│  │  • Address whitelisting                                              │   │
│  │  • Transaction limits and delays                                     │   │
│  │  • OpenZeppelin Defender for monitoring                              │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                    │                                        │
│  LAYER 6: IDENTITY                                                        │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │  • Multi-factor authentication                                       │   │
│  │  • Biometric verification (mobile)                                   │   │
│  │  • Hardware security keys (admin)                                    │   │
│  │  • Role-based access control (RBAC)                                  │   │
│  │  • Privileged access management                                      │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 3.2 Security Controls Matrix

| Control Category | Implementation | Verification |
|------------------|----------------|--------------|
| **Authentication** | MFA, biometrics, hardware keys | Quarterly access review |
| **Authorization** | RBAC, least privilege | Monthly permission audit |
| **Encryption** | AES-256, TLS 1.3 | Annual penetration test |
| **Monitoring** | SIEM, blockchain analytics | Real-time alerting |
| **Backup** | Encrypted offsite, 30-day retention | Quarterly restore test |
| **Incident Response** | Playbooks, 15-min response SLA | Bi-annual drill |

---

## 4. COMPLIANCE FRAMEWORK

### 4.1 AML/CFT Controls

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    AML/CFT CONTROL FRAMEWORK                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    CUSTOMER ONBOARDING (KYC)                          │  │
│  │                                                                       │  │
│  │  ┌─────────┐    ┌─────────┐    ┌─────────┐    ┌─────────┐            │  │
│  │  │ Identity│───▶│  Liveness│───▶│  Document│───▶│  Risk   │            │  │
│  │  │Verification│ │  Check  │    │Verification│   │ Scoring │            │  │
│  │  └─────────┘    └─────────┘    └─────────┘    └─────────┘            │  │
│  │                                                                       │  │
│  │  Providers: Jumio / Onfido / Shufti Pro                               │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    TRANSACTION MONITORING                             │  │
│  │                                                                       │  │
│  │  Real-time Screening:                                                 │  │
│  │  ├─ Amount thresholds (daily, monthly limits)                         │  │
│  │  ├─ Velocity checks (frequency of transactions)                       │  │
│  │  ├─ Sanctions screening (UN, OFAC, EU lists)                          │  │
│  │  ├─ PEP screening                                                     │  │
│  │  └─ Adverse media monitoring                                          │  │
│  │                                                                       │  │
│  │  Provider: Chainalysis KYT / Elliptic                                 │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                    SUSPICIOUS ACTIVITY REPORTING                      │  │
│  │                                                                       │  │
│  │  • Automated SAR generation for flagged transactions                  │  │
│  │  • 24-hour reporting to BNM for threshold breaches                    │  │
│  │  • Suspicious transaction record keeping (7 years)                    │  │
│  │                                                                       │  │
│  └───────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 4.2 Travel Rule Compliance (FATF R16)

| Requirement | Implementation |
|-------------|----------------|
| **Originator Info** | Name, account number, address collected |
| **Beneficiary Info** | Name, account number verified |
| **VASp Verification** | Counterparty VASP due diligence |
| **Secure Transmission** | Encrypted PII exchange |
| **Record Keeping** | 5-year retention of travel rule data |

---

## 5. INFRASTRUCTURE & DEPLOYMENT

### 5.1 Cloud Architecture

| Environment | Provider | Region | Purpose |
|-------------|----------|--------|---------|
| **Production** | AWS | Singapore (ap-southeast-1) | Primary operations |
| **DR** | AWS | Australia (ap-southeast-2) | Disaster recovery |
| **Sandbox** | AWS | Singapore | Testing, BNM sandbox |

### 5.2 High Availability Design

- **Multi-AZ Deployment**: Services distributed across 3 availability zones
- **Auto-scaling**: Horizontal pod autoscaling (HPA) based on CPU/memory
- **Database Replication**: PostgreSQL streaming replication with automatic failover
- **Load Balancing**: Application load balancer with health checks
- **Circuit Breakers**: Prevents cascade failures in microservices

### 5.3 Disaster Recovery

| Metric | Target | Implementation |
|--------|--------|----------------|
| **RPO** | < 5 minutes | Continuous replication |
| **RTO** | < 30 minutes | Automated failover |
| **Backup Frequency** | Hourly | Incremental + daily full |
| **Retention** | 30 days | Primary, 1 year archive |

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
