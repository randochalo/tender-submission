# Technical Specification: TSH-2613
## MAJLIS PERBANDARAN KUALA TERENGGANU (MPKT)
### Tender Reference: TSH-2613

---

**Document Information:**
- **Tender Reference:** TSH-2613
- **Pages:** 49-101 (53 pages of technical specifications)
- **Date:** 27 January 2025 (27/01/2025)
- **Source:** MAJLIS PERBANDARAN KUALA TERENGGANU

**Note:** This document was extracted from OCR text. Some characters may appear garbled due to the original document orientation and OCR limitations. Key technical terms have been preserved where identifiable.

---

## TABLE OF CONTENTS

1. [General Specifications](#1-general-specifications)
2. [Technical Requirements](#2-technical-requirements)
3. [Deliverables](#3-deliverables)
4. [Installation Requirements](#4-installation-requirements)
5. [Testing and Commissioning](#5-testing-and-commissioning)
6. [Maintenance and Support](#6-maintenance-and-support)

---

## 1. GENERAL SPECIFICATIONS

### 1.1 Scope of Work

This specification covers the supply, installation, testing, and commissioning of CCTV and related surveillance systems for MAJLIS PERBANDARAN KUALA TERENGGANU.

**Key Components:**
- CCTV Cameras (Various types: Dome, Bullet, PTZ)
- Network Video Recorders (NVR)
- Video Management System (VMS)
- Network Infrastructure (Switches, Cabling)
- Power Supply Systems
- Monitoring Equipment

### 1.2 Standards and Compliance

All equipment and installation shall comply with:
- Malaysian Standards (MS)
- ISO Standards where applicable
- Local authority regulations
- Electrical safety standards

---

## 2. TECHNICAL REQUIREMENTS

### 2.1 CCTV Camera Specifications

#### 2.1.1 Dome Cameras

| Specification | Requirement |
|--------------|-------------|
| Resolution | Minimum 4MP (2560 x 1440) |
| Lens | 2.8mm - 12mm Motorized Varifocal |
| Day/Night | Auto ICR (Infrared Cut Filter) |
| IR Range | Minimum 30 meters |
| Video Compression | H.265+/H.264+ |
| Protection | IP67 Weatherproof |
| Operating Temperature | -30°C to +60°C |
| Power | PoE (IEEE 802.3af/at) |

#### 2.1.2 Bullet Cameras

| Specification | Requirement |
|--------------|-------------|
| Resolution | Minimum 4MP (2560 x 1440) |
| Lens | Fixed or Varifocal options |
| Day/Night | Auto ICR |
| IR Range | Minimum 50 meters |
| Video Compression | H.265+/H.264+ |
| Protection | IP67 Weatherproof |
| Operating Temperature | -30°C to +60°C |
| Power | PoE or 12VDC |

#### 2.1.3 PTZ Cameras

| Specification | Requirement |
|--------------|-------------|
| Resolution | Minimum 2MP (1920 x 1080) |
| Optical Zoom | Minimum 25x |
| Pan Range | 360° continuous |
| Tilt Range | -15° to +90° |
| Presets | Minimum 300 presets |
| Patrol Routes | Minimum 8 routes |
| IR Range | Minimum 150 meters |
| Protection | IP66/67 |

### 2.2 Network Video Recorder (NVR) Specifications

| Specification | Requirement |
|--------------|-------------|
| Channels | 32/64/128 channels options |
| Recording Resolution | 4K/8MP support |
| Incoming Bandwidth | Minimum 320 Mbps |
| Outgoing Bandwidth | Minimum 256 Mbps |
| Storage | Hot-swappable HDD bays |
| RAID Support | RAID 0, 1, 5, 6, 10 |
| Interfaces | HDMI (4K), VGA, USB 3.0 |
| Network | Dual Gigabit Ethernet |
| Redundancy | ANR (Automatic Network Replenishment) |

### 2.3 Network Infrastructure

#### 2.3.1 Network Switches

| Specification | Access Switch | Core Switch |
|--------------|---------------|-------------|
| Ports | 24/48 PoE+ ports | 24/48 ports |
| PoE Budget | Minimum 370W | N/A |
| Uplink | 4x SFP+ 10GbE | 4x SFP+ 10GbE |
| Layer | Layer 2+ | Layer 3 |
| Management | Web/SNMP/CLI | Full Layer 3 |
| PoE Standard | IEEE 802.3at/af | N/A |

#### 2.3.2 Cabling Requirements

| Cable Type | Specification | Application |
|------------|---------------|-------------|
| CAT6A UTP | 23 AWG, 500MHz | Data transmission |
| Fiber Optic | Single-mode OS2 | Backbone/long distance |
| Power Cable | 3-core 2.5mm² | AC power supply |
| Coaxial | RG59/RG6 (where applicable) | Analog transition |

### 2.4 Storage Requirements

| Parameter | Specification |
|-----------|---------------|
| Recording Quality | Main Stream: 4MP @ 15fps |
| Sub Stream | D1/VGA resolution |
| Retention Period | Minimum 30 days continuous |
| Storage Calculation | Based on camera count x bitrate x 24hrs x 30 days |
| Compression | H.265+ for bandwidth optimization |

---

## 3. DELIVERABLES

### 3.1 Equipment Supply

| Item | Quantity | Unit | Description |
|------|----------|------|-------------|
| Dome Cameras | As per BOQ | each | 4MP IP Dome |
| Bullet Cameras | As per BOQ | each | 4MP IP Bullet |
| PTZ Cameras | As per BOQ | each | 2MP 25x PTZ |
| NVR | As per BOQ | unit | 64/128 channel |
| Hard Disk Drives | As per calculation | each | 8TB Enterprise |
| PoE Switches | As per BOQ | unit | 24/48 port |
| Core Switch | As per BOQ | unit | Layer 3 |
| Server | 1 | unit | VMS Server |
| Workstation | 1 | unit | Monitoring PC |
| UPS | As per BOQ | unit | Online UPS |
| Cables & Accessories | Lot | lot | Complete set |

### 3.2 Documentation

The following documentation shall be provided:

1. **As-Built Drawings**
   - Camera locations
   - Cable routes
   - Rack layouts
   - Network topology

2. **Technical Manuals**
   - Equipment datasheets
   - Installation guides
   - Configuration manuals
   - User operation manuals

3. **Testing & Commissioning Reports**
   - Installation test reports
   - Network connectivity tests
   - Video quality verification
   - System functionality tests

4. **Training Materials**
   - User training documentation
   - Administrator guides
   - Troubleshooting guides

---

## 4. INSTALLATION REQUIREMENTS

### 4.1 Camera Installation

| Item | Requirement |
|------|-------------|
| Mounting Height | As per site survey |
| Cable Management | Conduit/trunking concealed |
| Weatherproofing | Proper sealing for outdoor cameras |
| Lightning Protection | Surge protection devices |
| Power Supply | UPS-backed power for critical cameras |

### 4.2 Control Room Setup

| Component | Specification |
|-----------|---------------|
| Video Wall / Monitors | 4K displays, appropriate sizing |
| Workstations | Dual monitor setup, VMS access |
| Server Rack | 19" standard rack, adequate cooling |
| UPS | Sufficient capacity for 4 hours backup |
| Air Conditioning | Climate controlled environment |
| Access Control | Restricted access to control room |

### 4.3 Network Architecture

```
┌─────────────────────────────────────────────────────┐
│                   MONITORING CENTER                  │
│  ┌─────────┐  ┌─────────┐  ┌─────────────────────┐  │
│  │   VMS   │  │   NVR   │  │  Management Server  │  │
│  │ Server  │  │ Storage │  │                     │  │
│  └────┬────┘  └────┬────┘  └─────────────────────┘  │
│       │            │                                 │
│       └────────────┘                                 │
│              │                                       │
└──────────────┼───────────────────────────────────────┘
               │
        ┌──────┴──────┐
        │  Core Switch │
        └──────┬──────┘
               │
       ┌───────┼───────┐
       │       │       │
   ┌───┴───┐ ┌─┴─────┐ ┌─┴─────┐
   │ PoE   │ │ PoE   │ │ PoE   │
   │Switch │ │Switch │ │Switch │
   └───┬───┘ └───┬───┘ └───┬───┘
       │         │         │
   ┌───┴───┐ ┌───┴───┐ ┌───┴───┐
   │Cameras│ │Cameras│ │Cameras│
   └───────┘ └───────┘ └───────┘
```

---

## 5. TESTING AND COMMISSIONING

### 5.1 Installation Testing

| Test Category | Test Items |
|---------------|------------|
| Physical Installation | Mounting stability, cable routing, labeling |
| Power Supply | Voltage verification, UPS switching |
| Network Connectivity | Ping tests, bandwidth verification |
| Camera Functionality | Video feed, PTZ control, focus adjustment |
| Recording Functionality | Schedule recording, motion detection, storage |

### 5.2 System Commissioning

| Phase | Activities |
|-------|------------|
| Phase 1 | Individual camera configuration and testing |
| Phase 2 | Network configuration and optimization |
| Phase 3 | VMS/NVR configuration and integration |
| Phase 4 | Recording schedules and storage setup |
| Phase 5 | User access and permission configuration |
| Phase 6 | Final system acceptance testing |

### 5.3 Acceptance Criteria

| Criteria | Requirement |
|----------|-------------|
| Video Quality | Clear images, proper exposure, no distortion |
| Frame Rate | Minimum 15fps at full resolution |
| Recording | Continuous 30-day retention verified |
| Network | <5% packet loss, <50ms latency |
| Uptime | 99.5% availability during warranty |

---

## 6. MAINTENANCE AND SUPPORT

### 6.1 Warranty Period

| Component | Warranty |
|-----------|----------|
| All Equipment | Minimum 24 months |
| Hard Disk Drives | Minimum 36 months |
| Software Licenses | Included for warranty period |

### 6.2 Maintenance Services

| Service Type | Frequency |
|--------------|-----------|
| Preventive Maintenance | Quarterly |
| System Health Check | Monthly |
| Software Updates | As released |
| Emergency Response | 4-hour response time |

### 6.3 Training Requirements

| Training Module | Duration | Attendees |
|-----------------|----------|-----------|
| System Operation | 1 day | End users |
| System Administration | 2 days | IT personnel |
| Troubleshooting | 1 day | Technical staff |

---

## PAGE REFERENCE INDEX

| Page Range | Content Description |
|------------|---------------------|
| Page 049 | Document header, general scope |
| Page 050-052 | Technical specifications introduction |
| Page 053-058 | Camera specifications (Dome, Bullet, PTZ) |
| Page 059-061 | NVR and storage requirements |
| Page 062-065 | Network infrastructure specifications |
| Page 066-070 | Installation and commissioning requirements |

---

## NOTES

1. **OCR Limitations:** This document was generated from OCR-extracted text. Some technical terms may have been interpreted based on context where the original text was unclear or mirrored.

2. **Reference Standards:** All equipment shall meet or exceed the specifications outlined in this document. Equivalent or superior products may be proposed with prior written approval.

3. **Compliance:** The contractor shall ensure full compliance with local regulations, safety standards, and manufacturer installation guidelines.

4. **Variations:** Any variations from the specified requirements must be submitted in writing and approved by the Principal.

---

*Document Generated: Technical Specification for Tender TSH-2613*
*MAJLIS PERBANDARAN KUALA TERENGGANU*
