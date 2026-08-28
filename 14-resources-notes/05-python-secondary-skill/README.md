# Module 61: Python Secondary Skill

Python is a supporting skill in this workspace, not a replacement for the primary Go and React path. Use it for automation, data processing, ETL, prototypes, and focused service experiments where its ecosystem or iteration speed is the actual advantage.

## Prerequisites

Complete enough Go/API/database work to compare an implementation decision honestly. Keep TeamOps' primary backend in Go unless a planning decision documents a separate Python responsibility.

## Learn

- Core Python: collections, iterators, generators, decorators, context managers, exceptions, classes, modules, and environments.
- Typed/data work: type hints, Pydantic, pandas, structured input/output, and dependency pinning.
- Web/async work: FastAPI, REST APIs, `asyncio`, background jobs, and API integration boundaries.
- Trade-offs: Go versus Python for type system, performance, concurrency model, development speed, deployment, and ecosystem.

## Practice Deliverable

Build one small typed FastAPI utility or ETL script that consumes a TeamOps-compatible API. Examples: import/export reporting, safe data migration assistant, log analysis, or a one-off operational report. Keep the scope narrow and document why Python is appropriate instead of Go.

## Completion Criteria

- [ ] Use an isolated environment and pinned dependencies.
- [ ] Validate external inputs with types/schemas and handle failure paths.
- [ ] Add automated tests for one success and one failure path.
- [ ] Document operational run command, configuration, and data/privacy constraints.
- [ ] Compare the design against a Go implementation and state the reason for choosing Python.

## Common Mistakes

Adding a second backend language without a boundary, unpinned dependencies, untyped JSON/data pipelines, blocking I/O hidden in async code, secrets in notebooks/scripts, and treating a quick script as production without tests or operational ownership.

## TeamOps Connection

Keep TeamOps application APIs in Go. A Python tool may consume those APIs or support operations only after its purpose, data access, owner, deployment, and lifecycle are documented in TeamOps planning.
