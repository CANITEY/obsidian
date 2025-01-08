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
gobuster vhost -u <ip address> -w <wordlist file> -p <pattern file>
```
#### Reference
https://medium.com/r3d-buck3t/virtual-host-enumeration-for-uncovering-hidden-subdomains-e800625c2b8f#a4ed