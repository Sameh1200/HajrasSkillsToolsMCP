# nikto

## Repo
https://github.com/sullo/nikto

## Installation
```bash
sudo apt install nikto

# From source
git clone https://github.com/sullo/nikto
cd nikto/program
```

## Using
```bash
# Basic scan
nikto -h https://target.com

# Force SSL
nikto -h https://target.com -ssl

# Output file
nikto -h https://target.com -output nikto.txt

# Tuning (faster / focused)
nikto -h https://target.com -Tuning 123bde
```

## Current Step
Quick web server misconfiguration and known vulnerability checks.

## Next Step
Validate findings with nuclei or manual review. Do not treat nikto as complete coverage for modern apps.

## Errors Fixes
- SSL problems → -ssl or -nossl
- Timeout → -timeout 10
- Sparse results → target may be modern or behind WAF
- Perl issues → usually resolved by package manager install
