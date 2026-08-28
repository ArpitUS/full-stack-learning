# Module 08: Race Conditions and Deadlocks

Learn to reproduce, detect, and eliminate synchronization failures. Use the official [race detector guide](https://go.dev/doc/articles/race_detector.html), [Go memory model](https://go.dev/ref/mem), and [diagnostics guide](https://go.dev/doc/diagnostics.html).

## Learn

- Data races, race conditions, shared mutable state, and `go test -race`.
- Mutex/channel deadlocks, circular waits, livelocks, starvation, and goroutine leaks.
- Lock ordering, ownership boundaries, timeouts in tests, and failure-focused debugging.

## Practice Deliverable

Create the catalog's failing examples in a disposable package: one data race, one mutex or channel deadlock, and one goroutine leak. Write tests or repeatable commands that expose each issue, then fix them and document the root cause.

## Verify

```bash
go test -race ./...
go test -timeout 10s ./...
go vet ./...
```

## Completion Criteria

- [ ] Trigger and explain a race reported by the race detector.
- [ ] Diagnose a blocked goroutine using stack traces or a controlled timeout.
- [ ] Apply a lock-ordering or ownership rule that prevents the demonstrated deadlock.
- [ ] Verify the repair under repeated/race-enabled tests.

## Common Mistakes

Treating a passing race-detector run as proof that no race exists, adding sleeps instead of synchronization, hiding deadlocks with large buffers, retaining goroutines after caller cancellation, and sharing maps without protection.

## Next

Continue to [Module 09](../07-runtime-internals/).
