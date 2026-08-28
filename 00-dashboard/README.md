# Dashboard

Use this folder for high-level, manually maintained training visibility. It does not automatically aggregate learner files.

- `OVERALL_PROGRESS.md`: technology-level progress.
- `SKILL_TRACKER.md`: beginner to production skill assessment.
- `DAILY_LOG.md`: daily learning log template.
- `EFFORT_ALLOCATION.md`: suggested study allocation.
- `LEARNER_OVERVIEW.md`: lightweight comparison of independent learner progress.

Detailed learner records are kept separately in [Arpit's workspace](../15-learners/arpit/) and [Ashish's workspace](../15-learners/ashish/).

## Source of Truth and Update Workflow

| Information | Source of truth | When to update |
| --- | --- | --- |
| Module scope and deliverables | [Module catalog](../01-learning-roadmap/MODULES.md) | Only when the shared curriculum changes. |
| Individual module status and skills | `15-learners/<name>/` | At the end of a study session or module milestone. |
| Learner comparison | `LEARNER_OVERVIEW.md` | After a learner updates their own focus/progress. |
| Shared feature and contribution state | [TeamOps](../12-projects/teamops/) | When shared project work changes. |

To avoid merge conflicts, learners should primarily edit files in their own directories. Update the shared overview and TeamOps trackers in a focused pull request or during a planned pair session.
