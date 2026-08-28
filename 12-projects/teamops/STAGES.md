# TeamOps Stages

TeamOps is a shared production-style application. Each stage reuses concepts already practiced in the mapped modules; it is not a prerequisite to finishing every module.

| Stage | Goal | Curriculum inputs | Shared output | Completion criteria |
| --- | --- | --- | --- | --- |
| 1 | Foundation API | 03-15 | Go service with health endpoint, routing, validation, error model, and tests | API starts locally, has documented endpoints, and core logic is tested. |
| 2 | Durable data | 16-21 | PostgreSQL schema, migrations, repositories, and transactional operations | Fresh setup is repeatable and data constraints are enforced. |
| 3 | Authentication and authorization | 49-52 | User identity, protected routes, RBAC, secure configuration | Unauthorized access is rejected by server-side tests. |
| 4 | React client | 30-33 | Typed client, routes, forms, async states, API integration | A user can complete one end-to-end workflow with accessible error/loading states. |
| 5 | Cache and events | 22-25, 29 | Redis cache/rate limit and one justified notification/event flow | Cache has invalidation/TTL rules; async failures are observable. |
| 6 | Local platform | 37-38 | Dockerfiles, Compose, service configuration, health checks | Full stack starts from documented commands in a clean environment. |
| 7 | Quality pipeline | 34, 39-41 | Unit/integration/E2E checks, GitHub Actions, artifact/image build | Pull requests run checks and artifacts trace to commits. |
| 8 | AWS deployment | 42-48, 51 | AWS network, compute/ECS, ALB, S3/RDS, HTTPS, logging | A non-production deployment has health checks, least privilege, and rollback notes. |
| 9 | Infrastructure and orchestration | Terraform, 53-56 | Reproducible infrastructure plus Kubernetes deployment option | Infrastructure is reviewed through plans and workload has probes/scaling boundaries. |
| 10 | Operations | 57-60, 63-66 | Logs, metrics, traces, load test, incident runbook, architecture record | A simulated incident is diagnosed from telemetry and improvements are documented. |

## Stage Rules

- Each stage may be split into small pull requests; do not wait for a stage to be perfect before reviewing it.
- Keep experiments in learning workspaces until they are suitable for the shared application.
- Record completed shared work in [CONTRIBUTIONS.md](CONTRIBUTIONS.md) and update the feature tracker in [README.md](README.md).
- Prefer the modular monolith through the core stages. Introduce service boundaries only with an explicit decision record and a demonstrated need.
