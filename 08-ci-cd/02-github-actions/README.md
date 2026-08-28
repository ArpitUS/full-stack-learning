# Module 40: GitHub Actions

Implement pull-request quality checks and a traceable artifact workflow using GitHub Actions. Primary references: [Understanding GitHub Actions](https://docs.github.com/en/actions/get-started/understand-github-actions), [workflow syntax](https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax), [secure use](https://docs.github.com/en/actions/reference/security/secure-use), and [Docker builds with GitHub Actions](https://docs.docker.com/build/ci/github-actions/).

## Prerequisites

Complete Module 39. The Go and frontend projects must have reproducible local test/build commands. Docker image publishing requires a versioned Dockerfile and a registry/deployment target.

## Learn

- Workflow events, jobs, steps, runners, matrices, conditions, concurrency, variables, contexts, outputs, artifacts, and dependency caching.
- Pull request versus push workflow security boundaries; treat pull request content and event data as untrusted input.
- `GITHUB_TOKEN` permissions, repository/environment secrets, OpenID Connect for short-lived cloud credentials, and action pinning.
- Service containers for PostgreSQL/Redis, Docker Buildx, image metadata, attestations, and deployment environments.

## Practice Deliverable

Add a TeamOps pull-request workflow that checks the relevant changed projects: Go format/vet/tests, TypeScript typecheck/lint/tests/build, and optional Docker build validation. Use service containers when integration tests require PostgreSQL or Redis. Add a separate protected publish/deploy workflow only after the CI workflow is reliable.

## Verification

1. Open a pull request with a passing change and inspect every job log.
2. Open a controlled failing change and verify the workflow fails at the correct gate.
3. Confirm the workflow uses minimum permissions and no secrets appear in logs.
4. If publishing an image, verify its tag/digest is traceable to the commit and run.

## Completion Criteria

- [ ] Use narrow `pull_request`/`push` triggers and path filters only when they cannot skip required validation.
- [ ] Pin third-party actions to a full commit SHA or an approved immutable policy.
- [ ] Set explicit least-privilege `permissions` and separate deploy credentials from CI checks.
- [ ] Cache dependencies safely without treating cache contents as trusted artifacts.
- [ ] Publish artifacts/images only after relevant tests pass and use immutable references/digests for deployment.
- [ ] Use environments, approvals, and/or concurrency controls to prevent conflicting production deployments.

## Common Mistakes

Using `pull_request_target` to execute untrusted pull-request code, interpolating untrusted context values directly into shell commands, broad write permissions, secrets in logs, action tags that can move, path filters that bypass tests, cache misuse, and simultaneous deploys overwriting each other.

## TeamOps Connection

This implements the CI portion of TeamOps Stage 7. Record workflow changes and verified runs in [TeamOps contributions](../../12-projects/teamops/CONTRIBUTIONS.md). Use the existing [pull request template](../../.github/pull_request_template.md) to document verification.

## Next

Continue to [Module 41: Jenkins](../03-jenkins/).
