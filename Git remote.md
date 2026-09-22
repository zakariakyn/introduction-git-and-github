# Git remote

## Definition

A remote repo is a version of the project hosted on the internet (e.g. GitHub), allowing multiple people to work on the same code and share project history.

## Add a new remote

```bash
git remote add origin <url_of_repo>
```

## List remotes

```bash
git remote
```
Shows the names of the remotes configured (e.g. `origin`).

```bash
git remote -v
```
Same, but shows the URL next to each remote name — useful to check where `origin` actually points.

## List remote-tracking branches

```bash
git branch -r
```
Shows the branches that exist on the remote (e.g. `origin/main`, `origin/dev`). This is different from `git remote` — it lists branches, not remote names.

## Show more details about a remote

```bash
git remote show origin
```
Shows detailed info: the URL, the branches tracked, and their sync status with the local repo.

## Remove a remote

```bash
git remote remove origin
```
Requires the remote's name (e.g. `origin`) — removes it from your local config, without affecting the actual remote repo on GitHub.

## Summary table

| Command | What it does |
|---|---|
| `git remote add origin <url>` | Add a new remote |
| `git remote` | List remote names |
| `git remote -v` | List remote names with URLs |
| `git branch -r` | List remote-tracking branches |
| `git remote show origin` | Show detailed info about a remote |
| `git remote remove origin` | Remove a remote (needs its name) |
