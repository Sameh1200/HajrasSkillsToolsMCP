# amass

## Repo
https://github.com/owasp-amass/amass

## Installation
```bash
# Go
go install -v github.com/owasp-amass/amass/v4/...@master

# Docker
docker pull caffix/amass

# Binary from releases page
```

## Using
```bash
# Passive enum
amass enum -passive -d target.com -o amass_passive.txt

# Active enum
amass enum -active -d target.com -o amass_active.txt

# Intel
amass intel -d target.com -whois

# Config driven
amass enum -d target.com -config config.yaml -o out.txt
```

## Current Step
Deep attack surface mapping and subdomain discovery (passive + active).

## Next Step
Merge with subfinder output → resolve → probe with httpx → nuclei.

## Errors Fixes
- Slow → start with -passive, limit sources
- Missing data → configure API keys in config.yaml
- Graph DB issues → clear ~/.config/amass or use -dir
- Go install fails → use prebuilt binary or Docker
