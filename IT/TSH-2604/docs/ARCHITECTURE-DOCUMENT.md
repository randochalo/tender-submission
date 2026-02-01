# TSH-2604: ARCHITECTURE DOCUMENT
## System Design & Deployment

## 1. SYSTEM ARCHITECTURE

### 1.1 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    PRESENTATION LAYER                            │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐               │
│  │   Web   │ │ Mobile  │ │  API    │ │  Admin  │               │
│  │   App   │ │  App    │ │ Clients │ │  Panel  │               │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘               │
└───────┼───────────┼───────────┼───────────┼─────────────────────┘
        │           │           │           │
        └───────────┴───────────┴───────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────────┐
│                    APPLICATION LAYER                             │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐   │
│  │   HMS   │ │   FFS   │ │   WMS   │ │   TMS   │ │   FMS   │   │
│  │ Module  │ │ Module  │ │ Module  │ │ Module  │ │ Module  │   │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘   │
└─────────────────────────────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────────┐
│                    INTEGRATION LAYER                             │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐               │
│  │  Auth   │ │  API    │ │  Queue  │ │  Cache  │               │
│  │Service  │ │ Gateway │ │ Service │ │ Service │               │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘               │
└─────────────────────────────────────────────────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────────────────────────────┐
│                      DATA LAYER                                  │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐                          │
│  │PostgreSQL│ │  Redis  │ │  MinIO  │                          │
│  │Database │ │  Cache  │ │ Storage │                          │
│  └─────────┘ └─────────┘ └─────────┘                          │
└─────────────────────────────────────────────────────────────────┘
```

### 1.2 Technology Stack

| Layer | Technology | Version |
|-------|------------|---------|
| Frontend | Next.js | 14.x |
| Backend | Express.js | 4.x |
| Database | PostgreSQL | 15.x |
| ORM | Prisma | 5.x |
| Cache | Redis | 7.x |
| Auth | NextAuth.js | 4.x |
| Container | Docker | 24.x |

## 2. SECURITY ARCHITECTURE

### 2.1 Authentication & Authorization
- JWT-based session management
- MFA via TOTP/SMS
- RBAC with 50+ permissions
- 8 role levels

### 2.2 Encryption
- AES-256 at rest
- TLS 1.3 in transit
- Field-level encryption for PII

### 2.3 Audit & Compliance
- Immutable audit logs
- Tamper-resistant storage
- Blockchain anchoring (optional)

## 3. DEPLOYMENT ARCHITECTURE

### 3.1 Railway Deployment

```
┌────────────────────────────────────────┐
│           RAILWAY PLATFORM             │
│                                        │
│  ┌─────────┐    ┌─────────┐           │
│  │  Web    │    │   API   │           │
│  │ Service │    │ Service │           │
│  │ :3000   │    │ :3001   │           │
│  └────┬────┘    └────┬────┘           │
│       │              │                 │
│       └──────────────┼─────────────────┤
│                      │                 │
│              ┌───────┴───────┐        │
│              │  PostgreSQL   │        │
│              │    :5432      │        │
│              └───────────────┘        │
│                                        │
└────────────────────────────────────────┘
```

### 3.2 Environment Configuration

| Environment | URL | Purpose |
|-------------|-----|---------|
| Production | https://tsh2604.logisticspro.my | Live system |
| Staging | https://staging.tsh2604.logisticspro.my | UAT testing |
| Development | http://localhost:3000 | Local development |

## 4. INTEGRATION ARCHITECTURE

### 4.1 External Integrations
- Port Klang PCS (REST API)
- MyGBS Customs (REST API)
- Shipping Lines (API/EDI)
- IRBM MyInvois (REST API)

### 4.2 Internal Integrations
- HMS ↔ FMS (Billing)
- FFS ↔ HMS (Haulage)
- WMS ↔ FFS (Inventory)
- All ↔ FMS (Finance)

## 5. SCALABILITY

### 5.1 Horizontal Scaling
- Container orchestration
- Load balancing
- Database read replicas

### 5.2 Performance Targets
- API Response: < 200ms
- Page Load: < 2 seconds
- Throughput: 10,000 req/min

---

**Document Version:** 1.0  
**Date:** February 2026
