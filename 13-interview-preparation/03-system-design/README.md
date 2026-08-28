# Modules 64-65: System Design

Translate vague problems into requirements, estimates, architecture, trade-offs, and operational plans. Reuse lessons from TeamOps rather than designing systems as disconnected diagrams.

## Design Flow

```text
Clarify requirements -> estimate scale -> identify data/traffic paths
    -> choose components -> address reliability/security/operations
    -> explain trade-offs -> evolve the design
```

## Module 64 Deliverable: Fundamentals

Design one service from functional and non-functional requirements. Document APIs, data model, read/write paths, capacity estimate, scaling, availability, failure handling, caching, queues, security, observability, and intentional trade-offs.

## Module 65 Deliverable: Timed Practice

Produce six timed design documents selected from URL shortener, rate limiter, distributed cache, notifications, job processing, file upload, API gateway, distributed lock, event processing, monitoring, chat, e-commerce, payments, DNS, DoH, or telemetry ingestion.

## Design Document Template

```md
# System Design: Title

- Requirements and out-of-scope items:
- Scale assumptions and estimates:
- APIs and data model:
- Architecture and request/data flows:
- Availability, consistency, and failure handling:
- Security and privacy:
- Observability and operations:
- Bottlenecks and future evolution:
- Alternatives and trade-offs:
```

## Completion Criteria

- [ ] Ask clarifying questions and state assumptions.
- [ ] Estimate traffic, storage, and bandwidth at a useful order of magnitude.
- [ ] Explain why each major component exists and what failure it introduces.
- [ ] Address reliability, security, cost, and observability, not only scale.
- [ ] Compare at least one credible alternative.

## Common Mistakes

Starting with tools instead of requirements, no estimates, treating caches/queues as magic, ignoring write paths and data ownership, no failure plan, and presenting one architecture as universally correct.

## Next

Continue to [Module 66: Senior and Architect Interview](../04-senior-architect/).
