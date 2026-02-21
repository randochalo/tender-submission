# JADUAL KERJA / WORK SCHEDULE
## TSH-2613: Sistem Pengurusan Mesyuarat
### UMPSA/BEND/SH/2026(2)

---

## 1. MAKLUMAT PROJEK

| Item | Maklumat |
|------|----------|
| **Nama Projek** | Sistem Pengurusan Mesyuarat |
| **Tender** | UMPSA/BEND/SH/2026(2) |
| **Jabatan** | DiTec (Pusat Teknologi Digital) |
| **Tempoh Projek** | 8 bulan |
| **Tarikh Mula** | [Tarikh ditentukan selepas kontrak] |
| **Tarikh Siang** | 8 bulan dari tarikh mula |

---

## 2. GANTT CHART - JADUAL PELAKSANAAN PROJEK

### Fasa 1: Permulaan & Perancangan (Bulan 1)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M1-W1** | Kick-off Meeting | PM / UMPSA | Minit mesyuarat |
| | Pelantikan pasukan | PM | Struktur pasukan |
| | Setup development environment | Technical Lead | Repo GitLab |
| **M1-W2** | Bengkel Kajian Keperluan | BA / UMPSA | URS Draft |
| | Analisis sistem sedia ada | Technical Lead | Laporan analisis |
| **M1-W3** | Penyediaan Pelan Pelaksanaan | PM | Pelan projek |
| | WBS & CPM | PM | Carta WBS |
| **M1-W4** | Pengesahan pelan dengan UMPSA | PM / UMPSA | Pelan yang diluluskan |
| | Setup project tools | PM | Jira / Trello |

### Fasa 2: Reka Bentuk (Bulan 2)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M2-W1** | UI/UX Design Phase 1 | UI Designer | Wireframe |
| | Database Design | Technical Lead | ERD |
| **M2-W2** | UI/UX Design Phase 2 | UI Designer | Mockup |
| | API Design | Technical Lead | API Spec |
| **M2-W3** | System Architecture Design | Technical Lead | SDS |
| | Security Design | Security Lead | Security Plan |
| **M2-W4** | Review Design dengan UMPSA | Technical Lead | Design yang diluluskan |
| | Penyediaan SRS | BA | SRS Document |

### Fasa 3: Pembangunan - Fasa 1 (Bulan 3)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M3-W1** | Setup Laravel Framework | Dev Team | Base project |
| | Setup Database | Dev Team | DB Schema |
| | Modul Login development | Developer 1 | Modul Login |
| **M3-W2** | Modul E-Authorization development | Developer 1 | Modul Auth |
| | SSO Integration | Developer 2 | SSO berfungsi |
| **M3-W3** | Modul Meeting Registration | Developer 2 | Modul Registration |
| | e-Takwim Integration | Developer 3 | Integration |
| **M3-W4** | Unit Testing Fasa 1 | QA Engineer | Test Report |
| | Bug fixing | Dev Team | Bug fixes |

### Fasa 4: Pembangunan - Fasa 2 (Bulan 4)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M4-W1** | Modul E-Committee | Developer 1 | E-Committee |
| | Appointment Management | Developer 1 | Appointment |
| **M4-W2** | Modul E-Paper Meeting | Developer 2 | E-Paper |
| | Call for Paper | Developer 2 | Paper submission |
| **M4-W3** | Modul E-Decision | Developer 3 | E-Decision |
| | Workflow engine | Developer 3 | Workflow |
| **M4-W4** | Unit Testing Fasa 2 | QA Engineer | Test Report |
| | Integration testing | QA Engineer | Integration report |

### Fasa 5: Pembangunan - Fasa 3 (Bulan 5)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M5-W1** | Modul E-Minutes | Developer 1 | E-Minutes |
| | Draft & Review | Developer 1 | Minutes workflow |
| **M5-W2** | Modul E-Progress | Developer 2 | E-Progress |
| | Tracking system | Developer 2 | Tracking |
| **M5-W3** | Modul E-Cabutan | Developer 3 | E-Cabutan |
| | PDF Generation | Developer 3 | PDF feature |
| **M5-W4** | Unit Testing Fasa 3 | QA Engineer | Test Report |
| | Code review | Technical Lead | Review report |

### Fasa 6: Integrasi & Ujian (Bulan 6)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M6-W1** | System Integration | Dev Team | Integrated system |
| | Performance tuning | Technical Lead | Optimized system |
| **M6-W2** | Security Testing | Security Lead | PenTest Report |
| | Vulnerability fix | Dev Team | Security patches |
| **M6-W3** | UAT Preparation | QA / BA | UAT Plan |
| | Test scripts | QA Engineer | Test scripts |
| **M6-W4** | UAT 1 Execution | UMPSA / QA | UAT 1 Report |
| | Bug fixing | Dev Team | Fixes |

### Fasa 7: Ujian & Dokumentasi (Bulan 7)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M7-W1** | UAT 2 Execution | UMPSA / QA | UAT 2 Report |
| | Bug fixing | Dev Team | Fixes |
| **M7-W2** | FAT Preparation | PM / QA | FAT Plan |
| | Production setup | DevOps | Production ready |
| **M7-W3** | FAT Execution | UMPSA / QA | FAT Report |
| | Sign-off | UMPSA | Acceptance |
| **M7-W4** | Documentation | BA / Technical | User Manuals |
| | Training material | BA | Training docs |

### Fasa 8: Pelancaran & Latihan (Bulan 8)

| Minggu | Aktiviti | Tanggungjawab | Output |
|--------|----------|---------------|--------|
| **M8-W1** | Data Migration | Dev Team | Migrated data |
| | Production deployment | DevOps | Live system |
| **M8-W2** | User Training - Admin | Trainer | Admin trained |
| | User Training - End Users | Trainer | Users trained |
| **M8-W3** | Go-live support | Dev Team | Stable system |
| | Monitoring | DevOps | Monitoring |
| **M8-W4** | Project handover | PM | Handover docs |
| | Warranty period start | PM | Warranty begins |

---

## 3. WORK BREAKDOWN STRUCTURE (WBS)

```
Sistem Pengurusan Mesyuarat
├── 1.0 Permulaan Projek
│   ├── 1.1 Kick-off Meeting
│   ├── 1.2 Bengkel Kajian Keperluan
│   └── 1.3 Pelan Pelaksanaan
├── 2.0 Reka Bentuk
│   ├── 2.1 UI/UX Design
│   ├── 2.2 Database Design
│   ├── 2.3 System Architecture
│   └── 2.4 Security Design
├── 3.0 Pembangunan
│   ├── 3.1 Framework Setup
│   ├── 3.2 Modul Login & Auth
│   ├── 3.3 Modul Meeting Registration
│   ├── 3.4 Modul E-Committee
│   ├── 3.5 Modul E-Paper
│   ├── 3.6 Modul E-Decision
│   ├── 3.7 Modul E-Minutes
│   ├── 3.8 Modul E-Progress
│   └── 3.9 Modul E-Cabutan
├── 4.0 Integrasi
│   ├── 4.1 SSO Integration
│   ├── 4.2 e-Takwim Integration
│   ├── 4.3 E-Voting Integration
│   └── 4.4 Executive Approval Integration
├── 5.0 Pengujian
│   ├── 5.1 Unit Testing
│   ├── 5.2 Integration Testing
│   ├── 5.3 Security Testing
│   ├── 5.4 UAT 1
│   ├── 5.5 UAT 2
│   └── 5.6 FAT
├── 6.0 Dokumentasi
│   ├── 6.1 BRS, SRS, SDS
│   ├── 6.2 User Manuals
│   └── 6.3 Technical Manuals
└── 7.0 Pelancaran
    ├── 7.1 Data Migration
    ├── 7.2 Deployment
    ├── 7.3 Training
    └── 7.4 Handover
```

---

## 4. CRITICAL PATH METHOD (CPM)

### Aktiviti-aktiviti Kritikal

```
[Start]
   ↓
[1.1 Kick-off] → [1.2 Bengkel] → [1.3 Pelan]
   ↓
[2.1 UI/UX Design]
   ↓
[2.2 Database Design]
   ↓
[3.1 Framework Setup]
   ↓
[3.2-3.9 Modul Development]
   ↓
[4.1-4.4 Integrasi]
   ↓
[5.1-5.3 Testing]
   ↓
[5.4 UAT 1]
   ↓
[5.5 UAT 2]
   ↓
[5.6 FAT]
   ↓
[7.2 Deployment]
   ↓
[7.4 Handover] → [End]
```

### Float/Slack Activities

| Aktiviti | Float (Hari) |
|----------|--------------|
| Documentation (parallel) | 30 |
| Training preparation | 14 |
| Optional enhancements | 10 |

---

## 5. MILESTONE CHART

| Milestone | Target Date | Criteria | Status |
|-----------|-------------|----------|--------|
| M1: Project Kick-off | Week 1 | Minit mesyuarat | ☐ |
| M2: Requirements Finalized | Week 5 | URS diluluskan | ☐ |
| M3: Design Completed | Week 8 | SDS diluluskan | ☐ |
| M4: Phase 1 Development | Week 12 | Login & Auth ready | ☐ |
| M5: Phase 2 Development | Week 16 | Core modules ready | ☐ |
| M6: Phase 3 Development | Week 20 | All modules ready | ☐ |
| M7: UAT 1 Complete | Week 24 | UAT 1 passed | ☐ |
| M8: UAT 2 Complete | Week 28 | UAT 2 passed | ☐ |
| M9: FAT Complete | Week 30 | FAT passed | ☐ |
| M10: Go-Live | Week 32 | System live | ☐ |
| M11: Project Close | Week 34 | Handover complete | ☐ |

---

## 6. PERT CHART - ANALISIS MASA

### Aktiviti dengan Estimates

| Aktiviti | Optimistic (O) | Most Likely (M) | Pessimistic (P) | Expected (TE) |
|----------|---------------|-----------------|-----------------|---------------|
| Requirements | 2 | 3 | 4 | 3.0 |
| Design | 3 | 4 | 6 | 4.2 |
| Development | 12 | 16 | 20 | 16.0 |
| Testing | 4 | 6 | 8 | 6.0 |
| Deployment | 1 | 2 | 3 | 2.0 |
| **Total** | | | | **31.2** |

**Formula:** TE = (O + 4M + P) / 6

---

## 7. RESOURCE ALLOCATION

### 7.1 Sumber Manusia

| Peranan | Bulan 1 | Bulan 2 | Bulan 3-5 | Bulan 6-7 | Bulan 8 |
|---------|---------|---------|-----------|-----------|---------|
| Project Manager | 100% | 100% | 100% | 100% | 100% |
| Technical Lead | 50% | 100% | 100% | 100% | 50% |
| Business Analyst | 100% | 100% | 50% | 50% | 25% |
| Developer 1 | 0% | 50% | 100% | 100% | 50% |
| Developer 2 | 0% | 50% | 100% | 100% | 50% |
| Developer 3 | 0% | 50% | 100% | 100% | 50% |
| QA Engineer | 0% | 25% | 50% | 100% | 50% |
| UI/UX Designer | 0% | 100% | 25% | 0% | 0% |

### 7.2 Keperluan Infrastruktur

| Keperluan | Bulan 1 | Bulan 2-7 | Bulan 8+ |
|-----------|---------|-----------|----------|
| Development Server | ✓ | ✓ | ✓ |
| Staging Server | | ✓ | ✓ |
| Production Server | | | ✓ |
| GitLab Repository | ✓ | ✓ | ✓ |
| Jira/Project Tool | ✓ | ✓ | ✓ |
| Test Environment | | ✓ | ✓ |

---

## 8. RISK MANAGEMENT DALAM JADUAL

### 8.1 Risiko kepada Jadual

| Risiko | Kesan | Mitigasi | Contingency |
|--------|-------|----------|-------------|
| Integration delay | 2 weeks | Early POC | Buffer time |
| Resource unavailability | 1 week | Backup team | Cross-training |
| Scope change | 1-2 weeks | Change control | Buffer |
| Technical issues | 1 week | Code reviews | Expert consultant |

### 8.2 Buffer Time

- **Total Buffer**: 2 weeks (Week 31-32)
- **Critical Path Buffer**: 1 week
- **Management Reserve**: 1 week

---

## 9. DELIVERABLES SCHEDULE

| Deliverable | Planned Date | Actual Date | Status |
|-------------|--------------|-------------|--------|
| Project Plan | Week 4 | | ☐ |
| SRS Document | Week 8 | | ☐ |
| SDS Document | Week 8 | | ☐ |
| UI/UX Mockups | Week 8 | | ☐ |
| Test Scripts | Week 24 | | ☐ |
| UAT 1 Report | Week 24 | | ☐ |
| UAT 2 Report | Week 28 | | ☐ |
| FAT Report | Week 30 | | ☐ |
| User Manuals | Week 30 | | ☐ |
| Training Materials | Week 30 | | ☐ |
| Handover Document | Week 34 | | ☐ |

---

## 10. GANTT CHART VISUAL

```
Aktiviti                      | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 |
------------------------------|----|----|----|----|----|----|----|----|
1.0 Permulaan                 |████|    |    |    |    |    |    |    |
  1.1 Kick-off                |██  |    |    |    |    |    |    |    |
  1.2 Bengkel                 |  ██|    |    |    |    |    |    |    |
  1.3 Pelan                   |  ██|    |    |    |    |    |    |    |
2.0 Reka Bentuk               |    |████|    |    |    |    |    |    |
  2.1 UI/UX                   |    |████|    |    |    |    |    |    |
  2.2 Database                |    |  ██|    |    |    |    |    |    |
  2.3 Architecture            |    |  ██|    |    |    |    |    |    |
3.0 Pembangunan               |    |    |████|████|████|    |    |    |
  3.1 Framework               |    |    |██  |    |    |    |    |    |
  3.2 Login/Auth              |    |    |  ██|    |    |    |    |    |
  3.3 Meeting Reg             |    |    |  ██|    |    |    |    |    |
  3.4 E-Committee             |    |    |    |████|    |    |    |    |
  3.5 E-Paper                 |    |    |    |████|    |    |    |    |
  3.6 E-Decision              |    |    |    |    |████|    |    |    |
  3.7 E-Minutes               |    |    |    |    |████|    |    |    |
  3.8 E-Progress              |    |    |    |    |    |    |    |    |
  3.9 E-Cabutan               |    |    |    |    |  ██|    |    |    |
4.0 Integrasi                 |    |    |    |    |  ██|████|    |    |
5.0 Pengujian                 |    |    |  ██|  ██|  ██|████|████|    |
6.0 Dokumentasi               |    |  ██|  ██|  ██|  ██|  ██|████|    |
7.0 Pelancaran                |    |    |    |    |    |    |  ██|████|
  7.1 Migration               |    |    |    |    |    |    |    |██  |
  7.2 Deployment              |    |    |    |    |    |    |    |  ██|
  7.3 Training                |    |    |    |    |    |    |    |  ██|
  7.4 Handover                |    |    |    |    |    |    |    |  ██|

Legenda:
████ = Aktiviti aktif
```

---

## 11. KOORDINASI DENGAN UMPSA

### 11.1 Mesyuarat Berkala

| Jenis | Kekerapan | Peserta | Tujuan |
|-------|-----------|---------|--------|
| Steering Committee | Bulanan | Pengurusan atasan | Keputusan strategik |
| Progress Meeting | Mingguan | PM, Technical Lead | Status update |
| Technical Review | Dua minggu | Dev team, UMPSA IT | Isu teknikal |
| User Review | Fasa akhir | End users | Feedback |

### 11.2 Reporting

| Laporan | Kekerapan | Penerima |
|---------|-----------|----------|
| Status Report | Mingguan | Project Sponsor |
| Progress Report | Bulanan | Steering Committee |
| Issue Log | Seperti diperlukan | All stakeholders |
| Risk Register | Bulanan | Project Sponsor |

---

**Disediakan oleh:**

Sinergi Elit Sdn Bhd

**Tarikh:** 21 Februari 2026

**Versi:** 1.0
