# Module 48: AWS ECS and Fargate

Deploy the TeamOps container image through ECR and ECS/Fargate. Use the [Amazon ECS Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html), [AWS Fargate](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html), and [Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html).

## Learn

- ECR repositories/image tags, ECS clusters, task definitions, tasks, services, launch types, Fargate capacity, task CPU/memory, service discovery, and deployment controllers.
- Task execution roles versus task roles, environment/secrets delivery, `awsvpc` networking, ALB integration, health checks, logs, and ECS service auto scaling.
- Rolling/blue-green deployment concepts, rollback, and ECS versus EC2/EKS trade-offs.

## Practice Deliverable

Publish a versioned TeamOps API image to ECR and deploy it as an ECS Fargate service behind the ALB. Configure CPU/memory, task/execution roles, private networking, health checks, CloudWatch logs, non-secret configuration, secret references, and a rollback procedure. Prefer Terraform for repeatable resources after the initial learning pass.

## Completion Criteria

- [ ] Explain ECR image, task definition, task, service, cluster, task role, and execution role.
- [ ] Deploy an immutable image reference or a traceable image tag tied to a commit.
- [ ] Run tasks in deliberate network/security-group boundaries and expose them through the ALB only as required.
- [ ] Verify target health, service events, application logs, and a rollback path.
- [ ] Define scaling boundaries and cost limits for the service.
- [ ] Tear down learning resources or document their reviewed retention.

## Common Mistakes

Using task execution role for application AWS access, `latest` image tags, public task networking without need, secrets in task definitions, missing task resource limits, health-check mismatch, deployment without rollback evidence, and orphaned ECR images/load balancers/log groups.

## TeamOps Connection

This fulfills the shared AWS deployment stage. Update [TeamOps stages](../../12-projects/teamops/STAGES.md), the feature tracker, and [contributions](../../12-projects/teamops/CONTRIBUTIONS.md) only after the deployment evidence and cleanup/rollback documentation exist.

## Next

Continue to [Module 49: Authentication and Authorization](../../05-authentication-security/01-authentication-authorization/).
