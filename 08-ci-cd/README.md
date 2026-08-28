# CI/CD Training

This section automates the checks and delivery path for TeamOps through catalog modules 39-41: pipeline concepts, GitHub Actions, and Jenkins.

## Learning Order

1. Define build, test, static-analysis, image, deployment, and rollback stages.
2. Implement pull-request checks in GitHub Actions.
3. Add artifact/image publication and deployment gates only after tests are reliable.
4. Create an equivalent Jenkins pipeline to understand controller/agent and credential trade-offs.

## Prerequisites

Use a consistent Git workflow, runnable tests, and Docker builds. Deployment pipelines depend on a defined AWS/ECS or Kubernetes target.

## Practical Artifacts

- CI pipeline diagram and failure/rollback runbook.
- GitHub Actions workflow for formatting, tests, and builds.
- Dependency cache and artifact strategy.
- Jenkinsfile that explains differences from GitHub Actions.

## Completion Standard

A pull request automatically runs the relevant checks; a failed test blocks delivery; secrets are stored in platform secret stores; and a deployable image can be traced to a commit with a documented rollback method.

## Common Debugging Areas

Wrong trigger scopes, unpinned actions, cache mistakes, secrets in logs, inconsistent local/CI tooling, missing permissions, mutable image tags, and deployment without a verified artifact.

## TeamOps Handoff

Pipelines validate TeamOps contributions and later deploy its Docker image. Use the shared project for production workflows, not learner directories.

## Primary References

- [GitHub Actions documentation](https://docs.github.com/en/actions): workflows, runners, CI/CD, environments, artifacts, caching, and secure use.
- [GitHub Actions security hardening](https://docs.github.com/en/actions/security-for-github-actions/security-guides/security-hardening-for-github-actions): permissions, action pinning, untrusted input, and secrets.
- [Docker Build GitHub Actions](https://docs.docker.com/build/ci/github-actions/): Buildx, image metadata, attestation, cache, and publication practices.
- [Jenkins Pipeline documentation](https://www.jenkins.io/doc/book/pipeline/): pipeline-as-code, Jenkinsfiles, agents, syntax, and multibranch builds.
- [SLSA](https://slsa.dev/): supply-chain concepts and provenance guidance for later advanced work.

## Pipeline Rule

Keep CI and deployment changes small, reviewed, reproducible, and observable. A pipeline is production code: it needs least privilege, safe handling of untrusted inputs, tested failure paths, and a documented rollback strategy.
