# Module 09: Go Runtime and Internals

Use runtime knowledge to measure and improve real behavior, not to prematurely tune code. Read the [Go GC guide](https://go.dev/doc/gc-guide), [diagnostics guide](https://go.dev/doc/diagnostics.html), [runtime package](https://pkg.go.dev/runtime), [pprof package](https://pkg.go.dev/runtime/pprof), and [profile-guided optimization guide](https://go.dev/doc/pgo).

## Learn

- Scheduler concepts, G-M-P model, preemption, work stealing, blocking calls, stacks, and heap allocation.
- Escape analysis, garbage collection, allocation pressure, and memory behavior.
- CPU, heap, allocation, goroutine, mutex, and block profiles; benchmarks and `benchmem`.

## Practice Deliverable

Profile an intentionally inefficient program or earlier worker pipeline. Establish a baseline, identify one bottleneck using a profile or benchmark, make one justified change, and document before/after measurements and trade-offs.

## Verify

```bash
go test -bench=. -benchmem ./...
go test -cpuprofile cpu.out -memprofile mem.out ./...
go tool pprof cpu.out
go build -gcflags=-m ./...
```

## Completion Criteria

- [ ] State the workload and baseline before claiming an optimization.
- [ ] Use a profile or benchmark to identify the target bottleneck.
- [ ] Explain one escape-analysis finding without assuming all heap allocations are defects.
- [ ] Verify behavior and tests after performance changes.

## Common Mistakes

Benchmarking unrealistic workloads, comparing noisy one-off measurements, optimizing without a profile, treating all allocations as bad, retaining large objects accidentally, and exposing pprof endpoints publicly.

## Next

Continue to [Module 10](../08-system-programming/).
