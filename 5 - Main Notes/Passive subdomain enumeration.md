---
tags:
  - bugbounty
  - recon/mid
  - recon/passive
date: 2025-01-08 16:28
---
# Tools used and a description
## Subfinder
### Installation
```
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
--- or
yay -S subfinder
```

use config steps from https://0xn3ssus.notion.site/R3c0n-3861249725ba4c0f83cfe67087179c84 to setup the tool
### Commands
- `subfinder -d example.com -recursive -silent -t 200 -all -o example.com.subs`

## Amass
### Installation
```
use your package manager
yay -S amass
```
### Commands
`amass enum --passive -d example.com -o example.com.subs` 
## Assetfinder
### Installation
```
go install github.com/tomnomnom/assetfinder@latest
--- or 
yay -S assetfin
```
### Commands
# References
[[Recon by Omar Abu-Zekri]]
