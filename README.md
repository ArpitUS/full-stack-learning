# Full Stack Developer Learning Workspace

Target: production-ready full-stack developer.

Core stack: Go, React, TypeScript, PostgreSQL, Redis, Docker, AWS, GitHub Actions, Jenkins, Terraform, Kubernetes, and observability.

## Workspace map

- `00-dashboard`: progress, daily log, skill tracker, and effort allocation.
- `01-learning-roadmap`: the 66-module topic catalog, recommended sequence, and weekly trackers.
- `02-go-backend` through `11-observability`: topic folders for focused notes, exercises, and project work.
- `12-projects`: TeamOps, the integrated full-stack portfolio project.
- `13-interview-preparation`: DSA, system design, and senior/architect preparation.
- `14-resources-notes`: reusable notes, resource links, and Python secondary-skill practice.
- `15-learners`: independent progress records for Arpit and Ashish.

Start with `01-learning-roadmap/MODULES.md`. Each module maps to a workspace folder, has a measurable deliverable, and should be completed using the weekly tracker in `01-learning-roadmap/templates/WEEKLY_TRACKER.md`.

## Learners

The workspace supports two independent learners, Arpit and Ashish. Both follow the same [66-module curriculum](01-learning-roadmap/MODULES.md), while maintaining separate progress, notes, practice records, and retrospectives. Shared implementation work belongs in the [TeamOps project](12-projects/teamops/).

- [Arpit workspace](15-learners/arpit/)
- [Ashish workspace](15-learners/ashish/)
- [Shared module catalog](01-learning-roadmap/MODULES.md)
- [Shared TeamOps project](12-projects/teamops/)

## Folder Structure

```text
52_FullStack/
├── 00-dashboard/                 Shared training overview and skill tracking
├── 01-learning-roadmap/          66-module catalog, sequence, and templates
├── 02-go-backend/                Go, APIs, distributed systems, testing, networking
├── 03-react-typescript/          JavaScript, TypeScript, React, and API integration
├── 04-databases/                 PostgreSQL and Redis
├── 05-authentication-security/   Authentication, SSO, TLS, and application security
├── 06-docker/                    Containers and Docker Compose
├── 07-aws/                       AWS infrastructure and deployment services
├── 08-ci-cd/                     CI/CD, GitHub Actions, and Jenkins
├── 09-kubernetes/                Kubernetes workloads, scaling, and troubleshooting
├── 10-infrastructure-as-code/    Terraform and reproducible infrastructure
├── 11-observability/             Logging, metrics, tracing, and performance
├── 12-projects/teamops/          Shared full-stack integration project
├── 13-interview-preparation/     DSA, debugging, system design, and interviews
├── 14-resources-notes/           Shared references and Python secondary skill
└── 15-learners/                  Independent Arpit and Ashish learning records
```

## How to Use This Workspace

1. Start in the [66-module catalog](01-learning-roadmap/MODULES.md) and select the next module in sequence.
2. Read the mapped technology section guide to understand prerequisites, practice artifacts, and completion criteria.
3. In your learner workspace, set the module in `current-focus.md`, plan it in `weekly-planner.md`, and create `module-progress/module-NN.md`.
4. Study, practice, test, and debug in the module's mapped shared technology folder. Add personal notes and daily logs only in your learner folder.
5. When a validated exercise solves a TeamOps need, integrate it into [TeamOps](12-projects/teamops/) and record the shared work in `CONTRIBUTIONS.md`.
6. Update your `progress.md` and skill ratings at a meaningful milestone. Update the shared dashboard overview only after a high-level status changes.

```text
Select module -> Plan -> Learn -> Practice -> Build -> Test -> Debug
    -> Record personal progress -> Integrate with TeamOps -> Review
```

Use the [module workflow](01-learning-roadmap/templates/MODULE_WORKFLOW.md) whenever starting a module. The shared catalog defines the curriculum; learner folders contain personal records; TeamOps contains collaborative application work.
