# Database Training

This section teaches TeamOps data modeling, PostgreSQL query design and operation, then Redis as a bounded cache, session store, and messaging/rate-limit tool. Use [the catalog](../01-learning-roadmap/MODULES.md) for modules 16-25.

## Learning Order

1. PostgreSQL modules 16-18: schema, constraints, CRUD, joins, reporting, and query reasoning.
2. Modules 19-21: indexes, plans, transactions, locking, and Go connection pools.
3. Redis modules 22-25: data structures, TTL, cache-aside, invalidation, Pub/Sub, and rate limits.

## Prerequisites

Complete the HTTP/API foundation. Start schema work before TeamOps persistence; add Redis only once the PostgreSQL path is correct and measured.

## Practical Artifacts

- Versioned migrations, seed data, and schema diagrams for TeamOps.
- SQL exercises with expected results and `EXPLAIN ANALYZE` evidence for optimized queries.
- Transactional service operations and configured connection pools.
- Redis integration with an explicit key scheme, TTL policy, invalidation rule, and fallback behavior.

## Completion Standard

Model TeamOps relationships with constraints; implement parameterized queries and migrations; demonstrate an indexed slow-query improvement; protect a multi-write operation with a transaction; and add a measured Redis use case without treating cache as the source of truth.

## Common Debugging Areas

N+1 queries, missing indexes, incorrect joins, transaction scope errors, lock contention, pool exhaustion, stale cache data, cache stampedes, and keys without expiration.

## TeamOps Handoff

Database work enables the backend stages, authentication ownership rules, file metadata, audit logs, and later metrics. Record schema-impacting shared changes in [TeamOps contributions](../12-projects/teamops/CONTRIBUTIONS.md).
