# Module 04: Go Functions and Language Constructs

Learn to express behavior clearly with functions, methods, closures, `defer`, and controlled panic recovery. Use [A Tour of Go](https://go.dev/tour/flowcontrol/8), [Effective Go](https://go.dev/doc/effective_go), and the official article [Defer, Panic, and Recover](https://go.dev/blog/defer-panic-and-recover).

## Learn

- Multiple/named return values, variadic functions, function values, anonymous functions, closures, and higher-order functions.
- Method sets and receiver choices.
- `defer` execution order, cleanup, and interaction with returned values.
- `panic` and `recover`; when errors are preferable.

## Practice Deliverable

Implement the catalog parser exercise. Parse an input format of your choice, return clear errors for invalid records, and use `defer` to close the opened resource. Add tests for valid input, malformed input, and cleanup/error behavior.

## Verify

```bash
go fmt ./...
go test ./...
go vet ./...
```

## Completion Criteria

- [ ] Explain why `defer` executes in LIFO order.
- [ ] Return explicit errors for expected invalid input.
- [ ] Use `panic` only for unrecoverable programmer/invariant failures or framework boundaries.
- [ ] Test a closure or higher-order behavior only where it makes the design clearer.

## Common Mistakes

Using named return values without benefit, deferring expensive cleanup in unbounded loops, swallowing panics, and using panic/recover as normal control flow.

## Next

Continue to [Module 05](../03-error-handling/).
