# masscan

## Repo
https://github.com/robertdavidgraham/masscan

## Installation
```bash
sudo apt install masscan

# From source
git clone https://github.com/robertdavidgraham/masscan
cd masscan
make
sudo make install
```

## Using
```bash
# Fast top ports
sudo masscan -p1-1000 192.168.1.0/24 --rate 10000 -oL open.txt

# Specific ports
sudo masscan -p80,443,8080,8443 target.com --rate 5000

# With banners
sudo masscan -p80,443 target.com --banners --rate 1000
```

## Current Step
Ultra-fast large-scale port discovery.

## Next Step
Take open ports into nmap for version detection or naabu for refinement.

## Errors Fixes
- Requires root → always use sudo
- Interface selection → --interface eth0 or -e
- Too aggressive → lower --rate
- Scope → only scan authorized ranges
