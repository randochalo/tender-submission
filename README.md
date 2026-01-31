# Tender Submission Repository

**Repository:** tender-submission  
**Purpose:** Centralized tracking and management of tender submissions  
**Last Updated:** 2026-01-31

---

## Overview

This repository contains all tender submission documents, organized by category and submission ID.

## Structure

```
tender-submission/
├── README.md              # This file - main navigation
└── IT/                    # IT-related tenders
    ├── TSH-001/          # Tender Submission #001
    │   ├── README.md     # Tender details and progress
    │   ├── documents/    # Official tender documents
    │   ├── quotations/   # Price quotations and BOQ
    │   ├── technical/    # Technical proposals and specs
    │   ├── company/      # Company profile and certifications
    │   └── submission/   # Final submission package
    ├── TSH-002/          # Tender Submission #002
    ├── TSH-003/          # Tender Submission #003
    ├── TSH-004/          # Tender Submission #004
    └── TSH-005/          # Tender Submission #005
```

## IT Tenders Summary

| ID | Tender Reference | Agency | Title | Status | Deadline | Progress |
|----|------------------|--------|-------|--------|----------|----------|
| [TSH-001](./IT/TSH-001/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-002](./IT/TSH-002/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-003](./IT/TSH-003/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-004](./IT/TSH-004/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-005](./IT/TSH-005/) | - | - | - | 🟡 Draft | - | 0% |

**Status Legend:**
- 🟡 Draft - Initial preparation
- 🟠 In Progress - Documents being prepared
- 🔵 Submitted - Tender submitted
- 🟢 Won - Tender awarded
- 🔴 Lost - Tender not awarded
- ⚫ Cancelled - Submission cancelled

---

## Work Progress Overview

| Task | Status | Completion | Notes |
|------|--------|------------|-------|
| Repository Setup | ✅ Complete | 100% | Structure created |
| Tender Documentation | 🟡 In Progress | 20% | Templates ready |
| Company Profile Update | ⚪ Not Started | 0% | Pending |
| Certifications | ⚪ Not Started | 0% | Pending |
| Technical Proposals | ⚪ Not Started | 0% | Pending |
| Price Quotations | ⚪ Not Started | 0% | Pending |
| Submission Packages | ⚪ Not Started | 0% | Pending |

---

## Quick Links

- [IT/TSH-001](./IT/TSH-001/) - Tender Submission #001
- [IT/TSH-002](./IT/TSH-002/) - Tender Submission #002
- [IT/TSH-003](./IT/TSH-003/) - Tender Submission #003
- [IT/TSH-004](./IT/TSH-004/) - Tender Submission #004
- [IT/TSH-005](./IT/TSH-005/) - Tender Submission #005

---

## How to Use

### Adding a New Tender

1. Create a new folder under the appropriate category (e.g., `IT/TSH-XXX/`)
2. Use the next available number in sequence
3. Create a `README.md` inside the folder with tender details
4. Add documents to the appropriate subfolders:
   - `documents/` - Official tender notice, addendums
   - `quotations/` - Price quotations, BOQ, financial proposals
   - `technical/` - Technical specifications, drawings, proposals
   - `company/` - Company profile, certifications, financial statements
   - `submission/` - Final compiled submission package
5. Update this README.md with the new tender information

### Folder Structure per Tender

Each TSH-XXX folder contains:

```
TSH-XXX/
├── README.md           # Tender details, checklist, progress
├── documents/          # Official tender documents
│   └── .gitkeep
├── quotations/         # Price quotations and BOQ
│   └── .gitkeep
├── technical/          # Technical proposals and specs
│   └── .gitkeep
├── company/            # Company profile and certifications
│   └── .gitkeep
└── submission/         # Final submission documents
    └── .gitkeep
```

---

## Guidelines

1. **Naming Convention:** Use TSH-XXX format (Tender Submission #XXX)
2. **Documentation:** Always include a README.md in each submission folder
3. **File Organization:** Store documents in the appropriate subfolder:
   - Official documents → `documents/`
   - Pricing/BOQ → `quotations/`
   - Technical specs → `technical/`
   - Company info → `company/`
   - Final package → `submission/`
4. **Version Control:** Use Git commits to track changes
5. **Confidentiality:** Do not commit sensitive pricing in plain text (use password-protected PDFs)

---

## Recent Activity

| Date | Action | Tender ID |
|------|--------|-----------|
| 2026-01-31 | Repository created | - |
| 2026-01-31 | Templates added | TSH-001 to TSH-005 |
| 2026-01-31 | Folder structure updated | All TSH folders |

---

## Contact

For questions or updates to this repository, contact the repository maintainer.

---
*Generated: 2026-01-31*
