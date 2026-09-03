# Reverting changes and commits

## Definition

Sometimes something you've done breaks the code, or you need to go back to a previous working commit to fix a bug. Git gives different commands depending on **where** the change lives: working tree, staging area, or already committed.

## Revert a file in the working tree

```bash
git checkout <file>
```
or
```bash
git restore <file>
```
Reverts a file back to its last committed state (discards uncommitted changes in the working tree).

## Revert a file in the staging area

```bash
git reset <file>
```
Unstages a file — removes it from the staging area, but keeps the changes in the working tree.

## Modify a commit

```bash
git commit --amend
```
Changes the last commit (message and/or content).

⚠️ **Warning:** `--amend` is best used on **local repositories** (commits not yet pushed/shared), since it rewrites commit history.

## Restore a commit (project broken or bug found)

```bash
git revert <commit-id>
```
Creates a **new commit** that undoes the changes of a previous commit, identified by its ID. Safe to use even on shared/pushed history, since it doesn't rewrite existing commits.

### `git revert -e`
```bash
git revert -e <commit-id>
```
Opens a text editor to write the commit message. This is actually the **default** behavior of `git revert` — `-e` just makes it explicit.

### `git revert -n`
```bash
git revert -n <commit-id>
```
`-n` (`--no-commit`) applies the revert changes to the working tree and staging area, but does **NOT** create a commit automatically — you run `git commit` yourself afterward. Useful when reverting several commits and wanting to combine them into a single commit.

## Summary table

| Command | What it does |
|---|---|
| `git checkout <file>` / `git restore <file>` | Revert a file in the working tree |
| `git reset <file>` | Unstage a file (remove from staging area) |
| `git commit --amend` | Modify the last commit — best for local, unpushed commits |
| `git revert <commit-id>` | Create a new commit that undoes a previous commit |
| `git revert -n <commit-id>` | Same, but no auto-commit — lets you combine several reverts into one |
| `git revert -e <commit-id>` | Same as default — opens editor for commit message |
