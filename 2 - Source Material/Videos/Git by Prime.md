---
tags: 
date: 2025-01-06 22:21
---

# References
- [YouTube video](https://www.youtube.com/watch?v=rH3zE7VlIMs)
# Git by Prime
## Setup
### Porcelain and Plumbing
**porcelain** is the high level commands in git, you are will interact with them most of the  time
*Example*
```
- `git status`
- `git add`
- `git commit`
- `git push`
- `git pull`
- `git log`
```
**plumbing** is a low level commands
*Examples*
```
- `git apply`
- `git commit-tree`
- `git hash-object`
```

### Quick config
you can config git using this command `git config` all what comes after it just flags to till it what to configure and where.

you can use `git config` with some common flags:
```
--get <property> # --get user.name # used to get the property value

--add <property> <value> # --add user.name canitey # used to set the propery value

--global <other flags> # used to get/set property in the global space `~/.gitconfig`

--list # lists all configs and the values assigned to it

--unset <property> # used to unset the first property value
```


## Repositories
repositories are the core of projects, every project would have one repo, which is a .git file in your project directory

you can create a repository using `git init` inside your folder, we will be creating a webflyx project (directory) and create a repo inside

### Status
file can be in different status in a repo
- **untracked**: the file is not tracked by git, (new files, Note files, temp file, etc). You have total control on the status, here git doesn't sense or check this file
- **staged**: the file will be included when you commit
- **committed**: the file is committed

### Staging
staging means to make a file(s) tracked by git (added to your working directory) so git can check on it, to see if any changes where done, or any new things where added to it
you can switch the status of the file by using git commands
**Examples**:
```
git add <file> # adds a file to git working directory, so get can check on it, and makes it ready to be committed by changing its status to *staged*
```

### committing
