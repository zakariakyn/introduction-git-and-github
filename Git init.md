# The `git init` command
 
## Definition
 
`git init` turns a folder into a Git repository. It creates a hidden `.git` folder that will track all changes to your files from that point on.
 
## Two cases
 
- **No `.git` folder yet** → creates a brand new repository from scratch.
- **`.git` folder already exists** → re-running `git init` does **not** delete anything. It just reinitializes config files, hooks, and templates. Your commits and tracked files stay untouched. Safe to re-run.
## Check before running
 
```bash
cd ~/New
ls -la
```
Look for a `.git` folder in the list. If it's not there, you're starting fresh.
 
## Command
 
```bash
git init
```
 
**Expected output:**
```
Initialized empty Git repository in /home/New/.git/
```
