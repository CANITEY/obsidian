---
tags:
  - GIT
date: 2025-01-13 12:18
---
# Remote repositories
Remote repositories are repositories that can be on your *local* device or one some *cloud* platform, it may be shared between you and your coworkers, it will be used a deposit for your code, all your codes will be there for all of you to see it, add to it, modify, and eventually use all what you have done as a release

# Get a remote repository
you can get a remote repository be cloning it into your local machine, you can do that using `git clone <uri>`, *URL* can be a remote resource (github http repository link, username@host format `git@github.com:CANITEY/obsidian.git`) or can be a local path from already existing repo on your machine.

# Add a remote repository
the difference between adding a remote repository and cloning one, is that in adding process you act as a direct contribute or owner of the repo, you can make changes on [[local repositories|local repository]] and [[Git - push|push]] them to the remote repository

to do so you can use `git remote add <a name for your remote repo> <uri>` again the *URL* can be a remote resource or a local ones

# Commands
```
git clone <uri>
git remote add <remote repo name> <uri>
```

# References
- [[Git by Prime]]
