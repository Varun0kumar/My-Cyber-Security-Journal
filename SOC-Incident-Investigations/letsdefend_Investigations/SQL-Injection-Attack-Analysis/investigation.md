# Investigation Process – SQL Injection Alert

## 1. Initial Triage

Reviewed alert details and identified suspicious URL containing encoded SQL payload.

%22%20OR%201%20%3D%201%20--%20-

---

## 2. Payload Analysis

Used CyberChef to decode the payload:  " OR 1 = 1 -- -

Identified this as a classic SQL injection technique used to bypass conditions.

---

## 3. Threat Intelligence Check

Checked source IP (167.99.169.17) on VirusTotal:

- 3/94 vendors flagged as malicious  
- Identified as cloud-hosted infrastructure (DigitalOcean)

---

## 4. Endpoint Analysis

Investigated processes:

- OfficeClickToRun.exe identified  
- Verified hash on VirusTotal → legitimate  
- No malicious execution found  

Conclusion: No endpoint compromise

---

## 5. Log Correlation

Searched logs using source IP:

Found multiple suspicious requests:

- `' OR '1'='1`
- `' OR 'x'='x`
- `ORDER BY` payloads  

HTTP Response: 500 Internal Server Error

Indicates backend query errors → possible injection testing

---

## 6. Analysis Conclusion

- Attack originated externally  
- Multiple SQL injection attempts observed  
- No successful exploitation evidence  
- No data exfiltration detected  

---

##  Learning Notes

- HTTP 200 ≠ attack success  
- HTTP 500 often indicates SQL errors → useful indicator  
- Payload variations show attacker testing database structure  

---