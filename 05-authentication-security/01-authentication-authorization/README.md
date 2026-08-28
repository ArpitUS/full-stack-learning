# Module 49: Authentication and Authorization

Build server-enforced identity and permissions for TeamOps. Authentication answers who the caller is; authorization answers whether that caller may perform a specific action. Use [OpenID Connect concepts](https://openid.net/developers/how-connect-works/), [OAuth 2.0 security guidance](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-security-topics), and [OWASP authentication guidance](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html).

## Learn

- Authentication versus authorization, local credentials versus delegated identity, sessions versus bearer tokens.
- JWT structure and validation; access, refresh, and ID tokens have different purposes.
- OAuth 2.0 authorization, OpenID Connect authentication, scopes, claims, roles, and RBAC.
- Token expiry, revocation/logout limits, password storage with a modern password hash, and server-side authorization checks.
- SAML as an enterprise federation technology; understand its role without implementing it before OIDC basics.

## Practice Deliverable

Implement authenticated TeamOps API routes with role checks. Define a role/permission matrix for at least member and administrator actions. Use the server to authenticate the caller and authorize every protected resource operation. Add a React session state only after the API behavior is defined.

## Verify

```bash
go test ./...
go test -race ./...
go vet ./...
govulncheck ./...
```

Test unauthenticated, expired/invalid credential, authenticated-but-forbidden, and permitted requests.

## Completion Criteria

- [ ] Explain the purpose of access, ID, and refresh tokens.
- [ ] Validate signature, issuer, audience, expiry, and intended token use before trusting token claims.
- [ ] Enforce authorization in Go handlers/services, not only in React navigation.
- [ ] Store passwords only with an appropriate password-hashing algorithm; never log them.
- [ ] Add tests that prove one user cannot access another team's protected data.
- [ ] Document token/session storage, expiry, logout, and rotation decisions.

## Common Mistakes

Using an ID token as an API credential, decoding JWTs without verifying them, accepting arbitrary algorithms, missing issuer/audience checks, frontend-only RBAC, long-lived bearer tokens, credentials in URLs/logs, and vague roles without resource-level rules.

## TeamOps Connection

This enables the Authentication, User Management, Teams, and RBAC feature rows. Record decisions and implementation work in [TeamOps stages](../../12-projects/teamops/STAGES.md) and [contributions](../../12-projects/teamops/CONTRIBUTIONS.md).

## Next

Continue to [Module 50: SSO Integration](../02-sso-integration/).
