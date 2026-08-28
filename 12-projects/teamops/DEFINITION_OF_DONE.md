# TeamOps Definition of Done

A TeamOps task is complete only when its acceptance criteria and relevant items below are satisfied.

## Required for Every Change

- [ ] Scope, linked stage/module, and acceptance criteria are documented.
- [ ] Change is focused and reviewed through a pull request.
- [ ] Formatting, linting, and relevant automated tests pass.
- [ ] Manual verification covers the intended behavior and failure case.
- [ ] User-facing errors are understandable and internal details are not exposed.
- [ ] Documentation, contribution tracking, and feature/stage status are updated when applicable.

## Apply When Relevant

- [ ] API validation, authorization, status codes, and error contract are tested.
- [ ] Database migration is forward-only, repeatable, and protects integrity with constraints/transaction behavior.
- [ ] React UI covers loading, empty, error, and unauthorized states.
- [ ] Redis key/TTL/invalidation/outage behavior is documented and tested.
- [ ] Configuration/secrets are externalized and no sensitive values enter Git or logs.
- [ ] Docker/CI/deployment change has a documented verification and rollback path.
- [ ] Logs, metrics, and traces support debugging without emitting sensitive/high-cardinality data.

## Evidence

Link the pull request, tests, command output, dashboard/trace, migration plan, or deployment record in the backlog/contribution entry. Evidence should let a reviewer understand what changed and how it was verified.
