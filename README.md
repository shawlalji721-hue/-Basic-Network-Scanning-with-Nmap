# Nmap Scan Analysis

## Overview
This project contains the results of an Nmap scan performed on a Windows-based target machine in a local network environment. The scan was used to identify open ports, running services, and basic system information.

---

## Scan Command Used

```bash
nmap -A 192.168.188.143
```

- `-A` enables:
  - OS Detection
  - Version Detection
  - Script Scanning
  - Traceroute

---

## Scan Results

| Port | State | Service | Description |
|------|------|------|------|
| 135/tcp | Open | msrpc | Microsoft Remote Procedure Call |
| 139/tcp | Open | netbios-ssn | NetBIOS Session Service |
| 445/tcp | Open | microsoft-ds | SMB File Sharing Service |
| 5357/tcp | Open | http | Microsoft HTTPAPI Service |
| 49152-49157/tcp | Open | msrpc | Dynamic RPC Ports |

---
<img width="1653" height="878" alt="Screenshot_2026-05-14_08_21_46" src="https://github.com/user-attachments/assets/d72360ca-0aee-4bc8-b572-0033782b05a9" />


## Detailed Explanation

### Port 135 - MSRPC
Used for communication between Windows applications and network services.

### Port 139 - NetBIOS
Supports file and printer sharing over local networks.

### Port 445 - SMB
Used for Windows file sharing and remote access services.

### Port 5357 - HTTPAPI
Used by Microsoft devices for network service discovery.

### Dynamic RPC Ports (49152-49157)
Windows uses these high ports for internal RPC communication.

---

## System Information

- **Operating System:** Microsoft Windows
- **Hostname:** HALK-PC
- **Workgroup:** WORKGROUP
- **Virtualization:** VMware Virtual Machine

---

## Security Observations

- SMB service is enabled on port 445.
- Multiple RPC ports are exposed.
- NetBIOS is active on the network.
- The system appears to be running in a virtualized environment.

---

## Recommendations

1. Disable unused services.
2. Restrict SMB access using firewall rules.
3. Keep the system updated.
4. Avoid exposing RPC services publicly.
5. Use strong authentication methods.

---

## Files Included

- `nmap_scan_result.txt` → Raw Nmap scan output
- `README.md` → Scan explanation and analysis
---

## Tools Used

- Nmap

Official Website: https://nmap.org

---

## Disclaimer

This project was created for educational and cybersecurity learning purposes only.
Do not scan systems without proper authorization.
