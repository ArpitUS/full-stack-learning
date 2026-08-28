# TeamOps Planning

Use this folder for shared product decisions that guide implementation. Do not duplicate personal learner notes here.

## What Belongs Here

- Requirements, user stories, acceptance criteria, and scoped feature notes.
- Domain diagrams, data model decisions, API contracts, and architecture diagrams.
- Decision records in `decisions/` when a trade-off affects the shared system.
- Threat models, rollout/rollback plans, and incident/runbook material when they are product-specific.

## Decision Record Template

```md
# ADR-NNN: Decision title

- Status: Proposed | Accepted | Superseded
- Date:
- Context:
- Decision:
- Alternatives considered:
- Consequences:
- Validation / rollback:
- Related modules, stage, and pull request:
```

## Completion Rule

Planning is ready for implementation when the task has a clear user/product outcome, acceptance criteria, affected boundaries, verification method, security/data implications, and a small enough scope for review.

See [architecture](../ARCHITECTURE.md), [backlog](../BACKLOG.md), and [definition of done](../DEFINITION_OF_DONE.md).
