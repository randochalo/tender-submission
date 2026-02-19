# ANNEX-T18: Role-Based Access Control (RBAC) Matrix
## TSH-2607 MCMC UCMS Tender

**Document Reference:** TSH-2607-ANNEX-T18  
**Date:** February 2026  
**Version:** 1.0

---

## 1. OVERVIEW

### 1.1 Purpose
This annex defines the comprehensive Role-Based Access Control (RBAC) matrix for UCMS, specifying permissions for all internal and external users across all 10 system modules.

### 1.2 RBAC Principles

| Principle | Implementation |
|-----------|----------------|
| Least Privilege | Users receive minimum permissions required for their role |
| Segregation of Duties | Critical functions split across multiple roles |
| Role Hierarchy | Inheritance from base roles to specialized roles |
| Dynamic Permissions | Context-based access (e.g., project-specific) |
| Regular Review | Quarterly access certification |

---

## 2. ROLE DEFINITIONS

### 2.1 Internal MCMC Roles

| Role Code | Role Name | Description | User Count |
|-----------|-----------|-------------|------------|
| MC-SYS-ADM | System Administrator | Full system access, configuration | 2 |
| MC-USP-ADM | USP Administrator | USP division oversight | 3 |
| MC-FIN-MGR | Finance Manager | Financial approval authority | 5 |
| MC-FIN-ANL | Finance Analyst | Claims processing, reporting | 10 |
| MC-PM | Project Manager | Project oversight, coordination | 8 |
| MC-IT-SUP | IT Support | User support, troubleshooting | 5 |
| MC-AUDITOR | Auditor | Read-only access for audit | 4 |
| MC-VIEWER | Read-Only User | View reports and dashboards | 15 |
| MC-EXEC | Executive | Dashboard and summary access | 8 |

### 2.2 External DUSP Roles

| Role Code | Role Name | Description | User Count |
|-----------|-----------|-------------|------------|
| DS-ADMIN | DUSP Administrator | Company account management | 20 |
| DS-SUBMIT | Claim Submitter | Submit and track claims | 60 |
| DS-VIEWER | DUSP Viewer | View-only access to own data | 40 |

### 2.3 Subcontractor Roles

| Role Code | Role Name | Description | User Count |
|-----------|-----------|-------------|------------|
| SC-SUBMIT | Invoice Submitter | Submit subcontractor invoices | 15 |
| SC-VIEWER | Subcontractor Viewer | View own invoice status | 5 |

---

## 3. RBAC MATRIX BY MODULE

### 3.1 MASTER DATA MODULE

| Function | SYS-ADM | USP-ADM | FIN-MGR | FIN-ANL | PM | DUSP-ADM | DUSP-SUB | AUDIT |
|----------|:-------:|:-------:|:-------:|:-------:|:--:|:--------:|:--------:|:-----:|
| View Project Master | ✓ | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| Create Project | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Edit Project | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| View DUSP Master | ✓ | ✓ | ✓ | ✓ | ✓ | ✓** | ✗ | ✓ |
| Create DUSP Record | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| View Bond Records | ✓ | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| Create Bond Record | ✓ | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| View NOA Records | ✓ | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| Create NOA | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |

*Own projects only  
**Own company only

### 3.2 USER MANAGEMENT MODULE

| Function | SYS-ADM | USP-ADM | FIN-MGR | IT-SUP | DUSP-ADM | AUDIT |
|----------|:-------:|:-------:|:-------:|:------:|:--------:|:-----:|
| Create Internal User | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Create External User | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Modify User Roles | ✓ | ✓* | ✗ | ✗ | ✗ | ✗ |
| Reset Password | ✓ | ✗ | ✗ | ✓ | ✗ | ✗ |
| Unlock Account | ✓ | ✗ | ✗ | ✓ | ✗ | ✗ |
| Suspend User | ✓ | ✓ | ✗ | ✓ | ✗ | ✗ |
| View User Activity | ✓ | ✓ | ✗ | ✓ | ✗ | ✓ |
| Create Delegation | ✓ | ✓ | ✓ | ✗ | ✓** | ✗ |

*External users only  
**Own company users only

### 3.3 BUDGET MODULE

| Function | SYS-ADM | FIN-MGR | FIN-ANL | PM | DUSP-ADM | DUSP-VIEW | AUDIT |
|----------|:-------:|:-------:|:-------:|:--:|:--------:|:---------:|:-----:|
| View Budget | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| Create Budget | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Modify Budget | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Approve Budget | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| View Capped Cost | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| View BOQ | ✓ | ✓ | ✓ | ✓ | ✓* | ✓* | ✓ |
| Modify BOQ | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Budget Reports | ✓ | ✓ | ✓ | ✓ | ✓* | ✗ | ✓ |

*Own projects only

### 3.4 CLAIMS MODULE

| Function | SYS-ADM | FIN-MGR | FIN-ANL | PM | DUSP-SUB | DUSP-VIEW | AUDIT |
|----------|:-------:|:-------:|:-------:|:--:|:--------:|:---------:|:-----:|
| Create Claim | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ✗ |
| View Own Claims | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| View All Claims | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✓ |
| Edit Draft Claim | ✗ | ✗ | ✗ | ✗ | ✓* | ✗ | ✗ |
| Submit Claim | ✗ | ✗ | ✗ | ✗ | ✓ | ✗ | ✗ |
| Review Claim | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✓ |
| Approve Claim | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Reject Claim | ✗ | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ |
| Process Claim | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ |

*Before submission only

### 3.5 PAYMENT MODULE

| Function | SYS-ADM | FIN-MGR | FIN-ANL | PM | DUSP | AUDIT |
|----------|:-------:|:-------:|:-------:|:--:|:----:|:-----:|
| View Payment Status | ✓ | ✓ | ✓ | ✓ | ✓* | ✓ |
| Create Payment Memo | ✗ | ✓ | ✓ | ✗ | ✗ | ✗ |
| Approve Payment L1 | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Approve Payment L2 | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Approve Payment L3 | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Digital Sign Payment | ✗ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Generate Voucher | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ |
| View Payment Letter | ✓ | ✓ | ✓ | ✓ | ✓* | ✓ |

*Own payments only

### 3.6 REPORTS MODULE

| Function | SYS-ADM | FIN-MGR | FIN-ANL | PM | DUSP | EXEC | AUDIT |
|----------|:-------:|:-------:|:-------:|:--:|:----:|:----:|:-----:|
| View Standard Reports | ✓ | ✓ | ✓ | ✓ | ✓* | ✓ | ✓ |
| Generate Ad-hoc Report | ✓ | ✓ | ✓ | ✓ | ✗ | ✗ | ✓ |
| Schedule Report | ✓ | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ |
| Export Report | ✓ | ✓ | ✓ | ✓ | ✓* | ✓ | ✓ |
| Create Custom Report | ✓ | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| View Executive Dashboard | ✓ | ✓ | ✓ | ✓ | ✗ | ✓ | ✓ |
| View DUSP Reports | ✓ | ✓ | ✓ | ✓ | ✓* | ✗ | ✓ |
| View Audit Reports | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ | ✓ |

*Own organization only

### 3.7 DASHBOARD MODULE

| Function | SYS-ADM | ALL MCMC | DUSP | EXEC | AUDIT |
|----------|:-------:|:--------:|:----:|:----:|:-----:|
| View Operational Dashboard | ✓ | ✓ | ✗ | ✓ | ✓ |
| View Financial Dashboard | ✓ | ✓ | ✗ | ✓ | ✓ |
| View DUSP Dashboard | ✓ | ✓ | ✓* | ✗ | ✓ |
| View Executive Dashboard | ✓ | ✓ | ✗ | ✓ | ✓ |
| View Project Dashboard | ✓ | ✓ | ✓* | ✓ | ✓ |
| Configure Widgets | ✓ | ✗ | ✗ | ✗ | ✗ |
| Export Dashboard | ✓ | ✓ | ✓* | ✓ | ✓ |

*Own data only

### 3.8 SELF-SERVICE MODULE

| Function | SYS-ADM | DUSP-SUB | DUSP-VIEW | SC-SUBMIT | SC-VIEW |
|----------|:-------:|:--------:|:---------:|:---------:|:-------:|
| Submit Claim | ✗ | ✓ | ✗ | ✗ | ✗ |
| View Claim Status | ✓ | ✓ | ✓ | ✗ | ✗ |
| Upload Documents | ✗ | ✓ | ✗ | ✓ | ✗ |
| Track Approval | ✓ | ✓ | ✓ | ✓ | ✓ |
| Receive Notifications | ✓ | ✓ | ✓ | ✓ | ✓ |
| Submit Invoice (SC) | ✗ | ✗ | ✗ | ✓ | ✗ |
| View Invoice Status | ✗ | ✓* | ✓* | ✓ | ✓ |
| Update Profile | ✓ | ✓ | ✓ | ✗ | ✗ |

*Subcontractor invoices linked to their projects

---

## 4. PRIVILEGED OPERATIONS

### 4.1 Operations Requiring Additional Approval

| Operation | Primary Role | Secondary Approval | Digital Signature |
|-----------|--------------|-------------------|-------------------|
| Budget Transfer > RM 100K | FIN-MGR | USP-ADM | ✓ |
| Claim Reversal | FIN-MGR | Director | ✓ |
| Payment > RM 500K | FIN-MGR | 2x FIN-MGR | ✓ |
| User Role Elevation | SYS-ADM | Dept Head | ✗ |
| System Config Change | SYS-ADM | USP-ADM | ✓ |
| Data Export Bulk | SYS-ADM | Security Officer | ✗ |
| Audit Log Access | AUDITOR | Automatic | ✗ |

### 4.2 Dual Control Matrix

| Critical Function | User 1 | User 2 | User 3 |
|-------------------|--------|--------|--------|
| Payment Authorization | FIN-ANL (Prepare) | FIN-MGR (Review) | FIN-MGR (Approve) |
| Budget Release | PM (Request) | FIN-MGR (Approve) | USP-ADM (Final) |
| System Changes | SYS-ADM (Implement) | SYS-ADM (Verify) | USP-ADM (Authorize) |
| Data Migration | SYS-ADM (Execute) | PM (Validate) | USP-ADM (Approve) |

---

## 5. DATA ACCESS SCOPING

### 5.1 Organization-Based Scoping

```
┌─ DATA ACCESS HIERARCHY ───────────────────────────────────────────────────┐
│                                                                            │
│  MCMC INTERNAL USERS                                                      │
│  ├── System Administrators: All data (superuser)                         │
│  ├── USP Division: All USP project data                                  │
│  ├── Finance: All financial data across projects                         │
│  └── Project Managers: Assigned project data only                        │
│                                                                            │
│  EXTERNAL USERS (DUSP)                                                    │
│  ├── DUSP Administrator: Company-wide data                               │
│  ├── Claim Submitter: Own claims + related project data                  │
│  └── Viewer: Read-only access to own data                                │
│                                                                            │
│  SUBCONTRACTORS                                                           │
│  └── Limited to own invoices and related claim data only                 │
│                                                                            │
└────────────────────────────────────────────────────────────────────────────┘
```

### 5.2 Time-Based Restrictions

| Role | Business Hours | After Hours | Weekend |
|------|----------------|-------------|---------|
| Internal Users | Full access | Read-only | Emergency only* |
| External Users | Full access | Read-only | Read-only |
| System Admins | Full access | Full access | Full access |

*Emergency access requires manager approval

---

## 6. ACCESS REVIEW & CERTIFICATION

### 6.1 Quarterly Access Review Process

```
┌─ ACCESS CERTIFICATION WORKFLOW ───────────────────────────────────────────┐
│                                                                            │
│  Week 1: System generates access reports for all roles                   │
│  Week 2: Managers review and certify access for their team               │
│  Week 3: Security team reviews exceptions and anomalies                  │
│  Week 4: Remediation of unauthorized access, documentation               │
│                                                                            │
│  [Generate Report] → [Manager Review] → [Security Review] → [Remediate]  │
│                                                                            │
└────────────────────────────────────────────────────────────────────────────┘
```

### 6.2 Access Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Role Certification Completion | 100% | Quarterly |
| Orphaned Accounts | 0 | Monthly |
| Excessive Permissions | < 5% | Monthly |
| Privileged Access Reviews | 100% | Quarterly |
| Access Request Turnaround | < 48 hours | Ongoing |

---

## 7. KRISA COMPLIANCE MAPPING

| KRISA Requirement | RBAC Implementation |
|-------------------|---------------------|
| Access Control (8.1) | Role-based with least privilege |
| User Authentication (8.2) | MFA + SSO integration |
| Audit Logging (8.3) | All access events logged |
| Segregation of Duties (8.4) | Matrix enforces SoD |
| Access Review (8.5) | Quarterly certification process |
| Privileged Access (8.6) | Elevated role monitoring |

---

**END OF ANNEX T18**
