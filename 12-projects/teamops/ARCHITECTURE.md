# TeamOps Architecture

## Current Target

```text
Browser
  -> React + TypeScript client
  -> HTTPS entry: ALB or Kubernetes Ingress
  -> Go modular-monolith REST API
  -> PostgreSQL: durable source of truth
  -> Redis: cache, sessions/rate limits, selected transient events
  -> S3: private object storage for authorized file uploads

Supporting platform: Docker Compose -> CI/CD -> ECR/ECS or Kubernetes
Infrastructure: Terraform
Operations: structured logs, metrics, traces, dashboards, alerts
```

## Boundary Rules

| Boundary | Responsibility |
| --- | --- |
| React client | Accessible UI, typed request models, local UI state, safe display of server results. |
| Go API | Authentication, authorization, validation, domain behavior, error model, and orchestration. |
| PostgreSQL | Durable entities, relationships, constraints, transactions, and audit records. |
| Redis | Bounded transient data with explicit TTL, invalidation, and outage behavior. |
| S3 | Private objects; API authorizes metadata and short-lived presigned URL issuance. |
| Infrastructure | Repeatable network, identity, deployment, secret delivery, logging, and recovery boundaries. |

## Default Architecture Decision

Start as a modular monolith. Introduce separate services only when a documented requirement demonstrates an independent scaling, deployment, ownership, or failure-isolation need. Store such decisions in `01-planning/decisions/`.

## Contract Rules

- Version or evolve APIs deliberately; backend and frontend changes that alter a contract are reviewed together.
- API errors have stable machine-readable codes and user-safe messages.
- Authorization is checked server-side for every protected resource operation.
- PostgreSQL is authoritative. Redis cache invalidation occurs only after a successful source-of-truth change.
- Propagate request/trace context through API, database/cache calls, and asynchronous work where applicable.

## Related Curriculum

- API foundation: Modules 11-15
- Data and cache: Modules 16-25
- React client: Modules 30-33
- Security: Modules 49-52
- Platform and operations: Modules 37-48 and 53-60
