# nuclei

## Repo
https://github.com/projectdiscovery/nuclei  
Templates: https://github.com/projectdiscovery/nuclei-templates

## Installation
```bash
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
nuclei -update-templates
```

## Using
```bash
# Basic scan
nuclei -l live.txt -o findings.txt

# Severity filter
nuclei -l live.txt -severity critical,high -o critical.txt

# Template directories
nuclei -l live.txt -t cves/ -t exposures/ -o hits.txt

# Rate limited
nuclei -l live.txt -rl 50 -c 25 -o results.txt

# JSONL output
nuclei -l live.txt -jsonl -o results.jsonl
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| 50 live hosts, critical+high | 2 – 10 min | -rl 50 recommended |
| 200 hosts, full templates | 20 – 90 min | heavy; use severity filter |
| 1 000 hosts, cves/ only | 15 – 60 min | -t cves/ -rl 30-50 |
| Single host deep | 30 s – 5 min | depends on template set |

Default global rate is ~150 req/s. For bug bounty lower to -rl 30-50 to stay polite and avoid WAF bans. Always update templates before important runs.

## Current Step
Template-based vulnerability scanning on live hosts.

## Next Step
Validate high/critical findings manually in Burp. Chain with ffuf or sqlmap on interesting parameters.

## Errors Fixes
- Templates missing → run nuclei -update-templates
- Rate limited / WAF → lower -rl 20 -c 10
- False positives → restrict -severity medium,high,critical and verify manually
- Go version too old → install recent Go (1.21+)
