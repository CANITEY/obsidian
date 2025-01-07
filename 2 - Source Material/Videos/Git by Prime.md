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
- **tracked**: means that git will observe this file for changes, and modification, if any, it will track them and show them when asked (added to working tree)
- **staged**: the file will be included when you commit
- **committed**: the file is committed

### Staging
staging means to make a file(s) tracked by git (added to your working tree) so git can check on it, to see if any changes where done, or any new things where added to it

you can switch the status of the file by using git commands
**Examples**:
```
git add <file> # adds a file to git working directory, so get can check on it, and makes it ready to be committed by changing its status to *staged*
```

### Committing
committing means that all staged file (staged files not just tracked) will be saved as a snapshot to view, get back to if any thing gone wrong
each commit saves the whole directory not just the changed files, but for none changes files it will store a pointer to the file, and will not store the file it self again

you can commit using `git commit` this will open an editor to write a message, 
**Messages** must be verbose with one line title, and a verbose description of what you have done in this commit, to tell future-you and your friends, why did you add a crypto-mining malware to the coffee-machine software

you can add an inline message using `git commit -m "<your message>`

### Git log
this feature shows you the history of your commits, by default it shows 
- who did the commit
- the date of the commit
- commit message
you can make it shows more info

you can log using `git log`, some useful flags would be
```
--oneline # makes the log compact
--graph # shows a graph for the commits, helps to see branching and merging
```

### Commit hashes
every commit has a unique hash id which lets you interact with the commit without conflicting with other commits, (randomly generated)

## Internals
hashes differ from a user to another user

### Some plumbing
all data in .git are just files, commits, current branch, where the [[#^5b1ad8|pointer]] pointing

you commits are objects and saved in `.git/objects/` directory, in order for git to save all your commits, it compresses them into raw bytes format

if you try to read a file using regular cat, you won't be able, so git gives you a plumbing command `git cat-file -p <commit id>` which will allow you to read commit file
reading this will output the commit message, at the start of the commit message you will notice [[#^d837e9|tree]] with a hash (tree id) using the same command above it will show you the tree with its [[#^c14f87|blobls]], with each blob having an id as well, use the same command again will show you the content of the blob



# Appendex
*pointer*, is where you are standing (HEAD, or somewhere else) ^5b1ad8

*tree*, is a directory in git having all your files as blobs ^d837e9

*blob* is a file in get  ^c14f87