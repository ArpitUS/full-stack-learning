# Module 06: Go Concurrency

Use goroutines, channels, `select`, timers, and context cancellation to manage independent work without leaks. Start with [A Tour of Go concurrency](https://go.dev/tour/concurrency/1), [Go Concurrency Patterns](https://go.dev/talks/2012/concurrency.slide), and the [context package](https://pkg.go.dev/context).

## Learn

- Goroutine lifecycle, scheduling basics, stacks, and leak risks.
- Unbuffered/buffered channels, close ownership, directional channels, and closed/nil channel behavior.
- `select`, timeouts, timers, tickers, and cancellation propagation.
- Worker pools, fan-out/fan-in, pipelines, bounded concurrency, and graceful shutdown.

## Practice Deliverable

Build the catalog cancellable worker pipeline. It should accept a `context.Context`, process a bounded set of jobs, propagate the first relevant error, close channels from their owner, and stop workers on cancellation.

## Verify

```bash
go test ./...
go test -race ./...
go vet ./...
```

## Completion Criteria

- [ ] Explain who sends, receives, and closes each channel.
- [ ] Bound concurrency rather than creating an unbounded goroutine per input.
- [ ] Prove cancellation stops work using a test with a deadline or controlled blocking point.
- [ ] Explain why a nil channel blocks and why sending to a closed channel panics.

## Common Mistakes

Goroutine leaks, multiple closers, unbuffered sends with no receiver, ticker leaks, `time.After` in hot loops, ignored context cancellation, and assuming `select` gives deterministic fairness.

## Next

Continue to [Module 07](../05-synchronization/).
