# Module 07: Go Synchronization

Choose synchronization based on data ownership and access patterns. Read the [sync package](https://pkg.go.dev/sync), [sync/atomic](https://pkg.go.dev/sync/atomic), and the [Go memory model](https://go.dev/ref/mem) before relying on concurrent shared state.

## Learn

- `sync.Mutex`, `sync.RWMutex`, `sync.Once`, `sync.WaitGroup`, `sync.Cond`, `sync.Map`, and atomic operations.
- Mutual exclusion, coordination, visibility, lock ordering, and channel versus mutex trade-offs.
- Producer-consumer, worker pool, fan-in/fan-out, pipeline, and alternating-worker patterns.

## Practice Deliverable

Implement the same concurrent state operation twice: once with a mutex and once with channel ownership. Compare readability, contention, and correctness. Add a `sync.Once` initialization test only where one-time initialization is truly required.

## Verify

```bash
go test ./...
go test -race ./...
go test -bench=. -benchmem ./...
```

## Completion Criteria

- [ ] Explain which goroutine owns mutable state.
- [ ] Protect every shared read/write pair with a synchronization strategy.
- [ ] Use `WaitGroup` only for lifecycle waiting, not as a data-visibility substitute.
- [ ] Compare mutex and channel solutions using evidence rather than preference.

## Common Mistakes

Copying mutex-containing values, holding locks during blocking I/O, read-to-write lock upgrade attempts, calling `Add` concurrently with `Wait`, using `sync.Map` as a default map, and mixing ownership models without clear boundaries.

## Next

Continue to [Module 08](../06-race-conditions-deadlocks/).
