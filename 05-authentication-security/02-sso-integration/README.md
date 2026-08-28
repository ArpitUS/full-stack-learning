# Module 50: SSO Integration

Integrate a development OpenID Connect provider with the TeamOps React client and Go API. OIDC adds identity information to OAuth 2.0 authorization flows. Use [OpenID Connect: How it works](https://openid.net/developers/how-connect-works/), the [OpenID Connect Core specification](https://openid.net/specs/openid-connect-core-1_0.html), and the provider's current official documentation.

## Prerequisites

Complete Module 49 and have server-side role/permission rules under test. Use a development identity provider and test accounts. Do not implement a custom identity provider for this training module.

## Learn

- Relying party/client, authorization server/OpenID provider, resource server, redirect URI, scopes, claims, issuer, discovery, and JWKS.
- Authorization Code flow with PKCE for browser clients.
- Code/token exchange boundaries, token validation, session establishment, secure logout, and provider/session differences.
- Mapping external identity claims to internal TeamOps users and roles without trusting arbitrary claims.

## Practice Deliverable

Integrate one development OIDC provider. Configure exact redirect URIs, use Authorization Code plus PKCE for the React client, validate tokens/claims in the Go API or trusted backend boundary, create/link an internal TeamOps user, and implement secure local logout.

## Completion Criteria

- [ ] Use provider discovery and keys rather than hard-coded signing secrets.
- [ ] Register exact redirect URIs; reject untrusted redirect targets.
- [ ] Validate issuer, audience, signature, expiry, nonce/state where applicable, and intended token type.
- [ ] Keep provider configuration and secrets in environment-specific configuration, not Git.
- [ ] Test login, denied authorization, expired session/token, unauthorized role, and logout behavior.
- [ ] Explain why the client cannot be the sole token validation or authorization authority.

## Common Mistakes

Implicit flow for new browser applications, no PKCE/state/nonce, wildcard redirects, putting client secrets in browser code, using access tokens as proof of identity, trusting email alone for role assignment, and assuming provider logout always revokes local sessions.

## TeamOps Connection

This upgrades TeamOps authentication from local credentials to a development SSO flow. Keep identity-provider configuration documented as setup instructions without committing secrets.

## Next

Continue to [Module 51: SSL, TLS, and HTTPS](../03-ssl-tls-https/).
