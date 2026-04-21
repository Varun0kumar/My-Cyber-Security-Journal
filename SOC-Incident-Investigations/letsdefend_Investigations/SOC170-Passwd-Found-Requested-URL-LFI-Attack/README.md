# Passwd Found in Requested URL – Possible LFI Attack (True Positive)

## Alert Overview

- Event ID: 120  
- Rule: SOC170 - Passwd Found in Requested URL - Possible LFI Attack  
- Source IP: 106.55.45.162  
- Destination IP: 172.XX.XX.XX (WebServer1006)  
- Request Method: GET  
- Requested URL: https://172.16.17.13/?file=../../../../etc/passwd  
- Device Action: Allowed  

---

## Summary

An alert was triggered due to a request containing a directory traversal payload targeting `/etc/passwd`, indicating a Local File Inclusion (LFI) attack attempt. The request was allowed but resulted in an unsuccessful execution.

---

## Key Findings

- LFI payload detected: `../../../../etc/passwd`  
- External attacker attempted access  
- HTTP Response Status: 500 (Internal Server Error)  
- Response Size: 0 (no data returned)  

---

## Impact

- No sensitive data exposure  
- No successful exploitation  
- Malicious intent confirmed  

---

## Investigation Flow

LFI Attempt → Directory Traversal → Server Processing → Failed Execution  

---

## Final Verdict

True Positive – Unsuccessful LFI Attack Attempt  

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  

---
