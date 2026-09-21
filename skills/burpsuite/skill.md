# burpsuite

## Repo
https://portswigger.net/burp  
Community edition available free from PortSwigger.

## Installation
```bash
# Download Community or Pro from portswigger.net
java -jar burpsuite_community.jar

# Kali often ships with it or via apt
```

## Using
```bash
# Start Burp → set browser proxy to 127.0.0.1:8080
# Install CA certificate from http://burpsuite

# Core workflow:
# - Proxy: intercept + history
# - Repeater: manual request editing
# - Intruder: controlled fuzzing
# - Scanner (Pro): active scanning
# - Collaborator: out-of-band detection
```

## Real-time usage (typical)
| Activity | Duration | Notes |
|----------|----------|-------|
| Manual proxy session | ongoing | hours of interactive work |
| Intruder small payload | 1 – 15 min | rate limited by target |
| Pro active scan (single app) | 15 min – hours | scope dependent |
| Collaborator OOB wait | minutes – hours | async |

Primary tool for validation and deep manual testing after automated recon.

## Current Step
Manual traffic interception, request manipulation, and validation of automated findings.

## Next Step
Use Repeater / Intruder on interesting requests from httpx / nuclei / ffuf. Confirm impact and write the report.

## Errors Fixes
- Certificate warnings → install Burp CA in browser and system trust store
- Java version → use a supported JDK
- Low memory → increase -Xmx in the launch command
- Community limits → Pro required for full scanner and some extensions
