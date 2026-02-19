# DOC28-IDD-TSH2607.md
# Infrastructure Design Document (IDD)
## TSH-2607 Universal Service Provision (USP) Claims Management System (UCMS)

---

**Document Information**

| Attribute | Value |
|-----------|-------|
| Document ID | DOC28-IDD-TSH2607 |
| Version | 1.0 |
| Date | January 2025 |
| Status | Draft |
| Classification | Confidential |
| Project | TSH-2607 MCMC UCMS |

---

## 1.0 INTRODUCTION

### 1.1 Purpose
This Infrastructure Design Document (IDD) defines the complete technical infrastructure architecture for the Universal Service Provision (USP) Claims Management System (UCMS), including hardware, network, storage, security, and deployment specifications.

### 1.2 Scope
This document covers:
- System architecture and topology
- Server specifications and configurations
- Network infrastructure design
- Storage architecture
- Security infrastructure
- Backup and disaster recovery infrastructure
- Monitoring and management systems

### 1.3 Infrastructure Principles

| Principle | Description |
|-----------|-------------|
| High Availability | 99.9% uptime target with redundant components |
| Scalability | Horizontal scaling capability for peak loads |
| Security | Defense-in-depth security architecture |
| Performance | Sub-3 second response time for all transactions |
| Compliance | Adherence to government security standards |

---

## 2.0 SYSTEM ARCHITECTURE

### 2.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              INTERNET                                        │
└─────────────────────────────────┬───────────────────────────────────────────┘
                                  │
┌─────────────────────────────────▼───────────────────────────────────────────┐
│                         PERIMETER SECURITY                                  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   Firewall   │  │     WAF      │  │  DDoS Prot.  │  │   VPN GW     │    │
│  │  (Primary)   │  │   (Layer 7)  │  │              │  │              │    │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘    │
└─────────────────────────────────┬───────────────────────────────────────────┘
                                  │
┌─────────────────────────────────▼───────────────────────────────────────────┐
│                         DMZ / EDGE LAYER                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                      LOAD BALANCER CLUSTER                          │   │
│  │              (Application Delivery Controllers)                     │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │   API Gateway    │  │  Reverse Proxy   │  │  CDN Endpoint    │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
└─────────────────────────────────┬───────────────────────────────────────────┘
                                  │
┌─────────────────────────────────▼───────────────────────────────────────────┐
│                         APPLICATION TIER                                    │
│  ┌─────────────────────────────────────────────────────────────────────┐   │
│  │                    KUBERNETES CLUSTER                               │   │
│  │  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐       │   │
│  │  │ Web Server │ │   API      │ │  Workflow  │ │  Report    │       │   │
│  │  │   Pods     │ │  Server    │ │  Engine    │ │  Server    │       │   │
│  │  │  (x6)      │ │   Pods     │ │   Pods     │ │   Pods     │       │   │
│  │  └────────────┘ │   (x6)     │ │   (x4)     │ │   (x2)     │       │   │
│  │                 └────────────┘ └────────────┘ └────────────┘       │   │
│  └─────────────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────┬───────────────────────────────────────────┘
                                  │
┌─────────────────────────────────▼───────────────────────────────────────────┐
│                         DATA TIER                                           │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │  Primary DB      │  │  Replica DB      │  │  Cache Cluster   │         │
│  │  (PostgreSQL)    │◄►│  (Read Replica)  │  │  (Redis Cluster) │         │
│  │                  │  │                  │  │                  │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐         │
│  │  Object Storage  │  │  Search Engine   │  │  Message Queue   │         │
│  │  (MinIO/S3)      │  │  (Elasticsearch) │  │  (RabbitMQ)      │         │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘         │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│                         MANAGEMENT & SECURITY                               │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐    │
│  │   SIEM       │  │    AD/LDAP   │  │   Backup     │  │   Jump Host  │    │
│  │  (Wazuh)     │  │   Server     │  │   Server     │  │   (Bastion)  │    │
│  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐                       │
│  │  Monitoring  │  │   Logging    │  │   Vault      │                       │
│  │ (Prometheus) │  │   (ELK)      │  │  (Secrets)   │                       │
│  └──────────────┘  └──────────────┘  └──────────────┘                       │
└─────────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Environment Architecture

| Environment | Purpose | Configuration |
|-------------|---------|---------------|
| Production | Live system serving public | Full HA, 3 AZ |
| Staging | Pre-production validation | Reduced HA, 2 AZ |
| UAT | User acceptance testing | Single AZ, smaller |
| Development | Development activities | Minimal, on-demand |
| DR | Disaster recovery | Warm standby |

---

## 3.0 SERVER SPECIFICATIONS

### 3.1 Production Environment

#### 3.1.1 Web/Application Servers

| Specification | Value |
|---------------|-------|
| Quantity | 6 nodes |
| Platform | Virtual Machines / Cloud Instances |
| vCPU | 8 cores per node |
| Memory | 32 GB RAM per node |
| Storage | 200 GB SSD per node |
| OS | Ubuntu Server 22.04 LTS |
| Role | Web server, Application hosting |
| Scaling | Auto-scaling: 4-12 nodes |

#### 3.1.2 API Servers

| Specification | Value |
|---------------|-------|
| Quantity | 6 nodes |
| Platform | Kubernetes Worker Nodes |
| vCPU | 8 cores per node |
| Memory | 32 GB RAM per node |
| Storage | 300 GB SSD per node |
| OS | Ubuntu Server 22.04 LTS |
| Role | API services, Business logic |
| Scaling | Auto-scaling: 4-10 nodes |

#### 3.1.3 Database Servers

**Primary Database:**

| Specification | Value |
|---------------|-------|
| Quantity | 2 nodes (Primary + Standby) |
| Platform | Bare Metal / High-Performance VM |
| CPU | 16 cores per node |
| Memory | 64 GB RAM per node |
| Storage | 2 TB NVMe SSD per node |
| OS | Ubuntu Server 22.04 LTS |
| Database | PostgreSQL 15 |
| Role | Primary transactional database |
| Replication | Synchronous to standby |

**Read Replicas:**

| Specification | Value |
|---------------|-------|
| Quantity | 2 nodes |
| Platform | Virtual Machines |
| vCPU | 8 cores per node |
| Memory | 32 GB RAM per node |
| Storage | 1 TB SSD per node |
| Role | Read-only queries, reporting |

#### 3.1.4 Cache Servers

| Specification | Value |
|---------------|-------|
| Quantity | 3 nodes (Redis Cluster) |
| Platform | Virtual Machines |
| vCPU | 4 cores per node |
| Memory | 16 GB RAM per node |
| Storage | 100 GB SSD per node |
| Software | Redis 7.x |
| Role | Session storage, caching |

#### 3.1.5 Search Servers

| Specification | Value |
|---------------|-------|
| Quantity | 3 nodes |
| Platform | Virtual Machines |
| vCPU | 8 cores per node |
| Memory | 32 GB RAM per node |
| Storage | 500 GB SSD per node |
| Software | Elasticsearch 8.x |
| Role | Full-text search, analytics |

### 3.2 Server Hardware Summary

| Tier | Count | Total vCPUs | Total RAM | Total Storage |
|------|-------|-------------|-----------|---------------|
| Web/App | 6 | 48 | 192 GB | 1.2 TB |
| API | 6 | 48 | 192 GB | 1.8 TB |
| Database | 4 | 48 | 192 GB | 6 TB |
| Cache | 3 | 12 | 48 GB | 300 GB |
| Search | 3 | 24 | 96 GB | 1.5 TB |
| Management | 6 | 24 | 96 GB | 1.5 TB |
| **TOTAL** | **28** | **204** | **816 GB** | **12.3 TB** |

---

## 4.0 NETWORK INFRASTRUCTURE

### 4.1 Network Topology

```
┌─────────────────────────────────────────────────────────────────┐
│                        NETWORK DIAGRAM                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Internet                                                       │
│     │                                                           │
│     ▼                                                           │
│  ┌─────────┐     ┌─────────┐     ┌─────────┐                   │
│  │  ISP 1  │────►│   FW    │◄────│  ISP 2  │  (Redundant ISP)  │
│  └─────────┘     │ Primary │     └─────────┘                   │
│                  └────┬────┘                                   │
│                  ┌────┴────┐                                   │
│                  │   FW    │  (Secondary Firewall)              │
│                  │ Standby │                                   │
│                  └────┬────┘                                   │
│                       ▼                                         │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    CORE SWITCH                          │   │
│  │              (L3 Switch - Redundant)                    │   │
│  └────────────────────┬────────────────────────────────────┘   │
│                       │                                         │
│        ┌──────────────┼──────────────┐                         │
│        │              │              │                         │
│        ▼              ▼              ▼                         │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐                   │
│  │   DMZ    │   │  APP NET │   │  DB NET  │  (VLANs)          │
│  │  VLAN 10 │   │  VLAN 20 │   │  VLAN 30 │                   │
│  └──────────┘   └──────────┘   └──────────┘                   │
│        │              │              │                         │
│        ▼              ▼              ▼                         │
│  ┌──────────┐   ┌──────────┐   ┌──────────┐                   │
│  │ DMZ SW   │   │ APP SW   │   │  DB SW   │  (Access Switches)│
│  └──────────┘   └──────────┘   └──────────┘                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### 4.2 Network Segmentation

| VLAN | Purpose | Subnet | CIDR |
|------|---------|--------|------|
| VLAN 10 | DMZ/Public | 10.1.10.0 | /24 |
| VLAN 20 | Application | 10.1.20.0 | /24 |
| VLAN 30 | Database | 10.1.30.0 | /24 |
| VLAN 40 | Management | 10.1.40.0 | /24 |
| VLAN 50 | Storage | 10.1.50.0 | /24 |
| VLAN 99 | Out-of-Band | 10.1.99.0 | /24 |

### 4.3 Firewall Rules

| Source | Destination | Port | Protocol | Action |
|--------|-------------|------|----------|--------|
| Internet | DMZ | 443 | TCP | Allow |
| Internet | DMZ | 80 | TCP | Redirect to 443 |
| DMZ | Application | 8080 | TCP | Allow |
| Application | Database | 5432 | TCP | Allow |
| Application | Cache | 6379 | TCP | Allow |
| Management | All | 22 | TCP | Allow (Jump Host only) |
| All | Internet | Any | Any | Deny (Default) |

### 4.4 Load Balancer Configuration

| Component | Specification |
|-----------|---------------|
| Type | Hardware/Cloud Load Balancer |
| Mode | Active-Active |
| Algorithm | Least Connections |
| Health Checks | HTTP/HTTPS probes |
| SSL Offloading | Yes |
| Session Persistence | Cookie-based |
| Rate Limiting | 1000 req/sec per IP |

---

## 5.0 STORAGE ARCHITECTURE

### 5.1 Storage Tiers

| Tier | Technology | Use Case | Capacity |
|------|------------|----------|----------|
| Tier 1 | NVMe SSD | Database hot data | 4 TB |
| Tier 2 | SATA SSD | Application data | 10 TB |
| Tier 3 | SAS HDD | Archive, logs | 50 TB |
| Tier 4 | Object Storage | Documents, backups | 100 TB |

### 5.2 Database Storage

| Component | RAID Level | Capacity | IOPS Target |
|-----------|------------|----------|-------------|
| Data Files | RAID 10 | 2 TB | 50,000+ |
| WAL/Logs | RAID 1 | 500 GB | 10,000+ |
| Temp | RAID 0 | 200 GB | 20,000+ |
| Backups | RAID 5 | 4 TB | 5,000+ |

### 5.3 Object Storage Configuration

| Bucket | Purpose | Lifecycle Policy |
|--------|---------|------------------|
| ucms-documents | User uploads | Move to archive after 1 year |
| ucms-exports | Report exports | Delete after 90 days |
| ucms-backups | System backups | Keep 30 versions |
| ucms-logs | Application logs | Archive after 7 days |

---

## 6.0 SECURITY INFRASTRUCTURE

### 6.1 Security Architecture Layers

```
┌─────────────────────────────────────────────────────────────┐
│                    SECURITY LAYERS                          │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  Layer 7: Application Security                              │
│  ├── Input validation, WAF rules                            │
│  ├── Authentication, Authorization                          │
│  └── API security, Rate limiting                            │
│                                                             │
│  Layer 6: Data Security                                     │
│  ├── Encryption at rest (AES-256)                           │
│  ├── Encryption in transit (TLS 1.3)                        │
│  └── Database encryption, Tokenization                      │
│                                                             │
│  Layer 5: Network Security                                  │
│  ├── Firewall, IDS/IPS                                      │
│  ├── VPN, Network segmentation                              │
│  └── DDoS protection                                        │
│                                                             │
│  Layer 4: Endpoint Security                                 │
│  ├── Antivirus, EDR                                         │
│  ├── Host-based firewall                                    │
│  └── Patch management                                       │
│                                                             │
│  Layer 3: Physical Security                                 │
│  ├── Data center access control                             │
│  ├── Environmental controls                                 │
│  └── Hardware security                                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 6.2 Security Components

| Component | Product/Solution | Purpose |
|-----------|------------------|---------|
| Firewall | Palo Alto / Fortinet | Perimeter protection |
| WAF | ModSecurity / Cloud WAF | Application layer protection |
| SIEM | Wazuh / Splunk | Security monitoring |
| IDS/IPS | Suricata | Intrusion detection |
| EDR | CrowdStrike / SentinelOne | Endpoint protection |
| Secrets Mgmt | HashiCorp Vault | Credential management |
| DLP | Symantec / Forcepoint | Data loss prevention |
| VA/PT | Nessus / OpenVAS | Vulnerability scanning |

### 6.3 SSL/TLS Configuration

| Component | Protocol | Certificate |
|-----------|----------|-------------|
| Load Balancer | TLS 1.2, 1.3 | Wildcard SAN |
| Web Server | TLS 1.2, 1.3 | Domain-specific |
| API Gateway | TLS 1.3 | Extended Validation |
| Database | TLS 1.2 | Self-signed internal |

### 6.4 VPN Configuration

| VPN Type | Protocol | Authentication |
|----------|----------|----------------|
| Site-to-Site | IPsec/IKEv2 | Certificate |
| Client Access | OpenVPN/WireGuard | MFA + Certificate |
| Management | SSH Tunnel | Key-based |

---

## 7.0 BACKUP AND RECOVERY

### 7.1 Backup Strategy

| Data Type | Frequency | Retention | Method |
|-----------|-----------|-----------|--------|
| Database Full | Daily | 30 days | pg_dump + WAL |
| Database Incremental | Continuous | 7 days | WAL archiving |
| File System | Daily | 30 days | rsnapshot |
| Configuration | On change | 90 days | Git + backup |
| VM Images | Weekly | 4 weeks | Snapshot |
| Object Storage | Cross-region | 1 year | Replication |

### 7.2 Backup Infrastructure

| Component | Specification |
|-----------|---------------|
| Backup Server | Dedicated physical server |
| Storage | 50 TB NAS with expansion |
| Software | Bacula / Veeam / Restic |
| Offsite | Cloud storage replication |
| Encryption | AES-256 for all backups |

### 7.3 Recovery Objectives

| Metric | Target | Maximum |
|--------|--------|---------|
| RTO (Recovery Time) | 4 hours | 8 hours |
| RPO (Data Loss) | 1 hour | 4 hours |
| DR Failover | 2 hours | 4 hours |

---

## 8.0 MONITORING AND MANAGEMENT

### 8.1 Monitoring Stack

| Layer | Tool | Metrics |
|-------|------|---------|
| Infrastructure | Prometheus + Node Exporter | CPU, Memory, Disk, Network |
| Application | APM (New Relic/Dynatrace) | Response time, Errors, Throughput |
| Database | pg_stat_statements, PgHero | Query performance, Connections |
| Logs | ELK Stack (Elasticsearch) | Centralized log aggregation |
| Uptime | Uptime Kuma / Pingdom | Availability monitoring |
| Synthetic | Selenium / k6 | End-to-end testing |

### 8.2 Alerting Thresholds

| Metric | Warning | Critical |
|--------|---------|----------|
| CPU Usage | > 70% | > 90% |
| Memory Usage | > 80% | > 95% |
| Disk Usage | > 80% | > 90% |
| Response Time | > 2s | > 5s |
| Error Rate | > 1% | > 5% |
| DB Connections | > 80% | > 95% |

### 8.3 Management Tools

| Purpose | Tool |
|---------|------|
| Configuration Mgmt | Ansible |
| Container Orchestration | Kubernetes |
| Infrastructure as Code | Terraform |
| Secret Management | HashiCorp Vault |
| Certificate Management | cert-manager |
| Service Mesh | Istio (optional) |

---

## 9.0 CAPACITY PLANNING

### 9.1 Current Capacity

| Resource | Allocated | Utilized (Avg) | Headroom |
|----------|-----------|----------------|----------|
| Compute (vCPU) | 204 | 45% | 55% |
| Memory | 816 GB | 50% | 50% |
| Storage | 12.3 TB | 35% | 65% |
| Network | 10 Gbps | 20% | 80% |

### 9.2 Growth Projections

| Year | Users | Claims/Year | Storage Growth |
|------|-------|-------------|----------------|
| Year 1 | 50,000 | 100,000 | 2 TB |
| Year 2 | 100,000 | 250,000 | 5 TB |
| Year 3 | 200,000 | 500,000 | 10 TB |
| Year 5 | 500,000 | 1,000,000 | 25 TB |

### 9.3 Scaling Triggers

| Metric | Scale Up Trigger | Scale Out Trigger |
|--------|------------------|-------------------|
| CPU | > 80% for 5 min | > 70% average |
| Memory | > 85% for 5 min | > 75% average |
| Response Time | > 3s p95 | > 2s average |
| Queue Depth | > 1000 messages | > 500 messages |

---

## 10.0 COMPLIANCE AND CERTIFICATIONS

### 10.1 Security Standards

| Standard | Compliance Level |
|----------|------------------|
| ISO 27001 | Certified |
| ISO 27017 | Cloud security |
| ISO 27018 | Personal data protection |
| PCIDSS | Level 1 (if handling payments) |
| NIST CSF | Aligned |

### 10.2 Government Requirements

| Requirement | Implementation |
|-------------|----------------|
| MyGPSS | Government security standards |
| MAMPU | ICT security policies |
| PDPA | Personal data protection |
| OSA | Official Secrets Act compliance |

---

## 11.0 APPENDICES

### Appendix A: Infrastructure Bill of Materials

| Category | Item | Qty | Unit Cost | Total |
|----------|------|-----|-----------|-------|
| Compute | Application Servers | 12 | RM 15,000 | RM 180,000 |
| Compute | Database Servers | 4 | RM 45,000 | RM 180,000 |
| Compute | Supporting | 12 | RM 10,000 | RM 120,000 |
| Network | Firewalls | 2 | RM 80,000 | RM 160,000 |
| Network | Switches | 6 | RM 25,000 | RM 150,000 |
| Network | Load Balancers | 2 | RM 60,000 | RM 120,000 |
| Storage | SAN/NAS | 1 | RM 200,000 | RM 200,000 |
| Security | SIEM, EDR, etc. | 1 | RM 150,000 | RM 150,000 |
| Software | Licenses | 1 | RM 300,000 | RM 300,000 |
| **TOTAL** | | | | **RM 1,560,000** |

### Appendix B: Network Diagram (Detailed)
[Available in network architecture document]

### Appendix C: Rack Layout
[Available in datacenter specification]

---

**Document Approval**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Infrastructure Architect | | | |
| Network Engineer | | | |
| Security Officer | | | |
| Project Manager | | | |
| MCMC Representative | | | |

---

*Document Control: This Infrastructure Design Document is maintained by the Infrastructure team. All changes require approval from the Infrastructure Architect and MCMC Representative.*
