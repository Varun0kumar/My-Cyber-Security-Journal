# HTB Machine: Meow

## Introduction

Meow is a beginner-level machine on Hack The Box. I worked on this machine to get hands-on exposure to the basic workflow of enumeration and understanding exposed services.

This challenge helped me move from theory to practical learning.

## Enumeration

After connecting to the Hack The Box network using OpenVPN, I verified connectivity and started with enumeration.
I used **Nmap** to scan the target and identify open ports and running services.  
During this phase, I noticed that **Telnet (Port 23)** was open on the target system.

This reinforced the importance of enumeration before attempting any access.

## Accessing the System

Since Telnet was exposed, I attempted to interact with the service to understand its behavior.
I tried a few common identities and, after referring to the official walkthrough to understand the correct approach, I was able to gain access to the system as the root user.

## Capturing the Flag

Once inside the system, I explored the file structure and located the `flag.txt` file, successfully capturing my first flag.
This was a simple step technically, but an important milestone for me as a beginner.
 

## Key Learnings

- Risks of insecure or misconfigured services
- Basic use of Nmap for service identification
- Initial interaction with a Linux system after access
- Working with OpenVPN

## Tools Used

- Kali Linux ( Attacker machine )
- OpenVPN
- Nmap
- Telnet
- HackTheBox ( Target machine )

## Proof of Work

(https://labs.hackthebox.com/achievement/machine/3080587/394)

## 📈 Final Thoughts
This machine may be simple, but it gave me confidence and practical exposure to the basic attack methodology. I plan to continue practicing and improving my skills step by step.

Onward to the next machine..
