# ANNEX-T29-INTEGRATION-ARCHITECTURE-TSH2607.md

# ANNEX T29: INTEGRATION ARCHITECTURE
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T29  
**Version:** 1.0  
**Date:** February 2026  

---

## INTEGRATION LANDSCAPE

### System Integration Diagram

```
┌─────────────────────────────────────────────────────────────────────────────────────────┐
│                              UCMS INTEGRATION ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                          │
│                              ┌─────────────┐                                            │
│                              │    UCMS     │                                            │
│                              │   System    │                                            │
│                              └──────┬──────┘                                            │
│                                     │                                                     │
│          ┌──────────────────────────┼──────────────────────────┐                         │
│          │                          │                          │                         │
│          ▼                          ▼                          ▼                         │
│   ┌─────────────┐           ┌─────────────┐           ┌─────────────┐                    │
│   │    USPFS    │           │  Azure AD   │           │   Digital   │                    │
│   │  (Oracle    │           │    SSO      │           │  Signature  │                    │
│   │   EBS)      │           │             │           │  Provider   │                    │
│   └─────────────┘           └─────────────┘           └─────────────┘                    │
│                                                                                          │
│          ┌──────────────────────────┼──────────────────────────┐                         │
│          │                          │                          │                         │
│          ▼                          ▼                          ▼                         │
│   ┌─────────────┐           ┌─────────────┐           ┌─────────────┐                    │
│   │ Bank        │           │   OCR/RPA   │           │    SMS/     │                    │
│   │ Payment     │           │   Engines   │           │   Email     │                    │
│   │ Gateway     │           │             │           │   Gateway   │                    │
│   └─────────────┘           └─────────────┘           └─────────────┘                    │
│                                                                                          │
└─────────────────────────────────────────────────────────────────────────────────────────┘
```

### Integration Protocols

| System | Protocol | Security | Frequency |
|--------|----------|----------|-----------|
| USPFS | REST API / DB Link | mTLS + OAuth | Real-time |
| Azure AD | OIDC / SAML 2.0 | TLS 1.3 | On-demand |
| Digital Signature | REST API | API Key + TLS | On-demand |
| Bank Gateway | REST API | mTLS | Real-time |
| SMS Gateway | REST API | API Key | On-demand |
| Email Service | SMTP/SMTPS | TLS | On-demand |

---

**END OF ANNEX T29**
