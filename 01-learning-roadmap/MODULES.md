# Full Stack Learning Modules

Complete modules in order. For each one, use the [module workflow](templates/MODULE_WORKFLOW.md), create a weekly tracker from `templates/WEEKLY_TRACKER.md`, keep notes in the mapped workspace, commit the practice work, and add or extend a TeamOps feature when relevant. The Workspace column is a repository-relative path; every mapped workspace is present in the repository.

## Phase 1: Development Foundations

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 01 | Git and GitHub | repository, staging, commits, branches, merge, rebase, revert, stash, PRs, issues, reviews, tags | Create an issue, feature branch, PR, merge, tag, and release note | `01-learning-roadmap/01-git-github` |
| 02 | Linux and Development Environment | shell, files, permissions, processes, environment variables, SSH, ports, networking, logs | Write a shell setup checklist and troubleshoot a process listening on a port | `01-learning-roadmap/02-linux-networking` |

## Phase 2: Go Programming

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 03 | Go Language Fundamentals | packages, modules, types, pointers, structs, methods, interfaces, slices, maps, strings | Build a typed CLI domain model with table-driven tests | `02-go-backend/01-go-programming/01-language-fundamentals` |
| 04 | Go Functions and Constructs | multiple returns, variadic functions, closures, methods, defer, panic, recover | Implement a parser using deferred cleanup and documented error behavior | `02-go-backend/01-go-programming/02-functions-language-constructs` |
| 05 | Go Error Handling | errors, wrapping, `errors.Is`, `errors.As`, sentinel and custom errors | Design an error package and test error classification | `02-go-backend/01-go-programming/03-error-handling` |
| 06 | Go Concurrency | goroutines, channels, select, timers, cancellation, ownership | Build a cancellable worker pipeline | `02-go-backend/01-go-programming/04-concurrency` |
| 07 | Go Synchronization | mutexes, RWMutex, Once, WaitGroup, atomic, worker pools, fan-in/out | Compare channel and mutex implementations of concurrent state | `02-go-backend/01-go-programming/05-synchronization` |
| 08 | Race Conditions and Deadlocks | races, deadlocks, livelocks, starvation, leak prevention | Create failing race/deadlock examples, then fix and verify with `go test -race` | `02-go-backend/01-go-programming/06-race-conditions-deadlocks` |
| 09 | Go Runtime and Internals | scheduler, G-M-P, escape analysis, GC, pprof, benchmarks | Profile a slow allocation-heavy program and document the improvement | `02-go-backend/01-go-programming/07-runtime-internals` |
| 10 | Go System Programming | signals, files, TCP/UDP, sockets, graceful shutdown | Build a TCP service with signal-aware graceful shutdown | `02-go-backend/01-go-programming/08-system-programming` |

## Phase 3: Backend and API Development

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 11 | HTTP and REST API Development | HTTP, `net/http`, handlers, JSON, headers, validation, status codes | Build a JSON CRUD API using the standard library | `02-go-backend/02-api-development/01-http-rest` |
| 12 | Go REST API Design | resources, URL design, versioning, pagination, filtering, idempotency, contracts | Write an API contract for TeamOps tasks and implement pagination | `02-go-backend/02-api-development/02-rest-api-design` |
| 13 | Gin Framework | routing, binding, middleware, groups, validation, context | Port one API resource to Gin with request validation | `02-go-backend/02-api-development/03-gin-framework` |
| 14 | Middleware | logging, recovery, auth, authorization, metrics, tracing, rate limiting, timeout | Build and order a middleware chain with request IDs | `02-go-backend/02-api-development/04-middleware` |
| 15 | Backend Architecture | configuration, dependency injection, services, repositories, DTOs, workers, shutdown | Create the TeamOps backend skeleton with clear layers | `02-go-backend/02-api-development/05-backend-architecture` |

## Phase 4: Databases

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 16 | SQL and RDBMS Fundamentals | PostgreSQL, schema design, keys, constraints, normalization, CRUD, aggregates | Design and seed TeamOps users, teams, projects, and tasks | `04-databases/01-postgresql/01-sql-rdbms` |
| 17 | Joins and Advanced Queries | joins, subqueries, CTEs, window functions, ranking | Solve ten reporting queries against the TeamOps schema | `04-databases/01-postgresql/02-joins-advanced-queries` |
| 18 | SQL Interview Problems | duplicates, top N, group-wise maximum, running totals, pagination | Document and solve common SQL interview exercises | `04-databases/01-postgresql/03-sql-interview-problems` |
| 19 | Database Performance | B-tree/composite indexes, planner, `EXPLAIN ANALYZE`, N+1 | Optimize a deliberately slow query with measured evidence | `04-databases/01-postgresql/04-performance` |
| 20 | Database Transactions | ACID, isolation, rollback, locks, deadlocks, optimistic/pessimistic locking | Implement an atomic task assignment transaction | `04-databases/01-postgresql/05-transactions` |
| 21 | Database Connection Management | pooling, limits, timeout, lifetime, exhaustion, Go integration | Configure and test a production-safe Go connection pool | `04-databases/01-postgresql/06-connection-management` |

## Phase 5: Redis and Caching

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 22 | Redis Fundamentals | data types, persistence, TTL, expiration, streams | Store sessions and a short-lived value in Redis | `04-databases/02-redis/01-fundamentals` |
| 23 | Redis Caching | cache-aside, invalidation, stampede, hot keys, TTL jitter | Cache a TeamOps read endpoint with invalidation | `04-databases/02-redis/02-caching` |
| 24 | Redis Pub/Sub and Messaging | publish, subscribe, streams, fan-out, trade-offs | Publish and consume a TeamOps notification event | `04-databases/02-redis/03-pubsub-messaging` |
| 25 | Redis Rate Limiting | fixed/sliding window, token bucket, Lua, distributed limits | Protect an API route with a tested rate limiter | `04-databases/02-redis/04-rate-limiting` |

## Phase 6 and 7: Distributed Systems and Messaging

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 26 | Microservices Architecture | monolith vs microservices, boundaries, discovery, gateway, data ownership | Produce an ADR choosing a modular monolith or services for TeamOps | `02-go-backend/03-distributed-systems/01-microservices` |
| 27 | Distributed Systems | async processing, events, retries, consistency, CAP, partial failure | Model an idempotent event-driven task update flow | `02-go-backend/03-distributed-systems/02-distributed-systems` |
| 28 | Distributed Reliability | timeouts, backoff, jitter, circuit breakers, bulkheads, health checks | Add timeout, retry, and idempotency behavior to an API client | `02-go-backend/03-distributed-systems/03-reliability` |
| 29 | Messaging and Queues | Kafka, RabbitMQ, producers, consumers, offsets, retries, DLQs | Build a producer and consumer with retry and dead-letter handling | `02-go-backend/03-distributed-systems/04-messaging-queues` |

## Phase 8: React and Frontend

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 30 | JavaScript and TypeScript Foundations | async/await, event loop, modules, types, interfaces, generics, narrowing | Implement typed API client utilities and tests | `03-react-typescript/01-javascript-typescript` |
| 31 | React Fundamentals | components, props, state, hooks, forms, context, lists | Build TeamOps task list and form with accessible state handling | `03-react-typescript/02-react/01-fundamentals` |
| 32 | React Application Development | routing, state management, API integration, auth, loading, pagination | Create routed TeamOps screens backed by the Go API | `03-react-typescript/02-react/02-application-development` |
| 33 | React Performance and Security | code splitting, caching, CORS, XSS, token handling, frontend tests | Audit one UI flow and add secure loading/error behavior and tests | `03-react-typescript/02-react/03-performance-security` |

## Phase 9 and 10: Testing and Patterns

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 34 | Backend and Frontend Testing | unit, integration, E2E, mocks, coverage, load tests, browser tests | Add unit, API integration, and one E2E test to TeamOps | `02-go-backend/04-testing-design-patterns/01-testing` |
| 35 | Design Patterns | factory, adapter, decorator, strategy, observer, DI, repository, service, pipeline | Implement one appropriate pattern and document its trade-off | `02-go-backend/04-testing-design-patterns/02-design-patterns` |
| 36 | Singleton and `sync.Once` | thread-safe singleton, lazy/eager init, testing concerns, DI comparison | Build and test a `sync.Once` initialization example, then replace it with DI where appropriate | `02-go-backend/04-testing-design-patterns/03-singleton-sync-once` |

## Phase 11: Docker

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 37 | Docker Fundamentals | images, containers, Dockerfile, volumes, networking, health checks | Containerize a Go service and run it locally | `06-docker/01-fundamentals` |
| 38 | Docker Advanced | multi-stage builds, non-root users, security, Compose, optimization | Run TeamOps API, client, PostgreSQL, and Redis with Docker Compose | `06-docker/02-advanced` |

## Phase 12: CI/CD

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 39 | CI/CD Fundamentals | CI, CD, security scanning, artifacts, rollout strategies, rollback | Define a pipeline plan for build, test, image, deploy, rollback | `08-ci-cd/01-fundamentals` |
| 40 | GitHub Actions | workflows, triggers, jobs, cache, artifacts, secrets, deployments | Add PR checks for Go and frontend tests | `08-ci-cd/02-github-actions` |
| 41 | Jenkins | agents, Jenkinsfile, declarative/scripted pipelines, credentials | Create a Jenkinsfile equivalent to one GitHub Actions workflow | `08-ci-cd/03-jenkins` |

## Phase 13: AWS

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 42 | AWS Fundamentals | regions, AZs, IAM, VPC, subnets, routing, security groups, CloudWatch | Diagram a least-privilege TeamOps AWS network | `07-aws/01-fundamentals` |
| 43 | AWS EC2 | instances, AMIs, keys, EBS, user data, monitoring, lifecycle | Deploy a containerized API to an EC2 instance | `07-aws/02-ec2` |
| 44 | AWS Load Balancing | ALB, target groups, listeners, health checks, routing, TLS | Put the EC2 service behind an ALB with a health check | `07-aws/03-load-balancing` |
| 45 | AWS Auto Scaling | ASG, ECS scaling, target tracking, step/scheduled policies | Define and test a scaling policy from a CloudWatch metric | `07-aws/04-auto-scaling` |
| 46 | AWS S3 | buckets, policies, encryption, presigned URLs, uploads, lifecycle | Add a secure presigned TeamOps file-upload flow | `07-aws/05-s3` |
| 47 | AWS RDS | PostgreSQL, backups, multi-AZ, replicas, IAM auth, monitoring | Connect TeamOps to RDS with migrations and safe pool settings | `07-aws/06-rds` |
| 48 | AWS ECS | ECR, clusters, tasks, services, Fargate, deployment, logging | Deploy the API image to ECS Fargate | `07-aws/07-ecs-fargate` |

## Phase 14: Security, TLS, and SSO

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 49 | Authentication and Authorization | JWT, OAuth2, OIDC, SAML, tokens, RBAC, sessions, scopes | Implement authenticated API routes with role checks | `05-authentication-security/01-authentication-authorization` |
| 50 | SSO Integration | identity provider, React and Go integration, token validation, secure logout | Integrate a development OIDC provider into TeamOps | `05-authentication-security/02-sso-integration` |
| 51 | SSL, TLS, and HTTPS | handshake, certificates, CA chain, termination, mTLS, Go TLS | Serve a local Go endpoint over TLS and document the certificate chain | `05-authentication-security/03-ssl-tls-https` |
| 52 | Application Security | validation, SQL injection, XSS, CSRF, SSRF, CORS, secrets, scanning | Complete a security checklist and fix one deliberate vulnerability | `05-authentication-security/04-application-security` |

## Phase 15: Kubernetes

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 53 | Kubernetes Fundamentals | control plane, pods, deployments, services, ingress, config, secrets, storage | Deploy TeamOps API and dependencies to a local cluster | `09-kubernetes/01-fundamentals` |
| 54 | Kubernetes Workloads and Scaling | requests, limits, HPA, probes, rollouts, networking, storage | Add probes, resource limits, and an HPA | `09-kubernetes/02-workloads-scaling` |
| 55 | Kubernetes Troubleshooting | kubectl, logs, CrashLoopBackOff, OOMKilled, DNS, connectivity | Diagnose and document fixes for three broken manifests | `09-kubernetes/03-troubleshooting` |
| 56 | Kubernetes vs Docker and ECS | containers vs pods, ECS vs EKS, scaling, ingress, deployment trade-offs | Write a deployment-platform decision record | `09-kubernetes/04-vs-docker-ecs` |

## Phase 16 and 17: Observability and Networking

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 57 | Observability | structured logs, metrics, tracing, Prometheus, Grafana, OpenTelemetry | Instrument a TeamOps request with logs, metrics, and a trace | `11-observability/01-observability` |
| 58 | Performance Engineering | latency, throughput, profiling, benchmarks, load tests, capacity | Establish a baseline and improve one endpoint under load | `11-observability/02-performance-engineering` |
| 59 | DNS and Networking | DNS hierarchy, records, resolution, caching, TCP, UDP, sockets | Inspect a domain's DNS resolution and build a small Go lookup tool | `02-go-backend/05-networking/01-dns-networking` |
| 60 | DNS-over-HTTPS | DoH messages, HTTP/2, resolver design, caching, policy, rate limits | Call a DoH resolver and implement a minimal proxy experiment | `02-go-backend/05-networking/02-dns-over-https` |

## Phase 18: Python Secondary Skill

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 61 | Python | core types, generators, decorators, FastAPI, Pydantic, asyncio, ETL | Build a small typed FastAPI or data-processing utility without replacing the Go focus | `14-resources-notes/05-python-secondary-skill` |

## Phase 19 through 22: Interview and Production Readiness

| # | Module | Topics | Practice deliverable | Workspace |
| --- | --- | --- | --- | --- |
| 62 | DSA and Coding | arrays, strings, lists, stacks, trees, graphs, sorting, DP, Big-O | Solve and explain 25 curated problems | `13-interview-preparation/01-dsa` |
| 63 | Production Debugging | latency, memory, CPU, DB/Redis issues, outages, incidents | Run three incident simulations and write incident reports | `13-interview-preparation/02-production-debugging` |
| 64 | System Design Fundamentals | requirements, scale, availability, caching, queues, security, trade-offs | Design a scalable service using an explicit requirements template | `13-interview-preparation/03-system-design` |
| 65 | System Design Practice | URL shortener, rate limiter, notifications, uploads, chat, payments, DoH | Produce six timed system-design solutions | `13-interview-preparation/03-system-design` |
| 66 | Senior and Architect Interview | architecture, mentoring, code review, incidents, technical debt, trade-offs | Create a STAR story bank and conduct a mock architecture review | `13-interview-preparation/04-senior-architect` |
