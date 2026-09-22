# Git push

## Basic push

```bash
git push
```
Uploads your local commits to the remote repo (on the branch already tracked/linked).

## Force push (after rewriting history)

If you've changed commit history — using `git rebase` or `git commit --amend` — the remote repo won't accept a normal push, since the history no longer matches. You need:

```bash
git push -f
```
`-f` / `--force` forces Git to overwrite the remote branch with your local (rewritten) history.

⚠️ **Warning:** force push is risky on shared branches — it can overwrite a teammate's commits without warning if they pushed something you don't have locally. Safer alternative:

```bash
git push --force-with-lease
```
This refuses to force-push if the remote branch has commits you haven't seen yet — protects against accidentally deleting someone else's work.

## Push a specific branch (and set tracking)

```bash
git push -u origin branch-name
```
`-u` (`--set-upstream`) links your local branch to `origin/branch-name`, so future `git push`/`git pull` on this branch won't need the branch name repeated.

## Summary table

| Command | What it does |
|---|---|
| `git push` | Push commits to the tracked remote branch |
| `git push -f` | Force push — overwrites remote history (use with caution) |
| `git push --force-with-lease` | Safer force push — fails if remote has unseen commits |
| `git push -u origin branch-name` | Push a branch and set it as the tracked upstream |
