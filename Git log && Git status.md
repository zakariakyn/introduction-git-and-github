# Checking project status and commit history

## Definition

Before and after committing, Git gives you commands to see what's changed and to review commit history: `git status` for the current state of your files, and `git log` (with its options) for the history of commits already made.

## `git status`

```bash
git status
```

Shows the changes in your **working tree** (untracked and tracked files) and in the **staging area** — what's ready to be committed, what's modified but not staged, and what's untracked.

## `git log`

```bash
git log
```

Shows information about commits: hash, author, date, and commit message.

## More details per commit — `git log -p`

```bash
git log -p
```

`-p` = patch. Shows the full diff (line-by-line changes) for each commit, not just the message.

## Limit to a specific number of commits — `git log -n`

```bash
git log -n 3
```

Shows only the last 3 commits.

## Combine patch + limit

```bash
git log -p -n 3
```

Shows the full diff, but only for the last 3 commits.

## One line per commit — `git log --oneline`

```bash
git log --oneline
```

Shows each commit as a single line (short hash + message) — useful for a quick overview.

## Visual graph — `git log --graph`

```bash
git log --graph
```

Shows the commit history as a branch graph.

## Graph + one line

```bash
git log --graph --oneline
```

Combines both: a compact graph with one line per commit.

## One specific commit — `git log <commit-id>`

```bash
git log a1b2c3d
```

A commit ID is normally 40 characters, but you don't need to type the full hash — the first ~7 characters (as shown in `--oneline` output) are usually enough to identify a commit.

## Summary table

| Goal | Command |
|---|---|
| See changes (working tree + staging) | `git status` |
| See commit history | `git log` |
| See full diff per commit | `git log -p` |
| Limit to N commits | `git log -n 3` |
| Combine patch + limit | `git log -p -n 3` |
| One line per commit | `git log --oneline` |
| Visual graph | `git log --graph` |
| Graph + one line | `git log --graph --oneline` |
| See one specific commit | `git log <commit-id>` (short hash works, ~7 chars) |

## Note

Watch out: `-p`, `-n`, `--oneline`, and `--graph` are all options for `git log` (viewing history), not for `git commit` (creating a new commit). Mixing them up (e.g. `git commit -p -n 3`) will not do what you expect.
