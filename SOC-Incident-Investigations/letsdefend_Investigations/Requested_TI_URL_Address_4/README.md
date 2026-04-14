# Requested T.I. URL Address – BillPRD (Case 4)

## Alert Details

- **Event ID:** 16  
- **Rule:** SOC105 - Requested T.I. URL address  
- **Source IP:** 172.XX.XX.XX  
- **Hostname:** BillPRD  
- **Destination IP:** 5.188.0.251  
- **Destination Hostname:** pssd-ltdgroup.com  
- **Request URL:** https://pssd-ltdgroup.com  
- **Action:** Allowed  

---

## Summary

An alert was triggered due to access to a Threat Intelligence (T.I.) flagged URL. Investigation focused on validating the URL reputation, confirming access via logs, and identifying the originating process on the endpoint.

---

## Key Findings

- Domain and URL flagged as malicious (14+ detections on VirusTotal)  
- Proxy and firewall logs confirm successful access  
- Request originated from macro-enabled file execution  
- Suspicious file identified on endpoint (high detection rate)  

---

## Final Verdict

**True Positive – Malicious URL Access with Endpoint Correlation**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  

---