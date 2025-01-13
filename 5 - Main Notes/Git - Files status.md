---
tags: 
date: 2025-01-13 14:06
---
# Git - Files status
In your working directory, files and all contents of the repository.

Files can have several status:
###### untracked
this status is given to new files create but git didn't track them before, if any modification (addition, deletion) is done to this files git will not notice it will just keep the same status *untracked* and won't tell what changes made, and if the file is deleted or renamed git will not be able to help restore it
###### untracked
this status is given to file that you added them to git worktree using `git add` command, git will keep track of these files, will know if any changes happened to these files (addition, deletion, rename, deletion) and will offer you a [[Git - diff|diff]] that shows you the file before and after modifications


# References
[[Git by Prime]]
