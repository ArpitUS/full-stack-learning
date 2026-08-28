# Module Workflow

Use this workflow with the central [module catalog](../MODULES.md). The catalog defines module scope and deliverables; this template defines how to turn that scope into evidence of learning.

## Before Starting

- Identify the module number, mapped workspace, prerequisites, and deliverable in `MODULES.md`.
- Create a learner record: `15-learners/<name>/module-progress/module-NN.md`.
- Set the active module in `current-focus.md` and plan the work in `weekly-planner.md`.

## Learning Loop

1. Study the module concepts and write concise personal notes.
2. Complete the catalog deliverable in the mapped shared workspace or personal `practice/` area.
3. Add automated checks where the module calls for behavior that can be tested.
4. Debug one failure or edge case and record the lesson.
5. Link the artifact, pull request, or commit in the learner module record.
6. Update the learner progress dashboard and reassess the skill rating.

## Completion Evidence

A module is complete only when the learner can show the deliverable, explain key design choices, reproduce the core implementation without copying, and document verification. If the deliverable belongs to TeamOps, also update its feature and contribution trackers.

## Where Work Belongs

| Work type | Location |
| --- | --- |
| Shared curriculum and module definition | `01-learning-roadmap/MODULES.md` |
| Technology-specific exercise or artifact | The workspace mapped by the module catalog |
| Personal notes, planning, daily logs, and module status | `15-learners/<name>/` |
| Shared application code and integration | `12-projects/teamops/` |
| Reusable external references | `14-resources-notes/` |
