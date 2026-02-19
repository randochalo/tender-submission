# ANNEX T28: VALUE-ADDED FEATURES

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex outlines the value-added features included in the USP Claims Management System proposal that extend beyond the core requirements, providing enhanced functionality, efficiency gains, and strategic advantages to MCMC.

---

## 2. VALUE-ADDED FEATURES CATALOG

### 2.1 Feature Summary Matrix

| Feature ID | Feature Name | Category | Business Value | Effort |
|------------|--------------|----------|----------------|--------|
| VAF-001 | AI-Powered Claim Validation | Automation | 40% faster processing | Medium |
| VAF-002 | Intelligent Document Processing | Efficiency | 60% less manual entry | Medium |
| VAF-003 | Predictive Analytics Dashboard | Intelligence | Proactive decision making | Medium |
| VAF-004 | Fraud Detection Engine | Risk | 90% fraud identification | High |
| VAF-005 | Automated Compliance Checker | Compliance | 100% KRISA compliance | Low |
| VAF-006 | Chatbot Assistant | Support | 24/7 instant response | Medium |
| VAF-007 | Mobile App for Field Audits | Mobility | Real-time verification | Medium |
| VAF-008 | Blockchain Audit Trail | Security | Immutable records | High |
| VAF-009 | SP Performance Scoring | Governance | Data-driven evaluations | Low |
| VAF-010 | Geospatial Coverage Analysis | Planning | Strategic insights | Medium |

---

## 3. DETAILED FEATURE DESCRIPTIONS

### 3.1 VAF-001: AI-Powered Claim Validation

#### Description
Machine learning-based validation engine that automatically checks claim submissions for completeness, accuracy, and compliance before human review.

#### Capabilities

| Capability | Description | Accuracy |
|------------|-------------|----------|
| Smart Form Validation | Real-time field validation | 99.5% |
| Cross-Reference Check | Against historical data | 98% |
| Amount Benchmarking | Flag outliers automatically | 95% |
| Document Completeness | Verify required attachments | 97% |
| Duplicate Detection | Identify potential duplicates | 99% |

#### Business Impact

```
BEFORE AI VALIDATION:
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   SP Submits    │────▶│  Manual Check   │────▶│  Return if      │
│   Claim         │     │  (2-3 days)     │     │  Incomplete     │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                               │                        │
                               ▼                        ▼
                         ┌─────────────────┐     [Cycle repeats]
                         │  Human errors   │
                         │  missed         │
                         └─────────────────┘

WITH AI VALIDATION:
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   SP Submits    │────▶│  AI Validation  │────▶│  Instant        │
│   Claim         │     │  (Real-time)    │     │  Feedback       │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                               │                        │
                               ▼                        ▼
                         ┌─────────────────┐     Fix & Resubmit
                         │  Complete claim │     (Same session)
                         │  enters queue   │
                         └─────────────────┘
```

**Estimated Time Savings: 2-3 days per claim with issues**

---

### 3.2 VAF-002: Intelligent Document Processing (IDP)

#### Description
Advanced OCR and NLP-based document processing that automatically extracts data from uploaded documents and populates claim forms.

#### Supported Documents

| Document Type | Data Extracted | Accuracy |
|---------------|----------------|----------|
| Invoices | Amounts, dates, vendor, items | 95% |
| Receipts | Payment details, items | 92% |
| Bank Statements | Transaction history | 94% |
| Contracts | Terms, amounts, parties | 88% |
| Technical Reports | Specifications, quantities | 85% |
| Certificates | Dates, authorities, scope | 93% |

#### IDP Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│              INTELLIGENT DOCUMENT PROCESSING FLOW               │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┐    ┌──────────┐    ┌──────────┐    ┌──────────┐  │
│  │ Document │───▶│   OCR    │───▶│   NLP    │───▶│  Data    │  │
│  │  Upload  │    │  Engine  │    │  Parser  │    │ Extraction│  │
│  └──────────┘    └──────────┘    └──────────┘    └────┬─────┘  │
│                                                       │         │
│                              ┌────────────────────────┘         │
│                              ▼                                  │
│                    ┌─────────────────┐                          │
│                    │  Confidence     │                          │
│                    │  Assessment     │                          │
│                    └────────┬────────┘                          │
│                             │                                   │
│              ┌──────────────┼──────────────┐                    │
│              ▼              ▼              ▼                    │
│        ┌─────────┐    ┌─────────┐    ┌─────────┐               │
│        │ >95%    │    │ 80-95%  │    │ <80%    │               │
│        │ Auto    │    │ Review  │    │ Manual  │               │
│        │ Populate│    │ Flagged │    │ Entry   │               │
│        └─────────┘    └─────────┘    └─────────┘               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

### 3.3 VAF-003: Predictive Analytics Dashboard

#### Description
Advanced analytics platform using machine learning to predict claim volumes, processing times, budget requirements, and identify trends.

#### Predictive Models

| Model | Prediction | Data Sources | Update Frequency |
|-------|------------|--------------|------------------|
| Volume Forecaster | Monthly claim volume | 3 years historical | Weekly |
| Processing Estimator | Days to completion | Current pipeline | Daily |
| Budget Projector | Annual expenditure | Commitments + trends | Monthly |
| Risk Scorer | Claim approval likelihood | SP history + claim data | Real-time |

#### Dashboard Widgets

```
┌─────────────────────────────────────────────────────────────────┐
│              PREDICTIVE ANALYTICS DASHBOARD                     │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  NEXT QUARTER FORECAST                                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                                                         │   │
│  │  Predicted Claims: 245 (±15)                            │   │
│  │  Predicted Value: RM 45M (±3M)                          │   │
│  │  Confidence: 87%                                        │   │
│  │                                                         │   │
│  │  [Historical] [Forecast] [Confidence Interval]          │   │
│  │      │                                     ╭─╮          │   │
│  │  300 ┤                        ╭────╮      │ │          │   │
│  │  200 ┤      ╭──╮       ╭────╮│    │╭────╯ │          │   │
│  │  100 ┤╭────╯  ╰──╮╭───╯    ╰╯    ╰╯       │          │   │
│  │    0 ┼───────────┬┴───────────┬────────────┤          │   │
│  │      Q1      Q2      Q3      Q4    Q1(F)   │          │   │
│  │                                                         │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  RISK HEAT MAP                                                  │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    APPROVAL LIKELIHOOD                  │   │
│  │  SP Name        │ Q1    │ Q2    │ Q3    │ Q4    │ Score │   │
│  │  ───────────────┼───────┼───────┼───────┼───────┼───────│   │
│  │  Provider A     │ 🟢95% │ 🟢94% │ 🟢96% │ 🟢95% │ 95    │   │
│  │  Provider B     │ 🟢92% │ 🟢91% │ 🟢93% │ 🟢92% │ 92    │   │
│  │  Provider C     │ 🟡85% │ 🟡82% │ 🟢88% │ 🟡84% │ 85    │   │
│  │  Provider D     │ 🟡78% │ 🔴72% │ 🟡75% │ 🟡76% │ 75    │   │
│  │  Provider E     │ 🔴65% │ 🔴68% │ 🟡70% │ 🟡72% │ 69    │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

### 3.4 VAF-004: Fraud Detection Engine

#### Description
Advanced anomaly detection system using machine learning to identify potentially fraudulent claims based on patterns, behaviors, and cross-references.

#### Detection Capabilities

| Fraud Type | Detection Method | Alert Level |
|------------|------------------|-------------|
| Duplicate Billing | Document fingerprinting | High |
| Inflated Amounts | Statistical outlier detection | Medium |
| Fictitious Projects | Geographic verification | High |
| Shell Companies | Business registry cross-check | Critical |
| Document Forgery | Digital signature validation | Critical |
| Collusion | Network analysis | High |

#### Risk Scoring

| Score | Risk Level | Action |
|-------|------------|--------|
| 0-30 | Low | Standard processing |
| 31-60 | Medium | Enhanced review |
| 61-80 | High | Senior approval required |
| 81-100 | Critical | Investigation triggered |

---

### 3.5 VAF-005: Automated Compliance Checker

#### Description
Real-time compliance verification engine that ensures all claims and processes adhere to KRISA, financial regulations, and MCMC policies.

#### Compliance Checks

| Regulation | Check Points | Frequency |
|------------|--------------|-----------|
| KRISA | Security, audit, access controls | Continuous |
| PDPA | Data handling, consent, retention | Per transaction |
| Treasury | Payment thresholds, approval levels | Per payment |
| MCMC Policy | Eligibility, documentation | Per claim |
| Audit Requirements | Trail completeness, signatures | Continuous |

---

### 3.6 VAF-006: Chatbot Assistant

#### Description
AI-powered conversational assistant providing instant answers to common queries, claim status checks, and guided navigation.

#### Capabilities

| Function | Description | Availability |
|----------|-------------|--------------|
| Status Check | Claim status inquiry | 24/7 |
| FAQ | Policy and process questions | 24/7 |
| Form Guidance | Step-by-step assistance | 24/7 |
| Document Help | Required document list | 24/7 |
| Escalation | Handoff to human agent | Business hours |
| Multi-language | BM and English | 24/7 |

---

### 3.7 VAF-007: Mobile App for Field Audits

#### Description
Dedicated mobile application for MCMC officers to conduct on-site claim verification with offline capability and real-time sync.

#### Features

| Feature | Description | Benefit |
|---------|-------------|---------|
| Offline Mode | Work without connectivity | Remote areas |
| GPS Tagging | Auto-location capture | Verification |
| Photo Upload | Site condition documentation | Evidence |
| Digital Checklist | Structured inspection | Consistency |
| Electronic Signature | On-site approvals | Speed |
| Sync When Online | Automatic data sync | Reliability |

---

### 3.8 VAF-008: Blockchain Audit Trail

#### Description
Immutable blockchain-based audit trail for high-value claims and critical transactions, providing tamper-proof record keeping.

#### Blockchain Implementation

| Component | Technology | Purpose |
|-----------|------------|---------|
| Ledger | Hyperledger Fabric | Permissioned blockchain |
| Smart Contracts | Chaincode | Automated validation |
| Consensus | PBFT | Transaction agreement |
| Storage | IPFS | Document anchoring |

#### Use Cases

- Claims > RM 1 million
- Approval authority changes
- Policy modifications
- System configuration changes

---

### 3.9 VAF-009: SP Performance Scoring

#### Description
Comprehensive performance scoring system for Service Providers based on claim quality, timeliness, accuracy, and compliance.

#### Score Components

| Component | Weight | Metrics |
|-----------|--------|---------|
| Claim Quality | 30% | Error rate, rejection rate |
| Timeliness | 25% | Submission timing, response time |
| Documentation | 25% | Completeness, accuracy |
| Compliance | 20% | Policy adherence, audit results |

---

### 3.10 VAF-010: Geospatial Coverage Analysis

#### Description
Interactive GIS platform showing USP coverage, gaps, and infrastructure deployment across Malaysia.

#### Map Layers

| Layer | Data | Visualization |
|-------|------|---------------|
| Coverage | Served areas | Green shading |
| Claims | Project locations | Pins |
| Population | Density data | Heat map |
| Infrastructure | Towers, fiber | Icons |
| Gaps | Unserved areas | Red zones |

---

## 4. IMPLEMENTATION APPROACH

### 4.1 Phased Rollout

| Phase | Features | Timeline |
|-------|----------|----------|
| Phase 1 | VAF-001, VAF-005, VAF-006 | Month 3-6 |
| Phase 2 | VAF-002, VAF-009 | Month 6-9 |
| Phase 3 | VAF-003, VAF-010 | Month 9-12 |
| Phase 4 | VAF-004, VAF-007, VAF-008 | Month 12-15 |

### 4.2 Value Realization

| Metric | Baseline | Target (Year 1) | Target (Year 2) |
|--------|----------|-----------------|-----------------|
| Avg Processing Time | 21 days | 14 days | 10 days |
| Manual Data Entry | 100% | 60% | 30% |
| First-Time Approval | 60% | 80% | 90% |
| SP Self-Service Rate | 20% | 60% | 80% |
| Fraud Detection Rate | Reactive | 70% proactive | 90% proactive |

---

## 5. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T30-AI-ML-ARCH | AI Implementation |
| CR-002 | ANNEX-T25-DASHBOARD-DESIGNS | Analytics Dashboards |
| CR-003 | ANNEX-T31-SECURITY-FRAMEWORK | Blockchain Security |
| CR-004 | ANNEX-T27-SELF-SERVICE | Chatbot Integration |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
