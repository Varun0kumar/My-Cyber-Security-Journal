# Investigation Process – XSS Alert

## 1. Initial Triage

Reviewed alert details and identified JavaScript payload in requested URL:

<script>javascript:alert(1)</script>

This indicates a potential XSS attempt.

---

## 2. Threat Intelligence

Checked source IP (112.85.42.13) on VirusTotal:

- No significant malicious reputation found  

---

## 3. Endpoint Analysis

Reviewed endpoint (WebServer1002):

- No suspicious processes or activity detected  

Conclusion: No endpoint compromise

---

## 4. Log Analysis

Searched logs using source IP:

Observed multiple payloads:

- `prompt(8)`  
- `<img src=q onerror=prompt(8)>`  
- `<svg><script>alert(1)`  
- `<script>eval()`  

All requests returned:


302 Redirect


---

## 5. Analysis Conclusion

- Repeated XSS payload attempts detected  
- Attack originated externally  
- No evidence of script execution  
- No impact observed on endpoint  

---

## 🧠 Learning Notes

- HTTP 302 indicates redirection, not execution  
- XSS success requires script execution evidence  
- Multiple payloads indicate vulnerability testing  

---