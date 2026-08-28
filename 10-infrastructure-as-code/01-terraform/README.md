# Terraform Infrastructure as Code

Terraform is the shared infrastructure workflow for AWS and optional Kubernetes resources in TeamOps. It is cross-cutting: apply it after understanding each AWS/Kubernetes service, not as a replacement for learning the service itself. Use the [Terraform AWS get-started path](https://developer.hashicorp.com/terraform/tutorials/aws-get-started) and [Terraform documentation](https://developer.hashicorp.com/terraform/docs).

## Prerequisites

- AWS Module 42 knowledge: account boundaries, IAM, VPC, subnets, routes, security groups, tags, budgets, and cleanup.
- A dedicated sandbox account/environment with MFA, least-privilege credentials, budget alerts, and an explicit teardown owner.
- Terraform installed from the [official installation guide](https://developer.hashicorp.com/terraform/install).
- A decision on state storage and access before collaborative/shared infrastructure changes.

## Learning Path

1. Learn the lifecycle using a disposable local provider or limited AWS resource: `init`, `fmt`, `validate`, `plan`, `apply`, `show`, and `destroy`.
2. Define variables, outputs, data sources, locals, explicit provider version constraints, and meaningful resource tags.
3. Understand state, state locking, sensitive values, refresh/drift behavior, import, and how resource changes can cause replacement.
4. Split a single learning configuration into focused reusable modules only when a real boundary is repeated.
5. Create separate environment configuration and protected remote state for TeamOps development/staging infrastructure.
6. Use CI to format, validate, and plan infrastructure; require human review before applying to shared environments.

## Suggested Learning Layout

Create files only as needed inside this folder:

```text
01-terraform/
├── practice/              Disposable provider or sandbox experiments
├── modules/               Reusable components after a real repeated need
├── environments/          Environment-specific composition and safe examples
├── examples/              Minimal runnable references without credentials
└── README.md
```

Shared TeamOps production-candidate configuration belongs in `12-projects/teamops/04-infrastructure/`; do not duplicate it here.

## Practice Deliverables

### 1. Safe Terraform Lifecycle

Create a minimal disposable configuration and run:

```bash
terraform init
terraform fmt -check -recursive
terraform validate
terraform plan -out=tfplan
terraform show tfplan
terraform apply tfplan
terraform destroy
```

Document the planned resources, why each is needed, and confirmation that the destroy plan removed the learning resources.

### 2. TeamOps Network Foundation

Model a non-production network using variables and outputs: VPC, public/private subnet boundaries, route responsibilities, and security-group relationships. Run `terraform plan` and have it reviewed before applying.

### 3. Reusable Environment Composition

Extract a module only after a second environment or repeated component needs the same interface. Define documented inputs/outputs and avoid provider credentials or backend configuration inside reusable modules.

### 4. State and Drift Exercise

Document where state lives, who can read/write it, how locking works, how secrets are prevented/minimized in state, and how to investigate a controlled out-of-band change with `terraform plan` without blindly applying it.

### 5. CI Plan Gate

Add or design a GitHub Actions job that runs `terraform fmt -check`, `terraform validate`, and a non-privileged plan for pull requests. Apply only from protected branches/environments with scoped, short-lived credentials.

## Completion Criteria

- [ ] Explain configuration, provider, resource, data source, variable, output, module, backend, state, and plan.
- [ ] Run `fmt`, `validate`, and review a plan before every apply.
- [ ] Use version constraints and lock-file review to keep provider behavior reproducible.
- [ ] Separate configuration by environment and protect remote shared state with restricted access/locking.
- [ ] Use explicit tags and record cost/teardown responsibilities for every billable resource.
- [ ] Recognize when a plan will update, replace, destroy, or create resources before approving it.
- [ ] Investigate drift rather than silently overwriting out-of-band infrastructure changes.
- [ ] Build one reviewed TeamOps infrastructure component and document its rollback/destroy path.

## Common Mistakes

Committing `terraform.tfstate`, trusting a plan without reading it, using one state file for every environment, hard-coding account/region/secrets, module abstraction before repetition, manual infrastructure changes causing hidden drift, no resource tags, disabling state locking, and applying from an unreviewed local machine with broad credentials.

## TeamOps Connection

Terraform provisions the approved network and deployment dependencies for TeamOps Stages 8 and 9: VPC/security groups, ECS/ALB/RDS/S3 dependencies, and optional EKS/Kubernetes platform resources. Each change must be linked to the relevant [TeamOps stage](../../12-projects/teamops/STAGES.md), contribution record, plan review, and teardown/rollback note.

## Next

Use Terraform alongside the AWS deployment modules and then continue to [Kubernetes](../../09-kubernetes/) or [Observability](../../11-observability/) based on the TeamOps stage.
