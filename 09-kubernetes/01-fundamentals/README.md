# Module 53: Kubernetes Fundamentals

Deploy the TeamOps API to a local Kubernetes cluster using declarative manifests. Use [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/), [workloads](https://kubernetes.io/docs/concepts/workloads/), [Services](https://kubernetes.io/docs/concepts/services-networking/service/), [ConfigMaps](https://kubernetes.io/docs/concepts/configuration/configmap/), and [Secrets](https://kubernetes.io/docs/concepts/configuration/secret/).

## Learn

- Control plane, nodes, kubelet, scheduler, controllers, etcd, and Kubernetes API at a high level.
- Pods, Deployments, ReplicaSets, Services, labels/selectors, namespaces, and in-cluster DNS.
- ConfigMaps, Secrets, volumes, PersistentVolumes/PersistentVolumeClaims, StatefulSets, Jobs, and CronJobs.
- `kubectl` context/namespace awareness and declarative apply workflow.

## Practice Deliverable

Deploy the containerized TeamOps API to a local cluster with a Namespace, Deployment, ClusterIP Service, ConfigMap, and a safe development-only Secret creation method. Access it through port-forwarding first, then introduce an Ingress only after a controller is installed and understood. Keep database state outside the first application workload or explicitly document storage assumptions.

## Verify

```bash
kubectl config current-context
kubectl get namespaces
kubectl -n teamops get deploy,pods,svc
kubectl -n teamops describe pod <pod-name>
kubectl -n teamops logs deploy/<deployment-name>
kubectl -n teamops port-forward service/<service-name> 8080:8080
```

## Completion Criteria

- [ ] Explain Pod, Deployment, ReplicaSet, Service, Namespace, label, and selector roles.
- [ ] Apply manifests from Git and verify the desired versus actual state.
- [ ] Reach the API through a Service and explain why a ClusterIP is not directly public.
- [ ] Load non-secret and secret configuration through appropriate mechanisms without committing sensitive values.
- [ ] Explain where application data persists and what happens when a Pod is replaced.

## Common Mistakes

Labels/selectors that do not match, using `latest` images, applying to the wrong context/namespace, treating a Secret as encrypted source control, exposing a database unnecessarily, and assuming a Pod is a durable VM.

## Next

Continue to [Module 54: Kubernetes Workloads and Scaling](../02-workloads-scaling/).
