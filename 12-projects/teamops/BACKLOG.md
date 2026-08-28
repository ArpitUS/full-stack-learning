# TeamOps Backlog

Use this as the shared planning queue. Keep individual study plans in `15-learners/`; add an item here only when it changes or directly prepares the shared product.

## Ready-to-Scope Vertical Slices

| Priority | Feature / Task | Stage | Curriculum Modules | Acceptance Criteria | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | API health endpoint and service skeleton | 1 | 03-15 | Health endpoint, config, error model, and core tests are documented and runnable. | Unassigned | Not Started |
| 2 | TeamOps schema and migrations | 2 | 16-21 | Users, teams, memberships, projects, and tasks enforce key constraints through repeatable migrations. | Unassigned | Not Started |
| 3 | Task list and creation vertical slice | 2 and 4 | 11-17, 30-32 | API, migration, typed client, accessible UI, and tests support listing/creating one team's tasks. | Unassigned | Not Started |
| 4 | Authentication and team authorization | 3 | 49-52 | Protected API routes reject unauthenticated/forbidden access with server-side tests. | Unassigned | Not Started |
| 5 | Docker Compose local environment | 6 | 37-38 | API, client, PostgreSQL, and Redis start through documented commands and health checks. | Unassigned | Not Started |

## Task Template

Copy this block for a new task. Do not claim a task without acceptance criteria.

```md
### Task: Short description

- Feature:
- Stage:
- Curriculum modules:
- Scope:
- Acceptance criteria:
- Verification:
- Dependencies / risks:
- Owner:
- Reviewer:
- Status: Not Started | In Progress | Review | Blocked | Completed
- Pull request / commit:
```

The rows above are initial project options, not records of completed work.
