# katana

## Repo
https://github.com/projectdiscovery/katana

## Installation
```bash
go install github.com/projectdiscovery/katana/cmd/katana@latest
```

## Using
```bash
# Single target
katana -u https://target.com -o urls.txt

# From list
katana -list live.txt -o crawled.txt

# JS + depth
katana -u https://target.com -jc -d 3 -o deep.txt

# Silent + known files
katana -u https://target.com -silent -known-files all
```

## Current Step
Endpoint and URL discovery via crawling (including JavaScript).

## Next Step
Extract parameters, feed unique URLs into nuclei or ffuf, analyze JS for secrets / endpoints.

## Errors Fixes
- Slow → lower -c concurrency, raise -timeout
- Missing JS links → enable -jc
- Rate limited → -rate-limit 50
- Binary not found → export PATH=$PATH:$(go env GOPATH)/bin
