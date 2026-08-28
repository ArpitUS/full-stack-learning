# Module 20: Database Transactions

Protect multi-step data changes with PostgreSQL transactions, isolation awareness, and explicit error handling. Use [transactions](https://www.postgresql.org/docs/current/tutorial-transactions.html), [concurrency control](https://www.postgresql.org/docs/current/mvcc.html), and [transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html).

## Practice Deliverable

Implement an atomic TeamOps task assignment: verify membership, update the task, and write an audit event in one transaction. Add tests for a successful path, an invalid member, and a forced failure that proves no partial data remains.

## Verify

Use two `psql` sessions to observe locking when appropriate, then run the Go integration tests that exercise commit and rollback paths.

## Completion Criteria

- [ ] Explain ACID and the isolation level used by the operation.
- [ ] Keep transaction scope short and avoid network calls inside it.
- [ ] Roll back safely on every error path.
- [ ] Explain optimistic versus pessimistic locking for one TeamOps operation.
- [ ] Reproduce or reason through a deadlock and its prevention strategy.

## Common Mistakes

Long-running transactions, forgotten rollback, external calls inside transactions, assuming reads never conflict, retrying every error blindly, and relying on application checks without a database constraint.

## Next

Continue to [Module 21](../06-connection-management/).
