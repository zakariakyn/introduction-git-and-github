# Git merge

When we want to add a new feature or fix the code in our project, we should use a new branch to test and add changes to the code.

## Definition

`git merge` is a command to integrate a feature branch into another (usually the main or master branch).

## Workflow

We create a new branch:

```bash
git checkout -b feature
```

We do the changes or update the code.

To merge the changes into master:

First, switch to the master branch:

```bash
git switch master
```
or
```bash
git checkout master
```

Then merge the feature branch into it:

```bash
git merge feature
```

Handling Conflicts

If both branches modify the same lines of code, Git pauses the merge and flags a merge conflict.

To cancel the merge and return your branch to its state before git merge was run:
```bash
git merge --abort
```
