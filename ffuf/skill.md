# ffuf

## Repo
https://github.com/ffuf/ffuf

## Installation
```bash
go install github.com/ffuf/ffuf/v2@latest

# Binary from releases
# macOS: brew install ffuf
```

## Using
```bash
# Directory fuzz
ffuf -u https://target.com/FUZZ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -mc 200,301,302,403 -fc 404

# Vhost discovery
ffuf -u https://target.com -H "Host: FUZZ.target.com" -w subdomains.txt -fs 0

# Parameter fuzz
ffuf -u https://target.com/api?FUZZ=test -w params.txt -mc 200

# POST data
ffuf -u https://target.com/login -X POST -d "user=FUZZ&pass=test" -w users.txt -mc 200
```

## Current Step
Content discovery and parameter / vhost fuzzing on live targets.

## Next Step
Feed interesting paths into nuclei or Burp. Test discovered parameters with sqlmap or manual review.

## Errors Fixes
- Noise from 404s → use -fc 404 -fs <size>
- Rate limited → -rate 50 -t 20
- High memory → lower -t, use smaller wordlist
- Calibration needed → add -ac
