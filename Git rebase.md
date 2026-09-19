# Git rebase

## Definition

`git rebase` is a powerful command in Git to manage commit history — squash commits, reorder them, edit messages, drop commits, and more.

## Interactive rebase

```bash
git rebase -i <commit-or-branch>
```

This opens an interactive editor (usually Vim) showing a list of commits, letting you decide what to do with each one before they're rewritten into history.

**Example editor view:**
```bash
# Rebase 634e69a..634e69a onto 634e69a (1 command)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
```

## Key commands

| Command | Short | What it does |
|---|---|---|
| `pick` | `p` | Keep the commit as-is |
| `reword` | `r` | Keep the commit, but edit its message |
| `edit` | `e` | Pause here so you can amend the commit |
| `squash` | `s` | Merge this commit into the previous one, combining both messages |
| `fixup` | `f` | Like squash, but discard this commit's message |
| `drop` | `d` | Delete this commit entirely |
| `exec` | `x` | Run a shell command at this point in the rebase |
| `break` | `b` | Pause the rebase here (resume with `git rebase --continue`) |

## Rebase the last N commits

```bash
git rebase -i HEAD~n
```

Opens the interactive editor for only the last `n` commits (e.g. `HEAD~3` = last 3 commits), instead of rebasing from a specific commit ID or branch.

## Cancel a rebase

```bash
git rebase --abort
```

Stops the rebase and restores everything back to the state it was in before the rebase started. Useful if something goes wrong or you change your mind midway through.


## Warning

`git rebase` rewrites commit history — same caution as `git commit --amend`. Best used on local/unpushed commits, since rewriting shared history can cause problems for collaborators.
