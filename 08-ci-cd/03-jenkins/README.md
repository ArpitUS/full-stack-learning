# Module 41: Jenkins

Understand Jenkins pipeline-as-code by creating a `Jenkinsfile` equivalent to one TeamOps GitHub Actions workflow. Use the [Jenkins Pipeline handbook](https://www.jenkins.io/doc/book/pipeline/), [Jenkinsfile guide](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/), [Pipeline syntax](https://www.jenkins.io/doc/book/pipeline/syntax/), and [Jenkins security guidance](https://www.jenkins.io/doc/book/security/).

## Learn

- Controller/agent model, nodes, executors, workspaces, stages, steps, declarative versus scripted syntax, and multibranch pipelines.
- Jenkinsfile as versioned pipeline source; credentials, environment variables, Docker agents, artifacts, approvals, and shared libraries.
- Controller/agent trust boundaries, plugin lifecycle, credential scope, workspace cleanup, and GitHub Actions versus Jenkins trade-offs.

## Practice Deliverable

Create a declarative `Jenkinsfile` that mirrors the GitHub Actions CI stages for TeamOps: checkout, Go checks, frontend checks, optional Docker build, test report/artifact publication, and an explicitly gated deployment placeholder. Document the required agent tooling and credential assumptions without storing values in the repository.

## Verification

Run the pipeline on an authorized Jenkins learning instance. Verify a successful build, one expected failing check, artifact/report visibility, workspace cleanup behavior, and the inability of an untrusted branch to access deployment credentials.

## Completion Criteria

- [ ] Explain Pipeline, node/agent, stage, step, workspace, and Jenkinsfile roles.
- [ ] Use declarative syntax for the initial pipeline and keep stages visible/independent.
- [ ] Store the Jenkinsfile in source control and review it like application code.
- [ ] Scope credentials to the minimum pipeline/environment and avoid printing them.
- [ ] Explain the maintenance, security, and infrastructure trade-offs between Jenkins and GitHub Actions.

## Common Mistakes

Manual UI-only jobs, controller builds, overprivileged global credentials, unpinned/unreviewed plugins, stale workspaces, secrets in shell traces, no agent isolation, and Jenkins used as an excuse to duplicate an already-working workflow without a purpose.

## TeamOps Connection

Jenkins is a learning comparison and an alternative pipeline runtime. GitHub Actions remains the default shared CI path unless the TeamOps project records a reason to operate Jenkins. Link equivalent stages and artifacts so the comparison remains concrete.
