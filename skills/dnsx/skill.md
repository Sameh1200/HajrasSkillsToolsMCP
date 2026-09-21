# dnsx

## Repo
https://github.com/projectdiscovery/dnsx

## Installation
```bash
go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
```

## Using
```bash
# Resolve
cat subs.txt | dnsx -silent -o resolved.txt

# Records
cat subs.txt | dnsx -a -aaaa -cname -resp -o dns.txt

# Wildcard detection
cat subs.txt | dnsx -wd target.com

# JSON
cat subs.txt | dnsx -json -o dns.json
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| 1 000 subdomains | 10 – 60 s | very fast |
| 10 000 subdomains | 1 – 5 min | use good resolvers |
| With -resp + multiple types | +20-40% | richer data |

Almost always sub-minute for typical bug-bounty lists when resolvers are healthy.

## Current Step
DNS resolution and record enrichment after subdomain enumeration.

## Next Step
Pass resolved hosts to httpx or naabu / nmap.

## Errors Fixes
- No resolvers → -r 8.8.8.8,1.1.1.1 or custom resolvers file
- Rate issues → -rate-limit 100
- Empty output → check input format, try -retry 3
