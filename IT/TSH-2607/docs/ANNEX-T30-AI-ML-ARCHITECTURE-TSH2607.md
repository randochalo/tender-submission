# ANNEX-T30-AI-ML-ARCHITECTURE-TSH2607.md

# ANNEX T30: AI/ML ARCHITECTURE
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T30  
**Version:** 1.0  
**Date:** February 2026  

---

## AI/ML COMPONENTS

### Document Intelligence

| Capability | Technology | Accuracy Target |
|------------|------------|-----------------|
| Document Classification | Deep Learning (CNN) | 95% |
| OCR Text Extraction | Tesseract/AWS Textract | 90% |
| Handwriting Recognition | Custom Model | 85% |
| Table Extraction | LayoutLM | 92% |

### Fraud Detection

| Detection Type | Method | Threshold |
|---------------|--------|-----------|
| Duplicate Documents | Image Hashing | 90% similarity |
| Altered Documents | Metadata Analysis | Auto-flag |
| Anomalous Claims | Statistical Analysis | 2 std dev |
| Pattern Recognition | ML Classification | 85% confidence |

### Architecture

```
Documents ──► OCR Engine ──► NLP Processing ──► Classification
                                │
                                ▼
                         Fraud Detection ──► Risk Score
                                │
                                ▼
                         Human Review Queue (if needed)
```

---

**END OF ANNEX T30**
