# Redis: Modules 22-25

Redis supports TeamOps as a fast, bounded secondary system for cache, sessions, rate limits, and selected messaging patterns. PostgreSQL remains the durable source of truth. Use [Redis documentation](https://redis.io/docs/latest/develop/), the [Go client guide](https://redis.io/docs/latest/develop/clients/go/), and the [central catalog](../../01-learning-roadmap/MODULES.md).

## Learning Order

```text
22 data types, persistence, TTL
    -> 23 cache-aside and invalidation
    -> 24 Pub/Sub and Streams trade-offs
    -> 25 atomic rate limiting
```

## Working Rules

- Define key names, TTL, invalidation, ownership, and fallback before adding a Redis feature.
- Treat cache misses and Redis outages as expected failure modes.
- Use expiration for temporary keys; do not rely on memory eviction as a business rule.
- Do not use Pub/Sub when durable delivery/replay is required; evaluate Streams or the dedicated messaging module.
- Bound values, connection usage, and retry behavior.

## Shared Completion Standard

Implement a justified TeamOps Redis use case with metrics/logging, safe degradation, tests, and a written cache/session/rate-limit policy. The application must remain correct when Redis data is missing or unavailable.
