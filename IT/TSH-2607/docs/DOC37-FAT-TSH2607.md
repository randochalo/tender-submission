# DOC37-FAT-TSH2607.md
# Factory Acceptance Test (FAT) Report Template
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC37-FAT-TSH2607 |
| Version | 1.0 |
| Template Date | January 2025 |
| Status | Template |
| Project | TSH-2607 MCMC UCMS |

---

## INSTRUCTIONS

This Factory Acceptance Test (FAT) report documents the testing performed at the vendor's facility before shipment to the customer site. Complete all sections to verify that delivered equipment and software meet specifications.

---

## FACTORY ACCEPTANCE TEST REPORT

### SECTION A: GENERAL INFORMATION

| Field | Details |
|-------|---------|
| FAT Report No | FAT-UCMS-[EQUIP]-[YYYY]-[###] |
| Test Date | DD/MM/YYYY |
| Test Location | |
| Equipment/System Description | |
| Manufacturer/Vendor | |
| Model/Version | |
| Serial Number(s) | |
| Purchase Order Reference | |
| Related Delivery Order | |

#### Test Participants

| Role | Name | Organization | Signature | Date |
|------|------|--------------|-----------|------|
| Test Engineer (Vendor) | | | | |
| Test Engineer (Customer) | | | | |
| Technical Witness | | | | |
| QA Representative | | | | |

---

### SECTION B: TEST ENVIRONMENT

#### B.1 Test Setup

| Component | Specification | Actual | Status |
|-----------|---------------|--------|--------|
| Test Location | | | |
| Ambient Temperature | 18-27°C | | □ OK □ NOK |
| Humidity | 40-60% RH | | □ OK □ NOK |
| Power Supply | 240V AC, 50Hz | | □ OK □ NOK |
| Network Connectivity | | | □ OK □ NOK |
| Test Equipment Used | | | |

#### B.2 Test Configuration

| Item | Configuration |
|------|---------------|
| Hardware Configuration | |
| Software Version | |
| Firmware Version | |
| BIOS/UEFI Version | |
| Network Settings | |
| Test Data Used | |

---

### SECTION C: DOCUMENTATION VERIFICATION

| Document | Required | Provided | Version | Status |
|----------|----------|----------|---------|--------|
| Product Data Sheet | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Technical Specifications | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| User Manual | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Installation Guide | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Configuration Guide | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Warranty Certificate | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Calibration Certificate | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| Test Certificate | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| License/Activation Keys | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |
| MSDS/Safety Data Sheet | □ Yes □ No | □ Yes □ No | | □ Pass □ Fail |

---

### SECTION D: PHYSICAL INSPECTION

| Inspection Item | Criteria | Result | Status |
|-----------------|----------|--------|--------|
| Equipment Identification | Correct labels and markings | | □ Pass □ Fail |
| Physical Condition | No visible damage | | □ Pass □ Fail |
| Packaging | Adequate protection | | □ Pass □ Fail |
| Accessories Complete | All items per BOM | | □ Pass □ Fail |
| Cables and Connectors | Present and undamaged | | □ Pass □ Fail |
| Rack Mount Kit | Included if applicable | | □ Pass □ Fail |
| Power Cords | Correct type and rating | | □ Pass □ Fail |
| Serial Number Verification | Matches documentation | | □ Pass □ Fail |

---

### SECTION E: FUNCTIONAL TESTS

#### E.1 Power-On Self Test (POST)

| Test Step | Expected Result | Actual Result | Status |
|-----------|-----------------|---------------|--------|
| Power on device | System boots without errors | | □ Pass □ Fail |
| POST completion | All tests pass | | □ Pass □ Fail |
| Boot time | Within specification (< ___ min) | | □ Pass □ Fail |
| Error indicators | No error LEDs/messages | | □ Pass □ Fail |

#### E.2 Hardware Component Tests

| Component | Test Description | Expected Result | Actual Result | Status |
|-----------|------------------|-----------------|---------------|--------|
| CPU | Stress test | Pass 100% load for 1 hour | | □ Pass □ Fail |
| Memory | Memory test | No errors detected | | □ Pass □ Fail |
| Storage | SMART check + read/write | All sectors readable | | □ Pass □ Fail |
| Network Interface | Connectivity test | Full duplex, no errors | | □ Pass □ Fail |
| Power Supply | Load test | Stable under load | | □ Pass □ Fail |
| Cooling | Temperature monitoring | Within operating range | | □ Pass □ Fail |
| RAID Controller | Array status | Optimal status | | □ Pass □ Fail |
| Remote Management | IPMI/iLO/iDRAC test | Accessible and functional | | □ Pass □ Fail |

#### E.3 Software/Functional Tests

| Test ID | Test Description | Expected Result | Actual Result | Status |
|---------|------------------|-----------------|---------------|--------|
| F001 | Software installation | Successful installation | | □ Pass □ Fail |
| F002 | License activation | Valid license applied | | □ Pass □ Fail |
| F003 | Basic configuration | Settings applied correctly | | □ Pass □ Fail |
| F004 | User authentication | Login functional | | □ Pass □ Fail |
| F005 | Core functionality | Features working as spec | | □ Pass □ Fail |
| F006 | Database connectivity | Connection successful | | □ Pass □ Fail |
| F007 | API functionality | Endpoints respond correctly | | □ Pass □ Fail |
| F008 | Backup/Restore | Backup completed successfully | | □ Pass □ Fail |

---

### SECTION F: PERFORMANCE TESTS

| Test ID | Metric | Specification | Test Result | Status |
|---------|--------|---------------|-------------|--------|
| P001 | Boot time | < 5 minutes | | □ Pass □ Fail |
| P002 | CPU benchmark | Within 10% of reference | | □ Pass □ Fail |
| P003 | Memory throughput | Within 10% of reference | | □ Pass □ Fail |
| P004 | Disk I/O (Read) | > 500 MB/s (SSD) | | □ Pass □ Fail |
| P005 | Disk I/O (Write) | > 400 MB/s (SSD) | | □ Pass □ Fail |
| P006 | Network throughput | > 900 Mbps (1G) | | □ Pass □ Fail |
| P007 | Latency | < 1 ms local | | □ Pass □ Fail |
| P008 | Application response | < 2 seconds | | □ Pass □ Fail |

---

### SECTION G: SECURITY VERIFICATION

| Test ID | Security Check | Method | Result | Status |
|---------|----------------|--------|--------|--------|
| S001 | Default passwords changed | Attempt login | | □ Pass □ Fail |
| S002 | Unnecessary services disabled | Port scan | | □ Pass □ Fail |
| S003 | Security patches current | Vulnerability scan | | □ Pass □ Fail |
| S004 | Firewall rules applied | Rule verification | | □ Pass □ Fail |
| S005 | Encryption enabled | Configuration check | | □ Pass □ Fail |
| S006 | Access controls configured | Permission check | | □ Pass □ Fail |
| S007 | Audit logging enabled | Log verification | | □ Pass □ Fail |

---

### SECTION H: CONFIGURATION VERIFICATION

| Configuration Item | Specification | As-Built | Match | Status |
|--------------------|---------------|----------|-------|--------|
| Hostname | | | □ Yes □ No | □ Pass □ Fail |
| IP Address | | | □ Yes □ No | □ Pass □ Fail |
| Subnet Mask | | | □ Yes □ No | □ Pass □ Fail |
| Gateway | | | □ Yes □ No | □ Pass □ Fail |
| DNS Servers | | | □ Yes □ No | □ Pass □ Fail |
| NTP Servers | | | □ Yes □ No | □ Pass □ Fail |
| Time Zone | Asia/Kuala_Lumpur | | □ Yes □ No | □ Pass □ Fail |
| Admin User | | | □ Yes □ No | □ Pass □ Fail |
| SNMP Configuration | | | □ Yes □ No | □ Pass □ Fail |

---

### SECTION I: INTEGRATION TESTS (If Applicable)

| Test ID | Integration Point | Test Description | Expected Result | Actual Result | Status |
|---------|-------------------|------------------|-----------------|---------------|--------|
| I001 | | | | | □ Pass □ Fail |
| I002 | | | | | □ Pass □ Fail |
| I003 | | | | | □ Pass □ Fail |

---

### SECTION J: NON-CONFORMANCE REPORT

#### J.1 Issues Identified

| NCR No | Description | Severity | Corrective Action | Verified By | Status |
|--------|-------------|----------|-------------------|-------------|--------|
| | | □ Critical □ Major □ Minor | | | □ Open □ Closed |
| | | □ Critical □ Major □ Minor | | | □ Open □ Closed |
| | | □ Critical □ Major □ Minor | | | □ Open □ Closed |

#### J.2 Issue Summary

| Category | Count | Open | Closed |
|----------|-------|------|--------|
| Critical | | | |
| Major | | | |
| Minor | | | |
| **TOTAL** | | | |

---

### SECTION K: TEST RESULTS SUMMARY

#### K.1 Test Execution Summary

| Test Category | Total | Passed | Failed | Not Run | Pass Rate |
|---------------|-------|--------|--------|---------|-----------|
| Documentation | | | | | |
| Physical Inspection | | | | | |
| Functional Tests | | | | | |
| Performance Tests | | | | | |
| Security Tests | | | | | |
| Configuration Tests | | | | | |
| Integration Tests | | | | | |
| **TOTAL** | | | | | |

#### K.2 Overall Assessment

| Assessment | Result |
|------------|--------|
| Documentation Complete | □ Yes □ No |
| Physical Inspection Passed | □ Yes □ No |
| Functional Requirements Met | □ Yes □ No |
| Performance Requirements Met | □ Yes □ No |
| Security Requirements Met | □ Yes □ No |
| All Critical Tests Passed | □ Yes □ No |
| **OVERALL FAT RESULT** | □ **PASS** □ **FAIL** |

---

### SECTION L: ACCEPTANCE

#### L.1 FAT Result

| Result | □ ACCEPTED □ ACCEPTED WITH CONDITIONS □ REJECTED |
|--------|---------------------------------------------------|

#### L.2 Conditions (If Applicable)

| # | Condition | Resolution Required | Target Date |
|---|-----------|---------------------|-------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

#### L.3 Signatures

##### Vendor Representative

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Company | |
| Signature | |
| Date | |

##### Customer Representative (MCMC/Contractor)

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Organization | |
| Signature | |
| Date | |

##### Independent Witness (If Required)

| Field | Details |
|-------|---------|
| Name | |
| Designation | |
| Signature | |
| Date | |

---

### SECTION M: APPENDICES

| Appendix | Description | Included |
|----------|-------------|----------|
| A | Test procedure details | □ Yes □ No |
| B | Test data sets used | □ Yes □ No |
| C | Performance benchmark results | □ Yes □ No |
| D | Configuration files (sanitized) | □ Yes □ No |
| E | Screenshots/evidence | □ Yes □ No |
| F | Calibration certificates for test equipment | □ Yes □ No |

---

**Notes:**
1. All test equipment used must be calibrated and certificates attached
2. Any deviations from specifications must be documented as NCRs
3. FAT acceptance does not waive any warranty rights
4. Conditional acceptance requires written commitment for resolution

---

**Document Control:** Original - Customer | Copy - Vendor | Copy - Project Office
