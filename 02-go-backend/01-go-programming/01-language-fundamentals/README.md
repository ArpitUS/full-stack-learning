# Module 03: Go Language Fundamentals

Build fluency with Go modules, packages, types, values, pointers, structs, methods, interfaces, slices, maps, and strings. Start with [A Tour of Go](https://go.dev/tour/), [Create a Go module](https://go.dev/doc/tutorial/create-module), [How to write Go code](https://go.dev/doc/code), and [Effective Go](https://go.dev/doc/effective_go).

## Learn

- `package main`, imports, `go.mod`, package boundaries, and the `go` tool.
- Variables, constants, zero values, type inference/conversion, and `nil`.
- Value versus pointer semantics; structs, tags, methods, and receivers.
- Interfaces, interface composition, the empty interface (`any`), and nil-interface behavior.
- Arrays, slices, maps, strings, runes, bytes, and collection mutation/copying.

## Practice Deliverable

Build the typed CLI domain model named in the [catalog](../../../01-learning-roadmap/MODULES.md): model a small TeamOps-like entity such as `Task`, `Project`, or `Member`. Use separate packages for domain behavior and command entry point. Include table-driven tests for validation or state transitions.

## Verify

```bash
go fmt ./...
go vet ./...
go test ./...
go build ./...
```

## Completion Criteria

- [ ] Explain a slice's length, capacity, and when `append` can share backing storage.
- [ ] Use pointer receivers only when mutation, copying cost, or method-set rules justify them.
- [ ] Define a small interface at the consumer boundary, not preemptively around every type.
- [ ] Demonstrate the difference between a nil interface and an interface containing a nil pointer.
- [ ] Pass table-driven tests and document one design decision.

## Common Mistakes

Accidentally sharing slice backing arrays, taking addresses of loop variables, storing mutable maps without synchronization plans, using broad `any` values, and defining large interfaces before a consumer needs them.

## Next

Continue to [Module 04](../02-functions-language-constructs/).
