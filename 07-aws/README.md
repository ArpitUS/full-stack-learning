# AWS Training

This section progresses from AWS account and network fundamentals to TeamOps deployment on EC2/ALB and ECS/Fargate. It covers catalog modules 42-48.

## Learning Order

1. AWS foundations: regions, IAM, VPC, subnets, routing, security groups, CloudWatch.
2. EC2 and ALB: deploy a container, health checks, TLS termination, and routing.
3. Scaling and managed services: Auto Scaling, S3 uploads, and RDS PostgreSQL.
4. ECR and ECS/Fargate: image registry, tasks, services, deployment, logging, and scaling.

## Prerequisites

Complete Docker and baseline security. Use Terraform design before repeating infrastructure manually. Do not deploy credentials or local `.env` files.

## Practical Artifacts

- Least-privilege IAM policy and VPC diagram.
- EC2 or ECS deployment runbook with rollback notes.
- ALB health-check and target-group configuration evidence.
- S3 presigned upload flow and RDS migration plan.
- CloudWatch logs and metrics links or screenshots recorded in documentation.

## Completion Standard

Deploy the containerized TeamOps API with a health endpoint, least-privilege access, managed database connectivity, centralized logs, and a documented rollback path. Explain why EC2 or ECS was selected.

## Common Debugging Areas

Security groups versus NACLs, private subnet routing, IAM role assumptions, ALB health-check paths, container image tags, RDS connectivity, ECS task roles, and configuration/secrets propagation.

## TeamOps Handoff

AWS hosts the shared deployment stages. Pair it with [Terraform](../10-infrastructure-as-code/) so infrastructure can be reproduced and reviewed.

## Lab Safety and Cost Rules

- Use a dedicated sandbox account or clearly isolated learning environment, MFA, least-privilege roles, and a named budget/alarm before provisioning resources.
- Tag every resource with at least `project=teamops`, `environment=learning`, `owner`, and an expiry/review date.
- Prefer infrastructure as code after the first guided experiment. Review `terraform plan` or equivalent before changes.
- Record the teardown command/process before creating billable resources. Delete test resources, snapshots, unused IPs, images, load balancers, and volumes when finished.
- Do not commit access keys, `.env` files, certificates, or Terraform state containing secrets.

## Primary References

- [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html): security, reliability, performance, cost, and operational trade-offs.
- [IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) and [VPC User Guide](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html).
- [Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html), [Elastic Load Balancing](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html), and [Auto Scaling](https://docs.aws.amazon.com/autoscaling/).
- [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html), [Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Welcome.html), and [Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html).
- [AWS Pricing](https://aws.amazon.com/pricing/) and [AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html).
