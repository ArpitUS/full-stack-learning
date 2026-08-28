# Module 21: Database Connection Management

Configure Go database access as a bounded connection pool, not as one connection per request. Use [Go database access](https://go.dev/doc/database/), [opening a database handle](https://go.dev/doc/database/open-handle), [managing connections](https://go.dev/doc/database/manage-connections), and PostgreSQL [monitoring](https://www.postgresql.org/docs/current/monitoring.html).

## Practice Deliverable

Configure the TeamOps Go database pool with explicit maximum open/idle connections, connection lifetime, and request timeout behavior. Create a controlled load or failure case that demonstrates how pool exhaustion appears in application and database metrics/logs.

## Verify

```bash
go test ./...
go test -race ./...
```

Inspect database activity in an authorized development environment with `pg_stat_activity`.

## Completion Criteria

- [ ] Explain why `sql.DB` is a pool and is normally long-lived.
- [ ] Set pool values based on database capacity and application concurrency assumptions.
- [ ] Pass `context.Context` to database calls and handle timeout/cancellation errors.
- [ ] Close rows and check row iteration errors.
- [ ] Identify a pool exhaustion symptom and a remediation.

## Common Mistakes

Opening a database handle per request, never closing rows, unbounded open connections, no query context, max connection values exceeding database capacity, and confusing a Go pool setting with PostgreSQL server configuration.

## Next

Continue to [Redis Module 22](../../02-redis/01-fundamentals/).
