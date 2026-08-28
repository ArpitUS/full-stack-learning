# Module 30: JavaScript and TypeScript Foundations

Use JavaScript and TypeScript to model reliable frontend domain data and API boundaries before building complex React screens. Primary references: [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html), [React: Using TypeScript](https://react.dev/learn/typescript), and the [TypeScript React guide](https://dev.to/utkvishwas/the-full-typescript-guide-with-easy-react-examples-355m).

## Learn

- JavaScript values, objects, arrays, functions, modules, promises, `async`/`await`, closures, the event loop, and error handling.
- Type inference, object types, `type` aliases, interfaces, unions, narrowing, literal types, generics, and utility types.
- `tsconfig` strictness and the difference between compile-time checking and runtime validation.
- Typed request states and API results; TypeScript cannot prove that a remote JSON response matches a type.

## Practice Deliverable

Implement the catalog deliverable: typed TeamOps API client utilities and tests. Define domain types for at least one resource, model loading/success/error states with a discriminated union, check HTTP failures, and validate untrusted data at the boundary before treating it as typed application data.

## Verify

```bash
npm run typecheck
npm test
npm run lint
```

Use the actual project scripts once a frontend project is created. Do not add type assertions merely to silence errors.

## Completion Criteria

- [ ] Explain `unknown` versus `any` and prefer `unknown` at untrusted boundaries.
- [ ] Use unions and narrowing for request state or domain variants.
- [ ] Use a generic only when it expresses a real relationship between input and output types.
- [ ] Define API/domain types once and reuse them across the client.
- [ ] Test successful, HTTP-error, and invalid-data paths.

## Common Mistakes

Using `any`, asserting `response.json()` directly into a trusted type, optional properties that hide invalid states, non-null assertions, duplicate type definitions, and treating TypeScript as runtime validation.

## Next

Continue to [Module 31: React Fundamentals](../02-react/01-fundamentals/).
