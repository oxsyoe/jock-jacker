# 💀 JOCK-JACKER

### *The God-Tier Offensive Security Framework*

[![Python](https://img.shields.io/badge/Python-3.8%2B-red)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey)](https://)
[![License](https://img.shields.io/badge/License-Educational%20Use%20Only-red)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Operational-brightgreen)]()
[![Code Size](https://img.shields.io/github/languages/code-size/oxsyoe/jock-jacker)]()
[![Stars](https://img.shields.io/github/stars/oxsyoe/jock-jacker?style=social)](https://github.com/oxsyoe/jock-jacker/stargazers)

---

## ⚡ What is JOCK-JACKER?

**JOCK-JACKER** is an **advanced offensive security framework** that combines every major penetration testing technique into one autonomous, intelligent tool. 

It's designed for:
- 🔴 **Red Team Operations** — Simulate real-world adversaries
- 🦠 **Malware Development Research** — Understand EDR evasion
- 🏰 **Active Directory Security** — Test domain defenses
- 🎯 **Penetration Testing** — Automate post-exploitation
- 🧪 **Security Research** — Study attack techniques

---

## 🔥 Core Capabilities

| Engine | Technique | Impact |
|--------|-----------|--------|
| **🎭 Protocol Poisoning** | LLMNR, NBT-NS, mDNS | Capture hashes from entire network |
| **🔑 Kerberos Attacks** | Kerberoasting, AS-REP Roasting | Extract service account hashes |
| **🎫 Ticket Forgery** | Golden, Silver, Diamond Tickets | Permanent domain access |
| **🔄 NTLM Relay** | SMB Coercion (6 methods) | SYSTEM on any Windows machine |
| **💀 Persistence Matrix** | WMI, Tasks, Registry, ADS | Triple-redundant backdoors |
| **🛡️ EDR Evasion** | Direct syscalls, ETW patching, AMSI bypass | Invisible to CrowdStrike/SentinelOne |
| **📡 Multi-Protocol C2** | DNS, ICMP, HTTP/S, WebSocket | Unblockable command & control |
| **🧠 AI Targeting** | Autonomous target prioritization | Smart lateral movement |
| **🌊 DCSync** | NTDS.dit replication | All domain hashes |
| **📤 Exfiltration** | DNS tunneling, CDN hiding | Undetectable data theft |

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/oxsyoe/jock-jacker.git
cd jock-jacker

# Discover your network
python jock-jacker.py --discover

# Launch full assault (YOUR NETWORK ONLY)
python jock-jacker.py --full

# Start C2 listener
python jock-jacker.py --c2
```

---

## 📋 Command Reference

| Command | Function |
|---------|----------|
| `--discover` | Find all devices, OS, services, DCs |
| `--full` | Automated full-spectrum attack |
| `--persist <file>` | Install multi-method persistence |
| `--exfil <file>` | Steal data via DNS/CDN |
| `--c2` | Start C2 listener (port 4444) |
| `--kerberoast <domain>` | Extract AD service hashes |
| `--relay <targets>` | NTLM relay attack |
| `--config <file>` | Load custom settings |
| `--help` | Show all options |

---

## 🧠 Powered Targeting

JOCK-JACKER automatically:
- **Discovers** every host on your network
- **Fingerprints** OS and running services
- **Identifies** domain controllers (HIGH priority)
- **Prioritizes** targets by attack surface
- **Selects** optimal attack vector per target

```
[*] Prioritized targets:
    1. 192.168.1.10 (DC01) - Priority: 65
    2. 192.168.1.20 (SQL01) - Priority: 52
    3. 192.168.1.30 (WEB01) - Priority: 38
```

---

## 💀 Persistence Matrix

Installs **4 concurrent persistence mechanisms**:

| Method | Trigger | Stealth |
|--------|---------|---------|
| WMI Event Subscription | Every 60 seconds | Very High |
| Scheduled Task | User logon | High |
| Registry Run Key | System boot | Medium |
| NTFS Alternate Data Stream | Hidden execution | Extreme |

**Result:** Your payload runs every minute, survives reboots, and is nearly invisible.

---

## 📡 Multi-Protocol C2

| Protocol | Use Case | Detection Risk |
|----------|----------|----------------|
| TCP | Direct shells | Medium |
| DNS | Firewall evasion | Very Low |
| ICMP | Exfiltration | Low |
| HTTP/S | CDN hiding | Very Low |

---

## 🛡️ EDR Bypass Techniques

- **ETW Patching** — Disables Windows event logging
- **AMSI Bypass** — Evades PowerShell script scanning
- **Direct Syscalls** — Avoids user-mode hooks
- **DLL Sideloading** — Abuses signed binaries
- **Process Hollowing** — Injects into trusted processes

---

## 📂 Output Structure

```
jock-jacker_output_20260115_143022/
│
├── 📁 loot/
│   ├── kerberoast_hashes.txt    # Service account hashes
│   ├── asrep_hashes.txt         # AS-REP hashes
│   ├── domain_hashes.txt        # Full NTDS.dit
│   └── captured_credentials.txt # LLMNR/NTLM hashes
│
├── 📁 payloads/
│   ├── reverse_shell.ps1        # PowerShell payload
│   ├── persistence_install.ps1  # WMI script
│   └── ads_hidden.txt           # Hidden ADS payload
│
├── 📄 attack_timeline.json      # Complete attack log
└── 📄 compromised_hosts.json    # List of owned systems
```

---

## ⚙️ Requirements

| Requirement | Detail |
|-------------|--------|
| **OS** | Windows 10/11 (some modules work on Linux) |
| **Python** | 3.8+ |
| **Privileges** | Administrator (for full functionality) |
| **Disk** | ~50 MB |

### Optional Tools (Enhance functionality):
```powershell
pip install impacket      # NTLM relay, Kerberoast
pip install responder     # LLMNR poisoning
# Download Rubeus.exe     # Advanced Kerberos
# Download Mimikatz.exe   # Ticket forgery
```

---

## ⚠️ Legal & Ethical Use

> **THIS TOOL IS FOR EDUCATIONAL AND AUTHORIZED TESTING ONLY**

- ✅ **Use on:** Your own computers, your own lab, CTF competitions, authorized penetration tests
- ❌ **DO NOT use on:** Any system you don't own, any system without written permission

**Unauthorized use violates:**
- Computer Fraud and Abuse Act (CFAA) — 10+ years federal prison
- GDPR — €20 million fines
- Local computer misuse laws

**YOU are responsible for your actions.**

---

## 📚 How It Works (Technical Deep Dive)

### LLMNR Poisoning
When Windows can't resolve a hostname via DNS, it broadcasts an LLMNR request. JOCK-JACKER responds to these requests, pretending to be the requested host, and captures the victim's NTLM hash.

### Kerberoasting
Any domain user can request service tickets (TGS) for any service account. JOCK-JACKER requests these tickets, extracts the encrypted hash, and cracks them offline.

### Golden Ticket
Using the KRBTGT hash (obtained via DCSync or Kerberoasting), JOCK-JACKER forges a TGT for any user — including Domain Admin. This ticket is trusted by every DC in the domain.

### NTLM Relay
Forces targets to authenticate to us (via PetitPotam, PrintNightmare, etc.), captures the authentication, and relays it to another target — executing commands as SYSTEM.

---

## 🎯 Example Attack Flow

```
1. Run --discover to map network
2. LLMNR poisoning captures initial hash
3. Crack hash → get domain user credentials
4. Kerberoast with credentials → get service account hash
5. DCSync with service account → get KRBTGT hash
6. Forge Golden Ticket → Domain Admin
7. Install persistence on all machines
8. Exfiltrate all data via DNS tunnel
```

**Time to Domain Admin:** ~5-15 minutes

---

## 🏆 Why "JOCK-JACKER"?

*"They laughed. Then they got pwned."*

---

## 📄 License

**Educational Use Only** — Not for malicious purposes.

---

## ⭐ Star History

If this tool helped you understand offensive security, drop a star ⭐

---

## 🔗 Related Resources

- [MITRE ATT&CK Framework](https://attack.mitre.org/)
- [Active Directory Exploitation Cheat Sheet](https://github.com/S1ckB0y1337/Active-Directory-Exploitation-Cheat-Sheet)
- [Impacket Documentation](https://github.com/SecureAuthCorp/impacket)
- [Mimikatz](https://github.com/gentilkiwi/mimikatz)

---

**Made with OXSYOE for the security community**

*Know the attack to build the defense.*
