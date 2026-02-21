# Technical Specification: TSH-2614
## MAJLIS PERBANDARAN KUALA TERENGGANU (MPKT)
### Tender Reference: TSH-2614

---

**Document Information:**
- **Tender Reference:** TSH-2614
- **Pages:** 49-95 (47 pages of technical specifications)
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

This specification covers the supply, installation, testing, and commissioning of CCTV and related surveillance systems for MAJLIS PERBANDARAN KUALA TERENGGANU under Tender Reference TSH-2614.

**Key Components:**
- CCTV Cameras (Various types: Dome, Bullet, PTZ)
- Network Video Recorders (NVR) and Digital Video Recorders (DVR)
- Video Management System (VMS)
- Network Infrastructure (Switches, Cabling, Fiber)
- Power Supply Systems (UPS, Power Distribution)
- Monitoring and Display Equipment
- Video Analytics Software (where specified)

### 1.2 Standards and Compliance

All equipment and installation shall comply with:
- Malaysian Standards (MS)
- ISO/IEC Standards where applicable
- Suruhanjaya Komunikasi dan Multimedia Malaysia (SKMM) regulations
- Local authority electrical safety standards
- IEEE standards for network equipment

---

## 2. TECHNICAL REQUIREMENTS

### 2.1 CCTV Camera Specifications

#### 2.1.1 Indoor Dome Cameras

| Specification | Requirement |
|--------------|-------------|
| Image Sensor | 1/2.8" Progressive Scan CMOS |
| Resolution | Minimum 4MP (2688 x 1520) |
| Lens | 2.8mm fixed or 2.8-12mm motorized |
| Min. Illumination | 0.005 Lux (Color), 0 Lux (IR on) |
| Day/Night | Auto ICR (Infrared Cut Filter Removal) |
| IR Range | Minimum 20 meters |
| WDR | 120dB True WDR |
| Video Compression | H.265+, H.265, H.264+, H.264 |
| Protection | IP67, IK10 vandal-resistant |
| Operating Temperature | -30°C to +60°C |
| Power | DC 12V ± 25%, PoE (IEEE 802.3af) |
| Interface | RJ45 10M/100M Ethernet |

#### 2.1.2 Outdoor Bullet Cameras

| Specification | Requirement |
|--------------|-------------|
| Image Sensor | 1/2.8" Progressive Scan CMOS |
| Resolution | Minimum 4MP (2688 x 1520) |
| Lens | 2.8-12mm motorized varifocal |
| Min. Illumination | 0.005 Lux (Color), 0 Lux (IR on) |
| Day/Night | Auto ICR |
| IR Range | Minimum 50 meters with Smart IR |
| WDR | 120dB True WDR |
| Video Compression | H.265+, H.265, H.264+, H.264 |
| Protection | IP67 weatherproof, IK10 |
| Operating Temperature | -30°C to +60°C |
| Power | DC 12V ± 25%, PoE (IEEE 802.3af) |
| Interface | RJ45 10M/100M Ethernet |

#### 2.1.3 PTZ (Pan-Tilt-Zoom) Cameras

| Specification | Requirement |
|--------------|-------------|
| Image Sensor | 1/2.8" Progressive Scan CMOS |
| Resolution | Minimum 2MP (1920 x 1080) |
| Optical Zoom | 25x or 32x optical zoom |
| Digital Zoom | 16x |
| Pan Range | 360° endless pan |
| Tilt Range | -15° to +90° (auto flip) |
| Pan Speed | 0.1°-300°/s (preset), 0.1°-150°/s (manual) |
| Presets | Minimum 300 presets |
| Patrol Routes | Minimum 8 patrols, up to 32 presets each |
| Pattern Scan | Minimum 4 patterns |
| IR Range | Minimum 150 meters |
| WDR | 120dB True WDR |
| Video Compression | H.265+, H.265, H.264+, H.264 |
| Protection | IP66 weatherproof |
| Operating Temperature | -40°C to +70°C |
| Power | AC 24V, Hi-PoE |

### 2.2 Recording System Specifications

#### 2.2.1 Network Video Recorder (NVR)

| Specification | Requirement |
|--------------|-------------|
| Channels | 32/64/128 channels |
| IP Video Input | Up to 128 IP cameras |
| Incoming Bandwidth | 320 Mbps or higher |
| Outgoing Bandwidth | 256 Mbps or higher |
| Recording Resolution | 12MP/8MP/6MP/5MP/4MP/3MP/1080p/UXGA/720p/VGA/4CIF/DCIF/2CIF/CIF/QCIF |
| Decoding Capability | 16 x 1080p @ 30fps |
| Synchronous Playback | 16 channels |
| Storage Capacity | 16 SATA HDDs, up to 10TB each |
| RAID Support | RAID 0, 1, 5, 6, 10, 50, 60, JBOD |
| Network Interface | 2x RJ45 10M/100M/1000M adaptive Ethernet |
| USB Interface | 2x USB 2.0, 2x USB 3.0 |
| Alarm I/O | 16/4 or higher |
| Redundancy | Dual network, dual power (optional) |
| ANR | Automatic Network Replenishment support |

#### 2.2.2 Storage Requirements

| Parameter | Specification |
|-----------|---------------|
| HDD Type | Surveillance-grade enterprise HDD |
| Capacity per Drive | 8TB or 10TB |
| Recording Quality | 4MP @ 15fps (main stream) |
| Sub Stream | D1 @ 25fps |
| Retention Period | 30 days minimum |
| Recording Mode | Continuous + Motion/Event |
| Compression | H.265+ for optimal storage |

### 2.3 Video Management System (VMS)

| Feature | Requirement |
|---------|-------------|
| License | Perpetual license with annual support |
| Camera Support | Unlimited (per server specifications) |
| Client Workstations | Minimum 5 concurrent users |
| Mobile Access | iOS and Android apps |
| Video Analytics | Motion detection, line crossing, intrusion |
| Integration | API support for third-party integration |
| Backup | Automated backup and failover |
| Redundancy | Server redundancy options |

### 2.4 Network Infrastructure

#### 2.4.1 PoE Access Switches

| Specification | Requirement |
|--------------|-------------|
| Ports | 24 or 48 x 10/100/1000Base-T PoE+ |
| PoE Budget | 370W or higher |
| PoE Standard | IEEE 802.3af/at |
| Uplink Ports | 4 x SFP 1000M or 10G |
| Switching Capacity | 88 Gbps or higher |
| Forwarding Rate | 65 Mpps or higher |
| Management | Web, CLI, SNMP |
| Layer | Layer 2+ with basic Layer 3 features |
| VLAN Support | 802.1Q VLAN, up to 4094 VLANs |
| QoS | 802.1p/DSCP priority |
| Security | Port security, DHCP snooping, IP-MAC binding |

#### 2.4.2 Core Switch

| Specification | Requirement |
|--------------|-------------|
| Ports | 24/48 x 10/100/1000Base-T |
| Uplink | 4-8 x 10G SFP+ |
| Switching Capacity | 256 Gbps or higher |
| Forwarding Rate | 190 Mpps or higher |
| Layer | Layer 3 managed |
| Routing | Static, RIP, OSPF, BGP support |
| Redundancy | VRRP, MSTP, RSTP support |
| Management | Web, CLI, SNMP, Telnet, SSH |

#### 2.4.3 Fiber Optic Infrastructure

| Component | Specification |
|-----------|---------------|
| Fiber Type | Single-mode OS2 |
| Core/Cladding | 9/125 μm |
| Connector Type | LC/UPC or SC/UPC |
| Cable Type | Armored outdoor cable where exposed |
| Patch Panels | 19" rack-mountable with fiber management |
| SFP Modules | 1.25G or 10G compatible |

### 2.5 Cabling Requirements

| Cable Type | Specification | Application |
|------------|---------------|-------------|
| CAT6A UTP | 23 AWG, 500MHz, LSZH | Data transmission |
| Outdoor CAT6 | UV-resistant, gel-filled | Outdoor runs |
| Fiber SM | OS2, single-mode | Backbone/long distance |
| Power Cable | 3-core 2.5mm² PVC | AC power distribution |
| Conduit | 25mm/32mm PVC or metal | Cable protection |
| Trunking | Metal or PVC as specified | Indoor cable management |

### 2.6 Power Supply and Protection

| Component | Specification |
|-----------|---------------|
| UPS Capacity | Sufficient for all critical equipment |
| UPS Type | Online double-conversion |
| Backup Time | Minimum 4 hours for control room |
| Surge Protection | SPD on all power and network lines |
| Lightning Protection | External lightning arrestors for outdoor cameras |
| PDU | Rack-mounted with surge protection |

---

## 3. DELIVERABLES

### 3.1 Equipment Supply Schedule

| Item | Quantity | Unit | Description |
|------|----------|------|-------------|
| Indoor Dome Cameras | As per BOQ | each | 4MP IP Dome, vandal-resistant |
| Outdoor Bullet Cameras | As per BOQ | each | 4MP IP Bullet, weatherproof |
| PTZ Cameras | As per BOQ | each | 2MP 25x optical zoom |
| 32-Channel NVR | As per site | unit | Enterprise NVR |
| 64-Channel NVR | As per site | unit | Enterprise NVR with RAID |
| Hard Disk Drives | Calculated | each | 8TB/10TB Surveillance HDD |
| 24-Port PoE Switch | As per site | unit | Managed PoE+ switch |
| 48-Port PoE Switch | As per site | unit | Managed PoE+ switch |
| Core Switch | 1-2 | unit | Layer 3 managed switch |
| VMS Software | 1 | license | Enterprise VMS with API |
| VMS Server | 1 | unit | High-performance server |
| Monitoring Workstation | 2 | unit | Dual-monitor setup |
| Video Wall/Monitors | As specified | set | 4K display array |
| UPS 10-20kVA | As required | unit | Online UPS |
| UPS Battery Bank | As required | set | Extended runtime |
| Rack Cabinet | As required | unit | 42U server rack |
| Patch Panels | As required | unit | Copper and fiber |
| Cables & Accessories | Complete | lot | All required cabling |

### 3.2 Documentation Package

| Document | Copies | Format |
|----------|--------|--------|
| As-Built Drawings | 3 sets | PDF + CAD |
| System Architecture Diagrams | 3 sets | PDF + Visio |
| Equipment Datasheets | 2 sets | PDF |
| Installation Manuals | 2 sets | Hardcopy + PDF |
| Configuration Guides | 2 sets | PDF |
| User Operation Manuals | 5 sets | Hardcopy + PDF |
| Test and Commissioning Reports | 3 sets | Hardcopy + PDF |
| Training Materials | 10 sets | Hardcopy + PDF |
| Warranty Certificates | Original | Hardcopy |
| Maintenance Schedule | 3 sets | PDF |
| IP Address Allocation Table | 2 sets | PDF |
| Password Documentation (sealed) | 2 sets | Hardcopy |

### 3.3 Software Deliverables

| Item | Description |
|------|-------------|
| VMS Software | Licensed and activated |
| Camera Firmware | Latest stable version |
| Device Configuration Files | Backup of all configurations |
| Integration APIs | Documentation and SDKs |
| Mobile Apps | iOS and Android versions |

---

## 4. INSTALLATION REQUIREMENTS

### 4.1 Camera Installation Standards

| Aspect | Requirement |
|--------|-------------|
| Mounting Height | 2.5m - 4m (indoor), 3m - 6m (outdoor) |
| Camera Angle | Optimized for intended field of view |
| Cable Entry | Sealed to prevent water ingress |
| Grounding | Properly grounded per electrical code |
| Surge Protection | SPD installed at camera and control room |
| Labeling | Unique ID labels at camera and patch panel |

### 4.2 Control Room Installation

| Component | Specification |
|-----------|---------------|
| Server Rack | 42U, 800mm x 1000mm, ventilated |
| Cable Management | Horizontal and vertical cable organizers |
| Power Distribution | PDU with surge protection |
| Climate Control | 18-24°C, 40-60% humidity |
| Dust Control | Positive pressure or filtered air |
| Lighting | Suitable for monitor viewing |
| Ergonomics | Adjustable seating, proper sightlines |
| Access Control | Restricted access, keycard or biometric |

### 4.3 Network Architecture Diagram

```
                         ┌─────────────────────────────────────────┐
                         │          MONITORING CENTER              │
                         │  ┌─────────┐    ┌───────────────────┐  │
                         │  │  VMS    │    │  Video Wall/      │  │
                         │  │ Server  │    │  Workstations     │  │
                         │  └────┬────┘    └───────────────────┘  │
                         │       │                                 │
                         │  ┌────┴────┐    ┌─────────┐             │
                         │  │   NVR   │    │  NVR    │             │
                         │  │Primary  │    │ Backup  │             │
                         │  └────┬────┘    └────┬────┘             │
                         │       │              │                  │
                         └───────┼──────────────┼──────────────────┘
                                 │              │
                    ┌────────────┴──────────────┴────────────┐
                    │              CORE SWITCH                │
                    │         (Layer 3, 10G Uplinks)          │
                    └────────────┬────────────────┬───────────┘
                                 │                │
            ┌────────────────────┼────────────────┼────────────────────┐
            │                    │                │                    │
      ┌─────┴─────┐        ┌────┴─────┐    ┌────┴─────┐        ┌────┴─────┐
      │ PoE Switch │        │ PoE Switch│    │ PoE Switch│        │ PoE Switch│
      │  Zone 1    │        │  Zone 2   │    │  Zone 3   │        │  Zone 4   │
      └─────┬─────┘        └────┬─────┘    └────┬─────┘        └────┬─────┘
            │                   │                │                   │
      ┌─────┴─────┐        ┌────┴─────┐    ┌────┴─────┐        ┌────┴─────┐
      │  Cameras  │        │  Cameras │    │  Cameras │        │  Cameras │
      │  Zone 1   │        │  Zone 2  │    │  Zone 3  │        │  Zone 4  │
      └───────────┘        └──────────┘    └──────────┘        └──────────┘
```

---

## 5. TESTING AND COMMISSIONING

### 5.1 Pre-Installation Testing

| Test | Description |
|------|-------------|
| Equipment Inspection | Visual check for damage, verify model numbers |
| Factory Reset | All devices to factory defaults before configuration |
| Firmware Update | Apply latest stable firmware versions |
| Bench Testing | Verify all devices power on and respond |

### 5.2 Installation Testing

| Test Category | Test Items | Acceptance Criteria |
|---------------|------------|---------------------|
| Physical | Mounting, cabling, labeling | Secure, neat, properly labeled |
| Electrical | Voltage, grounding, PoE | Within specifications |
| Network | Connectivity, bandwidth | <1% packet loss |
| Camera | Video quality, angle, focus | Clear image, correct FOV |
| PTZ | Pan, tilt, zoom, presets | Full range, accurate presets |
| IR | Night vision coverage | Even illumination |

### 5.3 System Integration Testing

| Test | Procedure |
|------|-----------|
| NVR Configuration | Verify all cameras recording correctly |
| Storage Test | Verify 30-day retention calculation |
| Failover Test | Simulate network failure, verify ANR |
| Backup/Restore | Test configuration backup and restore |
| VMS Integration | Verify all cameras visible in VMS |
| User Access | Test user roles and permissions |
| Mobile Access | Verify remote viewing capability |

### 5.4 Acceptance Testing

| Criteria | Requirement |
|----------|-------------|
| Video Quality | Minimum 4MP resolution, no artifacts |
| Frame Rate | 15fps minimum at full resolution |
| Recording | Continuous 30 days verified |
| Network Performance | <5% packet loss, latency <50ms |
| System Availability | 99.5% uptime target |
| User Acceptance | Signed off by client representatives |

---

## 6. MAINTENANCE AND SUPPORT

### 6.1 Warranty Terms

| Component | Warranty Period |
|-----------|-----------------|
| All Cameras | 36 months |
| NVR/DVR | 36 months |
| Network Equipment | 36 months |
| Server/Workstation | 36 months |
| Hard Disk Drives | 36 months |
| Software | 24 months support and updates |
| Labor | 24 months |

### 6.2 Maintenance Schedule

| Service | Frequency | Description |
|---------|-----------|-------------|
| Routine Inspection | Monthly | Visual check, cleaning |
| Preventive Maintenance | Quarterly | Deep cleaning, connection check |
| System Health Check | Monthly | Performance verification |
| Firmware Updates | As released | Security and feature updates |
| Training Refresher | Annually | User retraining as needed |

### 6.3 Response Times

| Severity | Response Time | Resolution Target |
|----------|---------------|-------------------|
| Critical (System Down) | 4 hours | 24 hours |
| Major (Partial Failure) | 8 hours | 48 hours |
| Minor (Single Device) | 24 hours | 72 hours |
| Cosmetic/Query | 48 hours | 7 days |

### 6.4 Training Program

| Training | Duration | Attendees | Content |
|----------|----------|-----------|---------|
| Operator Training | 1 day | Security staff | Basic operation, playback |
| Administrator Training | 2 days | IT staff | Configuration, user management |
| Technical Training | 2 days | Maintenance staff | Troubleshooting, maintenance |

---

## PAGE REFERENCE INDEX

| Page Range | Content Description |
|------------|---------------------|
| Page 049-50 | Document introduction and scope |
| Page 051-52 | General technical specifications |
| Page 053-57 | Camera specifications (Dome, Bullet, PTZ) |
| Page 058-60 | NVR and storage specifications |
| Page 061-63 | Network infrastructure requirements |
| Page 064-66 | Installation and commissioning |

---

## APPENDICES

### Appendix A: Equipment Bill of Quantities
*(To be extracted from tender document BOQ section)*

### Appendix B: Site Layout Drawings
*(To be provided during implementation)*

### Appendix C: IP Addressing Scheme
*(To be designed during implementation)*

---

## NOTES

1. **OCR Limitations:** This document was generated from OCR-extracted text. Some technical terms may have been interpreted based on context where the original text was unclear or mirrored.

2. **Reference Standards:** All equipment shall meet or exceed the specifications outlined in this document. Equivalent or superior products may be proposed with prior written approval from the Principal.

3. **Compliance:** The contractor shall ensure full compliance with:
   - Local authority regulations
   - Electrical safety standards
   - Manufacturer installation guidelines
   - Malaysian Communications and Multimedia Commission guidelines

4. **Variations:** Any variations from the specified requirements must be submitted in writing and approved by the Principal before implementation.

5. **Documentation:** All documentation shall be provided in both hard copy and electronic (PDF) formats.

---

*Document Generated: Technical Specification for Tender TSH-2614*
*MAJLIS PERBANDARAN KUALA TERENGGANU*
*Date: January 2025*
