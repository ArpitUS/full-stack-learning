# Module 19: Database Performance

Measure PostgreSQL query behavior with indexes and query plans. Use the official [indexes](https://www.postgresql.org/docs/current/indexes.html), [performance tips](https://www.postgresql.org/docs/current/performance-tips.html), and [`EXPLAIN`](https://www.postgresql.org/docs/current/sql-explain.html) documentation.

## Practice Deliverable

Create a deliberately slow TeamOps query. Capture `EXPLAIN (ANALYZE, BUFFERS)`, identify the costly operation, add or revise an index, rerun the same workload, and document the plan/latency trade-off.

## Verify

```sql
EXPLAIN (ANALYZE, BUFFERS) SELECT ...;
```

## Completion Criteria

- [ ] Explain sequential scan, index scan, and planner estimates at a high level.
- [ ] Select an index based on query predicates, ordering, and selectivity.
- [ ] Include the write/storage cost of the new index in the decision.
- [ ] Identify and fix one N+1 application query path.

## Common Mistakes

Adding indexes blindly, evaluating plans with unrealistic tiny data, unused composite-index order, stale statistics, and optimizing only SQL while ignoring connection/application behavior.

## Next

Continue to [Module 20](../05-transactions/).
