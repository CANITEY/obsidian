---
tags: 
date: 2025-01-08 16:03
---
# Passive info gathering - wide scope - CIDR
This is the next step after [[Passive info gathering - wide scope - ASN numbers]]

CIDRs are an ip range in a subnet mask `192.168.1.1/24` for example, you gather them 
to get CIDRs from ASN, you may use 1 of three
```
whois -h whois.radb.net -- '-i origin AS16509' | grep -Eo "([0-9.]+){4}/[0-9]+" |uniq
https://bgp.he.net/ 
http://ipinfo.io/AS714
```




# References
[[]]