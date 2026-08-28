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
