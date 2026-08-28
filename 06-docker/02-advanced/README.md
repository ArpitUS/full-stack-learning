# Module 38: Docker Advanced

Build a small, secure, repeatable local TeamOps stack with multi-stage images and Docker Compose. Use [multi-stage builds](https://docs.docker.com/build/building/multi-stage/), [Compose](https://docs.docker.com/compose/), [Compose networking](https://docs.docker.com/compose/how-tos/networking/), and [build best practices](https://docs.docker.com/build/building/best-practices/).

## Prerequisites

Complete Module 37. Have a runnable Go API and the PostgreSQL/Redis modules sufficiently defined to start their local dependencies. Do not use Compose to hide an application that cannot run independently.

## Learn

- Named multi-stage build stages, build targets, cache-friendly Dockerfile order, and minimal runtime images.
- Non-root runtime users, read-only filesystem considerations, base-image updates, and vulnerability scanning.
- Compose services, networks, volumes, environment files, service DNS names, dependencies, health checks, and profiles.
- Persistent development data versus disposable test data and safe local environment reset.

## Practice Deliverable

Run TeamOps API, React client, PostgreSQL, and Redis with `compose.yaml`. Use a multi-stage API build, a non-root runtime user where compatible, named volumes for intentionally persistent database data, health checks, non-secret configuration examples, and service-to-service hostnames rather than `localhost` inside containers.

## Verify

```bash
docker compose config
docker compose up --build
docker compose ps
docker compose logs --follow api
docker compose exec api <health-or-test-command>
docker compose down
```

Use `docker compose down --volumes` only when intentionally discarding local database data. Document this explicitly in the TeamOps runbook.

## Completion Criteria

- [ ] Build and run the full local stack from a documented command on a clean machine/profile.
- [ ] Use named build stages and copy only the needed runtime artifacts.
- [ ] Use service names for inter-container connections and host port mappings only for developer access.
- [ ] Keep secrets out of images, `compose.yaml`, Git history, and logs; commit only safe examples.
- [ ] Demonstrate a database migration/seed path and a service health failure diagnosis.
- [ ] Explain the local Compose model versus ECS/Kubernetes deployment responsibilities.

## Common Mistakes

Connecting containers to `localhost`, `depends_on` mistaken for application readiness, mounting source into production-style images, containers running as root, build secrets in layers, accidental volume deletion, image builds that depend on an uncommitted local file, and no reproducible reset/run instructions.

## TeamOps Connection

This is TeamOps Stage 6. The Compose file and service Dockerfiles become inputs to CI/CD image builds and AWS/ECS or Kubernetes deployments. Record the shared implementation in [TeamOps contributions](../../12-projects/teamops/CONTRIBUTIONS.md) and stage tracker.

## Next

Continue to [Module 39: CI/CD Fundamentals](../../08-ci-cd/01-fundamentals/).
