# Module 22: Redis Fundamentals

Learn Redis data types, TTL/expiration, persistence concepts, and Go client usage. Use [Redis data types](https://redis.io/docs/latest/develop/data-types/), [Redis persistence](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/), and the [Go client guide](https://redis.io/docs/latest/develop/clients/go/).

## Practice Deliverable

Store a TeamOps development session or short-lived value in Redis. Use a documented key format, a TTL, and commands appropriate to the data type. Demonstrate expiration and a cache/session miss.

## Verify

```bash
redis-cli PING
redis-cli TTL <key>
redis-cli TYPE <key>
```

## Completion Criteria

- [ ] Choose strings, hashes, lists, sets, sorted sets, or streams based on access needs.
- [ ] Explain TTL, expiration, eviction, and persistence as different concerns.
- [ ] Use key prefixes/namespaces and avoid unbounded values.
- [ ] Handle a missing/expired key as normal application behavior.

## Common Mistakes

No TTL for temporary data, large keys, ambiguous key names, storing durable truth only in Redis, assuming eviction is predictable, and exposing Redis without authentication/network isolation.

## Next

Continue to [Module 23](../02-caching/).
