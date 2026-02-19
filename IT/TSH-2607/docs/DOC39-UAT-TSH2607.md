# DOC39-UAT-TSH2607.md
# User Acceptance Test (UAT) Scripts
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC39-UAT-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 UAT OVERVIEW

### 1.1 Purpose
This document contains detailed test scripts for User Acceptance Testing (UAT) of the Universal Service Provision (USP) Claims Management System (UCMS).

### 1.2 UAT Scope

| Module | Test Scenarios | Priority |
|--------|----------------|----------|
| User Authentication | 5 | High |
| Applicant Management | 8 | High |
| Claims Processing | 12 | High |
| Payment Processing | 6 | High |
| Document Management | 5 | Medium |
| Reporting | 6 | Medium |
| Administration | 8 | Medium |
| System Configuration | 4 | Low |

### 1.3 UAT Environment

| Parameter | Value |
|-----------|-------|
| UAT URL | https://uat-ucms.mcmc.gov.my |
| Database | UAT_DB |
| Test Data | Sanitized production-like data |
| User Accounts | Test accounts provided |
| Support Contact | [Contact details] |

---

## 2.0 TEST SCRIPT TEMPLATE

Each test script follows this format:

```
TEST SCRIPT: [TC-XXX]
-------------------
Module: [Module Name]
Feature: [Feature Name]
Priority: [High/Medium/Low]
Preconditions: [Required setup]

Test Steps:
1. [Step 1]
2. [Step 2]
...

Expected Result: [What should happen]
Actual Result: [To be filled during testing]
Status: [Pass/Fail/Blocked]
Tester: [Name]
Date: [Date]
Notes: [Any observations]
```

---

## 3.0 AUTHENTICATION & ACCESS CONTROL TESTS

### TC-AUTH-001: Successful Login
**Module:** Authentication | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to UCMS login page | Login page displayed |
| 2 | Enter valid username | Username accepted |
| 3 | Enter valid password | Password masked |
| 4 | Click "Login" button | User logged in, dashboard displayed |
| 5 | Verify welcome message | User name displayed |

**Test Data:**
- Username: test.mcmc.officer
- Password: [Test password]

---

### TC-AUTH-002: Invalid Login Credentials
**Module:** Authentication | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to login page | Login page displayed |
| 2 | Enter invalid username | Username accepted |
| 3 | Enter invalid password | Password masked |
| 4 | Click "Login" button | Error message: "Invalid credentials" |
| 5 | Verify still on login page | Login form displayed |

---

### TC-AUTH-003: Password Reset
**Module:** Authentication | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to login page | Login page displayed |
| 2 | Click "Forgot Password" | Password reset form displayed |
| 3 | Enter registered email | Email accepted |
| 4 | Click "Send Reset Link" | Success message displayed |
| 5 | Check email | Reset link received within 5 minutes |
| 6 | Click reset link | Password reset form displayed |
| 7 | Enter new password (meeting policy) | Password accepted |
| 8 | Confirm new password | Password accepted |
| 9 | Click "Reset Password" | Success message, redirect to login |

---

### TC-AUTH-004: Multi-Factor Authentication
**Module:** Authentication | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Login with valid credentials | MFA prompt displayed |
| 2 | Select MFA method (TOTP/SMS) | Selected method activated |
| 3 | Enter valid MFA code | User logged in successfully |
| 4 | Verify session active | Dashboard accessible |

---

### TC-AUTH-005: Session Timeout
**Module:** Authentication | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Login successfully | Dashboard displayed |
| 2 | Leave session idle for 30 minutes | Timeout warning at 25 minutes |
| 3 | Do not respond | Session terminated, redirect to login |
| 4 | Attempt to navigate | Login page displayed |

---

## 4.0 APPLICANT MANAGEMENT TESTS

### TC-APP-001: Register New Applicant (Individual)
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Applicants > New | Registration form displayed |
| 2 | Select "Individual" type | Individual fields displayed |
| 3 | Enter valid IC number: 900101-01-1234 | Format validated |
| 4 | Enter full name: Ahmad bin Abdullah | Name accepted |
| 5 | Enter email: ahmad@email.com | Format validated |
| 6 | Enter mobile: 012-3456789 | Format validated |
| 7 | Enter address details | All fields accepted |
| 8 | Select state: Johor | State selected |
| 9 | Enter postcode: 81000 | Postcode validated |
| 10 | Click "Save" | Success message, applicant created |
| 11 | Verify applicant ID generated | ID format: APP-XXXXX |

---

### TC-APP-002: Register New Applicant (Corporate)
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Applicants > New | Registration form displayed |
| 2 | Select "Corporate" type | Company fields displayed |
| 3 | Enter company registration: 1234567-A | Format validated |
| 4 | Enter company name | Name accepted |
| 5 | Enter contact person details | Fields accepted |
| 6 | Enter business address | Address accepted |
| 7 | Click "Save" | Success message, applicant created |
| 8 | Verify company verified against SSM | Verification status shown |

---

### TC-APP-003: Search Applicant
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Applicants > Search | Search form displayed |
| 2 | Enter IC number: 900101-01-1234 | IC entered |
| 3 | Click "Search" | Matching applicant(s) displayed |
| 4 | Verify result accuracy | Correct applicant shown |
| 5 | Try partial name search: "Ahmad" | All matching records displayed |
| 6 | Apply state filter: Johor | Results filtered correctly |

---

### TC-APP-004: Update Applicant Details
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Search and open applicant record | Applicant details displayed |
| 2 | Click "Edit" | Edit mode activated |
| 3 | Update mobile number | New number accepted |
| 4 | Update address | New address accepted |
| 5 | Click "Save" | Success message displayed |
| 6 | Verify changes persisted | Updated details shown |
| 7 | Check audit log | Update recorded with timestamp |

---

### TC-APP-005: Verify Applicant Identity (MyIDENTITY)
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open applicant record | Details displayed |
| 2 | Click "Verify Identity" | Verification initiated |
| 3 | System queries MyIDENTITY | Loading indicator shown |
| 4 | Wait for response | Verification result displayed |
| 5 | If successful | Status: "Verified", details populated |
| 6 | If failed | Status: "Verification Failed", reason shown |

---

### TC-APP-006: Upload Applicant Documents
**Module:** Applicant Management | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open applicant record | Details displayed |
| 2 | Navigate to Documents tab | Document section displayed |
| 3 | Click "Upload Document" | Upload dialog displayed |
| 4 | Select document type: IC Copy | Type selected |
| 5 | Select file (PDF, < 10MB) | File selected |
| 6 | Click "Upload" | Upload progress shown |
| 7 | Verify upload complete | Document listed with metadata |
| 8 | Try upload oversized file | Error: "File exceeds 50MB limit" |
| 9 | Try upload invalid type | Error: "Invalid file type" |

---

### TC-APP-007: Applicant Eligibility Check
**Module:** Applicant Management | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open applicant record | Details displayed |
| 2 | Click "Check Eligibility" | Eligibility screen displayed |
| 3 | Select scheme to check | Scheme selected |
| 4 | Click "Run Check" | Eligibility calculated |
| 5 | Review eligibility criteria | All criteria shown with status |
| 6 | Verify result | Eligible/Not Eligible displayed |
| 7 | View detailed explanation | Criteria-by-criteria breakdown shown |

---

### TC-APP-008: Deactivate Applicant
**Module:** Applicant Management | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Search and open applicant | Details displayed |
| 2 | Click "Deactivate" | Confirmation dialog displayed |
| 3 | Enter reason for deactivation | Reason captured |
| 4 | Confirm deactivation | Success message, status changed |
| 5 | Verify applicant inactive | Status: "Inactive" |
| 6 | Try create claim for inactive | Error: "Applicant is inactive" |

---

## 5.0 CLAIMS PROCESSING TESTS

### TC-CLM-001: Create New Claim
**Module:** Claims Processing | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Claims > New | Claim creation wizard started |
| 2 | Select applicant (search) | Applicant selected and displayed |
| 3 | Select service provider | Provider list displayed, select one |
| 4 | Select USP scheme | Scheme selected |
| 5 | Enter claim details | All required fields completed |
| 6 | Add line items | Items added with quantities/prices |
| 7 | Verify calculations | Totals calculated correctly |
| 8 | Upload supporting documents | Documents attached |
| 9 | Review and submit | Summary displayed |
| 10 | Click "Submit Claim" | Success message, claim reference generated |
| 11 | Verify claim status | Status: "Submitted" |

---

### TC-CLM-002: Review and Approve Claim
**Module:** Claims Processing | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Login as reviewer | Dashboard displayed |
| 2 | View pending claims queue | Claims awaiting review listed |
| 3 | Open claim for review | Claim details displayed |
| 4 | Review applicant information | Information displayed |
| 5 | Review claim details | Line items, amounts displayed |
| 6 | Review attached documents | Documents viewable |
| 7 | Verify eligibility | Eligibility status displayed |
| 8 | Click "Approve" | Approval dialog displayed |
| 9 | Enter approved amount | Amount entered |
| 10 | Add approval notes | Notes entered |
| 11 | Confirm approval | Success message, status: "Approved" |
| 12 | Verify workflow updated | Audit trail shows approval |

---

### TC-CLM-003: Reject Claim
**Module:** Claims Processing | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open claim for review | Claim details displayed |
| 2 | Review claim details | Assessment complete |
| 3 | Click "Reject" | Rejection dialog displayed |
| 4 | Select rejection reason | Reason selected from dropdown |
| 5 | Enter detailed explanation | Explanation provided |
| 6 | Confirm rejection | Success message, status: "Rejected" |
| 7 | Verify notification sent | Email/SMS notification logged |
| 8 | Check applicant notification | Notification content correct |

---

### TC-CLM-004: Request Additional Documents
**Module:** Claims Processing | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open claim requiring documents | Claim details displayed |
| 2 | Click "Request Documents" | Request form displayed |
| 3 | Select required document types | Types selected |
| 4 | Enter specific requirements | Details entered |
| 5 | Set deadline for submission | Date selected |
| 6 | Send request | Success message, status: "Pending Documents" |
| 7 | Verify notification to applicant | Notification sent |

---

### TC-CLM-005: Process Payment for Approved Claim
**Module:** Claims Processing | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to approved claims | Approved claims list displayed |
| 2 | Select claim for payment | Claim details displayed |
| 3 | Click "Process Payment" | Payment form displayed |
| 4 | Verify payment details | Amount, payee information correct |
| 5 | Select payment method | Method selected |
| 6 | Verify bank account details | Account details displayed |
| 7 | Enter payment reference | Reference entered |
| 8 | Submit for authorization | Sent to approver |
| 9 | Login as payment approver | Payment in approval queue |
| 10 | Review and authorize | Payment status: "Authorized" |
| 11 | Execute payment | Payment processed |
| 12 | Verify status | Claim status: "Paid" |

---

### TC-CLM-006: Search and Filter Claims
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Claims > Search | Search interface displayed |
| 2 | Search by claim reference | Specific claim found |
| 3 | Search by applicant name | Matching claims displayed |
| 4 | Filter by status | Only selected status shown |
| 5 | Filter by date range | Claims within range displayed |
| 6 | Filter by scheme | Only selected scheme shown |
| 7 | Combine filters | Correctly filtered results |
| 8 | Export results | Export file generated |

---

### TC-CLM-007: Claim Status Tracking
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open claim record | Details displayed |
| 2 | Navigate to Status/History tab | Timeline displayed |
| 3 | Review status history | All status changes shown |
| 4 | View action details | Who, when, what for each action |
| 5 | Check current status | Current status highlighted |
| 6 | View estimated completion | ETA displayed if applicable |

---

### TC-CLM-008: Bulk Claim Operations
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to claims list | Claims displayed |
| 2 | Select multiple claims (checkbox) | Claims selected |
| 3 | Select bulk action: Export | Export options displayed |
| 4 | Export selected claims | Export file generated |
| 5 | Select claims and action: Assign | Assign dialog displayed |
| 6 | Select assignee | Reviewer selected |
| 7 | Confirm assignment | Claims assigned to reviewer |

---

### TC-CLM-009: Claim Amendment Request
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open submitted claim | Details displayed |
| 2 | Click "Request Amendment" | Amendment form displayed |
| 3 | Select fields to amend | Fields marked for amendment |
| 4 | Enter new values | New values entered |
| 5 | Provide reason for amendment | Reason entered |
| 6 | Submit amendment request | Request submitted |
| 7 | Verify approval workflow | Sent for approval |
| 8 | Upon approval | Claim updated with new values |

---

### TC-CLM-010: Cancel Claim
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open claim (not yet paid) | Details displayed |
| 2 | Click "Cancel Claim" | Confirmation dialog displayed |
| 3 | Enter cancellation reason | Reason entered |
| 4 | Confirm cancellation | Success message, status: "Cancelled" |
| 5 | Verify workflow terminated | No further actions possible |
| 6 | Check audit trail | Cancellation logged |

---

### TC-CLM-011: Process Claim Appeal
**Module:** Claims Processing | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open rejected claim | Details displayed |
| 2 | Click "File Appeal" | Appeal form displayed |
| 3 | Enter grounds for appeal | Explanation provided |
| 4 | Upload supporting documents | Documents attached |
| 5 | Submit appeal | Success message, status: "Under Appeal" |
| 6 | Verify assignment | Assigned to appeal officer |
| 7 | Review appeal decision | Decision recorded |

---

### TC-CLM-012: Generate Claim Certificate
**Module:** Claims Processing | **Priority:** Low

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Open approved/paid claim | Details displayed |
| 2 | Click "Generate Certificate" | Certificate options displayed |
| 3 | Select certificate type | Type selected |
| 4 | Preview certificate | Certificate preview displayed |
| 5 | Download/Print certificate | Certificate generated in PDF |
| 6 | Verify certificate details | All details accurate |

---

## 6.0 REPORTING TESTS

### TC-RPT-001: Generate Claims Summary Report
**Module:** Reporting | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Reports > Claims | Report interface displayed |
| 2 | Select "Claims Summary" | Parameters displayed |
| 3 | Set date range | Dates entered |
| 4 | Select group by: State | Grouping selected |
| 5 | Click "Generate" | Report generated |
| 6 | Verify data accuracy | Numbers match database |
| 7 | Export to Excel | Excel file downloaded |
| 8 | Export to PDF | PDF file downloaded |

---

### TC-RPT-002: Generate Payment Report
**Module:** Reporting | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Reports > Payments | Payment reports listed |
| 2 | Select "Payment Summary" | Parameters displayed |
| 3 | Select month/year | Period selected |
| 4 | Click "Generate" | Report generated |
| 5 | Verify totals | Totals match payment records |
| 6 | Drill down to details | Detailed view accessible |

---

### TC-RPT-003: Dashboard Widgets
**Module:** Reporting | **Priority:** Medium

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Login and view dashboard | Dashboard displayed |
| 2 | Verify claim count widget | Current count displayed |
| 3 | Verify pending approvals widget | Count and list displayed |
| 4 | Verify payment status widget | Status summary displayed |
| 5 | Click widget for details | Drill-down report displayed |
| 6 | Refresh dashboard | Data updated |

---

## 7.0 ADMINISTRATION TESTS

### TC-ADM-001: Create New User
**Module:** Administration | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Admin > Users | User management displayed |
| 2 | Click "New User" | User creation form displayed |
| 3 | Enter user details | All fields completed |
| 4 | Select role | Role assigned |
| 5 | Set initial password | Password set |
| 6 | Click "Create" | Success message, user created |
| 7 | Verify email notification | Welcome email sent |

---

### TC-ADM-002: Configure USP Scheme
**Module:** Administration | **Priority:** High

| # | Step | Expected Result |
|---|------|-----------------|
| 1 | Navigate to Admin > Schemes | Schemes list displayed |
| 2 | Click "New Scheme" | Scheme form displayed |
| 3 | Enter scheme details | Name, description, period |
| 4 | Set eligibility criteria | Income limits, target group |
| 5 | Set funding parameters | Max claim, percentage |
| 6 | Set geographic scope | States/areas selected |
| 7 | Save scheme | Scheme created and active |

---

## 8.0 UAT EXECUTION SUMMARY

### Test Execution Tracker

| Test ID | Description | Tester | Date | Status | Defect ID |
|---------|-------------|--------|------|--------|-----------|
| TC-AUTH-001 | Successful Login | | | □ Pass □ Fail □ Blocked | |
| TC-AUTH-002 | Invalid Credentials | | | □ Pass □ Fail □ Blocked | |
| ... | ... | | | | |

### Summary Statistics

| Category | Total | Passed | Failed | Blocked | Pass Rate |
|----------|-------|--------|--------|---------|-----------|
| Authentication | 5 | | | | |
| Applicant Mgmt | 8 | | | | |
| Claims Processing | 12 | | | | |
| Payment Processing | 6 | | | | |
| Document Mgmt | 5 | | | | |
| Reporting | 6 | | | | |
| Administration | 8 | | | | |
| **TOTAL** | **50** | | | | |

---

**Document Control:** Original - Project Office | Copy - QA Team | Copy - Business Team
