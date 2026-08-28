# Authentication and Security Training

This section secures the TeamOps API, client, and deployment path. It covers modules 49-52 from the [central catalog](../01-learning-roadmap/MODULES.md): authentication, authorization, SSO, TLS, and application security.

## Learning Order

1. Model users, sessions/tokens, roles, and authorization boundaries.
2. Add JWT or session authentication to the existing Go API and React client.
3. Understand OAuth2/OIDC and integrate one development identity provider.
4. Learn certificate and TLS behavior before deploying HTTPS.
5. Threat-model the application and test common web/API vulnerabilities.

## Prerequisites

Complete the Go API, React API integration, and PostgreSQL data model. Do not add SSO before basic local authentication and authorization are testable.

## Practical Artifacts

- Authentication flow diagram and role/permission matrix.
- Protected Go routes and authenticated React routes.
- OIDC integration configuration that uses environment variables only.
- TLS test setup and an application security checklist.

## Completion Standard

Implement tested authentication and role-based authorization; reject invalid or expired credentials; demonstrate secure logout behavior; use HTTPS in a representative environment; and remediate at least one deliberate injection, XSS, CSRF, SSRF, or misconfiguration example.

## Common Debugging Areas

Token expiry/refresh, audience and issuer validation, authorization checks hidden in UI only, CORS confusion, secret leakage, insecure redirects, incorrect TLS trust chains, and missing server-side validation.

## TeamOps Handoff

Security gates TeamOps authentication, user management, RBAC, secure file uploads, and AWS IAM choices. Update feature and contribution trackers whenever a shared security boundary changes.

## Primary References

- [OpenID Connect: How it works](https://openid.net/developers/how-connect-works/): authentication flow, relying parties, identity providers, and token roles.
- [OAuth 2.0 Security Best Current Practice](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics): protocol-level security guidance.
- [OWASP Top 10](https://owasp.org/www-project-top-ten/): current web application security awareness baseline.
- [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/): practical verification guidance.
- [Go security best practices](https://go.dev/doc/security/best-practices): dependency scanning, fuzzing, race detection, and `go vet`.
- [Go `crypto/tls`](https://pkg.go.dev/crypto/tls) and [`net/http`](https://pkg.go.dev/net/http): implementation references for HTTPS services.

Use current official provider documentation for provider-specific integration details. Do not copy security snippets without understanding the threat model and the assumptions they require.
