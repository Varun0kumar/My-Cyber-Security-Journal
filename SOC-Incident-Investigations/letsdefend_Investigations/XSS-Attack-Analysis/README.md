# XSS Attack Investigation

## Alert Details

- **Event ID:** 116  
- **Rule:** SOC166 - Javascript Code Detected in Requested URL    
- **Source IP:** 112.**.**.**  
- **Destination IP:** 172.**.**.**  
- **Hostname:** WebServer1002  
- **Method:** GET  
- **Device Action:** Allowed  

---

## Summary

A Cross-Site Scripting (XSS) attempt was detected targeting the web application search functionality. The request contained JavaScript payloads embedded in URL parameters.

Multiple payload variations were observed, indicating repeated attempts to test for XSS vulnerabilities. However, there is no evidence confirming successful execution of the injected scripts.

---

## Key Findings

- JavaScript payload detected in URL parameters  
- Multiple XSS payload variations observed  
- HTTP 302 responses indicate redirection behavior  
- Source IP identified as external  
- No suspicious activity on endpoint  

---

## Analysis

Example payload:

<script>javascript:alert(1)</script>

Observed payload variations include:

- `prompt(8)`  
- `<img src=q onerror=prompt(8)>`  
- `<svg><script>alert(1)`  
- `<script>eval()`  

These payloads are commonly used to test XSS vulnerabilities.

---

## Final Verdict

  **True Positive – XSS Attempt Detected**  
  **Attack Status: Not Successful**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal

---

## Recommendations

- Implement input validation and output encoding  
- Use Content Security Policy (CSP)  
- Enable WAF protection for XSS  
- Monitor repeated malicious requests  

---