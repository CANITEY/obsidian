---
tags:
  - tool
---
# Description
**puredns** is a fast domain resolver and subdomain bruteforcing tool that can accurately filter out wildcard subdomains and DNS poisoned entries.

## Notes
**Puredns** uses resolvers.txt at this order
1. in current directory
2. `.config/puredns/resolvers.txt`
3. if none, you may optionally use resolvers by using this flag `--resolvers <path>`
4. or it will use `8.8.8.8` or `8.8.4.4` by defaul
# Installation
## Prerequisites
you need to install massdns through
```
git clone https://github.com/blechschmidt/massdns.git
cd massdns
make
sudo make install
```

## actual installation
```
go install github.com/d3mondev/puredns/v2@latest
--- or 
yay -S puredns # this will install massdns automatically
```


# Commands

