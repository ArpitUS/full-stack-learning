# Module 01: Git and GitHub

Learn to manage changes safely, collaborate through GitHub, and keep a reviewable history for every later module. The primary reference is the official [Pro Git book](https://git-scm.com/book/en/v2). A local `progit.pdf` is available in this folder for offline reading.

## Why This Module Comes First

Every exercise, learner record, and TeamOps contribution is versioned with Git. Before writing application code, learners must be able to inspect changes, isolate work on a branch, recover safely from mistakes, and submit a pull request for review.

## Prerequisites

- A GitHub account.
- Git installed and available from PowerShell.
- Access to this repository and its `origin` remote.

## Recommended Reading

Read the official book selectively while completing the matching exercises.

| Order | Pro Git chapters | Use in this workspace |
| --- | --- | --- |
| 1 | [Chapter 1: Getting Started](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) | Install Git, configure identity, understand local history and the command line. |
| 2 | [Chapter 2: Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository) | Worktree, staging, commits, history, remotes, tags, and safe undo. |
| 3 | [Chapter 3: Git Branching](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) | Branches, merges, remote branches, workflows, and rebasing. |
| 4 | [Chapter 5: Distributed Git](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows) | Small changes, review, collaboration, and maintaining shared history. |
| 5 | [Chapter 6: GitHub](https://git-scm.com/book/en/v2/GitHub-Account-Setup-and-Configuration) | Pull requests, review, issues, and GitHub collaboration. |
| 6 | [Chapter 7: Git Tools](https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection) | Stash, history inspection, reset, recovery, and debugging tools. |

Chapters 4, 8, 9, and 10 are valuable later references. Do not delay practical work until reading the entire book.

## Concepts to Understand

- Git stores snapshots locally; GitHub hosts and coordinates shared repositories.
- The working tree, staging area, and commit history are separate states.
- A branch is an independent line of development; a pull request is a review and integration process.
- `fetch` downloads remote history, while `pull` fetches and integrates it.
- `revert` adds a corrective commit; `reset` moves a branch pointer and must be used cautiously on shared work.
- Rebase rewrites local commit ancestry. Do not rebase commits already shared with collaborators unless the team has agreed.
- Resolve conflicts by understanding both changes, testing the result, and committing the resolution.

## Practice Sequence

Complete the tasks in [EXERCISES.md](EXERCISES.md). Store learner-specific answers and evidence in your own `15-learners/<name>/` workspace, not in this shared module folder.

## Completion Criteria

- [ ] Configure Git identity and verify it with `git config --list --show-origin`.
- [ ] Explain the working tree, staging area, local repository, remote, branch, and pull request.
- [ ] Create a focused branch, make atomic commits, push it, and open a pull request.
- [ ] Inspect and resolve a practice merge conflict.
- [ ] Demonstrate safe recovery using `git restore`, `git revert`, and `git reflog` in a disposable practice repository.
- [ ] Create an annotated tag and draft a release note.
- [ ] Record module completion evidence in your learner module-progress file.

## TeamOps Connection

Git workflow is the collaboration rule for TeamOps. Use a focused branch per task, reference the relevant issue, request review, and record merged work in [TeamOps contributions](../../12-projects/teamops/CONTRIBUTIONS.md). Do not commit credentials, generated build output, or local environment files.

## Next Module

Continue to [Module 02: Linux and Development Environment](../02-linux-networking/) to develop the shell, process, permissions, SSH, and networking skills used by the Git workflow.
