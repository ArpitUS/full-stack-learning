# React and Go Integration

This workspace bridges Modules 11-15 (Go API design) with Modules 30-33 (typed React application development). It is where the shared API contract becomes an end-to-end TeamOps workflow.

## Prerequisites

- A documented Go API endpoint with validation, stable response/error shape, and a local run command.
- Typed TypeScript domain models and a client request helper.
- React components that already represent loading, empty, error, and success states.

## Integration Contract

Agree on these boundaries before building a feature:

| Concern | API responsibility | Client responsibility |
| --- | --- | --- |
| Validation | Authoritative validation and safe error response | Immediate usability validation and display of server errors |
| Authentication | Verify credentials and authorize every protected action | Send credentials safely and reflect session state |
| Data shape | Versioned, documented JSON contract | Runtime-validate untrusted responses before relying on types |
| Pagination/filtering | Enforce limits and return metadata | Represent query state in UI/routes and render all response states |
| Errors | Stable status and machine-readable error code | User-safe message, retry/recovery where appropriate |
| Cancellation | Respect request context where possible | Cancel or ignore obsolete in-flight requests |

## Practice Deliverable

Implement one vertical TeamOps slice: list a resource, view its detail, and create or update it. Include a Go handler/service/repository path, migration when required, typed client call, accessible React screen, error states, and automated API/client tests.

## Completion Criteria

- [ ] The API contract is documented or tested at both ends.
- [ ] A successful request, validation error, authentication failure, and network failure have defined behavior.
- [ ] The client does not assume TypeScript validates server JSON at runtime.
- [ ] The backend owns authorization and data integrity.
- [ ] The vertical slice is tracked in [TeamOps stages](../../12-projects/teamops/STAGES.md) and [contributions](../../12-projects/teamops/CONTRIBUTIONS.md).

## Common Integration Failures

Field-name drift, treating `204` responses as JSON, frontend-only authorization, missing CORS configuration, mismatched pagination conventions, stale requests, leaking internal backend error details, and error types that cannot be handled consistently by the UI.

## Next

Use the shared application as input to [Testing](../../02-go-backend/04-testing-design-patterns/01-testing/), [Docker](../../06-docker/), and [Authentication and Security](../../05-authentication-security/).
