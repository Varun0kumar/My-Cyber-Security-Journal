# Malicious File/Script Download Attempt – NicolasPRD

## Alert Details

- **Event ID:** 76  
- **Rule:** SOC137 - Malicious File/Script Download Attempt  
- **Source IP:** 172.XX.XX.XX 
- **Hostname:** NicolasPRD  
- **File Name:** INVOICE PACKAGE LINK TO DOWNLOAD.docm  
- **File Hash:** f2d0c66b801244c059f636d08a474079  
- **Action:** Blocked  

---

## Summary

An alert was triggered due to a malicious file download attempt. Investigation focused on validating the file reputation, delivery method, and endpoint activity.

---

## Key Findings

- File hash flagged as malicious (38/66 detections on VirusTotal)  
- Download attempt was blocked by security controls  
- File delivered via phishing email (invoice-themed)  
- Endpoint shows suspicious command-line activity  
- Additional logs show communication with malicious URLs  

---

## Final Verdict

**True Positive – Malicious File Detected (Blocked)**  
**Endpoint shows signs of potential compromise**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  

---