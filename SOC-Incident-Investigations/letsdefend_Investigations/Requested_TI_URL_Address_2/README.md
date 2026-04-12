# Requested T.I. URL Address – BillPRD (Case 2)

## Alert Details

- **Event ID:** 28  
- **Rule:** SOC105 - Requested T.I. URL address  
- **Source IP:** 172.16.17.47  
- **Hostname:** BillPRD  
- **Destination IP:** 115.99.150.132  
- **Request URL:** http://115.99.150.132:56841/Mozi.m  
- **Action:** Blocked  

---

## Summary

An alert was triggered due to a request to a Threat Intelligence (T.I.) flagged URL. Investigation included threat intelligence validation, log analysis, and endpoint correlation.

---

## Key Findings

- URL and destination IP identified as malicious  
- Suspicious file detected on endpoint (high detection rate)  
- Associated macro-enabled file execution observed  
- Historical communication with malicious domains identified  
- Request to malicious infrastructure was blocked  

---

## Final Verdict

**Real SOC Verdict:** True Positive – Malicious activity detected (blocked C2 attempt)  
**LetsDefend Verdict:** False Positive – No confirmed interaction with T.I. URL  

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  

---