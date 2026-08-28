# Module 63: Production Debugging

Practice incident response using evidence from logs, metrics, traces, profiles, deployment history, and dependency state. The goal is structured diagnosis, not guessing or memorizing runbook commands.

## Incident Workflow

```text
Detect -> assess impact -> stabilize -> gather evidence -> isolate cause
    -> mitigate -> verify recovery -> document prevention
```

## Practice Deliverable

Run three controlled incident simulations using TeamOps or disposable labs. Choose scenarios such as API latency, CPU/memory growth, goroutine leak, database slowdown/pool exhaustion, Redis outage, cache hit-rate drop, consumer lag, deployment failure, pod restart, race/deadlock, or network dependency failure. Write one incident record per simulation.

## Incident Record Template

```md
# Incident: Title

- Date and environment:
- User/business impact:
- Detection signal:
- Timeline:
- Evidence reviewed:
- Root cause:
- Mitigation:
- Recovery verification:
- Prevention/follow-up:
- Related module, TeamOps stage, and pull request:
```

## Completion Criteria

- [ ] State impact and severity before proposing a fix.
- [ ] Use at least two evidence sources, such as metrics plus logs or trace plus database plan.
- [ ] Distinguish symptom, contributing factors, root cause, mitigation, and prevention.
- [ ] Verify recovery through a defined signal instead of assuming a restart fixed the problem.
- [ ] Create an actionable follow-up for the system, test, alert, or runbook.

## Common Mistakes

Changing multiple systems at once, restarting before collecting evidence, blaming the most recent change without proof, treating correlation as causation, and closing incidents without prevention work.

## Next

Continue to [Module 64: System Design Fundamentals](../03-system-design/).
