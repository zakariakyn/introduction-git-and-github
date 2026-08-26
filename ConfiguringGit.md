# Getting started: configuring Git
 
Now we're ready to start using Git.
 
The first step is configuration — telling Git who is making the changes, so it can track authorship.
 
`git config` is the command used to set values that identify who made the changes. The two main values are `user.email` and `user.name`:
 
```bash
git config --global user.email "name@example.com"
git config --global user.name "name"
```
 
The `--global` flag applies this configuration to every repository on your machine (not just the current one).
 
If you want a different identity for a specific repo — for work or study, for example — drop `--global` and run the command inside that repo:
 
```bash
git config user.email "name@company.com"
```
 
To list all your current configuration:
 
```bash
git config --list
```
 
To check a single value, like your `user.email` or `user.name`:
 
```bash
git config user.email
git config user.name
```
 
Finally, if you want to modify a value you've already set, just run the same command again with the new value — it overwrites the previous one:
 
```bash
git config --global user.email "newname@example.com"
```
 
