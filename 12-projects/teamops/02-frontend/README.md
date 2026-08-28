# TeamOps Frontend

This folder receives the shared React and TypeScript client when TeamOps reaches Stage 4. Learn component and API patterns first in `03-react-typescript/`; use this folder for approved product implementation.

## Expected Responsibilities

- Accessible pages for authentication, teams, projects, tasks, file uploads, and notifications.
- Typed API contracts, route/query state, forms, local UI state, and server-state handling.
- Loading, empty, validation-error, network-error, and unauthorized states.
- Component and browser tests for critical user workflows.

## Implementation Rules

- Do not rely on hidden UI controls for authorization; the Go API remains authoritative.
- Keep API/domain types centralized and validate untrusted response data at the boundary.
- Do not store secrets in client code. Treat browser-visible configuration as public.
- Link UI changes to their API contract and verify the full vertical slice.

See [React modules](../../../03-react-typescript/), [architecture](../ARCHITECTURE.md), and [definition of done](../DEFINITION_OF_DONE.md).
