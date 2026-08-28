# TeamOps Backend

This folder receives the shared Go service when TeamOps reaches Stage 1. Learn language/API patterns first in `02-go-backend/`; use this folder for approved shared implementation.

## Expected Responsibilities

- Go API routing, request validation, authentication, authorization, domain services, error model, and graceful shutdown.
- PostgreSQL migrations/repositories/transactions and Redis integrations with explicit key/TTL/invalidation rules.
- Background jobs or event consumers only when an explicit requirement justifies them.
- Unit, integration, race, and API tests as applicable.

## Implementation Rules

- Keep package boundaries clear: transport, application/domain behavior, persistence, and infrastructure configuration should not be mixed casually.
- Enforce validation and authorization server-side for every protected action.
- Use parameterized SQL, bounded database pools, short transactions, and cancellation contexts.
- Preserve useful error context internally but return stable, safe API errors to clients.
- Expose health/readiness and operational telemetry without leaking sensitive data.

See [Go backend modules](../../../02-go-backend/), [database modules](../../../04-databases/), [architecture](../ARCHITECTURE.md), and [definition of done](../DEFINITION_OF_DONE.md).
