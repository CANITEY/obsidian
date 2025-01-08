---
tags:
  - bugbounty
  - recon/passive
  - recon/wide
date: 2025-01-08 16:05
---
# Passive info gathering - wide scope - Network sweeping
In this step you turn CIDRs into IP addresses, it comes after this step [[Passive info gathering - wide scope - CIDR]]

## Tools and usage
### Nmap
- `nmap -n -sn 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt` gathers all active and put them in a file
- `nmap -n -Pn -sS 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt` gathers all active but protected ips and put them in a file






# References
this is used for source material and any other note linked to this note
