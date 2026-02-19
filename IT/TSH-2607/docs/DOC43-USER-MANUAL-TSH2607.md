# DOC43-USER-MANUAL-TSH2607.md
# UCMS End-User Manual
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC43-USER-MANUAL-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Project | TSH-2607 MCMC UCMS |
| Target Audience | End Users (MCMC Officers, Service Providers, Public Users) |

---

## TABLE OF CONTENTS

1. [Introduction](#1-introduction)
2. [Getting Started](#2-getting-started)
3. [User Interface Overview](#3-user-interface-overview)
4. [Authentication](#4-authentication)
5. [Applicant Management](#5-applicant-management)
6. [Claims Processing](#6-claims-processing)
7. [Document Management](#7-document-management)
8. [Reporting](#8-reporting)
9. [Notifications](#9-notifications)
10. [Troubleshooting](#10-troubleshooting)
11. [Glossary](#11-glossary)

---

## 1. INTRODUCTION

### 1.1 About This Manual

This manual provides step-by-step instructions for using the Universal Service Provision (USP) Claims Management System (UCMS). It is designed for:

- **MCMC Officers** - Process and manage USP claims
- **Service Providers** - Submit claims on behalf of beneficiaries
- **Public Users** - Check eligibility and claim status

### 1.2 System Overview

UCMS is a web-based application that streamlines the management of Universal Service Provision (USP) claims. It enables:

- Online applicant registration and verification
- Digital claim submission and processing
- Automated workflow management
- Secure document handling
- Real-time reporting and analytics

### 1.3 System Requirements

| Component | Minimum Requirement |
|-----------|-------------------|
| Web Browser | Chrome 90+, Firefox 88+, Edge 90+, Safari 14+ |
| Internet Connection | 2 Mbps or higher |
| Screen Resolution | 1366 x 768 or higher |
| PDF Viewer | Adobe Reader or equivalent |

---

## 2. GETTING STARTED

### 2.1 Accessing UCMS

1. Open your web browser
2. Navigate to: `https://ucms.mcmc.gov.my`
3. The UCMS login page will appear

### 2.2 First-Time Setup

If you are a new user:

1. Contact your system administrator for an account
2. You will receive an email with temporary credentials
3. Login and change your password immediately
4. Set up Multi-Factor Authentication (MFA)

---

## 3. USER INTERFACE OVERVIEW

### 3.1 Dashboard Layout

```
┌─────────────────────────────────────────────────────────────────┐
│  UCMS Logo    Search...              Notifications  User Menu  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┐  ┌────────────────────────────────────────────┐  │
│  │          │  │                                            │  │
│  │  MAIN    │  │              DASHBOARD                     │  │
│  │  MENU    │  │                                            │  │
│  │          │  │  ┌────────┐ ┌────────┐ ┌────────┐         │  │
│  │ Dashboard│  │  │ Widget │ │ Widget │ │ Widget │         │  │
│  │          │  │  └────────┘ └────────┘ └────────┘         │  │
│  │ Applicants│  │                                            │  │
│  │          │  │  ┌────────────────────────────────────┐   │  │
│  │ Claims   │  │  │        Recent Activity             │   │  │
│  │          │  │  └────────────────────────────────────┘   │  │
│  │ Payments │  │                                            │  │
│  │          │  └────────────────────────────────────────────┘  │
│  │ Reports  │                                                   │
│  │          │                                                   │
│  │ Admin    │                                                   │
│  │          │                                                   │
│  └──────────┘                                                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2 Main Menu Navigation

| Menu Item | Description | User Roles |
|-----------|-------------|------------|
| Dashboard | Overview and KPIs | All |
| Applicants | Manage applicant records | MCMC, Provider |
| Claims | Submit and process claims | All |
| Documents | Manage attached documents | All |
| Payments | View payment status | MCMC, Provider |
| Reports | Generate reports | MCMC |
| Administration | System configuration | Admin |

---

## 4. AUTHENTICATION

### 4.1 Logging In

1. Enter your **Username** in the first field
2. Enter your **Password** in the second field
3. Click the **Login** button
4. If MFA is enabled, enter the verification code

### 4.2 Password Requirements

Your password must meet the following criteria:

- Minimum 12 characters
- At least one uppercase letter (A-Z)
- At least one lowercase letter (a-z)
- At least one number (0-9)
- At least one special character (!@#$%^&*)
- Cannot be the same as your last 5 passwords

### 4.3 Changing Your Password

1. Click your **User Menu** (top right)
2. Select **Profile Settings**
3. Click **Change Password**
4. Enter current password
5. Enter new password (twice)
6. Click **Save**

### 4.4 Multi-Factor Authentication (MFA)

#### Setting Up MFA

1. Go to **Profile Settings**
2. Click **Security**
3. Click **Enable MFA**
4. Scan the QR code with your authenticator app
5. Enter the verification code from the app
6. Save the backup codes securely

#### Using MFA

1. Enter username and password as usual
2. When prompted, enter the 6-digit code from your authenticator app
3. Click **Verify**

### 4.5 Logging Out

1. Click your **User Menu** (top right)
2. Select **Logout**
3. Confirm if prompted

**Important:** Always log out when leaving your workstation.

---

## 5. APPLICANT MANAGEMENT

### 5.1 Registering a New Applicant (Individual)

1. Navigate to **Applicants > New Registration**
2. Select **Individual** as applicant type
3. Fill in the required fields:
   - **IC Number**: Enter 12-digit IC (system will format)
   - **Full Name**: As per IC
   - **Email**: Valid email address
   - **Mobile Number**: 10-12 digits
   - **Address**: Complete mailing address
   - **State**: Select from dropdown
   - **Postcode**: 5 digits
4. Optional fields:
   - **Date of Birth**: Auto-populated from IC
   - **Gender**: Auto-populated from IC
   - **GPS Coordinates**: Click map or enter manually
5. Click **Save**
6. System will display the new **Applicant ID**

### 5.2 Registering a New Applicant (Corporate)

1. Navigate to **Applicants > New Registration**
2. Select **Corporate** as applicant type
3. Fill in the required fields:
   - **Company Registration Number**: SSM format
   - **Company Name**: Full legal name
   - **Contact Person**: Primary contact details
   - **Business Address**: Complete address
4. Click **Verify Company** to check SSM registration
5. Complete remaining fields
6. Click **Save**

### 5.3 Searching for Applicants

1. Navigate to **Applicants > Search**
2. Enter search criteria:
   - IC Number (exact match)
   - Name (partial match)
   - Applicant ID (exact match)
   - Phone Number
3. Use **Advanced Search** for more filters:
   - State
   - Registration Date Range
   - Status
4. Click **Search**
5. Results will display in a table
6. Click on a record to view details

### 5.4 Updating Applicant Information

1. Search and open the applicant record
2. Click **Edit** (pencil icon)
3. Update the necessary fields
4. Click **Save Changes**
5. System will log the update with timestamp

### 5.5 Verifying Applicant Identity

1. Open the applicant record
2. Click **Verify Identity**
3. System will query MyIDENTITY (JPN)
4. Wait for verification result (typically 5-10 seconds)
5. Review the verification status:
   - **Verified**: Identity confirmed
   - **Failed**: Discrepancy detected
   - **Pending**: Awaiting response

### 5.6 Uploading Applicant Documents

1. Open the applicant record
2. Click the **Documents** tab
3. Click **Upload Document**
4. Select document type:
   - IC Copy
   - Proof of Income
   - Proof of Residence
   - Other
5. Click **Choose File** and select the file
6. Accepted formats: PDF, JPG, PNG (max 50MB)
7. Click **Upload**
8. Verify document appears in the list

---

## 6. CLAIMS PROCESSING

### 6.1 Creating a New Claim

1. Navigate to **Claims > New Claim**
2. **Step 1: Select Applicant**
   - Search for applicant by IC or name
   - Click to select
3. **Step 2: Select Service Provider**
   - Choose from registered providers
4. **Step 3: Select USP Scheme**
   - Select applicable scheme
   - Review scheme details displayed
5. **Step 4: Enter Claim Details**
   - Installation address
   - Service commencement date
   - Invoice details (if available)
6. **Step 5: Add Line Items**
   - Click **Add Item**
   - Select category
   - Enter description
   - Enter quantity and unit price
   - System calculates line total
   - Repeat for additional items
7. **Step 6: Upload Documents**
   - Attach supporting documents
8. **Step 7: Review and Submit**
   - Review all details
   - Check total amount
   - Click **Submit Claim**
9. System generates **Claim Reference** number

### 6.2 Checking Claim Status

1. Navigate to **Claims > My Claims** (or **All Claims** for officers)
2. View the status column:
   - **Draft** - In progress, not submitted
   - **Submitted** - Awaiting review
   - **Under Review** - Being evaluated
   - **Pending Documents** - Additional docs required
   - **Approved** - Approved for payment
   - **Rejected** - Not approved
   - **Paid** - Payment completed
   - **Cancelled** - Withdrawn
3. Click on claim reference for detailed status

### 6.3 Processing a Claim (Reviewers)

1. Navigate to **Claims > Pending Review**
2. Click on a claim to review
3. Review all sections:
   - Applicant information
   - Claim details
   - Line items and amounts
   - Attached documents
   - Eligibility check results
4. Take action:
   - **Approve**: Enter approved amount, add notes
   - **Reject**: Select reason, provide explanation
   - **Request Documents**: Specify required documents
   - **Forward**: Send to another reviewer
5. Click **Submit Decision**

### 6.4 Requesting Claim Amendments

1. Open the submitted claim
2. Click **Request Amendment**
3. Select fields that need amendment
4. Provide reason for amendment
5. Submit request
6. Await approval for amendment

### 6.5 Cancelling a Claim

**Note:** Only claims not yet paid can be cancelled.

1. Open the claim
2. Click **Cancel Claim**
3. Provide cancellation reason
4. Confirm cancellation
5. Claim status changes to **Cancelled**

---

## 7. DOCUMENT MANAGEMENT

### 7.1 Viewing Documents

1. Navigate to the relevant record (Applicant or Claim)
2. Click the **Documents** tab
3. Documents are listed with:
   - Type
   - Filename
   - Upload date
   - Size
4. Click **View** to open in browser
5. Click **Download** to save locally

### 7.2 Document Requirements

| Document Type | Format | Max Size | Required For |
|---------------|--------|----------|--------------|
| IC Copy | PDF/JPG/PNG | 10MB | All applicants |
| Proof of Income | PDF | 10MB | Income verification |
| Proof of Residence | PDF/JPG/PNG | 10MB | Address verification |
| Quotation | PDF | 10MB | Claims |
| Invoice | PDF | 10MB | Claims |
| Completion Certificate | PDF/JPG/PNG | 10MB | Claims |

---

## 8. REPORTING

### 8.1 Generating Reports

1. Navigate to **Reports > Standard Reports**
2. Select report type:
   - Claims Summary
   - Payment Summary
   - Scheme Utilization
   - Applicant Demographics
3. Set parameters:
   - Date range
   - State(s)
   - Scheme(s)
   - Status
4. Click **Generate Report**
5. View on screen or export:
   - PDF
   - Excel
   - CSV

### 8.2 Understanding Dashboard Widgets

| Widget | Description | Data Shown |
|--------|-------------|------------|
| Total Claims | Overall claim count | All-time total |
| Pending Review | Claims awaiting action | Current queue |
| Total Disbursed | Payments made | Amount & count |
| Scheme Utilization | Budget usage | By scheme |

---

## 9. NOTIFICATIONS

### 9.1 Types of Notifications

You will receive notifications for:

- Claim status changes
- Document requests
- Payment status updates
- System announcements
- Password expiry warnings

### 9.2 Viewing Notifications

1. Click the **Bell Icon** (top right)
2. Unread notifications are highlighted
3. Click a notification to view details
4. Click **Mark All Read** to clear

### 9.3 Notification Settings

1. Go to **Profile Settings > Notifications**
2. Choose channels:
   - In-app
   - Email
   - SMS
3. Select event types to receive
4. Click **Save Preferences**

---

## 10. TROUBLESHOOTING

### 10.1 Common Issues

| Issue | Solution |
|-------|----------|
| Cannot login | Check caps lock, reset password if needed |
| MFA code not working | Sync device time, use backup code |
| Page not loading | Clear browser cache, try different browser |
| Document upload fails | Check file size (<50MB) and format |
| Search returns no results | Try broader search criteria |
| Session expired | Login again, save work frequently |

### 10.2 Getting Help

| Support Channel | Contact |
|-----------------|---------|
| Help Desk | helpdesk@ucms.mcmc.gov.my |
| Phone | 03-XXXX XXXX (Business hours) |
| System Admin | admin@ucms.mcmc.gov.my |

### 10.3 Reporting Issues

1. Click **Help > Report Issue**
2. Describe the problem
3. Attach screenshots if applicable
4. Submit ticket
5. Note the ticket number for follow-up

---

## 11. GLOSSARY

| Term | Definition |
|------|------------|
| **Applicant** | Individual or entity applying for USP support |
| **B40** | Bottom 40% income group |
| **Claim** | Request for USP funding |
| **Disbursement** | Payment of approved funds |
| **GPS** | Global Positioning System coordinates |
| **IC** | Identity Card (MyKad) |
| **MFA** | Multi-Factor Authentication |
| **M40** | Middle 40% income group |
| **Rural** | Areas outside urban centers |
| **Scheme** | USP funding program |
| **SSM** | Companies Commission of Malaysia |
| **T20** | Top 20% income group |
| **USP** | Universal Service Provision |
| **USC** | Universal Service Contribution |

---

**Document Version Control**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Jan 2025 | Training Team | Initial release |

**Feedback:** Please send feedback on this manual to training@ucms.mcmc.gov.my

---

*Document Control: This manual is maintained by the UCMS Training Team. Updates are distributed to all registered users.*
