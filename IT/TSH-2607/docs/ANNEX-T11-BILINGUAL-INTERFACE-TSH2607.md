# ANNEX-T11-BILINGUAL-INTERFACE-TSH2607.md

# ANNEX T11: BILINGUAL INTERFACE SAMPLES
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T11  
**Version:** 1.0  
**Date:** February 2026  

---

## 1. BILINGUAL IMPLEMENTATION APPROACH

### 1.1 Internationalization (i18n) Framework

| Component | English (EN) | Bahasa Malaysia (BM) |
|-----------|--------------|----------------------|
| UI Language Code | en-MY | ms-MY |
| Date Format | DD/MM/YYYY | DD/MM/YYYY |
| Number Format | 1,234,567.89 | 1,234,567.89 |
| Currency Format | RM 1,234,567.89 | RM 1,234,567.89 |
| Time Format | 24-hour | 24-hour |
| Text Direction | LTR | LTR |

### 1.2 Language Toggle Implementation

```
┌─────────────────────────────────────────────────────────────────┐
│  [MCMC Logo]  Dashboard    🔔  👤 User    [🌐 EN ▼]  [Logout]  │
│                                              │                  │
│                                              ▼                  │
│                                    ┌─────────────────┐          │
│                                    │  🌐 Language    │          │
│                                    │  ───────────────│          │
│                                    │  ● English      │          │
│                                    │  ○ Bahasa       │          │
│                                    │    Malaysia     │          │
│                                    └─────────────────┘          │
└─────────────────────────────────────────────────────────────────┘
```

---

## 2. INTERFACE TRANSLATION SAMPLES

### 2.1 Navigation Menu

| English | Bahasa Malaysia |
|---------|-----------------|
| Dashboard | Papan Pemuka |
| My Claims | Tuntutan Saya |
| New Claim | Tuntutan Baru |
| Master Data | Data Induk |
| Reports | Laporan |
| Settings | Tetapan |
| Logout | Log Keluar |

### 2.2 Action Buttons

| English | Bahasa Malaysia |
|---------|-----------------|
| Submit | Hantar |
| Save as Draft | Simpan sebagai Draf |
| Cancel | Batal |
| Approve | Lulus |
| Reject | Tolak |
| Return | Pulangkan |
| Download | Muat Turun |
| Upload | Muat Naik |
| View | Lihat |
| Edit | Sunting |
| Delete | Padam |
| Search | Cari |
| Filter | Tapis |
| Export | Eksport |
| Print | Cetak |

### 2.3 Form Labels

| English | Bahasa Malaysia |
|---------|-----------------|
| Project Name | Nama Projek |
| Claim Amount | Jumlah Tuntutan |
| Claim Period | Tempoh Tuntutan |
| Submission Date | Tarikh Penghantaran |
| Status | Status |
| Approved Capped Cost | Kos Siling Diluluskan |
| Remaining Balance | Baki Baki |
| Performance Bond | Bon Prestasi |
| Document Type | Jenis Dokumen |
| Description | Penerangan |

---

## 3. BILINGUAL SCREEN EXAMPLES

### 3.1 Login Screen

```
┌─────────────────────────────────────────────────────────────────┐
│                     [MCMC LOGO]                                  │
│                                                                  │
│     Universal Service Provision (USP)                            │
│     Claims Management System (UCMS)                              │
│                                                                  │
│     ┌─────────────────────────────────────────────────────┐     │
│     │                                                     │     │
│     │  🔐 LOG MASUK / LOGIN                               │     │
│     │                                                     │     │
│     │  Nama Pengguna / Username                           │     │
│     │  ┌─────────────────────────────────────────────┐    │     │
│     │  │                                             │    │     │
│     │  └─────────────────────────────────────────────┘    │     │
│     │                                                     │     │
│     │  Kata Laluan / Password                             │     │
│     │  ┌─────────────────────────────────────────────┐    │     │
│     │  │                                     [👁]    │    │     │
│     │  └─────────────────────────────────────────────┘    │     │
│     │                                                     │     │
│     │  □ Ingat Saya / Remember Me                         │     │
│     │                                                     │     │
│     │  ┌─────────────────────────────────────────────┐    │     │
│     │  │          LOG MASUK / LOGIN                  │    │     │
│     │  └─────────────────────────────────────────────┘    │     │
│     │                                                     │     │
│     │  Lupa Kata Laluan? / Forgot Password?               │     │
│     │                                                     │     │
│     └─────────────────────────────────────────────────────┘     │
│                                                                  │
│  Bahasa / Language:  [Bahasa Malaysia ▼]                         │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### 3.2 Dashboard Widgets

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Aktif Projects / Active Projects                        │    │
│  │                                                          │    │
│  │                    12                                    │    │
│  │         ┌─────────────────┐                             │    │
│  │         │   [Chart]       │                             │    │
│  │         └─────────────────┘                             │    │
│  │                                                          │    │
│  │  Lihat Semua / View All →                               │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ Tuntutan Tertunggak / Pending Claims                    │    │
│  │                                                          │    │
│  │  Draf: 2        /  Draft: 2                             │    │
│  │  Tertunggak: 5  /  Pending: 5                           │    │
│  │  Diluluskan: 45 /  Approved: 45                         │    │
│  │  Ditolak: 1     /  Rejected: 1                          │    │
│  │                                                          │    │
│  │  Lihat Semua / View All →                               │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### 3.3 Claim Form

```
┌─────────────────────────────────────────────────────────────────┐
│  TUNTUTAN BARU / NEW CLAIM                                       │
│  ═══════════════════════════                                     │
│                                                                  │
│  Maklumat Projek / Project Information                           │
│  ─────────────────────────────────                               │
│                                                                  │
│  Projek / Project *                                              │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ ▼ Pilih Projek / Select Project...                       │    │
│  │   USP-2024-001: Broadband Expansion - Klang Valley       │    │
│  │   USP-2024-002: Rural Connectivity - Sabah               │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  Jenis Tuntutan / Claim Type *                                   │
│  ┌────────────────────┐  ┌────────────────────┐                 │
│  │ ○ Suku Tahunan     │  │ ○ Tahunan          │                 │
│  │   / Quarterly      │  │   / Yearly         │                 │
│  └────────────────────┘  └────────────────────┘                 │
│                                                                  │
│  Jumlah Tuntutan (RM) / Claim Amount (RM) *                      │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │ RM [                                               ]    │    │
│  │    Baki Bajet / Budget Balance: RM 12,500,000.00        │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  Keterangan / Description *                                      │
│  ┌─────────────────────────────────────────────────────────┐    │
│  │                                                         │    │
│  │                                                         │    │
│  │                                                         │    │
│  └─────────────────────────────────────────────────────────┘    │
│                                                                  │
│  ┌────────────────────────┐  ┌────────────────────────────────┐ │
│  │  Batal / Cancel        │  │  Seterusnya / Next →           │ │
│  └────────────────────────┘  └────────────────────────────────┘ │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 4. MULTILINGUAL DATABASE DESIGN

### 4.1 Translation Table Structure

```sql
-- Table: UCMS_TRANSLATIONS
CREATE TABLE UCMS_TRANSLATIONS (
    TRANSLATION_ID VARCHAR2(50) PRIMARY KEY,
    KEY VARCHAR2(200) NOT NULL,
    LOCALE VARCHAR2(10) NOT NULL,
    VALUE VARCHAR2(4000) NOT NULL,
    CATEGORY VARCHAR2(50), -- UI, EMAIL, REPORT, etc.
    CREATED_DATE TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    MODIFIED_DATE TIMESTAMP,
    CONSTRAINT UK_TRANSLATION_KEY_LOCALE UNIQUE (KEY, LOCALE)
);

-- Sample Data
INSERT INTO UCMS_TRANSLATIONS VALUES 
('TRN-001', 'dashboard.title', 'en-MY', 'Dashboard', 'UI', SYSTIMESTAMP, NULL);
INSERT INTO UCMS_TRANSLATIONS VALUES 
('TRN-002', 'dashboard.title', 'ms-MY', 'Papan Pemuka', 'UI', SYSTIMESTAMP, NULL);
INSERT INTO UCMS_TRANSLATIONS VALUES 
('TRN-003', 'button.submit', 'en-MY', 'Submit', 'UI', SYSTIMESTAMP, NULL);
INSERT INTO UCMS_TRANSLATIONS VALUES 
('TRN-004', 'button.submit', 'ms-MY', 'Hantar', 'UI', SYSTIMESTAMP, NULL);
```

---

**END OF ANNEX T11**
