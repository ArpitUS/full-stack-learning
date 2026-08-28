# PostgreSQL: Modules 16-21

PostgreSQL is TeamOps' source of truth for users, teams, projects, tasks, permissions, and audit data. Complete this sequence before introducing Redis caching. Use the [PostgreSQL documentation](https://www.postgresql.org/docs/current/) as the primary reference and the [catalog](../../01-learning-roadmap/MODULES.md) for canonical deliverables.

## Learning Order

```text
16 schema and CRUD
    -> 17 joins and reporting
    -> 18 query reasoning practice
    -> 19 indexes and plans
    -> 20 transactions and concurrency
    -> 21 Go connection pools
```

## Working Rules

- Create versioned, forward-only migrations for shared TeamOps schema changes.
- Use constraints to enforce invariants; application validation complements but does not replace them.
- Parameterize values in SQL. Do not build SQL with string concatenation.
- Capture an `EXPLAIN (ANALYZE, BUFFERS)` plan before and after an optimization.
- Keep transactions short and always handle rollback/error paths.

## Primary References

- [PostgreSQL tutorial](https://www.postgresql.org/docs/current/tutorial.html)
- [Data definition](https://www.postgresql.org/docs/current/ddl.html) and [data manipulation](https://www.postgresql.org/docs/current/dml.html)
- [Queries](https://www.postgresql.org/docs/current/queries.html), [indexes](https://www.postgresql.org/docs/current/indexes.html), and [performance tips](https://www.postgresql.org/docs/current/performance-tips.html)
- [Concurrency control](https://www.postgresql.org/docs/current/mvcc.html) and [transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html)
- [Monitoring database activity](https://www.postgresql.org/docs/current/monitoring.html)
- Go: [Accessing relational databases](https://go.dev/doc/database/) and [managing connections](https://go.dev/doc/database/manage-connections)

## Shared Completion Standard

Build a repeatable TeamOps schema and seed dataset; write correct queries; improve one measured slow query with an appropriate index; protect a multi-write operation with a transaction; and configure the Go pool deliberately. Record all schema-impacting shared work in TeamOps.
