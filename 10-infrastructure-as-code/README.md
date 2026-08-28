# Infrastructure as Code Training

Terraform provides reproducible, reviewable infrastructure for the AWS and Kubernetes work. The catalog references infrastructure-as-code within AWS modules even though Terraform is a cross-cutting capability rather than a separate numbered module.

## Learning Order

1. Providers, resources, variables, outputs, and plan/apply lifecycle.
2. Remote state, state safety, and environment-specific configuration.
3. Reusable modules for network, compute, storage, and data services.
4. Terraform-managed TeamOps infrastructure with a documented destruction/rollback strategy.

## Prerequisites

Understand AWS fundamentals and IAM. Begin with a disposable sandbox account and budget controls. Never place credentials or secrets in state files or commits.

## Practical Artifacts

- Terraform project with formatted, validated code and documented inputs/outputs.
- Environment layout such as development and staging with explicit state strategy.
- Modules for TeamOps VPC, security boundaries, and deployment dependencies.
- Architecture diagram and `terraform plan` review evidence.

## Completion Standard

Provision a non-production TeamOps environment reproducibly, review a plan before apply, protect state, separate environment configuration, and tear down or roll back resources safely.

## Common Debugging Areas

State drift, unsafe local state, provider credentials, implicit dependencies, resource replacement, missing outputs, environment leakage, and unexpectedly expensive resources.

## TeamOps Handoff

Terraform turns the AWS and Kubernetes deployment designs into shared, reviewable infrastructure. Keep implementation in `12-projects/teamops/04-infrastructure/` and learning experiments here.
