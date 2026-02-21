# JADUAL KERJA / WORK SCHEDULE
## TSH-2614: Sistem Portal Staf (eCommunity)
### UMPSA/BEND/SH/2026(3)

---

## 1. MAKLUMAT PROJEK

| Item | Maklumat |
|------|----------|
| **Nama Projek** | Sistem Portal Staf (eCommunity) |
| **Tender** | UMPSA/BEND/SH/2026(3) |
| **Jabatan** | DiTec (Pusat Teknologi Digital) |
| **Tempoh Projek** | 8 bulan |
| **Tarikh Mula** | [Tarikh ditentukan selepas kontrak] |
| **Tarikh Siang** | 8 bulan dari tarikh mula |

---

## 2. GANTT CHART - JADUAL PELAKSANAAN PROJEK

### Fasa 1: Permulaan & Perancangan (Bulan 1)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M1-W1** | Kick-off Meeting | Minit mesyuarat |
| | Pelantikan pasukan | Struktur pasukan |
| | Setup development environment | Repo GitLab |
| **M1-W2** | Bengkel Kajian Keperluan | URS Draft |
| **M1-W3** | Penyediaan Pelan Pelaksanaan | Pelan projek |
| **M1-W4** | Pengesahan pelan dengan UMPSA | Pelan diluluskan |

### Fasa 2: Reka Bentuk (Bulan 2)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M2-W1** | UI/UX Design Phase 1 | Wireframe |
| | Database Design | ERD |
| **M2-W2** | UI/UX Design Phase 2 | Mockup |
| **M2-W3** | System Architecture Design | SDS |
| **M2-W4** | Review Design | SRS Document |

### Fasa 3: Pembangunan - Fasa 1 (Bulan 3)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M3-W1** | Setup Laravel Framework | Base project |
| **M3-W2** | Modul Login development | Modul Login |
| **M3-W3** | SSO Integration | SSO berfungsi |
| **M3-W4** | Unit Testing Fasa 1 | Test Report |

### Fasa 4: Pembangunan - Fasa 2 (Bulan 4)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M4-W1** | Modul Calendar development | Calendar Module |
| **M4-W2** | Google Calendar Integration | Integration works |
| **M4-W3** | Modul Memo | Memo Module |
| **M4-W4** | Unit Testing Fasa 2 | Test Report |

### Fasa 5: Pembangunan - Fasa 3 (Bulan 5)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M5-W1** | Modul Announcements | Announcement Module |
| **M5-W2** | User Management Module | User Mgmt Module |
| **M5-W3** | Settings Module | Settings Module |
| **M5-W4** | Unit Testing Fasa 3 | Test Report |

### Fasa 6: Integrasi & Ujian (Bulan 6)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M6-W1** | Notification Module | Notifications |
| **M6-W2** | Security Testing | PenTest Report |
| **M6-W3** | UAT Preparation | UAT Plan |
| **M6-W4** | UAT 1 Execution | UAT 1 Report |

### Fasa 7: Ujian & Dokumentasi (Bulan 7)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M7-W1** | UAT 2 Execution | UAT 2 Report |
| **M7-W2** | FAT Preparation | FAT Plan |
| **M7-W3** | FAT Execution | FAT Report |
| **M7-W4** | Documentation | User Manuals |

### Fasa 8: Pelancaran & Latihan (Bulan 8)

| Minggu | Aktiviti | Output |
|--------|----------|--------|
| **M8-W1** | Data Migration | Migrated data |
| **M8-W2** | User Training | Admin & Users trained |
| **M8-W3** | Go-live support | Stable system |
| **M8-W4** | Project handover | Handover docs |

---

## 3. WORK BREAKDOWN STRUCTURE (WBS)

```
Sistem Portal Staf (eCommunity)
├── 1.0 Permulaan Projek
│   ├── 1.1 Kick-off Meeting
│   ├── 1.2 Bengkel Kajian Keperluan
│   └── 1.3 Pelan Pelaksanaan
├── 2.0 Reka Bentuk
│   ├── 2.1 UI/UX Design
│   ├── 2.2 Database Design
│   └── 2.3 System Architecture
├── 3.0 Pembangunan
│   ├── 3.1 Framework Setup
│   ├── 3.2 Modul Login
│   ├── 3.3 Modul Calendar
│   ├── 3.4 Modul Memo
│   ├── 3.5 Modul Announcements
│   ├── 3.6 User Management
│   ├── 3.7 Settings Module
│   └── 3.8 Notification Module
├── 4.0 Integrasi
│   ├── 4.1 SSO Integration
│   ├── 4.2 Google Calendar Integration
│   └── 4.3 Mobile Notification Integration
├── 5.0 Pengujian
│   ├── 5.1 Unit Testing
│   ├── 5.2 Integration Testing
│   ├── 5.3 Security Testing
│   ├── 5.4 UAT 1 & 2
│   └── 5.5 FAT
├── 6.0 Dokumentasi
│   ├── 6.1 SRS, SDS
│   └── 6.2 User Manuals
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
[3.2-3.8 Module Development]
   ↓
[4.1-4.3 Integrasi]
   ↓
[5.1-5.3 Testing]
   ↓
[5.4 UAT 1 & 2]
   ↓
[5.5 FAT]
   ↓
[7.2 Deployment]
   ↓
[7.4 Handover] → [End]
```

---

## 5. MILESTONE CHART

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| M1: Project Kick-off | Week 1 | ☐ |
| M2: Requirements Finalized | Week 5 | ☐ |
| M3: Design Completed | Week 8 | ☐ |
| M4: Phase 1 Development | Week 12 | ☐ |
| M5: Phase 2 Development | Week 16 | ☐ |
| M6: Phase 3 Development | Week 20 | ☐ |
| M7: UAT Complete | Week 24 | ☐ |
| M8: FAT Complete | Week 30 | ☐ |
| M9: Go-Live | Week 32 | ☐ |
| M10: Project Close | Week 34 | ☐ |

---

## 6. RESOURCE ALLOCATION

| Peranan | Bulan 1 | Bulan 2 | Bulan 3-5 | Bulan 6-7 | Bulan 8 |
|---------|---------|---------|-----------|-----------|---------|
| Project Manager | 100% | 100% | 100% | 100% | 100% |
| Technical Lead | 50% | 100% | 100% | 100% | 50% |
| Developers | 0% | 50% | 100% | 100% | 50% |
| QA Engineer | 0% | 25% | 50% | 100% | 50% |
| UI/UX Designer | 0% | 100% | 25% | 0% | 0% |

---

## 7. GANTT CHART VISUAL

```
Aktiviti                      | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 |
------------------------------|----|----|----|----|----|----|----|----|
1.0 Permulaan                 |████|    |    |    |    |    |    |    |
2.0 Reka Bentuk               |    |████|    |    |    |    |    |    |
3.0 Pembangunan               |    |    |████|████|████|    |    |    |
4.0 Integrasi                 |    |    |    |    |  ██|████|    |    |
5.0 Pengujian                 |    |    |  ██|  ██|  ██|████|████|    |
6.0 Dokumentasi               |    |  ██|  ██|  ██|  ██|  ██|████|    |
7.0 Pelancaran                |    |    |    |    |    |    |  ██|████|
```

---

**Disediakan oleh:**

Sinergi Elit Sdn Bhd

**Tarikh:** 21 Februari 2026
