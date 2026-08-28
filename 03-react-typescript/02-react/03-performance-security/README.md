# Module 33: React Performance and Security

Make the TeamOps client observable, secure at browser boundaries, and fast enough based on measurement. Use [React performance guidance](https://react.dev/learn/render-and-commit), [React TypeScript](https://react.dev/learn/typescript), [web.dev performance](https://web.dev/learn/performance/), and the Hands on React advanced/testing labs.

## Learn

- Rendering behavior, derived data, code splitting, lazy loading, and when memoization is unnecessary.
- Client caching, invalidation, request lifecycle, and performance measurement.
- Browser security boundaries: CORS, XSS prevention, safe rendering, token handling, and content from untrusted sources.
- Component, form, API, and browser tests for critical flows.

## Practice Deliverable

Audit one TeamOps screen. Add a measured improvement such as route-level lazy loading or removal of unnecessary state/render work. Add secure loading/error behavior, test a critical path, and document the security/data-handling decisions.

## Verify

```bash
npm run typecheck
npm test
npm run build
```

Record a before/after measurement or a clear rendering diagnosis. Do not add `useMemo` or `useCallback` without evidence; React Compiler may reduce the need for manual memoization in configured projects.

## Completion Criteria

- [ ] Identify a user-visible performance concern with evidence before changing code.
- [ ] Keep untrusted HTML/data out of unsafe render paths.
- [ ] Handle CORS as a server policy and client behavior constraint, not a client-side bypass.
- [ ] Cover a loading, error, and successful user path with appropriate tests.
- [ ] Explain the cache invalidation behavior for one server-backed screen.

## Common Mistakes

Manual memoization everywhere, stale cached server data, exposing tokens in logs/local storage without considering risk, `dangerouslySetInnerHTML` with untrusted input, treating CORS as authentication, and optimizing renders without measurement.

## TeamOps Connection

This work hardens TeamOps Stage 4 and supports Stage 7 testing/CI. Coordinate client token behavior, CORS, and error models with the backend security modules.
