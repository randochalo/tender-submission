# ANNEX T3: PORTAL INTERFACE MOCKUPS
## TSH-2607: Universal Service Provision (USP) Claims Management System (UCMS)
**Document Reference:** ANNEX-T03-PORTAL-MOCKUPS-TSH2607.md  
**Version:** 1.0  
**Date:** January 2025  
**Classification:** Technical Annexure

---

## 1. INTRODUCTION

This annexure presents the portal interface mockups and user interface design specifications for the USP Claims Management System (UCMS). The designs follow modern UI/UX principles with full bilingual support (English/Bahasa Malaysia) as required by MCMC.

**Cross-References:**
- URS Section 5: User Interface Requirements
- BRS Section 4: User Experience Specifications
- SRS Section 8: UI/UX Design Standards
- SDS Section 6: Interface Design

---

## 2. DESIGN SYSTEM

### 2.1 Design Principles

| Principle | Description | Implementation |
|-----------|-------------|----------------|
| **Simplicity** | Clean, uncluttered interfaces | Minimalist design, clear hierarchy |
| **Consistency** | Uniform patterns across modules | Design system, component library |
| **Accessibility** | WCAG 2.1 AA compliance | Screen reader support, color contrast |
| **Responsiveness** | Mobile-first approach | Responsive grid, touch-friendly |
| **Bilingual** | Full EN/BM support | RTL/LTR, dynamic language switching |

### 2.2 Color Palette

| Element | Color Code | Usage |
|---------|------------|-------|
| Primary | #003366 | Headers, primary buttons, branding |
| Secondary | #0066CC | Links, secondary actions |
| Success | #28A745 | Success messages, approved status |
| Warning | #FFC107 | Warnings, pending status |
| Danger | #DC3545 | Errors, rejected status |
| Info | #17A2B8 | Informational messages |
| Background | #F5F5F5 | Page background |
| Surface | #FFFFFF | Cards, panels |
| Text Primary | #333333 | Main text |
| Text Secondary | #666666 | Secondary text |

### 2.3 Typography

| Element | Font Family | Size | Weight |
|---------|-------------|------|--------|
| H1 (Page Title) | Roboto/Open Sans | 28px | Bold (700) |
| H2 (Section) | Roboto/Open Sans | 22px | Semi-bold (600) |
| H3 (Subsection) | Roboto/Open Sans | 18px | Medium (500) |
| Body Text | Roboto/Open Sans | 14px | Regular (400) |
| Small Text | Roboto/Open Sans | 12px | Regular (400) |
| Button | Roboto/Open Sans | 14px | Medium (500) |
| Data Table | Roboto Mono | 13px | Regular (400) |

---

## 3. PORTAL MOCKUPS

### 3.1 Login Page

```
+------------------------------------------------------------------+
|                           [MCMC LOGO]                            |
|                                                                  |
|                      USP CLAIMS MANAGEMENT                       |
|                         SISTEM PENGURUSAN                        |
|                         TUNTUTAN USP                             |
|                                                                  |
|  +----------------------------------------------------------+    |
|  |                                                          |    |
|  |    [Icon] SELAMAT DATANG / WELCOME                       |    |
|  |                                                          |    |
|  |    Username / Nama Pengguna                              |    |
|  |    +------------------------------------------------+    |    |
|  |    |                                                |    |    |
|  |    +------------------------------------------------+    |    |
|  |                                                          |    |
|  |    Password / Kata Laluan                                |    |
|  |    +------------------------------------------------+    |    |
|  |    |                                                |    |    |
|  |    +------------------------------------------------+    |    |
|  |    [ ] Show Password / Tunjuk Kata Laluan                |    |
|  |                                                          |    |
|  |    [Language Toggle: EN | BM]                            |    |
|  |                                                          |    |
|  |    +------------------------------------------------+    |    |
|  |    |              LOG MASUK / LOGIN                   |    |    |
|  |    +------------------------------------------------+    |    |
|  |                                                          |    |
|  |    [Forgot Password? / Terlupa Kata Laluan?]             |    |
|  |    [Register / Daftar]                                   |    |
|  |                                                          |    |
|  +----------------------------------------------------------+    |
|                                                                  |
|  [Security Notice] [Privacy Policy] [Terms of Use]               |
|                                                                  |
|              (C) 2025 MCMC. All Rights Reserved.                 |
+------------------------------------------------------------------+
```

**Key Features:**
- Bilingual labels with language toggle
- Password visibility toggle
- Forgot password link
- New user registration link
- Security and policy links

---

### 3.2 Dashboard - Claimant View

```
+------------------------------------------------------------------+
|  [MCMC Logo]    USP CLAIMS MANAGEMENT SYSTEM          [User ▼]   |
+------------------------------------------------------------------+
|  [Dashboard] [Submit Claim] [My Claims] [Documents] [Help] [BM]  |
+------------------------------------------------------------------+
|                                                                  |
|  SELAMAT DATANG, AHMAD BIN ABDULLAH                              |
|  Welcome, your last login was 15 January 2025, 09:30 AM          |
|                                                                  |
|  +-------------------+ +-------------------+ +----------------+  |
|  |   ACTIVE CLAIMS   | |  PENDING ACTIONS  | | TOTAL CLAIMED  |  |
|  |                   | |                   | |                |  |
|  |        3          | |        2          | |   RM 150,000   |  |
|  |                   | |                   | |                |  |
|  +-------------------+ +-------------------+ +----------------+  |
|                                                                  |
|  +----------------------------------------------------------+    |
|  | CLAIM STATUS OVERVIEW / STATUS TUNTUTAN                 [v]   |
|  +----------------------------------------------------------+    |
|  |                                                              | |
|  |  [Chart: Pending: 2] [Approved: 5] [Rejected: 1] [Paid: 4]   | |
|  |                                                              | |
|  +----------------------------------------------------------+    |
|                                                                  |
|  +----------------------------------------------------------+    |
|  | RECENT CLAIMS / TUNTUTAN TERKINI                    [View All]| |
|  +----------------------------------------------------------+    |
|  | Ref No.    | Type        | Date       | Amount    | Status  | |
|  |-----------|-------------|------------|-----------|---------| |
|  | UC2025-001| Infrastructure| 10/01/2025 | RM 50,000 | Pending | |
|  | UC2025-002| Equipment   | 12/01/2025 | RM 25,000 | Approved| |
|  | UC2025-003| Training    | 14/01/2025 | RM 10,000 | Review  | |
|  +----------------------------------------------------------+    |
|                                                                  |
|  +----------------------------------------------------------+    |
|  | NOTIFICATIONS / NOTIFIKASI                            [Mark All Read]|
|  +----------------------------------------------------------+    |
|  | [!] Your claim UC2025-002 has been approved           [2h ago]| |
|  | [!] Document required for claim UC2025-001            [1d ago]| |
|  | [!] System maintenance scheduled for 20/01/2025       [2d ago]| |
|  +----------------------------------------------------------+    |
|                                                                  |
+------------------------------------------------------------------+
|  Quick Links: [User Guide] [FAQ] [Contact Support] [Feedback]    |
+------------------------------------------------------------------+
```

**Key Features:**
- Summary cards with key metrics
- Visual claim status chart
- Recent claims table with status indicators
- Notification panel
- Quick action buttons

---

### 3.3 Claim Submission Form

```
+------------------------------------------------------------------+
|  [MCMC Logo]    USP CLAIMS MANAGEMENT SYSTEM          [User ▼]   |
+------------------------------------------------------------------+
|  [Dashboard] [Submit Claim▼] [My Claims] [Documents] [Help] [BM] |
+------------------------------------------------------------------+
|                                                                  |
|  SUBMIT NEW CLAIM / TUNTUTAN BARU                                |
|                                                                  |
|  +----------------------------------------------------------+    |
|  | Step 1: Project Details | Step 2: Financial | Step 3: Docs|   |
|  | [=====================>                         ] 33%      |    |
|  +----------------------------------------------------------+    |
|                                                                  |
|  1. PROJECT INFORMATION / MAKLUMAT PROJEK                        |
|  ----------------------------------------------------------------|
|                                                                  |
|  Project Name / Nama Projek:                                     |
|  +----------------------------------------------------------------+|
|  |                                                                ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  Project Type / Jenis Projek:                                    |
|  +-------------------------------+  +---------------------------+ |
|  | Infrastructure Development ▼  |  | Sub-Type: Broadband ▼     | |
|  +-------------------------------+  +---------------------------+ |
|                                                                  |
|  Project Location / Lokasi Projek:                               |
|  +-------------------------------+  +---------------------------+ |
|  | State: Selangor ▼             |  | District: Petaling Jaya ▼ | |
|  +-------------------------------+  +---------------------------+ |
|                                                                  |
|  Project Description / Keterangan Projek:                        |
|  +----------------------------------------------------------------+|
|  |                                                                ||
|  |                                                                ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  Expected Completion / Jangka Siap:                              |
|  +-------------------------------+  +---------------------------+ |
|  | Start Date: [__/____/____] 📅 |  | End Date: [__/____/____]📅| |
|  +-------------------------------+  +---------------------------+ |
|                                                                  |
|  2. APPLICANT DETAILS / BUTIRAN PEMOHON                          |
|  ----------------------------------------------------------------|
|                                                                  |
|  Company Name / Nama Syarikat:  [Pre-filled from CIMS]           |
|  +----------------------------------------------------------------+|
|  | TELEKOM MALAYSIA BERHAD                                       ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  Registration No / No. Pendaftaran: [Pre-filled]                 |
|  Contact Person / Orang Dihubungi:                               |
|  +----------------------------------------------------------------+|
|  | AHMAD BIN ABDULLAH                                            ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  Email / Emel:                           Phone / Telefon:        |
|  +-------------------------------+  +---------------------------+ |
|  | ahmad@telekom.com.my          |  | +60 12-345 6789           | |
|  +-------------------------------+  +---------------------------+ |
|                                                                  |
|  +-------------------+  +------------------------------------+   |
|  |  SAVE AS DRAFT    |  |        CONTINUE TO FINANCIAL ▶     |   |
|  +-------------------+  +------------------------------------+   |
|                                                                  |
+------------------------------------------------------------------+
|  Need help? Contact support at usp-support@mcmc.gov.my           |
+------------------------------------------------------------------+
```

**Key Features:**
- Multi-step wizard interface
- Progress indicator
- Bilingual field labels
- Pre-filled data from CIMS integration
- Draft save functionality
- Validation indicators

---

### 3.4 Claims List View (Administrator)

```
+------------------------------------------------------------------+
|  [MCMC Logo]    USP CLAIMS MANAGEMENT SYSTEM    [Admin ▼] [🔔]   |
+------------------------------------------------------------------+
|  [Dashboard] [Claims] [Reports] [Users] [Settings] [Audit] [BM]  |
+------------------------------------------------------------------+
|                                                                  |
|  CLAIMS MANAGEMENT / PENGURUSAN TUNTUTAN                         |
|                                                                  |
|  +----------------------------------------------------------------+|
|  | 🔍 Search claims...    | Status: [All ▼] | Date: [All ▼] | [🔍]||
|  +----------------------------------------------------------------+|
|                                                                  |
|  +----------------------------------------------------------------+|
|  | Show [25 ▼] entries |                  Export [Excel ▼] | [+] ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  +----------------------------------------------------------------+|
|  | ☑ | Claim Ref | Applicant           | Type    | Amount    | Submitted  | Status    | Actions ||
|  |---|-----------|---------------------|---------|-----------|------------|-----------|---------||
|  | ☐ | UC2025-001| Telecom Malaysia Bhd| Infra   | RM 50,000 | 10/01/2025 | ⏳ Pending| [View]  ||
|  | ☐ | UC2025-002| Maxis Broadband     | Equip   | RM 25,000 | 12/01/2025 | ✅ Approve| [View]  ||
|  | ☐ | UC2025-003| Celcom Axiata       | Training| RM 10,000 | 14/01/2025 | 🔍 Review | [View]  ||
|  | ☐ | UC2025-004| Digi Telecommunications| Infra| RM 75,000 | 15/01/2025 | ⏳ Pending| [View]  ||
|  | ☐ | UC2025-005| TIME dotCom         | Equip   | RM 30,000 | 16/01/2025 | ❌ Reject | [View]  ||
|  +----------------------------------------------------------------+|
|                                                                  |
|  +----------------------------------------------------------------+|
|  | Showing 1-5 of 156 records              [< Prev] 1 2 3 ... 16 [Next >]||
|  +----------------------------------------------------------------+|
|                                                                  |
|  LEGEND: ⏳ Pending | ✅ Approved | 🔍 Under Review | ❌ Rejected | 💰 Paid |
|                                                                  |
+------------------------------------------------------------------+
```

**Key Features:**
- Advanced filtering and search
- Bulk action capability
- Export functionality
- Status color coding
- Pagination controls
- Quick action buttons

---

### 3.5 Claim Detail View

```
+------------------------------------------------------------------+
|  [MCMC Logo]    USP CLAIMS MANAGEMENT SYSTEM    [Admin ▼] [🔔]   |
+------------------------------------------------------------------+
|  [Dashboard] [Claims] [Reports] [Users] [Settings] [Audit] [BM]  |
+------------------------------------------------------------------+
|                                                                  |
|  < Back to Claims List                                           |
|                                                                  |
|  CLAIM DETAILS / BUTIRAN TUNTUTAN                                |
|  =================================================================
|  Claim Reference: UC2025-001 | Status: ⏳ PENDING                |
|  =================================================================
|                                                                  |
|  +--------------------+  +--------------------+  +---------------+|
|  | Timeline          |  | Documents         |  | Actions       ||
|  |                   |  |                   |  |               ||
|  | • Submitted       |  | 📄 Proposal.pdf   |  | [Approve]     ||
|  |   10/01 09:30 AM  |  | 📄 Budget.xlsx    |  | [Reject]      ||
|  |                   |  | 📄 CompanyReg.pdf |  | [Request Info]||
|  | ⏳ Under Review   |  | 📄 (3 files)      |  | [Assign]      ||
|  |   12/01 02:15 PM  |  |                   |  |               ||
|  |                   |  | [View All]        |  | [Add Comment] ||
|  | ○ Decision        |  |                   |  |               ||
|  |   Pending...      |  |                   |  |               ||
|  +--------------------+  +--------------------+  +---------------+|
|                                                                  |
|  +-------------------------------------------------------------+ |
|  | TABS: [Project Info] [Financial] [Documents] [History] [Audit]| |
|  +-------------------------------------------------------------+ |
|                                                                  |
|  PROJECT INFORMATION / MAKLUMAT PROJEK                           |
|  ----------------------------------------------------------------|
|  Field                        | Value                            |
|  ------------------------------|----------------------------------|
|  Project Name                  | Rural Broadband Expansion Phase 2|
|  Project Type                  | Infrastructure Development       |
|  Applicant Company             | Telecom Malaysia Berhad          |
|  Registration Number           | 198401010123 (123456-A)          |
|  Project Location              | Kampung Baru, Selangor           |
|  Expected Duration             | 01/02/2025 - 31/07/2025          |
|  Target Beneficiaries          | 2,500 households                 |
|                                                                  |
|  FINANCIAL DETAILS / BUTIRAN KEWANGAN                           |
|  ----------------------------------------------------------------|
|  Cost Component                | Amount (RM)    | Approved (RM)   |
|  ------------------------------|---------------|-----------------|
|  Equipment & Materials         | 35,000.00     | -               |
|  Installation & Labor          | 10,000.00     | -               |
|  Training & Certification      | 5,000.00      | -               |
|  ------------------------------|---------------|-----------------|
|  TOTAL                         | 50,000.00     | -               |
|                                                                  |
|  +-------------------------------------------------------------+ |
|  | APPROVER COMMENTS / KOMEN KELULUSAN                          | |
|  +-------------------------------------------------------------+ |
|  |                                                             | |
|  | Enter your comments here... / Masukkan komen di sini...     | |
|  |                                                             | |
|  +-------------------------------------------------------------+ |
|                                                                  |
+------------------------------------------------------------------+
```

---

### 3.6 Mobile Responsive View

```
+-------------------+
| [Menu] MCMC  [🔔] |
+-------------------+
|                   |
|  Welcome,         |
|  Ahmad Abdullah   |
|                   |
|  +---------------+|
|  | Active Claims ||
|  |       3       ||
|  +---------------+|
|                   |
|  MY CLAIMS        |
|  +---------------+|
|  | UC2025-001   >||
|  | Infrastructure||
|  | ⏳ Pending     ||
|  | RM 50,000     ||
|  +---------------+|
|  +---------------+|
|  | UC2025-002   >||
|  | Equipment     ||
|  | ✅ Approved   ||
|  | RM 25,000     ||
|  +---------------+|
|                   |
|  QUICK ACTIONS    |
|  +-----+ +-------+|
|  | 📝  | | 📊    ||
|  |New  | |Status ||
|  |Claim| |Chart  ||
|  +-----+ +-------+|
|                   |
|  +---------------+|
|  | Notifications ||
|  | • Doc needed  ||
|  | • Claim approv||
|  +---------------+|
|                   |
+-------------------+
|  [🏠] [📋] [👤]   |
+-------------------+
```

---

## 4. INTERFACE SPECIFICATIONS

### 4.1 Component Library

| Component | Description | States |
|-----------|-------------|--------|
| **Button** | Primary, secondary, danger variants | Default, hover, active, disabled, loading |
| **Input** | Text, number, date, textarea | Default, focus, error, disabled |
| **Select** | Dropdown with search | Default, open, selected, disabled |
| **Table** | Sortable, filterable data grid | Default, loading, empty, error |
| **Card** | Information container | Default, hover, selected |
| **Modal** | Overlay dialog | Open, closed, loading |
| **Toast** | Notification banner | Success, error, warning, info |
| **Progress** | Step indicator | Pending, active, complete |

### 4.2 Responsive Breakpoints

| Breakpoint | Width | Target Devices |
|------------|-------|----------------|
| Mobile | < 576px | Phones |
| Tablet | 576px - 991px | Tablets |
| Desktop | 992px - 1199px | Small laptops |
| Large Desktop | 1200px+ | Desktops, monitors |

---

## 5. ACCESSIBILITY FEATURES

| Feature | Implementation | WCAG Reference |
|---------|----------------|----------------|
| Color Contrast | 4.5:1 minimum ratio | 1.4.3 |
| Keyboard Navigation | Full tab navigation | 2.1.1 |
| Screen Reader | ARIA labels, roles | 4.1.2 |
| Focus Indicators | Visible focus rings | 2.4.7 |
| Alt Text | Descriptive alt attributes | 1.1.1 |
| Error Identification | Clear error messages | 3.3.1 |
| Form Labels | Associated labels | 1.3.1 |
| Resizable Text | Up to 200% zoom support | 1.4.4 |

---

## 6. DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | January 2025 | UI/UX Team | Initial version |

---

**END OF ANNEX T3**
