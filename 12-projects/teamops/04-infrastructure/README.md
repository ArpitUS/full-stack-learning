# TeamOps Infrastructure

This folder receives shared Docker, CI/CD, AWS, Terraform, Kubernetes, and observability configuration as TeamOps reaches the relevant stages. Do not use it as a dumping ground for local credentials, state files, generated manifests, or unreviewed experiments.

## Expected Artifacts

- Dockerfiles, Compose configuration, safe environment examples, and local runbooks.
- GitHub Actions workflows, test/build/publish/deploy pipelines, artifact/image traceability, and rollback documentation.
- Terraform configuration for approved AWS/Kubernetes resources, protected state strategy, and plan evidence.
- Kubernetes manifests/Helm configuration, probes, resource settings, and operational runbooks.
- Observability configuration: log/metric/trace conventions, dashboard specifications, alerts, and incident evidence.

## Infrastructure Rules

- Infrastructure changes are reviewed, tested in non-production, and tied to a stage/backlog task.
- Use least privilege, separate environments, immutable image references, explicit tags, budgets, and teardown plans.
- Never commit access keys, secret values, certificates, `.env` files, Terraform state, or generated plan files containing sensitive data.
- Treat deployment success as incomplete until health, logs, metrics, and rollback verification are recorded.

See [Docker](../../../06-docker/), [CI/CD](../../../08-ci-cd/), [AWS](../../../07-aws/), [Terraform](../../../10-infrastructure-as-code/), [Kubernetes](../../../09-kubernetes/), [observability](../../../11-observability/), and [TeamOps stages](../STAGES.md).
