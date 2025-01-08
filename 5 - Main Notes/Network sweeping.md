---
tags:
  - cybersecurity
  - recon/passive
  - recon/wide
date: 2025-01-08 16:05
---
In this step you turn CIDRs into IP addresses, it comes after this step [[CIDR]]

## Tools and usage
### Nmap
- `nmap -n -sn 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt` gathers all active and put them in a file
- `nmap -n -Pn -sS 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt` gathers all active but protected ips and put them in a file






# References
[[Recon by Omar Abu-Zekri]]