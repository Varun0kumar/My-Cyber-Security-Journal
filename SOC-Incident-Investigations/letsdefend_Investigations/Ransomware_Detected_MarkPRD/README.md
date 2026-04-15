# Ransomware Detection – MarkPRD

## Alert Overview

- Event ID: 92  
- Rule: SOC145 - Ransomware Detected  
- Severity: High  
- Source IP: 172.XX.XX.XX  
- Hostname: MarkPRD  
- File Name: ab.exe  
- File Hash (MD5): 0b486fe0503524cfe4726a4022fa6a68  
- File Size: 775.50 KB  
- Device Action: Allowed  

---

## Summary

An alert was generated indicating ransomware activity on the endpoint MarkPRD. Investigation revealed that a malicious executable (ab.exe), associated with the Avaddon ransomware family, was successfully executed on the system.

Threat intelligence analysis confirmed the file as highly malicious. Endpoint telemetry validated execution, indicating a likely compromise and risk of data encryption.

---

## Key Findings

- File identified as ransomware (Avaddon family)  
- High detection rate (60/72 vendors) on VirusTotal  
- Malicious file execution confirmed on the endpoint  
- Suspicious activity observed in endpoint logs  
- Device action was Allowed, increasing risk of impact  

---

## Impact Assessment

- Potential file encryption and data loss  
- Possible persistence or lateral movement  
- Endpoint likely compromised  

---

## Final Verdict

**True Positive** – Ransomware Execution Confirmed

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- AnyRun
---

## Recommendations

- Immediately isolate the affected endpoint  
- Initiate incident response procedures  
- Perform full forensic analysis  
- Investigate for lateral movement and persistence  

---