---
tags:
  - GIT
date: 2025-01-13 12:01
---
# Local repositories
Local repositories are repositories being used for your *local* usage, they may be on your local machine mostly or on (cloud but the key characteristic about it is that you are the only one that can access and modify it).

On Local repositories you can play with it as much as you want, change code, add and delete files, change history, but **DON'T** change public history if your repository is connected to a [[remote repositories]] with other people working with you, **THIS WOULD GET YOU FIRED OR EVEN SUED**.

# Create a local repository on your local machine
To create a local repository on your machine you can use `git init` as simple as that, you can use some other [[#additional flags]] to change how will the commands behave


## Additional flags
```
-h : shows help message
-b : set initial branch name, github preferes main (default is master)
```

# Remove a local repository
you can do that simply by removing the `.git` directory at the root of your repository

# References
- [[Git by Prime]]
