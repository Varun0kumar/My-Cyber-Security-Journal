# Malicious Attachment Detected – Phishing Alert (True Positive)

## Alert Overview

- Event ID: 45  
- Rule: SOC114 - Malicious Attachment Detected - Phishing Alert  
- Source Email: accounting@cmail.carleton.ca  
- Destination Email: richard@letsdefend.io  
- Subject: Invoice  
- SMTP Address: 49.234.43.39  
- Device Action: Allowed  

---

## Summary

A phishing email containing a malicious attachment was delivered to the user. Analysis confirmed that the attachment is a trojan malware. Further investigation identified malicious network activity, C2 communication, and execution of a privilege escalation tool, indicating endpoint compromise.

---

## Key Findings

- Malicious attachment (MD5: c9ad9506bcccfaa987ff9fc11b91698d)  
- Trojan malware detected (36/63 vendors)  
- Malicious URL contacted:
  http://andaluciabeach.net/image/network.exe  
- C2 server identified:
  70.38.21.234  
- Malicious process executed:
  JuicyPotato.exe  

---

## Impact

- Malware execution confirmed  
- C2 communication observed  
- Endpoint compromise likely  

---

## Final Verdict

True Positive – Phishing Email Leading to Malware Execution and C2 Communication

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- Hybrid Analysis  
- Any.run  

---