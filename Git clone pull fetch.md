# Download a remote repo to local computer, or update it

## Clone a remote repo

In Git, we can download a remote repo from GitHub using `git clone URL_OF_REPO`:

```bash
git clone https://github.com/zakariakyn/introduction-git-and-github
```

## Update a repo with merge

```bash
git pull
```

Downloads the changes from the remote and **merges** them into your current branch automatically.

## Update a repo without merge

```bash
git fetch
```
or
```bash
git remote update
```

These commands download the changes from the remote **without merging them** into your branch — they let you see what changed and decide whether to merge or not.

## Merge the fetched changes manually

```bash
git merge origin/main
```

After `git fetch`, this merges the downloaded changes from `origin/main` into your current branch, once you've reviewed them.

## Summary table

| Command | What it does |
|---|---|
| `git clone <url>` | Download a remote repo to your local machine |
| `git pull` | Fetch + merge in one step |
| `git fetch` / `git remote update` | Download changes only, no merge |
| `git merge origin/main` | Manually merge changes fetched from the remote |
