# gau

## Repo
https://github.com/lc/gau

## Installation
```bash
go install github.com/lc/gau/v2/cmd/gau@latest
```

## Using
```bash
# Single domain
gau target.com > urls.txt

# From list
cat domains.txt | gau > all_urls.txt

# Specific providers
gau target.com --providers wayback,otx,commoncrawl

# JSON
gau target.com --json > urls.json
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| Single domain | 10 – 90 s | archive size dependent |
| 10 domains | 2 – 15 min | |
| Large historical target | 5 – 30 min | wayback heavy |

Mostly network-bound to archive providers. No direct target traffic.

## Current Step
Historical URL collection from archives (Wayback, OTX, Common Crawl, etc.).

## Next Step
Filter interesting extensions / parameters, feed into nuclei or ffuf, hunt for leaked endpoints.

## Errors Fixes
- Empty results → try alternate providers or check domain history
- Rate issues → --threads 5
- PATH → export PATH=$PATH:$(go env GOPATH)/bin
