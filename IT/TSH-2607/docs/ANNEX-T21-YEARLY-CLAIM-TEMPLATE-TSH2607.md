# ANNEX T21: YEARLY CLAIM TEMPLATE

## TENDER REFERENCE: TSH-2607
## PROJECT: Universal Service Provision (USP) Claims Management System (UCMS)
## CLIENT: Malaysian Communications and Multimedia Commission (MCMC)
## VERSION: 1.0
## DATE: June 2025

---

## 1. PURPOSE

This annex defines the standardized Yearly Claim Template structure for the Universal Service Provision (USP) Claims Management System. The template ensures consistent data capture, processing, and reporting across all USP claim submissions by Service Providers.

### 1.1 KRISA Compliance
This template design complies with:
- **KRISA Section 8**: Data quality and standardization requirements
- **KRISA Section 12**: Electronic government service delivery standards
- **MCMC USP Guidelines**: Claim submission and validation protocols

---

## 2. TEMPLATE OVERVIEW

The Yearly Claim Template serves as the primary data collection instrument for USP service providers to report eligible infrastructure investments and operational expenditures.

### 2.1 Template Categories

| Category | Description | Claim Period |
|----------|-------------|--------------|
| CAPEX Claims | Capital expenditure for infrastructure deployment | Annual |
| OPEX Claims | Operational expenditure for service maintenance | Annual |
| Shared Infrastructure | Multi-party infrastructure investments | Annual |
| Technology Upgrade | Equipment modernization claims | Annual |

---

## 3. TEMPLATE STRUCTURE

### 3.1 Header Information

| Field | Data Type | Required | Description |
|-------|-----------|----------|-------------|
| Claim Reference Number | VARCHAR(50) | Yes | Auto-generated UCMS reference |
| Service Provider ID | VARCHAR(20) | Yes | MCMC-registered SP identifier |
| Claim Year | INTEGER | Yes | Financial year (YYYY) |
| Submission Date | DATE | Yes | Date of claim submission |
| Claim Type | ENUM | Yes | CAPEX/OPEX/Shared/Tech Upgrade |
| Total Claim Amount | DECIMAL(15,2) | Yes | Aggregated claim value (RM) |
| Contact Person | VARCHAR(100) | Yes | Primary contact for queries |
| Contact Email | VARCHAR(100) | Yes | Validated email address |
| Contact Phone | VARCHAR(20) | Yes | Including country code |

### 3.2 Project Information Section

| Field | Data Type | Required | Description |
|-------|-----------|----------|-------------|
| Project Name | VARCHAR(200) | Yes | Official project designation |
| Project Code | VARCHAR(50) | Yes | Internal SP project reference |
| Project Location | VARCHAR(500) | Yes | Full address with coordinates |
| Coverage Area | VARCHAR(100) | Yes | District/State coverage |
| Population Served | INTEGER | Yes | Estimated beneficiary count |
| Service Type | ENUM | Yes | Fixed/Mobile/Broadband/Multi |
| Technology Platform | VARCHAR(100) | Yes | Fiber/Wireless/Satellite/Hybrid |
| Commencement Date | DATE | Yes | Project start date |
| Completion Date | DATE | Yes | Actual/projected completion |

### 3.3 Financial Breakdown Section

#### 3.3.1 Capital Expenditure (CAPEX) Template

| Line Item | Category | Sub-Category | Description | Quantity | Unit Cost (RM) | Total Cost (RM) | Supporting Doc Ref |
|-----------|----------|--------------|-------------|----------|----------------|-----------------|-------------------|
| 1 | Infrastructure | Civil Works | Trenching, ducting, manholes | | | | DOC-XXX-001 |
| 2 | Infrastructure | Cable/Fiber | Optical fiber cables | | | | DOC-XXX-002 |
| 3 | Infrastructure | Equipment | Switches, routers, OLT | | | | DOC-XXX-003 |
| 4 | Infrastructure | Site Works | Tower, shelter, power | | | | DOC-XXX-004 |
| 5 | Infrastructure | Installation | Labor and commissioning | | | | DOC-XXX-005 |
| 6 | Professional | Engineering | Design and supervision | | | | DOC-XXX-006 |
| 7 | Professional | Project Mgmt | PM and documentation | | | | DOC-XXX-007 |
| 8 | Other | Contingency | Approved contingency (max 5%) | | | | DOC-XXX-008 |

#### 3.3.2 Operational Expenditure (OPEX) Template

| Line Item | Category | Description | Monthly Cost (RM) | Annual Cost (RM) | Calculation Basis |
|-----------|----------|-------------|-------------------|------------------|-------------------|
| 1 | Maintenance | Preventive maintenance | | | Per site/month |
| 2 | Maintenance | Corrective maintenance | | | Actual costs |
| 3 | Power | Electricity consumption | | | Meter readings |
| 4 | Leasing | Site/space rental | | | Lease agreements |
| 5 | Bandwidth | Backhaul connectivity | | | Service invoices |
| 6 | Insurance | Equipment insurance | | | Policy documents |
| 7 | Staff | Dedicated personnel | | | Salary allocations |
| 8 | Other | Regulatory fees | | | Fee schedules |

### 3.4 Supporting Documentation Checklist

| Document Type | Format | Required | Validation |
|---------------|--------|----------|------------|
| Project Approval Letter | PDF | Yes | MCMC verification |
| Financial Statements | PDF/Excel | Yes | Audited accounts |
| Invoices & Receipts | PDF | Yes | Sequential numbering |
| Technical Specifications | PDF | Yes | Equipment details |
| Site Photographs | JPEG/PNG | Yes | Geotagged, dated |
| Completion Certificates | PDF | Conditional | For completed projects |
| Independent Auditor Report | PDF | Yes | For claims > RM 500K |
| Bank Statements | PDF | Yes | Payment verification |

---

## 4. VALIDATION RULES

### 4.1 Data Integrity Rules

| Rule ID | Rule Description | Validation Type | Error Action |
|---------|------------------|-----------------|--------------|
| VAL-001 | Claim amount must equal sum of line items | Computational | Reject submission |
| VAL-002 | All mandatory fields must be populated | Completeness | Highlight missing |
| VAL-003 | Project dates must be within claim year | Temporal | Flag for review |
| VAL-004 | Unit costs must be within benchmark ranges | Benchmark | Trigger audit |
| VAL-005 | Supporting docs must match claim references | Cross-reference | Request correction |
| VAL-006 | SP ID must be active and valid | Authorization | Reject submission |
| VAL-007 | Duplicate claim check (Project + Year) | Uniqueness | Block submission |
| VAL-008 | Currency format must be RM (Malaysian Ringgit) | Format | Auto-format |

### 4.2 Automated Calculations

```
Total CAPEX = SUM(Line Item Total Costs)
Total OPEX = SUM(Annual Costs)
Grand Total = Total CAPEX + Total OPEX
Eligible Amount = Grand Total × Eligibility Rate (%)
GST Component = Eligible Amount × 0% (zero-rated)
Net Claim = Eligible Amount - Previous Advances
```

---

## 5. WORKFLOW INTEGRATION

### 5.1 Template Processing Flow

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  SP Submission  │────▶│  Format Check   │────▶│  Data Validation│
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                        │
        ┌───────────────────────────────────────────────┘
        ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  Auditor Review │◀────│  Eligibility    │◀────│  Doc Verification│
└─────────────────┘     └─────────────────┘     └─────────────────┘
        │
        ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  MCMC Approval  │◀────│  Recommendation │◀────│  Site Verification│
└─────────────────┘     └─────────────────┘     └─────────────────┘
        │
        ▼
┌─────────────────┐
│  Payment Release│
└─────────────────┘
```

---

## 6. SYSTEM INTEGRATION

### 6.1 Oracle ERP Integration

| Integration Point | Direction | Frequency | Data Format |
|-------------------|-----------|-----------|-------------|
| GL Account Mapping | Outbound | Real-time | Oracle API |
| Payment Processing | Outbound | Batch | Oracle Payables |
| Budget Checking | Inbound | Real-time | Oracle Budgets |
| Vendor Master | Inbound | Daily | Oracle Suppliers |

### 6.2 Digital Signature Integration

All yearly claim submissions require:
- **Service Provider Digital Signature**: PKI-compliant certificate
- **Authorized Signatory Verification**: Against MCMC registry
- **Timestamp Validation**: MSC Trustgate or equivalent

---

## 7. REPORTING OUTPUTS

### 7.1 Generated Reports

| Report Name | Frequency | Recipients | Format |
|-------------|-----------|------------|--------|
| Claim Summary by SP | Monthly | MCMC Management | PDF/Excel |
| Eligibility Analysis | Quarterly | Finance Team | Excel |
| Exception Report | Weekly | Audit Team | PDF |
| Payment Forecast | Monthly | Treasury | Excel |

---

## 8. CROSS-REFERENCES

| Reference | Document | Section |
|-----------|----------|---------|
| CR-001 | ANNEX-T22-PAYMENT-WORKFLOW | Payment Processing |
| CR-002 | ANNEX-T23-LETTER-TEMPLATES | Approval Notifications |
| CR-003 | ANNEX-T24-REPORT-CATALOG | Claim Reports |
| CR-004 | ANNEX-T26-AUDIT-TRAIL | Change Tracking |
| CR-005 | ANNEX-T35-DEPLOYMENT-PLAN | Template Rollout |

---

## 9. VERSION CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | June 2025 | UCMS Team | Initial release for TSH-2607 |

---

*This document is part of the TSH-2607 Tender Submission for MCMC USP Claims Management System*
