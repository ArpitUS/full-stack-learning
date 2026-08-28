# Module 57: Observability

Instrument TeamOps so a learner can explain the state of a request and service from telemetry rather than guesswork. Use [OpenTelemetry](https://opentelemetry.io/docs/what-is-opentelemetry/), [Prometheus](https://prometheus.io/docs/introduction/overview/), [Grafana](https://grafana.com/docs/grafana/latest/getting-started/), and [Go diagnostics](https://go.dev/doc/diagnostics.html).

## Learn

- Logs, metrics, and traces answer different questions: event detail, aggregate behavior, and request path/latency.
- Structured logs, log levels, request/correlation IDs, error context, and safe data handling.
- RED signals for request-serving services: rate, errors, and duration; saturation/resource signals for service health.
- Counters, gauges, histograms, labels, PromQL concepts, dashboard design, alerts, SLO/SLI concepts, and alert routing.
- Trace/span hierarchy, context propagation, semantic conventions, sampling, and collector/backend roles.

## Practice Deliverable

Instrument one TeamOps request end to end. Emit a structured API log with request ID, expose HTTP request count/error/duration metrics, and create a trace with at least HTTP handler plus database/cache spans when those dependencies exist. Build a small dashboard specification showing traffic, error rate, latency distribution, saturation, and one dependency signal.

## Verify

1. Trigger a known successful request and find its log entry, metric effect, and trace.
2. Trigger a controlled failure and show how it appears without exposing sensitive data.
3. Query a metric over time and identify rate, errors, and latency rather than a single aggregate average.
4. Test a dashboard/alert query against expected normal and failing behavior.

## Completion Criteria

- [ ] Use structured logs with a consistent request/correlation identifier.
- [ ] Record request rate, errors, and latency with bounded labels.
- [ ] Trace a representative request through its meaningful dependencies.
- [ ] Explain the difference between OpenTelemetry instrumentation and a telemetry backend such as Prometheus/Grafana.
- [ ] Define one actionable alert with threshold rationale and a linked first-response runbook.
- [ ] Prevent sensitive data and unbounded/high-cardinality values from telemetry.

## Common Mistakes

Unstructured text logs, secrets in telemetry, metrics without units, high-cardinality labels, average-only latency, alerts without ownership/runbooks, duplicate counters at multiple layers, missing trace context, tracing every low-value function, and dashboards that do not answer an operational question.

## TeamOps Connection

This begins TeamOps Stage 10 and improves every earlier stage. Add telemetry to the Go API, Docker runtime, CI/CD deployment, AWS/ECS or Kubernetes environment, PostgreSQL/Redis dependencies, and asynchronous workers only when their signals support a real debugging or capacity question.

## Next

Continue to [Module 58: Performance Engineering](../02-performance-engineering/).
