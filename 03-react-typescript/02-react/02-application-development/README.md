# Module 32: React Application Development

Turn components into a complete client with routing, server-state handling, forms, pagination, error recovery, and authentication-aware navigation. Use [React Learn](https://react.dev/learn), the [Hands on React API/routing labs](https://handsonreact.com/docs/labs/react-tutorial-typescript), and the API contract from Module 11 onward.

## Prerequisites

Complete Modules 30-31. Start against a documented Go API contract. Authentication UI depends on the server-side model from Modules 49-52.

## Learn

- Route structure, route parameters, navigation, and route-level error/empty/loading states.
- Server state versus local UI state; fetch cancellation, retries, pagination, filtering, and cache invalidation.
- Form submission, validation, optimistic versus confirmed updates, and recoverable error feedback.
- Authentication-aware rendering without assuming the UI alone is an authorization boundary.

## Practice Deliverable

Build routed TeamOps project and task screens backed by the Go API. Implement list/detail routes, a create or edit form, typed API errors, pagination or filtering, and loading/empty/error/unauthorized states. Extract a custom hook only after repeated fetch/state behavior is proven.

## Verify

```bash
npm run typecheck
npm test
npm run build
```

Test at least one successful mutation, one validation failure, one network failure, and one unauthorized response.

## Completion Criteria

- [ ] Routes encode stable resource identity and handle missing/invalid parameters.
- [ ] Server data is not copied into unrelated local state without a reason.
- [ ] In-flight requests are cancelled or ignored safely when a screen becomes irrelevant.
- [ ] Errors are understandable to the user and contain safe diagnostic detail for developers.
- [ ] Client authentication behavior matches, but does not replace, server authorization.

## Common Mistakes

Fetching in every component, race conditions from stale requests, swallowed errors, optimistic updates without rollback, leaking access tokens, routing state encoded only in components, and caching stale data indefinitely.

## TeamOps Connection

This is TeamOps Stage 4. Record shared UI work in [TeamOps contributions](../../../12-projects/teamops/CONTRIBUTIONS.md) and ensure the API contract is versioned/reviewed with backend changes.

## Next

Continue to [Module 33: React Performance and Security](../03-performance-security/).
