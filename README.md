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
    ├── TSH-2601/         # Tender Submission #2601
    ├── TSH-2602/         # Tender Submission #2602
    ├── TSH-2603/         # Tender Submission #2603
    ├── TSH-2604/         # Tender Submission #2604 ⭐ URGENT
    ├── TSH-2605/         # Tender Submission #2605 ⭐ URGENT
    ├── TSH-2606/         # Tender Submission #2606
    └── TSH-2607/         # Tender Submission #2607
```

## IT Tenders Summary

| ID | Tender Reference | Agency | Title | Status | Deadline | Progress |
|----|------------------|--------|-------|--------|----------|----------|
| [TSH-2601](./IT/TSH-2601/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-2602](./IT/TSH-2602/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-2603](./IT/TSH-2603/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-2604](./IT/TSH-2604/) | MMFSB/TD 01/2026 | Multimodal Freight Sdn Bhd | IT System (Business Operating & Finance) | 🔴 **URGENT** | **05 Feb 2026** | 🟠 In Progress |
| [TSH-2605](./IT/TSH-2605/) | MMFSB/TD 02/2026 | Multimodal Freight Sdn Bhd | IT System (Support System) | 🔴 **URGENT** | **05 Feb 2026** | 🟠 In Progress |
| [TSH-2606](./IT/TSH-2606/) | - | - | - | 🟡 Draft | - | 0% |
| [TSH-2607](./IT/TSH-2607/) | - | - | - | 🟡 Draft | - | 0% |

**Status Legend:**
- 🟡 Draft - Initial preparation
- 🟠 In Progress - Documents being prepared
- 🔵 Submitted - Tender submitted
- 🟢 Won - Tender awarded
- 🔴 Lost - Tender not awarded
- ⚫ Cancelled - Submission cancelled

---

## 🚨 URGENT TENDERS - Action Required

### TSH-2604: Business Operating & Finance IT System
- **Tender No:** MMFSB/TD 01/2026
- **Agency:** Multimodal Freight Sdn Bhd (MMF)
- **Deadline:** 05 February 2026 at 12:00 NOON
- **Systems:** Haulage, Forwarding, Warehouse, Terminal, Finance Management
- **Document:** [78 pages OCR'd](./IT/TSH-2604/Tender-Document.md)
- **Status:** 🔴 **URGENT** - Documents being prepared

### TSH-2605: Support IT System
- **Tender No:** MMFSB/TD 02/2026
- **Agency:** Multimodal Freight Sdn Bhd (MMF)
- **Deadline:** 05 February 2026 at 12:00 NOON
- **Systems:** Equipment Management, Procurement, HRMS
- **Document:** [60 pages OCR'd](./IT/TSH-2605/Tender-Document.md)
- **Status:** 🔴 **URGENT** - Documents being prepared

**Note:** Both tenders share the same deadline and submission location:
> Multimodal Freight Sdn Bhd (Procurement Unit)  
> No. 40, Jalan Pengacara U1/48,  
> Temasya Industrial Park, Seksyen U1,  
> 40150 Glenmarie, Shah Alam, Selangor

---

## Work Progress Overview

| Task | Status | Completion | Notes |
|------|--------|------------|-------|
| Repository Setup | ✅ Complete | 100% | Structure created |
| Tender Documentation | 🟡 In Progress | 30% | TSH-2604/2605 OCR complete |
| Company Profile Update | ⚪ Not Started | 0% | Pending |
| Certifications | ⚪ Not Started | 0% | Pending |
| Technical Proposals | ⚪ Not Started | 0% | Pending for TSH-2604/2605 |
| Price Quotations | ⚪ Not Started | 0% | Pending for TSH-2604/2605 |
| Submission Packages | ⚪ Not Started | 0% | Pending |

---

## Quick Links

### Active Tenders
- [IT/TSH-2604](./IT/TSH-2604/) - MMF Business Operating & Finance System ⭐ URGENT
- [IT/TSH-2605](./IT/TSH-2605/) - MMF Support System ⭐ URGENT

### Draft Tenders
- [IT/TSH-2601](./IT/TSH-2601/) - Tender Submission #2601
- [IT/TSH-2602](./IT/TSH-2602/) - Tender Submission #2602
- [IT/TSH-2603](./IT/TSH-2603/) - Tender Submission #2603
- [IT/TSH-2606](./IT/TSH-2606/) - Tender Submission #2606
- [IT/TSH-2607](./IT/TSH-2607/) - Tender Submission #2607

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

1. **Naming Convention:** Use TSH-26XX format (Tender Submission #26XX)
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
| 2026-01-31 | Templates added | TSH-2601 to TSH-2607 |
| 2026-01-31 | Folder structure updated | All TSH folders |
| 2026-01-31 | OCR conversion complete | TSH-2604, TSH-2605 |
| 2026-01-31 | READMEs updated with tender info | TSH-2604, TSH-2605 |

---

## Skills & Tools

This repository includes documented skills for common tasks:

- **[pdf-ocr](./skills/pdf-ocr/)** - Convert scanned PDFs to searchable markdown
- **[gog-workspace](./skills/gog-workspace/)** - Google Workspace integration (Gmail, Drive, Calendar, Sheets, Docs)

---

## Contact

For questions or updates to this repository, contact the repository maintainer.

---
*Generated: 2026-01-31*
