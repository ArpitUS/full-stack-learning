# Docker Training

Docker turns the TeamOps services into repeatable local and deployment artifacts. This section covers catalog modules 37-38.

## Learning Order

1. Containerize one Go service: image, Dockerfile, ports, volumes, environment, and health check.
2. Improve it with multi-stage builds, small non-root runtime images, and build-cache awareness.
3. Use Compose to run the React client, Go API, PostgreSQL, and Redis together.

## Prerequisites

Have a runnable Go API; complete database modules before composing the local multi-service environment.

## Practical Artifacts

- Dockerfile for the API and client.
- `.dockerignore`, health-check strategy, and non-secret environment examples.
- `compose.yaml` for the local TeamOps dependency graph.
- A short runbook for starting, testing, resetting, and debugging containers.

## Completion Standard

Build a small production-oriented image, run services as a non-root user where possible, start the full local stack with one command, persist database data intentionally, and diagnose an image, network, or environment failure using container tooling.

## Common Debugging Areas

Incorrect build context, port mapping versus service networking, missing environment variables, bind-mount permissions, stale images, large images, root containers, and health checks that only prove a process exists.

## TeamOps Handoff

The Compose environment is the contract used by CI/CD and deployment stages. Keep TeamOps container work under `12-projects/teamops/` and use this section for experiments and notes.

## Primary References

- [Docker Get Started](https://docs.docker.com/get-started/): images, containers, registries, volumes, and workflows.
- [Dockerfile reference](https://docs.docker.com/reference/dockerfile/): instructions and build behavior.
- [Build best practices](https://docs.docker.com/build/building/best-practices/): small, secure, maintainable images.
- [Multi-stage builds](https://docs.docker.com/build/building/multi-stage/): separate build tools from runtime images.
- [Docker Compose](https://docs.docker.com/compose/): local multi-container application definition.
- [Container security](https://docs.docker.com/engine/security/): runtime isolation assumptions and limitations.

Use the module guides below to build evidence. Docker is a packaging and runtime tool, not a substitute for application validation, authorization, secrets management, or observability.
