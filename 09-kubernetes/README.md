# Kubernetes Training

This section teaches orchestration for TeamOps through catalog modules 53-56: workloads, networking, configuration, scaling, troubleshooting, and deployment-platform trade-offs.

## Learning Order

1. Deploy containerized services as Pods, Deployments, and Services.
2. Add ConfigMaps, Secrets, volumes, Ingress, and probes.
3. Set resource requests/limits and HPA, then practice rollout and rollback.
4. Break and troubleshoot manifests before evaluating ECS versus Kubernetes.

## Prerequisites

Complete Docker and understand the service's health endpoint, configuration, and logs. Use a local cluster before EKS.

## Practical Artifacts

- Versioned manifests or Helm chart for TeamOps.
- Separate configuration examples with no committed secrets.
- Readiness, liveness, and startup probes plus resource boundaries.
- Troubleshooting notes for broken images, DNS, services, and resource failures.

## Completion Standard

Deploy TeamOps to a cluster, reach it through a Service/Ingress, perform a safe rollout and rollback, scale it with resource-aware settings, and diagnose at least three intentionally broken workload scenarios.

## Common Debugging Areas

CrashLoopBackOff, ImagePullBackOff, incorrect labels/selectors, missing config, bad probes, OOMKilled, pending pods, service DNS, ingress routing, and RBAC denials.

## TeamOps Handoff

Kubernetes is an advanced TeamOps deployment option after the Compose and ECS paths. The platform comparison should be documented as an explicit decision rather than assumed.
