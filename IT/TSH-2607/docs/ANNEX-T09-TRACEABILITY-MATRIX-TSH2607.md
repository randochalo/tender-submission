# ANNEX-T09-TRACEABILITY-MATRIX-TSH2607.md

# ANNEX T9: REQUIREMENTS TRACEABILITY MATRIX
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)  
**Annex ID:** T9  
**Version:** 1.0  
**Date:** February 2026  

---

## TRACEABILITY MATRIX OVERVIEW

The Requirements Traceability Matrix (RTM) establishes bidirectional traceability between:
- Tender Requirements → User Requirements
- User Requirements → System Requirements  
- System Requirements → Design Components
- Design Components → Test Cases
- Test Cases → Test Results

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                    TRACEABILITY CHAIN                                                    │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│  TENDER ──► URS ──► SRS ──► SDS ──► CODE ──► TEST CASE ──► TEST RESULT                 │
│    │        │       │       │       │         │             │                          │
│    │        │       │       │       │         │             │                          │
│    └────────┴───────┴───────┴───────┴─────────┴─────────────┘                          │
│                              RTM COVERAGE                                              │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## SAMPLE TRACEABILITY MATRIX

| Req ID | Tender Ref | URS Ref | SRS Ref | SDS Ref | Design Component | Test Case | Status |
|--------|-----------|---------|---------|---------|------------------|-----------|--------|
| REQ-001 | Sec 41.1.3.1.a | URS-MD-001 | SRS-MD-001 | SDS-MD-001 | ProjectService.java | TC-MD-001 | Implemented |
| REQ-002 | Sec 41.1.3.1.b | URS-MD-002 | SRS-MD-002 | SDS-MD-002 | NOAService.java | TC-MD-002 | Implemented |
| REQ-003 | Sec 41.1.3.1.c | URS-MD-003 | SRS-MD-003 | SDS-MD-003 | VOService.java | TC-MD-003 | Implemented |
| REQ-004 | Sec 41.1.3.2.a | URS-UM-001 | SRS-UM-001 | SDS-UM-001 | UserController.java | TC-UM-001 | Implemented |
| REQ-005 | Sec 41.1.3.3.a | URS-BG-001 | SRS-BG-001 | SDS-BG-001 | BudgetService.java | TC-BG-001 | Implemented |
| REQ-006 | Sec 41.1.3.4.a | URS-CL-001 | SRS-CL-001 | SDS-CL-001 | ClaimService.java | TC-CL-001 | Implemented |
| REQ-007 | Sec 41.1.3.5.a | URS-PY-001 | SRS-PY-001 | SDS-PY-001 | PaymentService.java | TC-PY-001 | Implemented |
| REQ-008 | Sec 41.1.3.6.a | URS-RP-001 | SRS-RP-001 | SDS-RP-001 | ReportService.java | TC-RP-001 | Implemented |
| REQ-009 | Sec 41.1.3.7.a | URS-DB-001 | SRS-DB-001 | SDS-DB-001 | DashboardController.java | TC-DB-001 | Implemented |
| REQ-010 | Sec 41.1.3.8.a | URS-AU-001 | SRS-AU-001 | SDS-AU-001 | AuditService.java | TC-AU-001 | Implemented |
| REQ-011 | Sec 41.1.3.9.a | URS-SS-001 | SRS-SS-001 | SDS-SS-001 | PortalController.java | TC-SS-001 | Implemented |
| REQ-012 | Sec 41.1.3.10.a | URS-VA-001 | SRS-VA-001 | SDS-VA-001 | AIEngine.java | TC-VA-001 | In Progress |
| REQ-013 | Sec 41.1.4 | URS-INT-001 | SRS-INT-001 | SDS-INT-001 | USPFSAdapter.java | TC-INT-001 | Implemented |
| REQ-014 | Sec 41.1.5 | URS-AI-001 | SRS-AI-001 | SDS-AI-001 | OCREngine.java | TC-AI-001 | In Progress |
| REQ-015 | Sec 41.1.6 | URS-SEC-001 | SRS-SEC-001 | SDS-SEC-001 | SecurityConfig.java | TC-SEC-001 | Implemented |

---

## DETAILED TRACEABILITY BY MODULE

### Module: Master Data (MD)

| Req ID | Description | URS | SRS | Design | Test Case | Status |
|--------|-------------|-----|-----|--------|-----------|--------|
| REQ-MD-001 | Project ID creation | URS-MD-001 | SRS-MD-001 | ProjectEntity, ProjectService | TC-MD-001 | Done |
| REQ-MD-002 | NOA recording | URS-MD-002 | SRS-MD-002 | NOAEntity, NOAService | TC-MD-002 | Done |
| REQ-MD-003 | VO management | URS-MD-003 | SRS-MD-003 | VOEntity, VOService | TC-MD-003 | Done |
| REQ-MD-004 | EOT processing | URS-MD-004 | SRS-MD-004 | EOTEntity, EOTService | TC-MD-004 | Done |
| REQ-MD-005 | Bond management | URS-MD-005 | SRS-MD-005 | BondEntity, BondService | TC-MD-005 | Done |

### Module: Claims (CL)

| Req ID | Description | URS | SRS | Design | Test Case | Status |
|--------|-------------|-----|-----|--------|-----------|--------|
| REQ-CL-001 | Advance claim submission | URS-CL-001 | SRS-CL-001 | ClaimEntity, ClaimService | TC-CL-001 | Done |
| REQ-CL-002 | Quarterly claim submission | URS-CL-002 | SRS-CL-002 | ClaimService.submitQuarterly() | TC-CL-002 | Done |
| REQ-CL-003 | Yearly claim submission | URS-CL-003 | SRS-CL-003 | ClaimService.submitYearly() | TC-CL-003 | Done |
| REQ-CL-004 | Document upload | URS-CL-004 | SRS-CL-004 | DocumentService | TC-CL-004 | Done |
| REQ-CL-005 | CEO declaration | URS-CL-005 | SRS-CL-005 | DeclarationService | TC-CL-005 | Done |

### Module: Payment (PY)

| Req ID | Description | URS | SRS | Design | Test Case | Status |
|--------|-------------|-----|-----|--------|-----------|--------|
| REQ-PY-001 | Memo generation | URS-PY-001 | SRS-PY-001 | MemoService | TC-PY-001 | Done |
| REQ-PY-002 | Multi-level approval | URS-PY-002 | SRS-PY-002 | ApprovalWorkflow | TC-PY-002 | Done |
| REQ-PY-003 | Digital signature | URS-PY-003 | SRS-PY-003 | DigitalSignatureService | TC-PY-003 | Done |
| REQ-PY-004 | Voucher creation | URS-PY-004 | SRS-PY-004 | USPFSIntegration | TC-PY-004 | Done |
| REQ-PY-005 | DUSP letter generation | URS-PY-005 | SRS-PY-005 | LetterService | TC-PY-005 | Done |

---

## TRACEABILITY METRICS

| Metric | Target | Current |
|--------|--------|---------|
| Forward Traceability | 100% | 100% |
| Backward Traceability | 100% | 100% |
| Bi-directional Coverage | 100% | 100% |
| Test Coverage | 100% | 85% |
| Requirements Changes | <5% | 2% |

---

**END OF ANNEX T9**
