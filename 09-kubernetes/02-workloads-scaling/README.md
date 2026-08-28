# Module 54: Kubernetes Workloads and Scaling

Make the TeamOps workload safe to roll out and scale with resource boundaries, probes, configuration, ingress, and autoscaling. Use [Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/), [probes](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-probes), [resource management](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/), and [HPA](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/).

## Learn

- Requests versus limits, QoS implications, HPA, Cluster Autoscaler scope, and capacity constraints.
- Liveness, readiness, and startup probes; rolling updates, rollout status/history, and rollback.
- Ingress/controller responsibilities, service networking, configuration changes, persistent workloads, and disruption considerations.
- Service accounts, RBAC basics, security contexts, and principle of least privilege.

## Practice Deliverable

Add readiness/liveness/startup probes and explicit CPU/memory requests/limits to the TeamOps Deployment. Configure a rolling update, perform a controlled rollback, and add an HPA only after metrics support exists in the local cluster. Create a minimal service account/RBAC policy only if the application needs Kubernetes API access.

## Verify

```bash
kubectl -n teamops rollout status deploy/<deployment-name>
kubectl -n teamops rollout history deploy/<deployment-name>
kubectl -n teamops get hpa
kubectl -n teamops top pods
kubectl -n teamops describe deploy <deployment-name>
```

## Completion Criteria

- [ ] Explain readiness versus liveness versus startup and choose endpoints that match each purpose.
- [ ] Set requests and limits based on observed/assumed workload with documented rationale.
- [ ] Roll out a new immutable image and roll back deliberately.
- [ ] Explain what drives HPA and why it cannot solve all scaling/capacity problems.
- [ ] Keep application permissions and pod security settings minimal.

## Common Mistakes

Using the same probe blindly for all lifecycle states, probes that depend on unstable downstream services, no resource limits, HPA without metrics, rollouts using mutable tags, broad service-account permissions, and assuming Ingress exists without an installed controller.

## TeamOps Connection

This extends TeamOps Stage 9. Reuse the Docker health contract and AWS/observability decisions rather than inventing Kubernetes-only behavior.

## Next

Continue to [Module 55: Kubernetes Troubleshooting](../03-troubleshooting/).
