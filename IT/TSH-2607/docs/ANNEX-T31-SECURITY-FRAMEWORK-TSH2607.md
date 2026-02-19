# ANNEX-T31-SECURITY-FRAMEWORK-TSH2607.md

# ANNEX T31: SECURITY FRAMEWORK
## Universal Service Provision (USP) Claims Management System (UCMS)

**Tender Reference:** MCMC/FD/UFMD(01)/UCMS/TC/01/2026(02)**Annex ID:** T31  
**Version:** 1.0  
**Date:** February 2026  

---

## SECURITY LAYERS

### Defense in Depth

```
Layer 1: Perimeter Security
├── DDoS Protection (Azure DDoS Standard)
├── Web Application Firewall (WAF)
└── CDN with Edge Security

Layer 2: Network Security
├── Network Segmentation (DMZ/App/Data)
├── Network Security Groups (NSG)
├── Private Link / Private Endpoints
└── VPN Gateway for site-to-site

Layer 3: Application Security
├── Azure AD SSO with MFA
├── OAuth 2.0 / OIDC
├── RBAC with fine-grained permissions
├── Input validation and sanitization
└── CSRF/XSS protection

Layer 4: Data Security
├── AES-256 encryption at rest (TDE)
├── TLS 1.3 for data in transit
├── Column-level encryption for PII
├── Azure Key Vault for secrets
└── Data masking for non-prod

Layer 5: Monitoring & Audit
├── SIEM integration
├── Real-time threat detection
├── Immutable audit logs
└── Security alerting
```

### Security Controls

| Control | Implementation | Standard |
|---------|----------------|----------|
| Authentication | Azure AD + MFA | ISO 27001 |
| Authorization | RBAC/ABAC | NIST 800-53 |
| Encryption | AES-256/TLS 1.3 | FIPS 140-2 |
| Audit Logging | Immutable logs | KRISA |
| Vulnerability Management | Weekly scans | OWASP |

---

**END OF ANNEX T31**
