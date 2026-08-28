# Module 25: Redis Rate Limiting

Protect sensitive or costly API operations with an explicit, atomic rate-limit algorithm. Use [Redis transactions](https://redis.io/docs/latest/develop/interact/transactions/), [Lua scripting](https://redis.io/docs/latest/develop/programmability/eval-intro/), and Redis atomic command semantics.

## Learn

- Fixed-window, sliding-window, token-bucket, and leaky-bucket behavior.
- `INCR` with expiration, sorted-set windows, atomic operations, Lua scripts, limit keys, and identity selection.
- Limit responses, retry hints, distributed deployment, and fail-open versus fail-closed decisions.

## Practice Deliverable

Protect one TeamOps API route with a tested Redis rate limiter. Choose an algorithm, key by a documented identity (for example account plus route), set TTL/cleanup behavior, and return a consistent `429` response with safe retry information.

## Completion Criteria

- [ ] Explain the selected algorithm's burst and boundary behavior.
- [ ] Ensure increment/check/expiration steps are atomic.
- [ ] Define behavior when Redis is unavailable and justify the security/usability trade-off.
- [ ] Test allowed, rejected, expiry/reset, and Redis-error paths.
- [ ] Avoid keys based solely on untrusted spoofable headers.

## Common Mistakes

Non-atomic read-then-write checks, no expiry, fixed-window boundary bursts without acknowledgement, global keys that punish all users, trusting arbitrary client headers, and no fallback decision for Redis failure.

## Next

Continue to [Module 26: Microservices Architecture](../../02-go-backend/03-distributed-systems/01-microservices/).
