# Module 51: SSL, TLS, and HTTPS

Learn how TLS protects traffic and how to deploy HTTPS correctly for Go services. The term SSL is historical; use TLS for current implementations. Primary references: [Go `crypto/tls`](https://pkg.go.dev/crypto/tls), [Go `net/http`](https://pkg.go.dev/net/http), [OWASP TLS Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html), and [Mozilla SSL Configuration Generator](https://ssl-config.mozilla.org/).

## Learn

- TLS handshake at a high level: ClientHello, ServerHello, certificate validation, key agreement, and encrypted application data.
- Public/private keys, certificate authorities, root/intermediate chains, SANs, expiration, rotation, and revocation limitations.
- TLS termination at a load balancer versus end-to-end TLS and mutual TLS.
- Secure protocol/cipher defaults, HTTP redirects, HSTS, certificate management, and local-development trust differences.

## Practice Deliverable

Serve a local Go endpoint over TLS with a development certificate. Inspect the certificate chain and handshake using a client tool, then document where TLS terminates in the TeamOps AWS ALB deployment and how traffic is protected behind that boundary.

## Verify

```bash
curl -v https://localhost:<port>/health
openssl s_client -connect localhost:<port> -servername localhost
go test ./...
```

Use development certificates only for local exercises. Never bypass production certificate validation to make an integration work.

## Completion Criteria

- [ ] Explain certificate subject/SAN, issuer, chain, and expiration.
- [ ] Configure a current TLS server using safe library defaults rather than obsolete SSL/TLS versions.
- [ ] Redirect HTTP to HTTPS where appropriate and identify exceptions such as local development/health infrastructure.
- [ ] Explain the ALB termination decision and the trust boundary behind it.
- [ ] Document certificate renewal/rotation ownership and failure monitoring.

## Common Mistakes

Disabling certificate verification, trusting a hostname mismatch, using expired/self-signed certificates in production, logging secrets, assuming TLS termination protects unencrypted internal hops automatically, and confusing encryption with authorization.

## TeamOps Connection

TLS is required for browser authentication and secure deployment. Coordinate with AWS ALB, OIDC redirect URIs, secrets/configuration, and Kubernetes Ingress before marking a deployed TeamOps route secure.

## Next

Continue to [Module 52: Application Security](../04-application-security/).
