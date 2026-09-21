# httpx

## Repo
https://github.com/projectdiscovery/httpx

## Installation
```bash
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest

# ensure PATH
export PATH=$PATH:$(go env GOPATH)/bin
```

## Using
```bash
# Basic probe
cat subs.txt | httpx -silent -o live.txt

# Status + title + tech
cat subs.txt | httpx -sc -title -tech-detect -o live_rich.txt

# JSON
cat subs.txt | httpx -json -o live.json

# Threads + rate limit
cat subs.txt | httpx -threads 100 -rate-limit 150 -silent
```

## Current Step
Live host probing and basic fingerprinting after subdomain enum.

## Next Step
Feed live hosts into nuclei, katana, or ffuf. Optional screenshots with -screenshot.

## Errors Fixes
- Timeout / connection refused → increase -timeout 15
- Too many open files → ulimit -n 65535
- Rate limited → lower -rate-limit or -threads
- Empty output → verify input hosts, add -status-code for debug
