---
tags:
  - recon
  - bugbounty
  - recon/mid
date: 2025-01-08 16:18
---
In this step you start gathering subdomains, there are 2 ways 
# [[Passive subdomain enumeration]]
In this method you try to get subdomains using passive tools, to gather data scattered on the internet without interacting with the target

This step has the following pros:
- fast
- doesn't make targets notice you
- gets a lot of results
cons:
- lots of domains may be dead
- doesn't get you all data

# [[Active subdomain enumeration]]
In this method you try to get subdomains using active tools and methods, by bruteforcing or gather domains from the actual site

This step has the following pros:
- accurate
- gives fresh, alive domains
- domains gathered depends on the wordlist used, if you have private wordlist you will get unique results
cons:
- slower
- generated a lot of traffic
- makes the target notice you


# References
[[Recon by Omar Abu-Zekri]]
