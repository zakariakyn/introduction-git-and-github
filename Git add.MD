# The `git add` command

## Definition

After creating or reinitializing a repo with `git init`, the next step is to add files — untracked or tracked — to the **staging area**, so they're ready to be included in the next commit.

## Key terms

| Term | Meaning |
|---|---|
| Untracked file | A brand new file Git has never seen before |
| Tracked file | A file Git already knows about (added/committed before) — can be unmodified, modified, or staged |
| Staging area (index) | Holds the file changes that will go into the next commit |

## Add a specific file

```bash
git add filename
```

## Add all files

```bash
git add .
```

## Add changes interactively — `git add -p`

`-p` stands for **patch**. Instead of staging a whole file at once, it lets you review and choose which **parts (hunks)** of the changes to stage — useful when you changed several things in one file but want to split them into separate commits.

When you run it, Git shows each change block and asks:

```
Stage this hunk [y,n,q,a,d,s,e,?]?
```

| Key | Action |
|---|---|
| `y` | Yes, stage this hunk |
| `n` | No, skip it |
| `s` | Split into smaller hunks |
| `q` | Quit |

## What happens next

Once files are staged, the next step is `git commit` to save them permanently in the repo's history.
