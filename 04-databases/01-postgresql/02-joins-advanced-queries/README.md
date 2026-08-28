# Module 17: Joins and Advanced Queries

Build reporting queries with joins, subqueries, CTEs, and window functions. Use [PostgreSQL queries](https://www.postgresql.org/docs/current/queries.html) and [window functions](https://www.postgresql.org/docs/current/tutorial-window.html).

## Practice Deliverable

Write ten TeamOps queries, including project task counts, members without assignments, latest task per project, ranked contributors, paginated project results, and a running activity total. Store expected results with each query.

## Verify

```bash
psql "$DATABASE_URL" -f queries.sql
```

## Completion Criteria

- [ ] Choose the join type that preserves the intended rows.
- [ ] Explain `WHERE` versus `HAVING` and `GROUP BY` versus `DISTINCT`.
- [ ] Use a CTE or window function where it improves clarity over a nested query.
- [ ] Define deterministic ordering for pagination and ranking.

## Common Mistakes

Accidental cartesian products, filtering an outer join in `WHERE`, grouping non-aggregated columns incorrectly, offset-only pagination at scale, and nondeterministic order.

## Next

Continue to [Module 18](../03-sql-interview-problems/).
