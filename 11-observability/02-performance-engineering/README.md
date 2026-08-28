# Module 58: Performance Engineering

Improve TeamOps performance through a measurement loop: define workload, establish baseline, identify bottleneck, change one variable, verify improvement, and record the trade-off. Use [Go diagnostics](https://go.dev/doc/diagnostics.html), [Go GC guide](https://go.dev/doc/gc-guide), [`runtime/pprof`](https://pkg.go.dev/runtime/pprof), and [Prometheus metric types](https://prometheus.io/docs/concepts/metric_types/).

## Prerequisites

Complete Module 57 enough to observe request rate, errors, latency, resource use, and key dependency behavior. Have reproducible API tests and a controlled non-production load environment. Do not load-test shared production services without an approved plan.

## Learn

- Latency, throughput, concurrency, utilization, saturation, tail latency, capacity, and bottleneck theory.
- Load, stress, soak, and benchmark tests; representative workload and success/error criteria.
- Go CPU, heap, allocation, goroutine, block, mutex, and execution profiles.
- Database plans/indexes/connection pools, Redis hit rate/latency, network dependencies, queues, GC, memory allocation, and lock contention.
- Performance trade-offs: cost, correctness, complexity, cache consistency, and operational risk.

## Practice Deliverable

Choose one TeamOps endpoint. Define a repeatable representative workload and success criteria, capture baseline latency/throughput/error/resource/dependency metrics, identify one bottleneck using traces, profiles, database plans, or metrics, make one targeted change, and publish before/after evidence with risks and rollback notes.

## Verify

```bash
go test -bench=. -benchmem ./...
go test -cpuprofile cpu.out -memprofile mem.out ./...
go tool pprof cpu.out
go tool pprof mem.out
```

Use profiles in isolation when possible: detailed memory/block profiling can affect CPU/profiling results. Pair runtime evidence with application and dependency telemetry.

## Completion Criteria

- [ ] State workload, environment, baseline, target, and measurement method before optimizing.
- [ ] Measure p50/p95/p99 or another stated latency distribution, not only an average.
- [ ] Identify a bottleneck from evidence rather than intuition.
- [ ] Change one primary variable and re-run the same workload.
- [ ] Verify correctness, errors, cost, and resource behavior after the change.
- [ ] Document the result, trade-off, regression risk, and rollback path.

## Common Mistakes

Benchmarking unrealistic workloads, profiling too many signals at once, optimizing without baseline, replacing a database query with stale cache without a policy, increasing concurrency without bounds, treating throughput as success while error rate rises, ignoring tail latency, and exposing pprof endpoints publicly.

## TeamOps Connection

Use the findings to improve TeamOps Stage 10 and create a production-debugging scenario in [Module 63](../../13-interview-preparation/02-production-debugging/). Performance work should produce a measurable technical record, not an unverified claim that a change is faster.

## Next

Continue to [Module 59: DNS and Networking](../../02-go-backend/05-networking/01-dns-networking/).
