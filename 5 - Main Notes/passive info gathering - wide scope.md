---
tags: bugbounty recon/passive 
date: 2025-01-08 15:38
---
# passive info gathering - wide scope
## ASN numbers gathering
This is a group of CIDRs under one tag called ASN, tools used with there commands
```
theHarvester -d target.com -b all
amass enum -active -d target.com
https://bgp.he.net/ - website
```
## CIDRs gathering
CIDRs are an ip range in a subnet mask `192.168.1.1/24` for example, you gather them 
to get CIDRs from ASN, you may use 1 of three
```
whois -h whois.radb.net -- '-i origin AS16509' | grep -Eo "([0-9.]+){4}/[0-9]+" |uniq
https://bgp.he.net/ 
http://ipinfo.io/AS714
```


# References
- [[Recon by Omar Abu-Zekri]]
