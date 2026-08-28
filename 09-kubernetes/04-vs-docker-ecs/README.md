# Module 56: Kubernetes vs Docker and ECS

Choose a deployment platform based on operational needs, team capability, and constraints. Docker is a container build/runtime tool; ECS and Kubernetes are orchestration platforms with different operational models. Use the [Kubernetes overview](https://kubernetes.io/docs/concepts/overview/), [Amazon ECS documentation](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html), and the existing Docker/AWS modules.

## Compare

| Concern | Docker Compose | Amazon ECS/Fargate | Kubernetes/EKS |
| --- | --- | --- | --- |
| Primary fit | Local multi-service development | AWS-managed container application deployment | Portable, extensible orchestration for complex platform needs |
| Control plane | None | AWS-managed ECS control plane | Kubernetes control plane and ecosystem to operate/govern |
| Deployment unit | Container/service | Task/service | Pod/Deployment/Service |
| Network entry | Host port mapping | ALB plus task networking | Service plus Ingress/Gateway/controller |
| Scaling | Manual/local | ECS service auto scaling | HPA plus cluster capacity strategy |
| Operational cost | Low locally | Lower platform overhead for AWS-focused teams | Higher complexity; justified by platform requirements |

## Practice Deliverable

Write a TeamOps architecture decision record (ADR) comparing Compose, ECS/Fargate, and Kubernetes/EKS. State functional requirements, operational requirements, team skills, security boundaries, cost expectations, deployment/rollback model, observability needs, and the selected platform for the current stage.

## Completion Criteria

- [ ] Explain Docker container versus Kubernetes Pod versus ECS Task.
- [ ] Compare ALB/ECS routing with Service/Ingress routing.
- [ ] Compare ECS service auto scaling with Kubernetes HPA and underlying capacity needs.
- [ ] State when ECS is the lower-complexity choice and when Kubernetes is justified.
- [ ] Make a decision based on TeamOps requirements rather than technology preference.

## Common Mistakes

Calling Docker Compose a production orchestrator by default, adopting Kubernetes only for resume value, assuming EKS removes operational responsibility, ignoring platform costs/skills, and migrating to microservices/orchestration before the modular monolith is stable.

## TeamOps Connection

Store the approved decision with TeamOps planning/infrastructure artifacts. The current curriculum uses Compose for local development, ECS/Fargate as the primary AWS deployment path, and Kubernetes/EKS as an advanced deployment exercise unless the ADR establishes another justified choice.

## Next

Continue to [Module 57: Observability](../../11-observability/01-observability/).
