# Git Command Reference

Use `git <command> --help` or the official [Git reference](https://git-scm.com/docs) for full details. This is a practical shortlist, not a replacement for the Pro Git book.

| Need | Command | Safety note |
| --- | --- | --- |
| Inspect state | `git status` | Run before staging, committing, pulling, or switching branches. |
| Inspect unstaged changes | `git diff` | Does not include staged changes. |
| Inspect staged changes | `git diff --cached` | Review this before committing. |
| Create/switch branch | `git switch -c name` | Branch names should identify learner and task. |
| Save work | `git add <files>` then `git commit -m "message"` | Stage intended files, not `git add .` by habit. |
| Update local history | `git pull --ff-only` | Avoids accidental merge commits when a fast-forward is not possible. |
| Send branch | `git push -u origin branch-name` | Never force-push shared branches. |
| Download remote refs | `git fetch origin` | Lets you inspect changes before integration. |
| View graph | `git log --oneline --decorate --graph --all` | Useful before merges, rebases, and recovery. |
| Discard unstaged file edit | `git restore <file>` | Loses the selected uncommitted edit. |
| Unstage file | `git restore --staged <file>` | Keeps the working-tree edit. |
| Safely undo a shared commit | `git revert <commit>` | Creates a new reversing commit. |
| Find lost local commits | `git reflog` | Use before considering destructive recovery. |
| Temporarily set work aside | `git stash push -m "message"` | Prefer a small commit when the work is meaningful. |
| Create annotated tag | `git tag -a name -m "message"` | Tag completed, reviewable milestones. |

## Collaboration Rules

- Pull or fetch before starting work; inspect the state before integrating remote changes.
- One focused task per branch and pull request.
- Write imperative commit messages, for example `Add task validation`.
- Do not force-push `main` or rewrite commits already under review without agreement.
- Resolve conflicts in the relevant branch, run checks, and explain the resolution in the pull request.
- Keep secrets in local environment files ignored by Git; never add them to a commit, even temporarily.
