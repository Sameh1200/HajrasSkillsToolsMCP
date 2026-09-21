# dirsearch

## Repo
https://github.com/maurosoria/dirsearch

## Installation
```bash
git clone https://github.com/maurosoria/dirsearch.git
cd dirsearch
pip3 install -r requirements.txt
# run: python3 dirsearch.py
```

## Using
```bash
# Basic
python3 dirsearch.py -u https://target.com -e php,html,js

# Custom wordlist
python3 dirsearch.py -u https://target.com -w /usr/share/seclists/Discovery/Web-Content/common.txt

# Recursive + all extensions
python3 dirsearch.py -u https://target.com -e * -r

# Output
python3 dirsearch.py -u https://target.com -o results.txt
```

## Real-time usage (typical)
| Scope | Duration | Notes |
|-------|----------|-------|
| Common wordlist | 1 – 5 min | |
| Medium list + extensions | 5 – 20 min | |
| Recursive deep | 20 min – hours | use carefully |
| Multiple hosts | multiply | sequential by default |

Slower than ffuf for pure speed; useful when you want built-in recursion and extension handling.

## Current Step
Directory and file brute-forcing on web targets.

## Next Step
Review found paths, test for sensitive files, feed into Burp or nuclei.

## Errors Fixes
- Slow → lower threads -t 20
- Status noise → --exclude-status 403,404
- Missing deps → pip3 install -r requirements.txt
- Wordlist missing → install seclists package
