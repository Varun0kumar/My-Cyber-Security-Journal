## Alert Details

- **Event ID:** 115  
- **Rule:** SOC165 - Possible SQL Injection Payload Detected    
- **Source IP:** 167.**.***.**  
- **Destination IP:** 172.**.**.**  
- **Hostname:** WebServer1001  
- **Method:** GET  
- **Device Action:** Allowed  

---

## Summary

A potential SQL Injection attempt was detected targeting a web application search endpoint. The payload included classic SQL injection patterns such as `" OR 1 = 1 --`.

Threat intelligence and log analysis confirm that the activity originated from an external source. Although multiple injection attempts were observed, there is no evidence of successful exploitation.

---

## 🔍 Key Findings

- SQL Injection payload detected in URL parameters  
- Multiple crafted payload variations observed  
- HTTP 500 responses indicate backend query errors  
- Source IP flagged as suspicious (VirusTotal)  
- No malicious activity observed on endpoint  

---

## Analysis

Decoded payload:  " OR 1 = 1 -- -

This payload attempts to bypass application logic by forcing a true condition.

Multiple requests with variations such as:

- `' OR '1'='1`
- `' OR 'x'='x`
- `1' ORDER BY 3--+`

indicate automated or manual testing for SQL injection vulnerabilities.

---

## Threat Intelligence

- **IP:** 167.**.***.**  
- **Reputation:** 3/94 flagged (VirusTotal)  
- **ASN:** DigitalOcean (Cloud Hosting Provider)  

---

## Evidence Summary

- Multiple SQL injection payloads observed in web logs  
- HTTP 500 responses indicate backend query errors  
- Source IP identified as external and flagged by threat intelligence  
- No successful execution or data exposure detected  

## Note

All evidence is summarized to avoid exposing raw logs or sensitive data. This follows standard security best practices for public reporting.

---

## Final Verdict

**True Positive – SQL Injection Attempt Detected**  
**Attack Status: Not Successful**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- CyberChef  

---

## Recommendations

- Implement input validation and sanitization  
- Use parameterized queries / prepared statements  
- Enable WAF rules for SQL injection protection  
- Monitor repeated requests from suspicious IPs  
