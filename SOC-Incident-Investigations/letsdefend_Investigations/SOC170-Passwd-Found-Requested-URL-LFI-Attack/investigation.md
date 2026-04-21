# Investigation Report – Possible LFI Attack (SOC170)

## 1. Initial Triage

- Source IP: 106.55.45.162 (External)  
- Destination: 172.XX.XX.XX (WebServer1006)  
- URL: https://172.16.17.13/?file=../../../../etc/passwd  

The alert was triggered due to a suspicious URL containing `/etc/passwd`, indicating a possible LFI attempt.

---

## 2. Threat Analysis

- Payload detected:
  ../../../../etc/passwd  

- This represents a directory traversal attack used in Local File Inclusion (LFI) to access sensitive files.

- `/etc/passwd` is a common target containing system user details.

---

## 3. Log Analysis

- Request was allowed by the firewall  
- HTTP Response Status: 500  
- Response Size: 0  

Interpretation:
- Request reached the server  
- Server failed to process it  
- No sensitive data returned  

---

## 4. Source Analysis

- External IP address  
- Reputation: Clean  

Conclusion:
- Despite clean reputation, behavior indicates malicious intent  

---

## 5. Attack Flow

1. Attacker targets web application endpoint  
2. Injects directory traversal payload  
3. Request processed by server  
4. Server returns error (execution failed)  

---

## 6. Impact Assessment

- No evidence of file access  
- No data leakage  
- No compromise detected  

---

## 7. Response Actions

- Block source IP (106.55.45.162)  
- Implement input validation on file parameters  
- Restrict directory access  
- Deploy WAF rules for LFI detection  
- Monitor repeated attempts  

---

## 8. Detection Opportunities

- Detect `../` traversal patterns  
- Monitor access attempts to `/etc/passwd`  
- Alert on abnormal file query parameters  

---

## 9. Conclusion

- LFI attack attempt detected  
- Attack unsuccessful  
- No impact on system  

---

## 10. Final Verdict

True Positive – Unsuccessful LFI Attack Attempt