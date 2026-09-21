# naabu

## Repo
https://github.com/projectdiscovery/naabu

## Installation
```bash
go install -v github.com/projectdiscovery/naabu/v2/cmd/naabu@latest

# libpcap required on some systems
sudo apt install libpcap-dev
```

## Using
```bash
# Top ports
naabu -list hosts.txt -top-ports 1000 -o ports.txt

# Full range
naabu -list hosts.txt -p - -o allports.txt

# Hand off to nmap
naabu -list hosts.txt -nmap-cli 'nmap -sV -sC'

# Silent
naabu -host target.com -silent -top-ports 100
```

## Current Step
Fast port scanning on resolved hosts.

## Next Step
Feed open ports to nmap for service detection or httpx for web ports.

## Errors Fixes
- Permission denied → run with sudo for raw scans or use connect mode
- libpcap missing → install libpcap-dev
- Rate limit → -rate 1000
- No results → confirm hosts are up
