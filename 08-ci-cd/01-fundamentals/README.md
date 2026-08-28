# Module 39: CI/CD Fundamentals

Design a reliable path from a pull request to a deployable TeamOps artifact. Continuous integration validates every change; continuous delivery keeps a verified artifact ready for controlled release; continuous deployment automatically releases when defined safeguards pass. Use [GitHub Actions CI](https://docs.github.com/en/actions/get-started/continuous-integration), [GitHub Actions CD](https://docs.github.com/en/actions/get-started/continuous-deployment), and the [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html).

## Learn

- Build, test, static analysis, dependency/security scan, package/image, publish, deploy, verify, and rollback stages.
- Artifact identity, immutable versioning, provenance, deployment environments, approval gates, and traceability from source commit to runtime.
- Rolling, blue-green, and canary deployments; when each is appropriate and how rollback works.
- Pipeline failure modes, flaky tests, secret boundaries, least-privilege automation credentials, and manual recovery.

## Practice Deliverable

Create a TeamOps pipeline design document. Define the stages, commands, inputs/outputs, quality gates, artifact/image naming strategy, deployment target, environment protections, signals for post-deploy verification, rollback trigger, and the responsible owner for each step.

## Completion Criteria

- [ ] Explain CI, continuous delivery, and continuous deployment without conflating them.
- [ ] Define the minimum checks required before an artifact can be published.
- [ ] Trace a proposed image or artifact to its commit, test run, and deployment.
- [ ] Define what happens when a test, scan, build, deploy, or health check fails.
- [ ] Select a rollout strategy and document rollback before deployment automation exists.

## Common Mistakes

Deploying untested branches, mutable `latest` tags, no artifact retention policy, pipelines that require permanent admin credentials, treating a successful deployment command as a healthy release, skipped tests, and rollback plans that have never been rehearsed.

## TeamOps Connection

This defines TeamOps Stage 7. The design becomes the basis for GitHub Actions in Module 40 and the Jenkins comparison in Module 41. Keep actual shared workflow files with TeamOps or `.github/workflows/`, not in learner folders.

## Next

Continue to [Module 40: GitHub Actions](../02-github-actions/).
