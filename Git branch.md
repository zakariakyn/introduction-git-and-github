# Git branches

## Definition

A branch is an independent line of development in a repository. It lets you work on new features or fixes without affecting the main codebase, then merge the changes back later.

## Create a new branch

```bash
git branch branch_name
```
Creates the branch, but does **not** switch to it.

## Switch to another branch

```bash
git checkout branch_name
```

## Create and switch in one command

```bash
git checkout -b branch_name
```
Creates a new branch **and** switches to it immediately.

## Rename a branch

```bash
git branch -m old_name new_name
```

## Delete a branch

```bash
git branch -d branch_name
```
Safe delete — Git refuses if the branch has unmerged changes.

## Force-delete a branch

```bash
git branch -D branch_name
```
Deletes the branch even if it has changes that were never merged.

## List branches

```bash
git branch -a
```
Lists **all** branches — local **and** remote-tracking branches.

```bash
git branch -r
```
Lists **only** remote-tracking branches (not local ones).

## Summary table

| Command | What it does |
|---|---|
| `git branch branch_name` | Create a new branch |
| `git checkout branch_name` | Switch to an existing branch |
| `git checkout -b branch_name` | Create a new branch and switch to it |
| `git branch -m old_name new_name` | Rename a branch |
| `git branch -d branch_name` | Delete a branch (safe — refuses if not merged) |
| `git branch -D branch_name` | Force-delete a branch, even with unmerged changes |
| `git branch -a` | List all branches — local + remote |
| `git branch -r` | List only remote-tracking branches |
