# Proxy - Malicious Executable File Detected (False Positive)

## Alert Overview

- Event ID: 83  
- Rule: SOC119 - Proxy - Malicious Executable File Detected  
- Source IP: 172.XX.XX.X  
- Hostname: SusieHost  
- Destination IP: 51.195.68.163  
- Destination Hostname: win-rar.com  
- Username: Susie  
- Request URL: https://www.win-rar.com/postdownload.html?&L=0&Version=32bit  
- User Agent: Chrome - Windows  
- Device Action: Allowed  

---

## Summary

An alert was triggered for a potential malicious executable file download via proxy logs. Investigation determined that the request was made to the official WinRAR website and corresponds to legitimate software download activity.

No malicious indicators were identified during analysis.

---

## Key Findings

- URL belongs to official WinRAR website  
- No detection on VirusTotal or Any.run  
- Destination IP is clean  
- Valid user agent observed  
- No endpoint activity or execution evidence  
- Normal HTTP GET request  

---

## Impact Assessment

- No evidence of compromise  
- No malicious activity observed  
- Legitimate user-initiated download  

---

## Final Verdict

False Positive – Legitimate Download Activity

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- Any.run  
- APIvoid  

---

## Recommendations

- No action required  
- Continue monitoring for similar alerts  

---