# Complete Backend Security Mastery Checklist

## 1. Security Fundamentals

- [ ] What is cybersecurity?
- [ ] What is application security?
- [ ] What is backend security?
- [ ] CIA triad
- [ ] Confidentiality
- [ ] Integrity
- [ ] Availability
- [ ] Authentication
- [ ] Authorization
- [ ] Accountability
- [ ] Non-repudiation
- [ ] Asset
- [ ] Threat
- [ ] Vulnerability
- [ ] Exploit
- [ ] Risk
- [ ] Attack surface
- [ ] Attack vector
- [ ] Security control
- [ ] Defense in depth
- [ ] Least privilege
- [ ] Fail-safe defaults
- [ ] Secure by default
- [ ] Zero trust concepts

---

## 2. Threat Modeling

- [ ] What is threat modeling?
- [ ] Why threat modeling?
- [ ] Identify assets
- [ ] Identify trust boundaries
- [ ] Identify entry points
- [ ] Identify threats
- [ ] Identify attackers
- [ ] Identify attack vectors
- [ ] Identify security controls
- [ ] Risk assessment
- [ ] Threat prioritization

### STRIDE

- [ ] Spoofing
- [ ] Tampering
- [ ] Repudiation
- [ ] Information disclosure
- [ ] Denial of service
- [ ] Elevation of privilege

### Practice

- [ ] Threat-model login system
- [ ] Threat-model payment API
- [ ] Threat-model file upload
- [ ] Threat-model admin dashboard
- [ ] Threat-model multi-tenant SaaS

---

## 3. Trust Boundaries

- [ ] What is a trust boundary?
- [ ] Browser → backend
- [ ] Backend → database
- [ ] Backend → external API
- [ ] Backend → file storage
- [ ] Backend → queue
- [ ] Service → service
- [ ] User → admin boundary
- [ ] Tenant → tenant boundary
- [ ] Internal → external network

### Understand

- [ ] Never trust client-side authorization
- [ ] Never trust client-provided identity
- [ ] Never trust external API responses
- [ ] Never trust uploaded files
- [ ] Never trust request parameters

---

## 4. Authentication Security

- [ ] Authentication fundamentals
- [ ] Identity
- [ ] Credentials
- [ ] Login security
- [ ] Registration security
- [ ] Logout
- [ ] Session management
- [ ] Token authentication
- [ ] Password authentication
- [ ] Account verification

### Attacks

- [ ] Brute force
- [ ] Credential stuffing
- [ ] Password spraying
- [ ] Account enumeration
- [ ] Session hijacking
- [ ] Token theft
- [ ] Replay attacks
- [ ] Authentication bypass

---

## 5. Password Security

- [ ] Never store plaintext passwords
- [ ] Hashing vs encryption
- [ ] Password hashing
- [ ] Salt
- [ ] Work factor
- [ ] Password verification
- [ ] Password strength
- [ ] Password reset
- [ ] Password change
- [ ] Password history concepts
- [ ] Compromised password concepts

### Algorithms

- [ ] Argon2
- [ ] bcrypt
- [ ] scrypt
- [ ] PBKDF2

### Understand

- [ ] Why SHA-256 is not a password hashing algorithm
- [ ] Why fast hashes are bad for passwords
- [ ] Salt vs pepper

---

## 6. Session Security

- [ ] What is a session?
- [ ] Session ID
- [ ] Session storage
- [ ] Session expiration
- [ ] Session rotation
- [ ] Session invalidation
- [ ] Logout invalidation
- [ ] Concurrent sessions
- [ ] Session revocation
- [ ] Session fixation
- [ ] Session hijacking

---

## 7. Cookie Security

- [ ] Cookies
- [ ] Secure cookies
- [ ] `HttpOnly`
- [ ] `Secure`
- [ ] `SameSite`
- [ ] `Strict`
- [ ] `Lax`
- [ ] `None`
- [ ] Domain
- [ ] Path
- [ ] Expiration
- [ ] Cookie prefixes
- [ ] Session cookies
- [ ] Persistent cookies

---

## 8. JWT Security

- [ ] JWT structure
- [ ] Header
- [ ] Payload
- [ ] Signature
- [ ] Claims
- [ ] `exp`
- [ ] `iat`
- [ ] `nbf`
- [ ] `iss`
- [ ] `aud`
- [ ] `sub`
- [ ] Signature verification
- [ ] Algorithm selection
- [ ] Key management
- [ ] Token expiration
- [ ] Refresh tokens
- [ ] Token rotation
- [ ] Token revocation
- [ ] Token theft
- [ ] Replay attacks
- [ ] JWT storage
- [ ] JWT invalidation limitations

---

## 9. OAuth 2.0 Security

- [ ] OAuth fundamentals
- [ ] Authorization Code Flow
- [ ] PKCE
- [ ] Client authentication
- [ ] Redirect URI validation
- [ ] State parameter
- [ ] Scope
- [ ] Access token
- [ ] Refresh token
- [ ] Token endpoint
- [ ] Authorization endpoint
- [ ] Authorization code interception
- [ ] Redirect URI manipulation
- [ ] CSRF in OAuth
- [ ] Token leakage
- [ ] Open redirect abuse
- [ ] State validation failures

---

## 10. OpenID Connect Security

- [ ] OAuth vs OIDC
- [ ] ID token
- [ ] UserInfo
- [ ] Claims
- [ ] Nonce
- [ ] Discovery
- [ ] JWKS
- [ ] Signature verification
- [ ] Issuer validation
- [ ] Audience validation

---

## 11. Multi-Factor Authentication

- [ ] What is MFA?
- [ ] OTP
- [ ] TOTP
- [ ] Recovery codes
- [ ] Backup authentication
- [ ] MFA enrollment
- [ ] MFA reset
- [ ] MFA recovery
- [ ] OTP brute force
- [ ] OTP rate limiting
- [ ] MFA bypass
- [ ] Recovery-flow security

---

## 12. Authorization Security

- [ ] Authorization fundamentals
- [ ] RBAC
- [ ] Permission-based access
- [ ] ABAC
- [ ] Resource-based access
- [ ] Ownership checks
- [ ] Policy-based access
- [ ] Least privilege
- [ ] Deny by default
- [ ] Server-side authorization

---

## 13. Broken Access Control

- [ ] IDOR
- [ ] BOLA
- [ ] BFLA
- [ ] Broken object authorization
- [ ] Broken function authorization
- [ ] Broken property authorization
- [ ] Privilege escalation
- [ ] Horizontal privilege escalation
- [ ] Vertical privilege escalation
- [ ] Forced browsing
- [ ] Missing authorization checks
- [ ] Client-side authorization bypass
- [ ] User A accessing User B's resource
- [ ] Normal user accessing admin endpoint
- [ ] User modifying protected fields
- [ ] Cross-tenant access attempt

---

## 14. Multi-Tenant Security

- [ ] Tenant isolation
- [ ] Tenant ID validation
- [ ] Tenant-aware queries
- [ ] Tenant-aware authorization
- [ ] Organization membership
- [ ] Organization roles
- [ ] Cross-tenant access prevention
- [ ] Tenant-specific secrets
- [ ] Tenant-specific resources
- [ ] Cross-tenant data leak
- [ ] Tenant ID manipulation
- [ ] Missing tenant filter
- [ ] Insecure shared resources

---

## 15. Input Security

- [ ] Never trust user input
- [ ] Input validation
- [ ] Schema validation
- [ ] Type validation
- [ ] Length validation
- [ ] Range validation
- [ ] Allowlist validation
- [ ] Denylist limitations
- [ ] Normalization
- [ ] Canonicalization
- [ ] Sanitization
- [ ] Encoding

---

## 16. SQL Injection

- [ ] What is SQL injection?
- [ ] Why it happens
- [ ] Parameterized queries
- [ ] Prepared statements
- [ ] ORM security
- [ ] Query builders
- [ ] Input validation
- [ ] Least-privilege DB accounts
- [ ] Authentication bypass
- [ ] Data extraction
- [ ] Data modification
- [ ] Blind SQL injection
- [ ] Error-based injection
- [ ] Time-based injection

---

## 17. NoSQL Injection

- [ ] What is NoSQL injection?
- [ ] Operator injection
- [ ] Query object manipulation
- [ ] Input schema validation
- [ ] Type validation
- [ ] Safe query construction

---

## 18. Command Injection

- [ ] What is command injection?
- [ ] OS command execution
- [ ] Shell injection
- [ ] Command arguments
- [ ] Input validation
- [ ] Avoid unnecessary shell execution
- [ ] Safe process APIs
- [ ] Least privilege

---

## 19. Path Traversal

- [ ] What is path traversal?
- [ ] `../`
- [ ] Absolute paths
- [ ] Path normalization
- [ ] File access validation
- [ ] Allowlisted directories
- [ ] Symlink considerations

---

## 20. SSRF

- [ ] What is SSRF?
- [ ] Server-side request forgery
- [ ] User-controlled URLs
- [ ] Internal services
- [ ] Cloud metadata endpoints
- [ ] URL validation
- [ ] IP validation
- [ ] DNS rebinding concepts
- [ ] Network-level restrictions
- [ ] Allowlist approach

---

## 21. XSS

- [ ] What is XSS?
- [ ] Stored XSS
- [ ] Reflected XSS
- [ ] DOM XSS
- [ ] Output encoding
- [ ] HTML escaping
- [ ] Context-aware encoding
- [ ] Content Security Policy
- [ ] Safe templating
- [ ] Sanitization

---

## 22. CSRF

- [ ] What is CSRF?
- [ ] Why cookie authentication can be vulnerable
- [ ] CSRF token
- [ ] Synchronizer token pattern
- [ ] Double-submit cookie
- [ ] SameSite cookies
- [ ] Origin validation
- [ ] Referer validation
- [ ] When CSRF protection is necessary

---

## 23. CORS Security

- [ ] Same-Origin Policy
- [ ] CORS
- [ ] Origin
- [ ] Preflight
- [ ] OPTIONS
- [ ] Allowed origins
- [ ] Allowed methods
- [ ] Allowed headers
- [ ] Credentials
- [ ] Wildcard origin risks
- [ ] CORS misconfiguration

---

## 24. HTTP Security

- [ ] HTTPS
- [ ] TLS
- [ ] TLS certificates
- [ ] Certificate validation
- [ ] HSTS
- [ ] HTTP security headers
- [ ] Content-Type
- [ ] Content-Length
- [ ] Request limits
- [ ] Response headers
- [ ] Content-Security-Policy
- [ ] Strict-Transport-Security
- [ ] X-Content-Type-Options
- [ ] Referrer-Policy
- [ ] Permissions-Policy
- [ ] Frame protection
- [ ] Secure cookie attributes

---

## 25. Cryptography Fundamentals

- [ ] Encryption
- [ ] Hashing
- [ ] Encoding
- [ ] Digital signatures
- [ ] MAC
- [ ] HMAC
- [ ] Symmetric cryptography
- [ ] Asymmetric cryptography
- [ ] Public key
- [ ] Private key
- [ ] Key exchange
- [ ] Randomness
- [ ] Nonces
- [ ] IVs
- [ ] Salts

---

## 26. Symmetric Encryption

- [ ] AES
- [ ] AES-GCM
- [ ] Encryption key
- [ ] Nonce
- [ ] IV
- [ ] Authentication tag
- [ ] Authenticated encryption
- [ ] Key rotation
- [ ] Why ECB is unsafe
- [ ] Why nonce reuse can be dangerous

---

## 27. Asymmetric Cryptography

- [ ] RSA
- [ ] ECC
- [ ] Public/private key
- [ ] Encryption
- [ ] Digital signatures
- [ ] Key exchange
- [ ] Certificate concepts

---

## 28. Hashing

- [ ] SHA-256
- [ ] SHA-512
- [ ] SHA-3
- [ ] Collision
- [ ] Preimage
- [ ] Avalanche effect
- [ ] Hash integrity
- [ ] Hashing ≠ encryption
- [ ] Hashing ≠ encoding
- [ ] Password hashing ≠ normal hashing

---

## 29. Digital Signatures

- [ ] What is a digital signature?
- [ ] Signing
- [ ] Verification
- [ ] Integrity
- [ ] Authenticity
- [ ] Non-repudiation concepts
- [ ] RSA signatures
- [ ] ECDSA
- [ ] EdDSA
- [ ] Sign message
- [ ] Verify message
- [ ] Detect modified message

---

## 30. Secrets Management

- [ ] API keys
- [ ] Database passwords
- [ ] JWT secrets
- [ ] Encryption keys
- [ ] OAuth secrets
- [ ] Cloud credentials
- [ ] Environment variables
- [ ] Secret managers
- [ ] Secret rotation
- [ ] Secret expiration
- [ ] Secret revocation
- [ ] Never commit secrets
- [ ] Never log secrets
- [ ] Never send secrets to frontend unnecessarily
- [ ] Never hardcode production credentials

---

## 31. Environment Security

- [ ] Development environment
- [ ] Testing environment
- [ ] Staging environment
- [ ] Production environment
- [ ] Environment isolation
- [ ] Separate credentials
- [ ] Production secret protection
- [ ] Secure configuration
- [ ] Configuration validation

---

## 32. Security Misconfiguration

- [ ] Debug mode
- [ ] Default passwords
- [ ] Default credentials
- [ ] Exposed admin endpoints
- [ ] Unnecessary services
- [ ] Unnecessary ports
- [ ] Verbose errors
- [ ] Exposed stack traces
- [ ] Missing security headers
- [ ] Incorrect CORS
- [ ] Public databases
- [ ] Public storage
- [ ] Insecure cloud permissions

---

## 33. Error Handling Security

- [ ] Don't expose stack traces
- [ ] Don't expose SQL errors
- [ ] Don't expose internal paths
- [ ] Don't expose secrets
- [ ] Don't expose internal service details
- [ ] Generic production errors
- [ ] Detailed internal logs
- [ ] Consistent error responses
- [ ] Fail securely
- [ ] Rollback failed operations

---

## 34. API Security

- [ ] API attack surface
- [ ] API authentication
- [ ] API authorization
- [ ] BOLA
- [ ] Broken authentication
- [ ] Property-level authorization
- [ ] Function-level authorization
- [ ] Resource consumption
- [ ] Sensitive business flows
- [ ] SSRF
- [ ] API misconfiguration
- [ ] API inventory
- [ ] Unsafe third-party APIs

---

## 35. API Rate Limiting

- [ ] Why rate limiting?
- [ ] IP-based limits
- [ ] User-based limits
- [ ] Token-based limits
- [ ] Endpoint-specific limits
- [ ] Login rate limiting
- [ ] OTP rate limiting
- [ ] Password reset rate limiting
- [ ] API quotas
- [ ] Burst limits
- [ ] Fixed window
- [ ] Sliding window
- [ ] Token bucket
- [ ] Leaky bucket

---

## 36. Resource Exhaustion

- [ ] Request body limits
- [ ] File size limits
- [ ] Pagination limits
- [ ] Query complexity limits
- [ ] Upload limits
- [ ] CPU-intensive operation protection
- [ ] Memory-intensive operation protection
- [ ] Timeout limits
- [ ] Regex DoS / ReDoS
- [ ] Infinite loop protection
- [ ] Recursive input protection

---

## 37. Business Logic Security

- [ ] What is business logic vulnerability?
- [ ] Trust boundaries in workflows
- [ ] State transitions
- [ ] Workflow validation
- [ ] Price manipulation
- [ ] Quantity manipulation
- [ ] Coupon abuse
- [ ] Replay
- [ ] Race conditions
- [ ] Double spending
- [ ] Privilege abuse
- [ ] Skipping workflow steps

### Practice

- [ ] E-commerce checkout
- [ ] Payment workflow
- [ ] Password reset
- [ ] Email verification
- [ ] Account upgrade
- [ ] Admin approval workflow

---

## 38. Race Conditions

- [ ] What is a race condition?
- [ ] TOCTOU
- [ ] Concurrent requests
- [ ] Duplicate requests
- [ ] Double spending
- [ ] Inventory race
- [ ] Database locking
- [ ] Transactions
- [ ] Atomic operations
- [ ] Distributed locks
- [ ] Idempotency

---

## 39. Idempotency Security

- [ ] What is idempotency?
- [ ] Idempotency keys
- [ ] Duplicate requests
- [ ] Payment protection
- [ ] Order creation protection
- [ ] Retry safety
- [ ] Idempotency storage
- [ ] Expiration
- [ ] Replay prevention

---

## 40. File Upload Security

- [ ] File upload threats
- [ ] File size validation
- [ ] MIME validation
- [ ] Extension validation
- [ ] Magic bytes
- [ ] Filename sanitization
- [ ] Path traversal
- [ ] Executable uploads
- [ ] Archive bombs
- [ ] Image processing vulnerabilities
- [ ] Virus scanning
- [ ] Quarantine
- [ ] Object storage permissions
- [ ] Signed URLs

---

## 41. SSRF & External Requests

- [ ] User-controlled URLs
- [ ] URL parsing
- [ ] Allowlist domains
- [ ] Block private IPs
- [ ] Block loopback
- [ ] Block link-local addresses
- [ ] DNS rebinding
- [ ] Redirect validation
- [ ] Outbound firewall rules
- [ ] Cloud metadata protection

---

## 42. Webhook Security

- [ ] Webhook authentication
- [ ] Signature verification
- [ ] HMAC signatures
- [ ] Timestamp validation
- [ ] Replay protection
- [ ] Idempotency
- [ ] IP allowlisting concepts
- [ ] Webhook secrets
- [ ] Retry handling
- [ ] Event validation

---

## 43. Third-Party API Security

- [ ] Don't blindly trust external APIs
- [ ] Validate responses
- [ ] Timeouts
- [ ] Retries
- [ ] Rate limits
- [ ] Authentication
- [ ] API key security
- [ ] OAuth security
- [ ] Response size limits
- [ ] SSRF considerations
- [ ] Dependency failures

---

## 44. Software Supply Chain Security

- [ ] Dependencies
- [ ] Transitive dependencies
- [ ] Package lock files
- [ ] Dependency pinning
- [ ] Vulnerability scanning
- [ ] Dependency updates
- [ ] Malicious packages
- [ ] Typosquatting
- [ ] Dependency confusion
- [ ] Package integrity
- [ ] SBOM
- [ ] Build security
- [ ] CI/CD security

---

## 45. Node.js Security

- [ ] Node.js permission concepts
- [ ] Dependency security
- [ ] `npm audit`
- [ ] Lockfiles
- [ ] `package-lock.json`
- [ ] Prototype pollution
- [ ] Unsafe deserialization
- [ ] Command execution
- [ ] Path traversal
- [ ] Environment variables
- [ ] Process permissions
- [ ] Child processes
- [ ] Worker security
- [ ] HTTP server limits
- [ ] Request size limits

---

## 46. Prototype Pollution

- [ ] What is prototype pollution?
- [ ] JavaScript prototypes
- [ ] `__proto__`
- [ ] Constructor pollution
- [ ] Object merging risks
- [ ] Unsafe deep merge
- [ ] Dependency vulnerabilities
- [ ] Prevention
- [ ] Detection

---

## 47. Deserialization Security

- [ ] Serialization
- [ ] Deserialization
- [ ] Unsafe deserialization
- [ ] Object injection
- [ ] Prototype pollution
- [ ] Untrusted serialized data
- [ ] Safe JSON handling
- [ ] Validation after parsing

---

## 48. Database Security

- [ ] Database authentication
- [ ] Database authorization
- [ ] Least privilege
- [ ] Separate DB users
- [ ] Read-only users
- [ ] Connection encryption
- [ ] Database network isolation
- [ ] Connection security
- [ ] Query parameterization
- [ ] SQL injection
- [ ] NoSQL injection
- [ ] Sensitive data protection
- [ ] Database backups
- [ ] Backup encryption
- [ ] Audit logs

---

## 49. Sensitive Data Protection

- [ ] Identify sensitive data
- [ ] Data classification
- [ ] Data minimization
- [ ] Encryption at rest
- [ ] Encryption in transit
- [ ] Access control
- [ ] Data masking
- [ ] Data redaction
- [ ] Secure deletion
- [ ] Retention policies
- [ ] Never unnecessarily log passwords
- [ ] Never unnecessarily log access tokens
- [ ] Never unnecessarily log refresh tokens
- [ ] Never unnecessarily log API keys
- [ ] Never unnecessarily log encryption keys
- [ ] Never unnecessarily log sensitive personal data

---

## 50. Logging Security

- [ ] Security event logging
- [ ] Authentication logs
- [ ] Authorization failures
- [ ] Input validation failures
- [ ] Admin actions
- [ ] Password reset events
- [ ] Token events
- [ ] Suspicious activity
- [ ] Audit logs
- [ ] Log integrity
- [ ] Log retention
- [ ] Log access control

---

## 51. Monitoring & Detection

- [ ] Failed login monitoring
- [ ] Brute-force detection
- [ ] Abnormal API usage
- [ ] Permission failures
- [ ] Unusual traffic
- [ ] Resource spikes
- [ ] Suspicious IP activity
- [ ] Account takeover indicators
- [ ] Data access anomalies
- [ ] Security alerts

---

## 52. Incident Response

- [ ] What is a security incident?
- [ ] Detection
- [ ] Triage
- [ ] Containment
- [ ] Eradication
- [ ] Recovery
- [ ] Post-incident analysis
- [ ] Incident timeline
- [ ] Evidence preservation
- [ ] Credential rotation
- [ ] Token revocation
- [ ] Secret rotation
- [ ] Communication plan

---

## 53. Backup & Recovery Security

- [ ] Database backups
- [ ] Backup encryption
- [ ] Backup access control
- [ ] Backup retention
- [ ] Backup testing
- [ ] Disaster recovery
- [ ] Recovery point objective
- [ ] Recovery time objective
- [ ] Immutable backups
- [ ] Restore testing

---

## 54. Infrastructure Security

- [ ] Server hardening
- [ ] Minimal software
- [ ] Firewall
- [ ] Network segmentation
- [ ] Private networks
- [ ] Public/private services
- [ ] SSH security
- [ ] Key-based authentication
- [ ] Least privilege
- [ ] OS updates
- [ ] Security patches
- [ ] Service isolation

---

## 55. Container Security

- [ ] Docker security
- [ ] Minimal images
- [ ] Non-root containers
- [ ] Read-only filesystem
- [ ] Container capabilities
- [ ] Secret management
- [ ] Image scanning
- [ ] Dependency scanning
- [ ] Container isolation
- [ ] Network isolation
- [ ] Resource limits

---

## 56. Cloud Security Fundamentals

- [ ] IAM
- [ ] Users
- [ ] Roles
- [ ] Policies
- [ ] Permissions
- [ ] Least privilege
- [ ] Security groups
- [ ] Private networks
- [ ] Public exposure
- [ ] Object storage permissions
- [ ] Encryption keys
- [ ] Secrets management
- [ ] Audit logs
- [ ] Cloud monitoring

---

## 57. TLS / HTTPS Deep Dive

- [ ] Why HTTPS?
- [ ] TLS handshake
- [ ] Certificates
- [ ] Certificate authorities
- [ ] Public/private keys
- [ ] Certificate validation
- [ ] TLS versions
- [ ] Cipher suites
- [ ] Perfect forward secrecy
- [ ] Certificate renewal
- [ ] HSTS

---

## 58. Secure API Design

- [ ] HTTPS only
- [ ] Authentication
- [ ] Authorization
- [ ] Input validation
- [ ] Output filtering
- [ ] Rate limiting
- [ ] Pagination limits
- [ ] Request size limits
- [ ] Error handling
- [ ] Security headers
- [ ] API versioning
- [ ] API inventory
- [ ] Audit logging

---

## 59. GraphQL Security

- [ ] GraphQL fundamentals
- [ ] Authentication
- [ ] Authorization
- [ ] Query depth limits
- [ ] Query complexity limits
- [ ] Introspection considerations
- [ ] Rate limiting
- [ ] Batch query abuse
- [ ] Resolver authorization
- [ ] DataLoader considerations

---

## 60. gRPC Security

- [ ] gRPC authentication
- [ ] TLS
- [ ] Mutual TLS
- [ ] Authorization
- [ ] Metadata security
- [ ] Request limits
- [ ] Message size limits
- [ ] Service identity

---

## 61. Security Testing

- [ ] Security test strategy
- [ ] Unit security tests
- [ ] Integration security tests
- [ ] API security tests
- [ ] Authentication tests
- [ ] Authorization tests
- [ ] Input validation tests
- [ ] Rate-limit tests
- [ ] Session tests
- [ ] File-upload tests
- [ ] Business-logic tests

---

## 62. SAST

- [ ] What is SAST?
- [ ] Static analysis
- [ ] Security linting
- [ ] Code scanning
- [ ] Vulnerability patterns
- [ ] False positives
- [ ] CI integration

---

## 63. DAST

- [ ] What is DAST?
- [ ] Black-box testing
- [ ] API scanning
- [ ] Authentication testing
- [ ] Injection testing
- [ ] Configuration testing
- [ ] Automated scanning

---

## 64. Dependency Scanning

- [ ] Dependency vulnerabilities
- [ ] CVE
- [ ] CWE
- [ ] CVSS
- [ ] Direct dependency
- [ ] Transitive dependency
- [ ] Lockfile
- [ ] Automated dependency updates
- [ ] Vulnerability alerts

---

## 65. Secret Scanning

- [ ] Detect leaked secrets
- [ ] Git history scanning
- [ ] API key detection
- [ ] Token detection
- [ ] Credential rotation
- [ ] Secret revocation
- [ ] Prevent secrets before commit

---

## 66. Penetration Testing Fundamentals

Only test systems you own or are explicitly authorized to assess.

- [ ] Reconnaissance concepts
- [ ] Attack surface mapping
- [ ] Endpoint discovery
- [ ] Authentication testing
- [ ] Authorization testing
- [ ] Input testing
- [ ] API testing
- [ ] Configuration testing
- [ ] Vulnerability validation
- [ ] Reporting
- [ ] Remediation

---

## 67. Security Tools

Learn what each category does rather than memorizing tools.

- [ ] Browser DevTools
- [ ] HTTP clients
- [ ] API testing tools
- [ ] Proxy tools
- [ ] Vulnerability scanners
- [ ] Dependency scanners
- [ ] Secret scanners
- [ ] SAST tools
- [ ] DAST tools
- [ ] Container scanners
- [ ] Network analysis tools
- [ ] Log analysis tools

---

## 68. OWASP Top 10: 2025

- [ ] A01 Broken Access Control
- [ ] A02 Security Misconfiguration
- [ ] A03 Software Supply Chain Failures
- [ ] A04 Cryptographic Failures
- [ ] A05 Injection
- [ ] A06 Insecure Design
- [ ] A07 Authentication Failures
- [ ] A08 Software/Data Integrity Failures
- [ ] A09 Security Logging & Alerting Failures
- [ ] A10 Mishandling Exceptional Conditions

---

## 69. OWASP API Security Top 10

- [ ] API1 Broken Object Level Authorization
- [ ] API2 Broken Authentication
- [ ] API3 Broken Object Property Level Authorization
- [ ] API4 Unrestricted Resource Consumption
- [ ] API5 Broken Function Level Authorization
- [ ] API6 Unrestricted Access to Sensitive Business Flows
- [ ] API7 Server-Side Request Forgery
- [ ] API8 Security Misconfiguration
- [ ] API9 Improper Inventory Management
- [ ] API10 Unsafe Consumption of APIs

---

## 70. Secure Architecture

- [ ] Secure-by-design
- [ ] Defense in depth
- [ ] Least privilege
- [ ] Network segmentation
- [ ] Service isolation
- [ ] Authentication boundaries
- [ ] Authorization boundaries
- [ ] Data boundaries
- [ ] Tenant isolation
- [ ] Secret boundaries
- [ ] Failure isolation

---

## 71. DevSecOps

- [ ] Security in development
- [ ] Security in code review
- [ ] SAST
- [ ] Dependency scanning
- [ ] Secret scanning
- [ ] Container scanning
- [ ] DAST
- [ ] Security tests
- [ ] CI security
- [ ] CD security
- [ ] Production monitoring
- [ ] Vulnerability management

---

## 72. Secure Development Lifecycle

- [ ] Security requirements
- [ ] Threat modeling
- [ ] Secure design
- [ ] Secure coding
- [ ] Code review
- [ ] Security testing
- [ ] Dependency scanning
- [ ] Deployment hardening
- [ ] Monitoring
- [ ] Incident response
- [ ] Security maintenance

---

## 73. Security Documentation

- [ ] Security architecture
- [ ] Threat model
- [ ] Data flow diagrams
- [ ] Authentication flow
- [ ] Authorization model
- [ ] Security assumptions
- [ ] Security controls
- [ ] Incident procedures
- [ ] Dependency inventory
- [ ] Security checklist

---

## 74. Practical Security Projects

### Beginner

- [ ] Secure login API
- [ ] Password reset system
- [ ] Email verification system
- [ ] Session-based authentication
- [ ] JWT authentication
- [ ] RBAC system

### Intermediate

- [ ] Multi-tenant authorization system
- [ ] Secure file-upload API
- [ ] API rate limiter
- [ ] Webhook verification system
- [ ] API gateway authentication
- [ ] Audit logging system

### Advanced

- [ ] OAuth/OIDC authentication server
- [ ] Security monitoring dashboard
- [ ] Secret management service
- [ ] API security testing framework
- [ ] Secure multi-tenant SaaS backend
- [ ] Distributed authentication system

---

## 75. Security Labs

Create intentionally vulnerable applications in a local lab and fix them.

- [ ] SQL injection lab
- [ ] NoSQL injection lab
- [ ] XSS lab
- [ ] CSRF lab
- [ ] IDOR/BOLA lab
- [ ] Broken RBAC lab
- [ ] JWT vulnerability lab
- [ ] Session fixation lab
- [ ] SSRF lab
- [ ] Path traversal lab
- [ ] File upload vulnerability lab
- [ ] Rate-limit bypass lab
- [ ] Race-condition lab
- [ ] Business-logic vulnerability lab
- [ ] Prototype-pollution lab

---

## 76. Security Code Review Checklist

For every backend endpoint, ask:

- [ ] Who can call this endpoint?
- [ ] Is authentication required?
- [ ] Is authorization checked?
- [ ] Is resource ownership checked?
- [ ] Is tenant isolation enforced?
- [ ] Is input validated?
- [ ] Is output safe?
- [ ] Can the request be replayed?
- [ ] Can the request be abused repeatedly?
- [ ] Can the request consume excessive resources?
- [ ] Can user input reach SQL?
- [ ] Can user input reach shell commands?
- [ ] Can user input control a URL?
- [ ] Can user input control a file path?
- [ ] Are sensitive fields protected?
- [ ] Are errors safe?
- [ ] Are security events logged?
- [ ] Are secrets protected?
- [ ] Are external dependencies trusted safely?

---

## 77. Final Backend Security Mastery Checklist

- [ ] I understand CIA
- [ ] I understand threats, vulnerabilities and risks
- [ ] I can threat-model a backend
- [ ] I understand trust boundaries
- [ ] I can build secure authentication
- [ ] I understand password security
- [ ] I understand sessions
- [ ] I understand cookies
- [ ] I understand JWT security
- [ ] I understand OAuth/OIDC security
- [ ] I understand MFA
- [ ] I understand authorization
- [ ] I understand RBAC
- [ ] I understand ABAC
- [ ] I understand BOLA/IDOR
- [ ] I understand privilege escalation
- [ ] I understand multi-tenant security
- [ ] I understand input validation
- [ ] I understand SQL injection
- [ ] I understand NoSQL injection
- [ ] I understand command injection
- [ ] I understand XSS
- [ ] I understand CSRF
- [ ] I understand SSRF
- [ ] I understand path traversal
- [ ] I understand prototype pollution
- [ ] I understand unsafe deserialization
- [ ] I understand cryptography fundamentals
- [ ] I understand encryption
- [ ] I understand hashing
- [ ] I understand digital signatures
- [ ] I can manage secrets securely
- [ ] I understand HTTPS/TLS
- [ ] I can secure APIs
- [ ] I can implement rate limiting
- [ ] I understand resource exhaustion
- [ ] I understand race conditions
- [ ] I understand business-logic vulnerabilities
- [ ] I can secure file uploads
- [ ] I can secure webhooks
- [ ] I understand dependency/supply-chain security
- [ ] I can secure a Node.js backend
- [ ] I understand database security
- [ ] I understand logging and auditing
- [ ] I understand monitoring and detection
- [ ] I understand incident response
- [ ] I understand backups and recovery
- [ ] I understand container security
- [ ] I understand cloud IAM/security fundamentals
- [ ] I understand SAST
- [ ] I understand DAST
- [ ] I understand dependency scanning
- [ ] I understand secret scanning
- [ ] I can perform secure code reviews
- [ ] I can threat-model applications
- [ ] I can build security into CI/CD
- [ ] I can design a secure production backend
- [ ] I can identify and fix common backend vulnerabilities
- [ ] I can reason about security instead of blindly using security libraries

---

# Recommended Learning Order

1. Security fundamentals
2. HTTP + HTTPS + TLS
3. Authentication security
4. Passwords + Sessions + Cookies
5. JWT + OAuth/OIDC
6. Authorization → RBAC → Permissions → Ownership
7. BOLA/IDOR + Privilege Escalation
8. Input Validation
9. SQL/NoSQL/Command Injection
10. XSS + CSRF + CORS
11. SSRF + Path Traversal + File Upload
12. Cryptography
13. Secrets Management
14. API Security + Rate Limiting
15. Business Logic + Race Conditions + Idempotency
16. Database + Node.js Security
17. Supply Chain + Dependencies
18. Logging + Monitoring + Incident Response
19. Threat Modeling + Secure Architecture
20. SAST + DAST + Security Testing
21. DevSecOps
22. Production/Cloud/Container Security

## Recommended Security Path

**Backend Fundamentals → Backend Security → OWASP Top 10 → API Security → ASVS → Security Testing → DevSecOps**
