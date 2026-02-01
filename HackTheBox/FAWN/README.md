# HTB Machine: Meow

## Introduction

I started my second CTF on Hack The Box, which is **FAWN**.  
I downloaded the OpenVPN file and connected to the lab network using the command:

**sudo openvpn "starting_points_us-starting-point-1-dhcp (1).ovpn"**
The connection was successful.

I verified the connection using the **ping** command, which confirmed that the target machine was up. Then I ran an Nmap scan using the **-sV** option to identify the running services.
From the scan results, I found that the FTP service was running on the target system with version vsftpd 3.0.3. Using the **-O** option, I identified that the target was running a Linux/Unix operating system.

To understand FTP commands, I used: **ftp -?**
This command displays the FTP client help menu. By referring to the help output, I initially tried connecting anonymously using the **ftp -a** option. After several attempts, I was unable to establish a proper connection. Since I was not familiar with FTP connections at that point, I referred to the official walkthrough for guidance.

I then successfully connected to the FTP service using:**ftp 10.129.126.232**
After entering the username and password as mentioned in the walkthrough, I gained access to the FTP server. Inside the FTP session, I used the help command to explore available FTP commands.

I used the following command to download the flag: **get flag.txt**
This downloaded the flag.txt file to my local machine. After exiting the FTP session, I was able to read the file and capture my second flag. This room was simple, but as a beginner, it helped me understand basic service enumeration and FTP interaction, which kept me motivated toward offensive security learning.

ftp> bye
221 Goodbye.