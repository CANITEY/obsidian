---
tags: 
date: 2025-01-06 22:21
---
# References
- [YouTube video](https://www.youtube.com/watch?v=rH3zE7VlIMs)
# Git 1 by Prime
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


### config 
these are some commands that are used to operate on config use them as a flag with `git config --<operation>`
#### get
used to get a value of a key
#### add
used to set a key:value
#### unset
used to remove a key
#### remove-section
is used to remove the whole [[#^fea776|section]], with key:value pairs from git config

## Branching
a branch in git is where you are working, making a new branch it will make a new pointer to the commit you are standing on, so you can work on it without damaging the main branch

all branching operations are done through `branch` subcommand, in this subcommand you have lots of things to do
```
w/o flags : creates a new branch
-m : to rename a branch
```

there are another commands to interact with a branch `checkout`/`switch`
- **`switch`**  is used switch between branches use it with `-c` to create a branch and switch to it
- **`checkout`** is for the old Gs, used to switch branches, use it with `-b` to create a branch and switch to it

### Log flags
use these flags with log to change how it is shown to you
```
--decorate=(short/full/no) # the whole difference is that it show the full ref of your branch or not
--oneline # this shows the log in a consice way without any bloat-text
--graph # will show the log as a graph
--all # to show you about all branches
```

## Merging
this allow you to merge branches together, by using `git merge <branch>` this will put the branch you specify infront of the branch you are standing on merging all the commits into 1 child commit (merge commit)

### Merge types
### Fast forward 
is the first merge type when your new branch has commits, and the old branch is still at the same state when you branched from it, so git will only move your new branch commits infront of the old branch you branched from

## Rebasing
rebase is used to move all commits from a branch to the tip of the base branch you specify, this will allow you to fast-forward merge even if the main branch has new commits into it, allow a merge free git history

## New branch
created a new branch, made some commits in this new branch and the main one, after rebasing we can see that the main commit went to the upper of the tree

## When to rebase
Do it or do merges as you want
## Resetting
### undo changes
in this we will go back in commit history without discarding changes
### Git reset
is a command that can be used to undo the last commits

using `git reset --soft <POSITION>` will bring you to old commit with all changes done before committing, meaning that if you have files staged or changed and staged it will be in stage, (You will keep the changes)

using `git reset --hard <POSTION>` will reset the changes

## Remote work
when you are working with coworkers, you are often to use a remote repo as you trust repo, this repo will have the latest version of accepted code, this remote repo can be any repository (online or offline),.

when you and your coworkers trust this repo on your code, you may call id **Origin**.

you can add remote repo using `git remote add <repo name> <repo uri>`
### Fetching
to grab the changes done to a repo you may use `fetch`  it brings all the changes without updating any thing, it is like downloading without installing

after you fetch, you may check the changes using `git log <remote repo name>/<branch>`, then you can merge them using `git merge <remote repo name>/<branch>`

### Pushing
you must at some point push your changes to the remote repo, so your friends can see it.

use `git push <repo name>/<branch>` to push your changes

### Pulling
this thing does the fetch and merge automatically `git fetch <repo name>/<branch>`

## Gitignore
is a file that allows you to specify a file or class of files to make git ignore, you can create a file in each directory to make the ignores local to the file, and it accepts symbols, like
```
* wildcard symbol
/ means the root of the gitignore file
! this execludes from the ignore, EXAMPLE
	```
	*.txt
	!important.txt
	```
# a comment
```

### `.git/info/execlude` 
this file is like gitignore but local to your repo, means it will not be pushed to the remote rebo to you coworkers


## Amending commits
`git commit --amend` This command will get the last commit and allow you to change the commit message, 

If you added files to stage it will allow you to add these staged files into your last commit



# Git 2 by Prime
## Fork
is a copy from a repo that you can get and modify without harming the original repo, this is done through your remote repo SP (github, gitlab)
### Fork workflow
1. create a fork of the main repo
2. clone your forked repo
3. make changes to your repo
4. push changes to your repo
5. open a pull request to the main repo explaining your changes, with details

**TIP** when you clone a forked repo, add a remote to the main repo so you pull from it in case of updates

## Reflog
this command makes you show more info about your log, even the reset commits, and with git plumbing you can get your shit back, if you have deleted something this doesn't mean it all gone, you can use `reflog` and `cat-file` to get the files you deleted

or you can merge the commit before you delete the file, by using the comittish from the reflog

## Conflicts
**PAUSED**
conflicts happens when some changes happens on the same line on the same time, when one commit is the parent of the other, git doesn't know how to do so we need to help it figure it out, conflicts will raise as you *merge* or *rebase* 

git will warn you about the conflict, where are they, and you can show these info using `git status`, fix the conflict and then you add them and commit,

when working on more than one branch, when merging conflicts merge the main to your branch (checkout to your branch then run `git merge main`), then you checkout to main and merge your branch

## Rebase conflicts
when you create a conflict in rebase, you can solve the conflict as you solved in merge but after you add the file you run `git rebase --continue`
**DON'T** merge/commit in rebasing, do a `rebase --continue` if you did that by mistake you reset before that commit `git reset --soft HEAD~1`

## Squashing
squashing is the process of grouping more than one commit into one commit, this will keep your history clean and makes you have a concise commits

squashing is done using rebase command use `git rebase -i HEAD~n` where n is the commit you want to squash into EX
```
A-B-C-D-E-F <- HEAD

using git rebase -i HEAD~3 will group [F..D] for squashing
```

then you can choose to 
`pick` to pick the commit to keep
`squash` when you flag commits as squash, it will combine them into the pick commit

##### Squashing is scary it will delete all individual commits because you merge them into one commit, but you can still go back and git you shit using plumbing and `git reflog & git commit`

## Stash
git stashing is like a pocket, you can put the current stage in your working directory for later to get it out of your pocket

```
git stash -> stash
git stash list -> to list all your stashes
git stash pop -> will remove the last stash and apply it to the *current* working directory

### both these commands can have an index to apply or drop, using stash@{N} as an argument
git stash apply -> is like stash pop but it will keep the last stash
git stash drop -> will remove the last stash only
```

stash stores stashed as a stack

## Reverts
if reset is a devil, revert is an angel. It re-apply commits from history not be removing commits till we reach it, but by creating a new commit with the changes of the previous commit, keeping the history intact with no change. Revert may create conflicts, resolve them as well

## Diffs
`git diff` shows you the diff between anything that can be mentioned (files, commitish)
```
git diff -> show the change between the current working tree, and the last commit
```

## When to reset/revert that is the question
**reset** when you work at your own changes nothing public until the moment you decide to reset
**revert** when you want to respect your coworkers

## Cherry pick
# Appendix
*pointer*, is where you are standing (HEAD, or somewhere else) ^5b1ad8

*tree*, is a directory in git having all your files as blobs ^d837e9

*blob* is a file in get  ^c14f87

*section*, is a place in config file that includes key:value pairs ^fea776