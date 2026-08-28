# TeamOps Project Workflow

TeamOps is shared implementation work. Learning experiments belong in their mapped curriculum folders until they solve a real TeamOps need.

## Before Starting a Task

1. Select a small backlog item or create one in [BACKLOG.md](BACKLOG.md).
2. Link its curriculum module(s), TeamOps stage, feature, acceptance criteria, and owner/reviewer.
3. Confirm whether it changes frontend, backend, schema, infrastructure, security, or telemetry.
4. Create a focused branch, for example `arpit/teamops-task-create-api`.

## Delivery Loop

```text
Requirement -> API/data/UI design -> small vertical slice -> tests
    -> local verification -> pull request -> review -> merge
    -> feature/stage/contribution tracking -> learner reflection
```

## Collaboration Rules

- Prefer one feature slice per pull request. Separate schema/infrastructure changes when they need distinct review or rollback.
- The backend owns data validation, authorization, and data integrity. The frontend owns user feedback and safe UI state.
- Schema migrations are forward-only and reviewed with the code that depends on them.
- No credentials, production data, generated build artifacts, or private certificates in Git.
- Pair work still needs a named driver/reviewer and a contribution entry after it is merged.
- Update `CONTRIBUTIONS.md`, the feature tracker, and `STAGES.md` only after the shared change is reviewed or its status meaningfully changes.

## Handoff to Learner Records

Each contributor records what they learned, tested, and would improve in their own learner workspace. TeamOps documents shared product decisions and implementation evidence, not personal study logs.
