---
tags:
  - tool
  - recon/subdomain-enum
  - recon/active
---
# Description
A tools written in go used in all sorts of fuzzing, and enumeration
used in:
- active subdomain enumeration
- [[VHOSTs]] discovery
- directory bruteforcing

# Installation
```
yay -S gobuster
--- or
through github and go
```

# Commands
## Subdomain bruteforcing
```
gobuster dns -d <domain> -w <wordlist>
```
## VHOSTs discovery
```
gobuster vhost -u <ip address
```
