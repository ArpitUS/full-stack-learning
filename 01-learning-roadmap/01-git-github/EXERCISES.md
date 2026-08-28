# Git and GitHub Exercises

Use a disposable repository inside this folder's `practice/` directory for destructive or recovery exercises. Do not experiment with `reset --hard`, force pushes, or history rewrites in the shared training repository.

## 1. Configure and Inspect Git

```powershell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --list --show-origin
```

Deliverable: record the commands used and explain the difference between global and repository configuration.

## 2. Worktree, Staging, and Commits

In a disposable repository:

```powershell
git init
git status
git add <file>
git diff
git diff --cached
git commit -m "Add initial practice note"
git log --oneline --decorate --graph
```

Deliverable: make at least three small commits. Use `git status`, `git diff`, and `git diff --cached` before each commit and explain what each command shows.

## 3. Branch, Merge, and Conflict Resolution

1. Create `feature/practice-conflict` from `main`.
2. Edit the same line differently on `main` and the feature branch.
3. Merge the feature branch into `main`.
4. Resolve the conflict deliberately, run a relevant check, and commit the resolution.

Deliverable: save the conflict-resolution steps and explain why the chosen final content is correct.

## 4. Remotes and Pull Requests

In this repository, create a branch named `<learner>/module-01-git-practice`.

```powershell
git switch -c <learner>/module-01-git-practice
git add <intended-files>
git commit -m "docs: record module 01 Git practice"
git push -u origin <learner>/module-01-git-practice
```

Open a GitHub pull request. Include what changed, how you verified it, and the module number. Review the diff before merging.

Deliverable: merged pull request URL recorded in `15-learners/<name>/module-progress/module-01.md`.

## 5. Safe Undo and Recovery

In a disposable repository, practice each operation:

```powershell
git restore <file>
git restore --staged <file>
git revert <commit>
git reflog
```

Deliverable: describe when to use each command. Use `git reset` only after reading Pro Git's reset chapter and only in the disposable repository.

## 6. Tags and Release Notes

Create an annotated tag after a completed practice milestone:

```powershell
git tag -a module-01-complete -m "Complete Git and GitHub practice"
git show module-01-complete
```

Deliverable: a short release note containing scope, verification, and known limitations.

## Self-Assessment

- Can I predict the output of `git status` after modifying, staging, unstaging, and committing a file?
- Can I explain why a merge conflict occurred and resolve it without discarding either side blindly?
- Can I open a focused pull request and review the full diff before merging?
- Can I recover a local mistake without damaging shared history?
