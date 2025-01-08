---
tags: 
date: 2025-01-08 14:34
---

# References
- https://0xn3ssus.notion.site/R3c0n-3861249725ba4c0f83cfe67087179c84

# Recon by Omar Abu-Zekri
he follows a solid steps that are 
1. IPs
2. Subdomains
3. Js Files
4. Directories
5. Parameters
6.  Emails

you don't need to follow the same steps in order

## ASN numbers
you can gather ASN numbers using harvester `theHarvester -d target.com -b all` or amass `amass enum -active -d target.com` or https://bgp.he.net/
## CIDR
now you turn these ASN numbers into CIDRs, you may use `whois -h whois.radb.net -- '-i origin AS16509' | grep -Eo "([0-9.]+){4}/[0-9]+" |uniq`  or https://bgp.he.net/ or http://ipinfo.io/AS714
## Network sweeping
here you turn your CIDRs into ips and sweep for active ones `nmap -n -sn 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt`
```
-sn does ping scan, stops port scan so it goes faster
-n to stop dns resolving
```


after that do the same scan again with `nmap -n -Pn -sS 13.35.121.0/24 |grep "for" |cut -d " " -f 5 >> IP.txt`
```
-Pn to assume all hosts are up
-sS sends only a tcp SYN packet
```

## Subdomain enumeration
### subfinder
`subfinder -d example.com -recursive -silent -t 200 -all -o example.com.subs`

follow the configuration section in the article
### amass
`amass enum --passive -d example.com -o example.com.subs` **Don't just use this command be dynamic**
### assetfinder
`echo domain | assetfinder --subs-only`

### The harvester
`theHarvester -d cisco.com -b all`
### Use favicons
https://medium.com/@Asm0d3us/weaponizing-favicon-ico-for-bugbounties-osint-and-what-not-ace3c214e139
### CRT.sh
## Get working hosts
use httpx
## Gather info about the site
1. js files
2. interesting endpoints
3. directories
4. parameters
these info can be gathered using 
- gau: to get endpoints cached in wayback machine
- ffuf, gobuster, dir: to discover directories