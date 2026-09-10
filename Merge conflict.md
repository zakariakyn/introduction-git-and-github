# Merge conflict

When using `git merge` or `git pull`, sometimes Git gives a message about a merge conflict — so why does this happen?

In Git (Version control system), if two people do modifications on the same code and the same files, Git finds this out and gives the message "merge conflict." In this case, you manually open the file and resolve the conflict markers (e.g., `<<<<<<<`, `=======`, `>>>>>>>`).

`git pull` is a collaboration command, used to update the local repo from the remote repo.

## Conflict markers explained

```
<<<<<<< HEAD
Your local changes
=======
Incoming changes from the other branch
>>>>>>> feature
```

| Marker | Meaning |
|---|---|
| `<<<<<<< HEAD` | Start of your current branch's version |
| `=======` | Separator between the two versions |
| `>>>>>>> feature` | End of the incoming branch's version |

## Resolving a conflict

1. Open the file — the conflict markers are visible directly inside it
2. Decide which lines to keep (yours, theirs, or a mix), and delete the markers
3. Save the file
4. Stage it: `git add filename`
5. Complete the merge: `git commit`
