# Module 10: Go System Programming

Apply Go to operating-system integration and network services: files, processes, signals, TCP/UDP sockets, and graceful shutdown. Use the standard-library documentation for [os](https://pkg.go.dev/os), [os/signal](https://pkg.go.dev/os/signal), [net](https://pkg.go.dev/net), [net/http](https://pkg.go.dev/net/http), and [context](https://pkg.go.dev/context).

## Learn

- Files, descriptors, resource cleanup, process interaction, and operating-system signals.
- TCP and UDP listeners/connections, deadlines, concurrent connection handling, and network error handling.
- Context cancellation, server shutdown, resource management, and observability-friendly shutdown behavior.

## Practice Deliverable

Build the catalog TCP service. It must accept `context.Context` or a controlled shutdown signal, set useful read/write deadlines where appropriate, close listeners and active resources, and exit gracefully on `SIGINT`/`SIGTERM`. Add an integration test or repeatable manual verification script.

## Verify

```bash
go test ./...
go test -race ./...
go vet ./...
go run .
```

In Linux/WSL, use `ss -ltnp` and a client such as `nc` to confirm listener behavior; see [Module 02](../../../01-learning-roadmap/02-linux-networking/).

## Completion Criteria

- [ ] Bind deliberately to an address and port and explain the exposure implications.
- [ ] Handle connection/read/write errors and always release resources.
- [ ] Gracefully stop accepting new work and drain/close existing work on shutdown.
- [ ] Test or demonstrate shutdown without relying on process termination as cleanup.

## Common Mistakes

Ignoring errors from `Close`, unbounded goroutines per connection, no I/O deadlines, process termination without cleanup, binding unintentionally to all interfaces, and confusing network reachability with application readiness.

## Next

Continue to [Module 11: HTTP and REST API Development](../../02-api-development/01-http-rest/).
