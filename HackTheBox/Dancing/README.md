# Dancing – Hack The Box (Third Flag)

## Overview

This write-up documents my approach to solving the Dancing machine on Hack The Box. The objective was to enumerate services, identify accessible resources, and capture the user flag through SMB enumeration.

## Initial Connection

I started the Dancing machine and connected to the HTB VPN using OpenVPN. After confirming a successful connection to the target machine, I began the enumeration phase.

## Port Scanning with Nmap

First, I performed a service and version scan:

**nmap -sC -sV 10.129.11.235**

The scan revealed that **SMB (Server Message Block) was running on port 445**

What is SMB?

SMB (Server Message Block) is a network file-sharing protocol primarily used in Windows environments. It allows systems to share files, printers, and other resources over a network.

Since the HTB question was specifically related to SMB, I narrowed the scan to focus only on port 445:

**nmap -sC -sV -p 445 10.129.11.235**

## SMB Enumeration

To list available SMB shares, I used:

**smbclient -L //10.129.11.235**

After identifying accessible shares, I connected to the WorkShares directory anonymously:

**smbclient //10.129.11.235/WorkShares -N**

## Navigating the Share

Inside the share, I navigated through the available directories and found a file named:

flag.txt

The file was located inside the James.P directory.

## Downloading the Flag

To download the file, I used:

**get flag.txt**

After retrieving the file locally, I opened it and successfully captured my third easiest flag on Hack The Box.

## Key Takeaways

- Always begin with service enumeration.
- If a challenge focuses on a specific protocol, narrow your scan for efficiency.
- SMB misconfigurations can allow anonymous access to sensitive files.
- Enumeration is critical in CTF challenges.

## Tools Used

- Kali Linux ( Attacker machine )
- OpenVPN
- Nmap
- SMB
- HackTheBox ( Target machine )

## Proof of Work

https://labs.hackthebox.com/achievement/machine/3080587/395

*** Onward to the next machine.. ***