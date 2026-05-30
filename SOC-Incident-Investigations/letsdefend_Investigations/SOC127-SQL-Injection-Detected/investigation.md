# Investigation Process – SQL Injection Alert

## 1. Initial Triage

Reviewed alert details and analyzed the requested URL.

The request contained multiple SQL Injection indicators including:

- UNION SELECT statements
- information_schema table enumeration
- SQL comments (`--`)
- xp_cmdshell command execution attempt
- Directory traversal references to `/etc/passwd`

These patterns are commonly associated with SQL Injection attacks and post-exploitation activity.

---

## 2. Threat Intelligence

Checked source IP address (118.194.247.28) using VirusTotal.

Findings:

- 10 security vendors flagged the IP address as malicious
- Reputation data indicates previous malicious activity

Conclusion: Source IP has a malicious reputation and increases confidence in the alert.

---

## 3. Traffic Analysis

Observed request details:

- Source IP: 118.194.247.28
- Destination Host: WebServer1000
- Destination IP: 172.16.20.12
- Direction: Internet to Internal Network
- Device Action: Allowed

The request successfully reached the target application.

---

## 4. Payload Analysis

Decoded payload elements revealed:

- Database enumeration attempts
- UNION-based SQL Injection techniques
- Extraction of database table information
- Attempted execution of operating system commands using xp_cmdshell
- Access attempt to sensitive system files

The payload demonstrates a deliberate attempt to identify database structures and potentially gain access to underlying operating system resources.

---

## 5. Analysis Conclusion

- Malicious SQL Injection payload detected
- External attacker targeted internal web server
- Request successfully processed by the application
- Source IP identified as malicious
- Attack was not part of a planned test
- Further investigation required to determine impact

---

## Learning Notes

- UNION SELECT statements are common indicators of SQL Injection attacks.
- information_schema enumeration is frequently used to discover database structures.
- xp_cmdshell can be abused to execute operating system commands through SQL Server.
- HTTP 200 responses may indicate successful processing of malicious requests.
- SQL Injection attacks can lead to unauthorized data access, system compromise, and remote command execution.