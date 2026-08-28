# React and TypeScript Training

This section builds the TeamOps client, from typed JavaScript foundations to accessible routed screens, API integration, and client-side security/performance practices. Module scope remains in the [central catalog](../01-learning-roadmap/MODULES.md).

## Module Map and Order

1. Module 30: JavaScript and TypeScript foundations.
2. Module 31: components, hooks, forms, state, and accessibility.
3. Module 32: routing, server API integration, authentication, loading, and pagination.
4. Module 33: testing, performance, and browser security.

## Prerequisites

Complete Git/Linux fundamentals. Begin API integration after module 11 defines the backend contract; begin authentication UI after module 49 defines the security model.

## Practical Artifacts

- Typed domain models and an API client with typed error handling.
- Accessible TeamOps task, project, and team screens.
- Loading, empty, unauthorized, and error UI states.
- Component and browser tests for critical flows.

## Completion Standard

Deliver a routed TypeScript React client that calls the Go API, validates forms, handles asynchronous states, protects authenticated views appropriately, and has test coverage for a critical user journey.

## Common Debugging Areas

Stale state, missing effect cleanup, unstable list keys, incorrect dependency arrays, unsafe HTML rendering, leaking tokens, request races, and API error states that are not represented in the UI.

## TeamOps Handoff

The frontend joins TeamOps after the backend and database contract exist. Add client features stage by stage instead of building disconnected mock screens. See [TeamOps stages](../12-projects/teamops/STAGES.md).

## Learning Materials

- [React: Using TypeScript](https://react.dev/learn/typescript): primary reference for component props, hooks, events, children, and React types.
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html): primary language reference.
- [Full TypeScript Guide with React examples](https://dev.to/utkvishwas/the-full-typescript-guide-with-easy-react-examples-355m): guided introduction to types, interfaces, unions, generics, props, state, events, and API lists.
- [Hands on React TypeScript tutorial](https://handsonreact.com/docs/labs/react-tutorial-typescript): progressive project labs for components, forms, HTTP, routing, custom hooks, React Query, Redux, and testing.

Use the official React and TypeScript documentation to resolve behavior or type questions. Use the guided materials to choose small practice milestones rather than copying a finished application.
