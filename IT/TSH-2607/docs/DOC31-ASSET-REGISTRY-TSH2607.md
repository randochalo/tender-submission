# DOC31-ASSET-REGISTRY-TSH2607.md
# Asset Registry and Tagging Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC31-ASSET-REGISTRY-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This Asset Registry template is used to track all physical and digital assets procured and deployed under the UCMS project. Each asset requires unique identification and tagging.

---

## ASSET REGISTRY

### ASSET TAGGING CONVENTION

**Format:** `UCMS-[CATEGORY]-[YYYY]-[#####]`

| Category Code | Description |
|---------------|-------------|
| SRV | Server |
| NET | Network Equipment |
| STO | Storage Device |
| WKS | Workstation |
| LPT | Laptop |
| MON | Monitor |
| PRN | Printer |
| UPS | UPS/Power |
| SEC | Security Equipment |
| LIC | Software License |
| PER | Peripheral |
| CAB | Cabinet/Rack |
| OTH | Other |

---

### ASSET REGISTRATION FORM

#### SECTION A: ASSET IDENTIFICATION

| Field | Details |
|-------|---------|
| Asset Tag Number | UCMS-_____-_____-_____ |
| Asset Category | |
| Asset Type | |
| Asset Description | |
| Manufacturer | |
| Brand | |
| Model | |
| Model Number | |
| Part Number | |
| Serial Number | |
| SKU/Item Code | |

#### SECTION B: ACQUISITION DETAILS

| Field | Details |
|-------|---------|
| Purchase Order No | |
| Delivery Order No | |
| Vendor/Supplier | |
| Vendor Contact | |
| Date Purchased | DD/MM/YYYY |
| Date Received | DD/MM/YYYY |
| Purchase Cost | RM _______ |
| Currency | □ MYR □ USD □ EUR □ Other |
| Warranty Period | _______ months/years |
| Warranty Start Date | DD/MM/YYYY |
| Warranty End Date | DD/MM/YYYY |
| Warranty Reference | |
| Insurance Value | RM _______ |

#### SECTION C: SPECIFICATIONS

##### C.1 Hardware Specifications

| Component | Specification |
|-----------|---------------|
| Processor / CPU | |
| Memory / RAM | |
| Storage Capacity | |
| Storage Type | □ HDD □ SSD □ NVMe □ Other |
| Graphics | |
| Network Interface | |
| Ports/Connectivity | |
| Power Rating | |
| Dimensions (H×W×D) | _______ × _______ × _______ cm |
| Weight | _______ kg |
| Color | |

##### C.2 Software Specifications

| Component | Specification |
|-----------|---------------|
| Operating System | |
| OS Version | |
| OS License Key | |
| Installed Software | |
| Software Versions | |
| License Type | □ Perpetual □ Subscription □ Open Source |
| License Expiry | DD/MM/YYYY |
| Number of Licenses | |
| License Key(s) | |

#### SECTION D: LOCATION AND ASSIGNMENT

| Field | Details |
|-------|---------|
| Current Location | |
| Building | |
| Floor/Level | |
| Room/Area | |
| Rack/Cabinet No | |
| Shelf/Position | |
| GPS Coordinates | |
| Assigned Department | |
| Cost Center | |
| Assigned To (Name) | |
| Employee ID | |
| Assignment Date | DD/MM/YYYY |
| Expected Return Date | DD/MM/YYYY |

#### SECTION E: ASSET STATUS

| Field | Status |
|-------|--------|
| Current Status | □ In Storage □ In Transit □ Deployed □ In Use □ Under Maintenance □ Retired □ Disposed |
| Condition | □ New □ Excellent □ Good □ Fair □ Poor □ Damaged |
| Functional Status | □ Operational □ Non-Operational □ Partially Operational |
| Availability | □ Available □ Allocated □ Reserved □ Quarantined |

#### SECTION F: MAINTENANCE INFORMATION

| Field | Details |
|-------|---------|
| Maintenance Provider | |
| Support Contract No | |
| Support Level | □ 24×7 □ Business Hours □ Next Business Day |
| Last Maintenance Date | DD/MM/YYYY |
| Next Scheduled Maintenance | DD/MM/YYYY |
| Maintenance Notes | |

#### SECTION G: DOCUMENTATION

| Document Type | Available | Reference |
|---------------|-----------|-----------|
| Purchase Invoice | □ Yes □ No | |
| Delivery Order | □ Yes □ No | |
| Packing List | □ Yes □ No | |
| User Manual | □ Yes □ No | |
| Technical Manual | □ Yes □ No | |
| Certificate of Warranty | □ Yes □ No | |
| Calibration Certificate | □ Yes □ N/A | |
| Test Report | □ Yes □ No | |
| Configuration Document | □ Yes □ No | |
| Photos | □ Yes □ No | |

#### SECTION H: DEPRECIATION AND VALUATION

| Field | Details |
|-------|---------|
| Depreciation Method | □ Straight Line □ Reducing Balance |
| Useful Life (Years) | |
| Salvage Value | RM _______ |
| Annual Depreciation | RM _______ |
| Current Book Value | RM _______ |
| Revaluation Date | DD/MM/YYYY |
| Revaluation Amount | RM _______ |

---

## MASTER ASSET REGISTER

### Hardware Assets

| Asset Tag | Category | Description | Brand/Model | Serial No | Location | Status | User |
|-----------|----------|-------------|-------------|-----------|----------|--------|------|
| UCMS-SRV-2025-00001 | SRV | Application Server | Dell R750 | | Data Center | In Storage | - |
| UCMS-SRV-2025-00002 | SRV | Database Server | Dell R750 | | Data Center | In Storage | - |
| UCMS-SRV-2025-00003 | SRV | Database Server | Dell R750 | | Data Center | In Storage | - |
| UCMS-NET-2025-00001 | NET | Core Switch | Cisco Catalyst | | Data Center | In Storage | - |
| UCMS-NET-2025-00002 | NET | Firewall | Palo Alto PA-3220 | | Data Center | In Storage | - |
| UCMS-STO-2025-00001 | STO | SAN Storage | Dell EMC Unity | | Data Center | In Storage | - |
| UCMS-UPS-2025-00001 | UPS | UPS 10kVA | APC Smart-UPS | | Data Center | In Storage | - |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

### Software Assets

| Asset Tag | Category | Description | Version | Licenses | Expiry Date | Location | Status |
|-----------|----------|-------------|---------|----------|-------------|----------|--------|
| UCMS-LIC-2025-00001 | LIC | Operating System License | Windows Server 2022 | 10 | Perpetual | Data Center | Active |
| UCMS-LIC-2025-00002 | LIC | Database License | PostgreSQL Enterprise | 1 | 31/12/2028 | Data Center | Active |
| UCMS-LIC-2025-00003 | LIC | Antivirus License | CrowdStrike | 100 | 31/12/2026 | All Sites | Active |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

---

## ASSET MOVEMENT LOG

| Movement ID | Asset Tag | From Location | To Location | Movement Date | Moved By | Authorized By | Reason |
|-------------|-----------|---------------|-------------|---------------|----------|---------------|--------|
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

---

## ASSET MAINTENANCE LOG

| Maintenance ID | Asset Tag | Date | Type | Description | Performed By | Cost | Next Due |
|----------------|-----------|------|------|-------------|--------------|------|----------|
| | | | □ Preventive □ Corrective □ Upgrade | | | | |
| | | | □ Preventive □ Corrective □ Upgrade | | | | |
| | | | □ Preventive □ Corrective □ Upgrade | | | | |
| | | | □ Preventive □ Corrective □ Upgrade | | | | |
| | | | □ Preventive □ Corrective □ Upgrade | | | | |

---

## ASSET DISPOSAL LOG

| Asset Tag | Description | Disposal Date | Method | Approved By | Sale Value | Certificate Ref |
|-----------|-------------|---------------|--------|-------------|------------|-----------------|
| | | | □ Sold □ Donated □ Recycled □ Destroyed | | | |
| | | | □ Sold □ Donated □ Recycled □ Destroyed | | | |
| | | | □ Sold □ Donated □ Recycled □ Destroyed | | | |
| | | | □ Sold □ Donated □ Recycled □ Destroyed | | | |

---

## PHYSICAL ASSET TAG SPECIFICATIONS

### Tag Format

**Size:** 50mm × 25mm (standard) or 75mm × 50mm (large equipment)

**Material:** Aluminum (for servers/network) / Polyester (for workstations)

**Adhesive:** Industrial-grade permanent adhesive

**Printing:** Thermal transfer, barcode + human-readable

### Tag Layout

```
┌─────────────────────────────────────────┐
│  TSH-2607 UCMS PROJECT                  │
│                                         │
│  ┌──────────────┐                       │
│  │ ▄▄▄▄ ▄▄▄▄    │  ASSET TAG:          │
│  │ ▄▄▄▄ ▄▄▄▄    │  UCMS-SRV-2025-00001 │
│  │ ▄▄▄▄ ▄▄▄▄    │                       │
│  │ ▄▄▄▄ ▄▄▄▄    │  DESC: Dell Server   │
│  └──────────────┘                       │
│                                         │
│  MCMC Property - Do Not Remove          │
└─────────────────────────────────────────┘
```

### Tag Placement Guidelines

| Asset Type | Tag Placement |
|------------|---------------|
| Servers | Front bezel or top panel |
| Network Equipment | Front panel, upper right |
| Storage | Front bezel |
| Workstations | Top or side panel |
| Laptops | Palm rest or lid |
| Monitors | Back panel, upper right |
| UPS | Front panel |
| Racks | Front door, upper right |

---

## BARCODE/QR CODE STANDARDS

### Barcode Format
- **Type:** Code 128
- **Density:** High
- **Check Digit:** Mod 103

### QR Code Format
- **Version:** 4 (33×33 modules)
- **Error Correction:** Level M (15%)
- **Data Format:** JSON encoded

### QR Code Data Structure
```json
{
  "asset_tag": "UCMS-SRV-2025-00001",
  "category": "SRV",
  "description": "Dell PowerEdge R750",
  "serial": "ABC123456789",
  "location": "DC-FL1-RK03",
  "url": "https://assets.ucms.mcmc.gov.my/UCMS-SRV-2025-00001"
}
```

---

## ASSET INVENTORY PROCEDURES

### Monthly Inventory Check
1. Generate asset location report
2. Verify physical presence of high-value items
3. Update location changes
4. Report missing items within 24 hours

### Annual Full Inventory
1. Schedule during maintenance window
2. Scan all asset tags
3. Verify condition and status
4. Reconcile with register
5. Update depreciation values
6. Identify disposal candidates

### Asset Disposal Procedure
1. Identify asset for disposal
2. Obtain written approval
3. Backup and sanitize data
4. Remove asset tags
5. Update register status
6. Complete disposal log
7. Issue disposal certificate

---

**Confidentiality Notice:** This asset registry contains sensitive procurement information. Access is restricted to authorized personnel only.

**Document Control:** Original - Project Office | Copy - Finance | Copy - Technical Team | Copy - Asset Custodian
