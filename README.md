# SERVICE-SCAN

# Port Scanning Assignment — Local Network Reconnaissance

**Student:** Talha qureshi
**Date:** 2025-09-22

## Summary
Scanned local network and target host 192,168.240.1 open ports and services. Captured network traffic for proof-of-concept and analyzed common risks & mitigations.

## Commands run
- `nmap -sS 192.168.1.0/24 -oN nmap_scan_basic.txt`
- `nmap -sS -sV -sC -O -Pn -p 135,139,443,445,808,903,8080,8090,60443 192,168.240.1 -oA nmap_report`

## Findings
- Open ports: 135 (msrpc), 139 (netbios-ssn), 443 (https), 445 (microsoft-ds), 808 (ccproxy-http), 903 (iss-console-mgr), 8080 (http-proxy), 8090 (opsmessaging), 60443 (unknown).
- Detailed outputs: `nmap_services.txt`.
- Captures: `nmao poc`.
- Screenshots: `wireshark_screenshot_http.png`

## Remediation recommendations
1. Patch Windows services and SMB.
2. Block 139/445/135 from untrusted networks.
3. Restrict admin interfaces to VPN or admin subnet.
4. Harden TLS configurations on 443/60443.
5. Remove/disable unused services.

## Files included
- `nmap_scan_basic.txt`, `nmap_services.txt`, `wireshark_screenshot_http.png`

