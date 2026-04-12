# Investigation Process – Requested T.I. URL Address

## 1. Initial Triage

Alert triggered for a request to a Threat Intelligence flagged URL: https://bit.ly/TAPSCAN

---

## 2. Log Analysis

Proxy logs reviewed for source IP **10.XX.XX.XX**:

- Request observed to destination IP **67.XXX.XXX.XX** over port **443**
- No further suspicious or repeated communication detected
- No abnormal traffic patterns observed

---

## 3. Endpoint Analysis

- Endpoint: **MarksPhone (10.XX.XX.XX)**
- No suspicious processes or activity identified
- No indicators of compromise (IOC) found

---

## 4. Email Analysis

- Multiple emails received by **mark@letsdefend.io**
- Several attachments and URLs flagged as malicious
- Common themes include phishing and social engineering

Examples:
- Malicious ZIP attachments flagged by VirusTotal  
- Suspicious domains such as `nuangaybantiep.xyz`  
- Phishing-themed emails (COVID-19, credit card, etc.)

---

## 5. Analysis

- No evidence that the user accessed or executed any malicious content  
- No correlation between alert and email-based threats  
- Alert likely triggered due to passive or non-impactful request  

---

## 6. Conclusion

- No successful exploitation or compromise observed  
- Alert classified as False Positive  

---

## Learning Notes

- Not all flagged URLs indicate active compromise  
- Correlation between logs, endpoint, and email is critical  
- Always verify user interaction before concluding impact  

---