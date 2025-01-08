---
tags:
  - tool
---
# Description
A tool by owasp used for general info gathering about hosts(domains, IP addresses, CIDRs, )

# Installation
```
use your package manager
yay -S amass
```

# Commands
## Gather subdomains - `enum`
### Passive
`amass enum --passive -d example.com -o example.com.subs` 
### Active

### Additional flags
```
-norecursive: Turn off recursive brute forcing
-cidr <value>: CIDRs separated by commas
-df <value>: Path to a file providing root domain names
-w <path>: Path to a different wordlist file for brute forcing
```