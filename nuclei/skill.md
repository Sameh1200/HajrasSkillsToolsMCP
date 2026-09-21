# nuclei

## Repo
https://github.com/projectdiscovery/nuclei  
Templates: https://github.com/projectdiscovery/nuclei-templates

## Installation
```bash
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest

# Update templates
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

## Current Step
Template-based vulnerability scanning on live hosts.

## Next Step
Validate high/critical findings manually in Burp. Chain with ffuf or sqlmap on interesting parameters.

## Errors Fixes
- Templates missing → run nuclei -update-templates
- Rate limited / WAF → lower -rl 20 -c 10
- False positives → restrict -severity medium,high,critical and verify manually
- Go version too old → install recent Go (1.21+)
