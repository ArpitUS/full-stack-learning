# Module 23: Redis Caching

Use Redis to reduce repeat work while preserving PostgreSQL correctness. Study [Redis data types](https://redis.io/docs/latest/develop/data-types/), [Redis Go clients](https://redis.io/docs/latest/develop/clients/go/), and cache patterns from reliable system-design references.

## Learn

- Cache-aside, lazy loading, read-through, write-through, write-behind, and refresh-ahead trade-offs.
- Hits/misses, TTL, invalidation, stale data, cache warming, negative caching, and consistency.
- Stampede, penetration, avalanche, hot keys, memory pressure, TTL jitter, locks, and request coalescing.

## Practice Deliverable

Cache one read-heavy TeamOps endpoint using cache-aside. Define the cache key, TTL, invalidation event, miss path, and Redis-outage fallback. Log or count hits, misses, invalidations, and errors.

## Completion Criteria

- [ ] PostgreSQL remains authoritative on every correctness-sensitive update.
- [ ] Cache invalidation happens after a successful source-of-truth change.
- [ ] A cache miss, stale value, and Redis outage have defined behavior.
- [ ] TTL is selected and documented rather than arbitrary.
- [ ] Tests verify hit, miss, invalidation, and fallback paths.

## Common Mistakes

Cache-aside without invalidation, deleting cache before a failed database write, caching permission-sensitive data with incomplete keys, thundering-herd misses, infinite retry loops, and caching errors accidentally.

## Next

Continue to [Module 24](../03-pubsub-messaging/).
