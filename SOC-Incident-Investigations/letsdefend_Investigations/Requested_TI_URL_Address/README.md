# Requested T.I. URL Address – MarksPhone

## Alert Details

- **Event ID:** 75  
- **Rule:** SOC105 - Requested T.I. URL address  
- **Source IP:** 10.XX.XX.XX  
- **Destination IP:** 67.XXX.XXX.XX  
- **Hostname:** MarksPhone  
- **Request URL:** https://bit.ly/TAPSCAN  

---

## Summary

An alert was triggered due to a request to a Threat Intelligence (T.I.) flagged URL. Initial investigation focused on validating whether the URL was accessed and if it resulted in any malicious activity.

---

## Key Findings

- No evidence of access to the flagged URL from the endpoint  
- Proxy logs show request entry but no confirmed malicious interaction  
- No suspicious activity observed on endpoint (MarksPhone)  
- Multiple phishing emails identified for user **mark@letsdefend.io**  
- Several email attachments and URLs flagged as malicious by VirusTotal  

---

## Final Verdict

👉 **False Positive – No confirmed access or impact from T.I. URL**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- ANY.RUN  

---