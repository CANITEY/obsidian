---
tags:
  - cybersecurity
  - computer-networks
  - protocols/HTTP/technologies
date: 2025-01-08 19:28
---
# Virtual hosting
Is a feature that allow one server to host several websites.

Some physical hosts may have more than one host, referred to as VHOSTing, in this technology, a company may make one IP address used to host more than one host, company determine what host to send the request to by using the `Host` header in HTTP request

## VHOSTing types
### IP based
in this type, server is configured to host more than one website, but each of them has a unique IP address.
when you send a request to the server, server routes the request based on the IP address associated with it

### Name based
in this type, server is configured to host more than one website on the same IP address, but the server routes the request based on the HOST name in the header of the HTTP request



# References
[Virtual Host Enumeration for Uncovering Hidden Subdomains](https://medium.com/r3d-buck3t/virtual-host-enumeration-for-uncovering-hidden-subdomains-e800625c2b8f)
[[Recon by Omar Abu-Zekri]]
