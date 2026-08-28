# TeamOps

An authenticated team and project management application.

## Target Architecture

React and TypeScript client -> ALB -> Go REST API -> PostgreSQL and Redis.

Supporting platform: S3 file storage, OIDC/SSO, Docker, GitHub Actions, ECR/ECS, Terraform, Kubernetes/EKS, and observability.

## Project Goal

TeamOps is a production-style team and project management application. It exists to turn shared learning into end-to-end evidence: a user can sign in, join a team, manage projects and tasks, attach files, receive notifications, and operate the system through repeatable delivery and observability practices.

## Learning Integration

TeamOps is built in small stages that follow the curriculum dependencies. The source of the staged plan is [STAGES.md](STAGES.md); do not mark a stage complete until its completion criteria are met.

## Start Here

1. Read [PROJECT_WORKFLOW.md](PROJECT_WORKFLOW.md) before claiming a shared task.
2. Use [ARCHITECTURE.md](ARCHITECTURE.md) for the current system boundaries and contracts.
3. Select a scoped vertical slice from [BACKLOG.md](BACKLOG.md), then link it to a catalog module and stage.
4. Put planning, frontend, backend, and infrastructure artifacts in their relevant project directories.
5. Meet the [Definition of Done](DEFINITION_OF_DONE.md), open a pull request, then update the feature/stage/contribution trackers after review.

## Feature Tracker

| Feature | Backend | Frontend | Database | Tests | Deployed |
| --- | --- | --- | --- | --- | --- |
| Authentication | [ ] | [ ] | [ ] | [ ] | [ ] |
| User management | [ ] | [ ] | [ ] | [ ] | [ ] |
| Teams | [ ] | [ ] | [ ] | [ ] | [ ] |
| Projects | [ ] | [ ] | [ ] | [ ] | [ ] |
| Tasks | [ ] | [ ] | [ ] | [ ] | [ ] |
| File upload | [ ] | [ ] | [ ] | [ ] | [ ] |
| RBAC | [ ] | [ ] | [ ] | [ ] | [ ] |
| Audit logs | [ ] | [ ] | [ ] | [ ] | [ ] |
| Notifications | [ ] | [ ] | [ ] | [ ] | [ ] |

## Collaboration

TeamOps is shared by [Arpit](../../../15-learners/arpit/) and [Ashish](../../../15-learners/ashish/). Keep learner-specific notes, plans, and progress in their individual workspaces. Record shared implementation work in [CONTRIBUTIONS.md](CONTRIBUTIONS.md).

Use one of these contribution categories:

- Arpit
- Ashish
- Pair Programming
- Shared
- Review

## Project Areas

- [Planning](01-planning/): requirements, domain model, decisions, API contracts, and backlog.
- [Frontend](02-frontend/): React and TypeScript client implementation and client tests.
- [Backend](03-backend/): Go API, database migrations, background work, and API tests.
- [Infrastructure](04-infrastructure/): Docker, CI/CD, AWS, Terraform, Kubernetes, and operational configuration.
