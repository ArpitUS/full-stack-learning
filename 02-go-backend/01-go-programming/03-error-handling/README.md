# Module 05: Go Error Handling

Design errors that preserve context while allowing callers to make correct decisions. Use the [errors package](https://pkg.go.dev/errors), [fmt package](https://pkg.go.dev/fmt), and [Error handling and Go](https://go.dev/blog/error-handling-and-go).

## Learn

- The `error` interface, `errors.New`, `fmt.Errorf`, and `%w` wrapping.
- `errors.Is` and `errors.As` for sentinel and typed errors.
- Error propagation, custom error types, API error boundaries, and panic versus error.

## Practice Deliverable

Build the catalog error package for the Module 03/04 domain. Define a small set of domain errors, wrap lower-level failures with useful operation context, and test caller classification with `errors.Is` or `errors.As`.

## Verify

```bash
go test ./...
go vet ./...
```

## Completion Criteria

- [ ] Preserve the original cause when a caller must classify it.
- [ ] Add context that identifies the failed operation without exposing secrets.
- [ ] Avoid string matching to make control-flow decisions.
- [ ] Translate domain errors to an API error model only at the HTTP boundary in later modules.

## Common Mistakes

Dropping the wrapped cause, wrapping with `%v` instead of `%w` when classification is needed, exposing database/internal details to clients, ignoring errors, and using sentinel errors for values that need structured data.

## Next

Continue to [Module 06](../04-concurrency/).
