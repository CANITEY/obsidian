---
tags: 
date: 2025-01-13 15:17
---
# Git - Commits
Commits in git are like a snapshot for the current working directory, these snapshots can have an author, commit message, files modified in the commit, and date, etc.

Commits saves the whole tracked files not just the staged ones, but for not staged files it will keep them by having something like a symbolic link to the file in a previous commit, and all staged files will have new objects having new *[[Git - Dictionary#^6d8c71|committish]]*, having modified files, but not staged will make git treat them as not changed files linking them with old *[[Git - Dictionary#^6d8c71|committish]]*

# Operations
all committing operation are done in case of having [[Git - Staging|staged]] files, if no files are staged, it will automatically stage all [[Git - Files status#tracked|tracked]] files and commit them
###### committing
to commit you can use `git commit` after that an editor will open up default editor to add commit message.
**COMMIT MESSAGES ARE NECESSARY AND THE COMMIT WILL NOT PROCEED WITHOUT IT**

Make commit messages descriptive with a short title, and verbose message why, and what have you modified

NOTE: editor is specified through [[Git - config]] under the `core.editor` name.

you can add short commit message through cli, using `git commit -m "<message>`.


# References
- [[Git by Prime]]