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
repositories are the core of projects, every project would have one repo, which is a .git file in your project direct
### config



