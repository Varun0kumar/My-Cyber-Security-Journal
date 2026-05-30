# SQL Injection Attack Investigation

## Alert Details

- **Event ID:** 235
- **Rule:** SOC127 - SQL Injection Detected
- **Source IP:** 118.**.**.**
- **Destination IP:** 172.**.**.**
- **Hostname:** WebServer1000
- **Method:** GET
- **Device Action:** Allowed

---

## Summary

A SQL Injection attack was detected targeting a web application hosted on WebServer1000. The malicious request contained database enumeration techniques, UNION-based SQL Injection payloads, and an attempt to execute operating system commands through xp_cmdshell.

Threat intelligence analysis confirmed that the source IP address has a malicious reputation. The request was allowed by the web application and returned an HTTP 200 response, requiring further investigation to determine the extent of any impact.

---

## Key Findings

- SQL Injection payload detected in HTTP request
- Database enumeration activity observed
- Attempted operating system command execution via xp_cmdshell
- Request successfully reached the target application
- Source IP flagged as malicious by multiple security vendors
- Traffic originated from an external source

---

## Analysis

Observed payload components included:

```sql
UNION ALL SELECT
```

```sql
FROM information_schema.tables
```

```sql
EXEC xp_cmdshell(...)
```

These techniques are commonly used by attackers to:

- Enumerate database structures
- Extract sensitive information
- Execute commands on the underlying server
- Attempt privilege escalation

The combination of these indicators strongly suggests malicious SQL Injection activity.

---

## Final Verdict

**True Positive – SQL Injection Attack Detected**

**Attack Status: Potentially Successful – Further Investigation Required**

---

## Tools Used

- LetsDefend SIEM
- VirusTotal

---

## Recommendations

- Investigate WebServer1000 for signs of compromise
- Review web application and database logs
- Block or monitor the source IP address
- Implement parameterized queries and input validation
- Enable or review WAF protections
- Conduct vulnerability assessment of the affected application
- Monitor for additional SQL Injection attempts