# netbios-hardening-report
Hardening Windows Port 139 (NetBIOS) using Nmap
# 🔐 NetBIOS Port 139 Hardening Report

**Author**: Chidiebere Aneke  
**Date**: July 7, 2025  
**System**: Windows 10  
**Tool Used**: Nmap 7.97

---

## 🧠 Objective

To improve system security by disabling NetBIOS over TCP/IP and verifying that Port 139 is no longer exposed to the network.

---

## 🔍 Initial Finding

A full TCP SYN scan showed Port 139 (`netbios-ssn`) in the open state:

```
nmap -sS -sV -Pn 172.20.10.12
```
Result

139/tcp open netbios-ssn

🛠️ Action Taken
Opened ncpa.cpl (Network Connections)

Adapter properties → Internet Protocol Version 4 (TCP/IPv4)

Advanced → WINS tab

Set to “Disable NetBIOS over TCP/IP”

Applied changes and restarted the PC

🔁 Verification Scan

nmap -Pn -p 139 172.20.10.12

Result

139/tcp closed netbios-ssn

🛡️ Security Impact

| Benefit                        | Description                               |
| ------------------------------ | ----------------------------------------- |
| ✅ Reduced Attack Surface       | Removed legacy file-sharing service       |
| ✅ Blocked NetBIOS Enumeration  | Prevented access to host shares & info    |
| ✅ Hardened Windows Workstation | Safer in both public and private networks |

## 📷 Screenshots

**After NetBIOS was disabled (Port 139 closed):**

![after-scan](https://github.com/user-attachments/assets/6202c5cf-2b77-4070-902f-2efc390521bc)

📚 Keywords
NetBIOS Port 139 Windows Security Nmap Network Hardening Cybersecurity Portfolio

✅ Status
Secured and Verified


