# Go Programming: Modules 03-10

This sequence builds the language and runtime foundation for the Go API modules. Complete the modules in directory order and use the [central catalog](../../01-learning-roadmap/MODULES.md) for the canonical curriculum and deliverables.

## Setup and Workflow

Install Go from the official [installation guide](https://go.dev/doc/install), then verify the toolchain:

```bash
go version
go env GOROOT GOPATH GOPROXY
```

Create isolated exercises within each module's `practice/` directory when needed. Keep learner plans, completion records, and personal notes under `15-learners/<name>/`; use this shared workspace for reusable examples and module artifacts.

## Recommended Official References

- [A Tour of Go](https://go.dev/tour/): syntax, methods, interfaces, generics, and concurrency.
- [Tutorial: Create a Go module](https://go.dev/doc/tutorial/create-module): modules, functions, errors, collections, and tests.
- [Effective Go](https://go.dev/doc/effective_go): idiomatic code and package design.
- [Standard library](https://pkg.go.dev/std): primary package API reference.
- [How to write Go code](https://go.dev/doc/code): module/package layout and `go` commands.
- [Go language specification](https://go.dev/ref/spec): precise behavior when documentation or intuition conflicts.

## Shared Completion Standard

For every module, commit a small, readable implementation with a module README or learner record that identifies the artifact, the key design choice, the verification command, and one debugging lesson. Prefer `go fmt ./...`, `go vet ./...`, and `go test ./...` before opening a pull request.

## Dependency Map

```text
03 language fundamentals
    -> 04 functions and control flow
    -> 05 error handling
    -> 06 goroutines and channels
    -> 07 synchronization patterns
    -> 08 races, deadlocks, and leak prevention
    -> 09 runtime, profiling, and benchmarks
    -> 10 OS, signals, files, and TCP/UDP services
    -> 11 HTTP and REST APIs
```

Do not use concurrency to compensate for an unclear sequential design. Do not optimize before measuring.
