# nmap

## Repo
https://nmap.org  
https://github.com/nmap/nmap

## Installation
```bash
# Debian / Kali / Ubuntu
sudo apt update && sudo apt install -y nmap

# From source
git clone https://github.com/nmap/nmap.git
cd nmap
./configure
make
sudo make install
```

## Using
```bash
# Host discovery
nmap -sn 192.168.1.0/24

# Service + default scripts
nmap -sV -sC -oA target target.com

# Full TCP + OS detect
nmap -p- -sV -O -T4 target.com

# Aggressive
nmap -A -T4 target.com

# UDP top ports
nmap -sU --top-ports 100 target.com

# Output formats
nmap -sV -oX target.xml -oN target.nmap target.com
```

## Current Step
Network discovery and service fingerprinting after subdomain / IP list is ready.

## Next Step
Pipe open ports into httpx or nuclei. Feed live hosts into masscan for large-scale follow-up.

## Errors Fixes
- Permission denied on raw sockets → run with sudo or switch to -sT TCP connect scan.
- Host appears down / filtered → add -Pn to skip host discovery.
- Rate limited by ISP or WAF → lower timing to -T2 or -T3, add --max-rate 100.
- Scripts missing → install nmap-scripts package or reinstall nmap.
