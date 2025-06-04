---
type: tool
phase:
  - "[[Scanning]]"
  - "[[Enumeration]]"
order: "5"
tags:
  - tools
  - nmap
---
# 📍 Nmap

## Description
Nmap (Network Mapper) is a powerful tool used for port scanning, service identification, OS fingerprinting, and more.

## Common Commands
```bash
# Quick scan
nmap -T4 -F <target>

# Full TCP scan
nmap -sS -T4 -p- <target>

# Detect versions and OS
nmap -sV -O <target>

# Save output
nmap -oA results <target>

# Combination of previous commands
nmap -sS -sV -T4 -p- -oN full_scan.txt <target>
```
## Scripts
```bash
# Get vulnerabilities
nmap --script=vuln <target>

# HTTP enumeration
nmap --script=http-enum -p80 <target>
```

## Tips
- Use `-Pn`if ICMP is blocked.
- Combine with `Masscan` for large networks.

## 🔗Related Phases
- [[Scanning]]
- [[Enumeration]]

## Alternatives
- [[Masscan]]
- [[RustScan]]
