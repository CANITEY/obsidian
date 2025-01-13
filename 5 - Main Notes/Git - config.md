---
tags:
  - GIT
date: 2025-01-13 13:32
---
# Git - config
Configuring your repository is essential for a good, clear, comfortable workflow. Your configuration can be through multiple levels, I'll order them with the first level has the highest priority
1. local config
   this config is applied per repo, no local config of a repo can be used in another user unless you copied it, the local config resides itself in `.git/config` file in your repository
2. global
   global config is applied to all repositories for a certain user, it can be found in `$HOME/.gitconfig`
3. system wide
   this will be applied to all repositories on the machine, will work for all users. Can be found in `/etc/gitconfig`

any of the upper files is note required for git to work, but you need to set them


# References
[[Git by Prime]]
