# Module 52: Application Security

Apply secure defaults to the TeamOps API, client, data layer, and deployment configuration. Use the current [OWASP Top 10](https://owasp.org/Top10/2025/), [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/), [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/), and [Go security best practices](https://go.dev/doc/security/best-practices).

## Learn

- Threat modeling: assets, trust boundaries, entry points, abuse cases, and mitigations.
- Input validation, output encoding, parameterized SQL, secure file handling, and error disclosure.
- Injection, broken access control, authentication failures, XSS, CSRF, SSRF, CORS, security misconfiguration, dependency risk, and secrets management.
- Rate limiting, least privilege, security headers, logging without sensitive data, dependency scanning, fuzzing, and code review.

## Practice Deliverable

Create a concise TeamOps threat model and security checklist. In a local/disposable environment, introduce or inspect one safe training example of a weakness, such as an authorization bypass test, unsafe query construction, missing input validation, unsafe redirect, or overly broad CORS setting. Fix it and add a regression test.

## Verify

```bash
go vet ./...
go test ./...
go test -race ./...
govulncheck ./...
```

Run client tests and dependency checks when the frontend exists. Treat automated scans as evidence to investigate, not proof of security.

## Completion Criteria

- [ ] Define an asset, threat, control, and test for one TeamOps feature.
- [ ] Validate input at the server boundary and parameterize database values.
- [ ] Prove authorization with negative tests, not only successful requests.
- [ ] Configure CORS to specific trusted origins/methods/headers rather than using a broad default.
- [ ] Keep secrets out of source, URLs, browser bundles, logs, and error responses.
- [ ] Scan Go dependencies and review reachable findings before remediation decisions.
- [ ] Document the fixed weakness and the test that prevents regression.

## Common Mistakes

Relying only on frontend checks, trusting client input, detailed production error responses, wildcard CORS with credentials, secrets in committed configuration, logging tokens, missing upload limits/content checks, unreviewed dependency updates, and confusing a passing scanner with a complete security review.

## TeamOps Connection

Security is continuous, not a one-time stage. Apply this checklist to authentication, RBAC, file uploads, Docker images, GitHub Actions secrets, AWS IAM, Terraform state, Kubernetes Secrets, and observability data. Record fixes and review findings in TeamOps contributions.
