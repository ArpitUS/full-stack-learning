# Go Backend Training

This section builds the backend foundation for TeamOps: Go language fluency, HTTP services, persistence-facing API design, reliability, messaging, tests, and networking. It is not a second curriculum; use the [central catalog](../01-learning-roadmap/MODULES.md) for complete module definitions.

## Module Map and Order

1. Modules 03-10: `01-go-programming` establishes language, concurrency, runtime, and systems foundations.
2. Modules 11-15: `02-api-development` turns those foundations into a layered Go API.
3. Modules 26-29: `03-distributed-systems` adds boundaries, reliability, and messaging after the API is sound.
4. Modules 34-36: `04-testing-design-patterns` verifies behavior and applies patterns intentionally.
5. Modules 59-60: `05-networking` extends network understanding after HTTP, DNS, and resilience are familiar.

## Prerequisites

Complete modules 01-02. Before API persistence work, complete PostgreSQL module 16.

## Practical Artifacts

- Small Go exercises and benchmarks in the mapped topic folders.
- A standard-library API, then a Gin API with validation, middleware, structured errors, and graceful shutdown.
- Test suites using unit, integration, race, and benchmark commands as appropriate.
- Architecture decision records for service boundaries and reliability trade-offs.

## Completion Standard

Build a Go REST API that validates input, returns a consistent error model, supports cancellation and graceful shutdown, has tested business logic, and explains its package boundaries. Use `go test ./...`, `go test -race ./...`, and benchmarks or profiles when relevant.

## Common Debugging Areas

Nil interfaces, pointer ownership, goroutine leaks, unbounded concurrency, channel deadlocks, forgotten context cancellation, race conditions, bad error wrapping, and exhausted database connections.

## TeamOps Handoff

Modules 11-15 establish the TeamOps backend. Modules 16-25 connect it to PostgreSQL and Redis. Modules 26-29 add asynchronous work only after the modular monolith is observable and tested. See [TeamOps stages](../12-projects/teamops/STAGES.md).
