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
