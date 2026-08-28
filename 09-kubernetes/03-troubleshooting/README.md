# Module 55: Kubernetes Troubleshooting

Diagnose Kubernetes problems from resource state, events, logs, configuration, network path, and resource usage instead of changing manifests blindly. Use [Kubernetes application troubleshooting](https://kubernetes.io/docs/tasks/debug/debug-application/), [debugging Services](https://kubernetes.io/docs/tasks/debug/debug-application/debug-service/), [logging](https://kubernetes.io/docs/tasks/debug/debug-application/get-shell-running-container/), and [DNS debugging](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/).

## Diagnostic Sequence

1. Confirm `kubectl` context and namespace.
2. Inspect desired workload state, Pod status, and recent events.
3. Inspect the current and previous container logs.
4. Verify image, configuration, Secret/ConfigMap references, command, and probes.
5. Verify labels, selectors, endpoints, Service DNS, ports, and network policy path.
6. Inspect requested/limited and actual resource use.
7. Fix one cause, apply declaratively, and verify the recovery.

## Practice Deliverable

Create three intentionally broken local manifests and incident notes. Include at least one of: wrong image/command causing `CrashLoopBackOff`, bad image reference causing `ImagePullBackOff`, missing configuration, mismatched Service selector, failed probe, insufficient resource limit causing `OOMKilled`, or DNS/connectivity failure. Document symptom, evidence, root cause, fix, and prevention.

## Verify

```bash
kubectl -n teamops get pods,events --sort-by=.lastTimestamp
kubectl -n teamops describe pod <pod-name>
kubectl -n teamops logs <pod-name> --previous
kubectl -n teamops get svc,endpointslices
kubectl -n teamops exec <pod-name> -- <diagnostic-command>
kubectl -n teamops top pods
```

## Completion Criteria

- [ ] Diagnose and repair three distinct failure classes with retained evidence.
- [ ] Explain `CrashLoopBackOff`, `ImagePullBackOff`, Pending, and `OOMKilled` causes at a high level.
- [ ] Trace a request from Service selector to EndpointSlice to Pod port.
- [ ] Use events/logs/resource state before editing the manifest.
- [ ] Add a preventive check, probe, resource boundary, test, or runbook for each repair.

## Common Mistakes

Debugging the wrong context, deleting Pods before gathering evidence, changing multiple variables at once, relying only on `kubectl get`, ignoring prior logs, confusing Service DNS with external ingress, and treating restart count as the root cause.

## TeamOps Connection

Convert one completed diagnostic into a TeamOps operational runbook and relate it to logs, metrics, or traces from the observability modules.

## Next

Continue to [Module 56: Kubernetes vs Docker and ECS](../04-vs-docker-ecs/).
