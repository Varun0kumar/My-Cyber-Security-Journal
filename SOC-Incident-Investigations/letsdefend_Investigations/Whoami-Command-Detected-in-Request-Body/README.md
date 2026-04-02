# Command Injection (RCE) Investigation – WebServer1004

## Alert Details

- **Event ID:** 118  
- **Rule:** SOC168 - Whoami Command Detected  
- **Source IP:** 61.XXX.XXX.XX 
- **Destination:** 172.XX.XX.XX  
- **Hostname:** WebServer1004  

---

## Summary

A command injection attack was identified targeting the `/video/` endpoint. The attacker successfully executed system-level commands via HTTP POST parameters.

---

## Key Findings

- Multiple commands executed: `ls`, `whoami`, `uname`, `cat`
- Commands executed with **root privileges**
- Access to sensitive files (`/etc/passwd`, `/etc/shadow`)
- External attacker IP flagged as suspicious
- Host successfully contained

---

## Final Verdict

  **True Positive – Command Injection (Successful RCE)**

---

## Impact

- Full system compromise  
- Sensitive data exposure  
- High risk of lateral movement  

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  

---