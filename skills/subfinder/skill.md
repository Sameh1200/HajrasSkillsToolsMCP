# subfinder

## Repo
https://github.com/projectdiscovery/subfinder

## Installation
```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest

# Binary
wget https://github.com/projectdiscovery/subfinder/releases/latest/download/subfinder_linux_amd64.zip
unzip subfinder_linux_amd64.zip
sudo mv subfinder /usr/local/bin/

export PATH=$PATH:$(go env GOPATH)/bin
```

## Using
```bash
# Single domain
subfinder -d target.com -o subs.txt

# All sources
subfinder -d target.com -all -o subs.txt

# Domain list
subfinder -dL domains.txt -o all_subs.txt

# Silent pipe
subfinder -d target.com -silent | httpx -silent
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| Single domain (default sources) | 15 – 60 s | very fast passive |
| Single domain -all | 1 – 4 min | more sources, slower |
| 10 domains | 2 – 10 min | parallel internally |
| Large program (100+ domains) | 15 – 45 min | use -dL + rate limits |

API keys in provider-config.yaml dramatically increase coverage and can slightly increase time.

## Current Step
Passive subdomain enumeration. First recon phase.

## Next Step
Resolve with dnsx → probe live hosts with httpx → feed into nuclei or amass for deeper mapping.

## Errors Fixes
- Empty results → configure API keys in ~/.config/subfinder/provider-config.yaml
- Rate limit → lower -rl or restrict sources with -s
- go: command not found → install golang-go then re-run go install
- Binary not found → add $(go env GOPATH)/bin to PATH
