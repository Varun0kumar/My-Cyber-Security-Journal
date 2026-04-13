# Investigation Process – Requested T.I. URL Address (Case 3)

## 1. Initial Triage

Alert triggered for the following URL: https://raw.githubusercontent.com/django/django/master/setup.py

---

## 2. Threat Intelligence Analysis

- URL checked against VirusTotal  
- Only 1/95 vendors flagged the URL  
- No data found on URLhaus  
- URL belongs to official Django GitHub repository  

---

## 3. Log Analysis

Proxy logs confirm:

- Source: 172.16.20.4 (gitServer)  
- Destination: raw.githubusercontent.com  
- Request Method: GET  
- Device Action: Allowed  

---

## 4. Endpoint Analysis

- Host shows command-line activity:
  - `ls`, `pwd`, `cat /etc/passwd`  
- `wget` used to download files from GitHub  
- Additional script downloaded:
  - LinEnum.sh (privilege escalation enumeration script)  

---

## 5. Analysis

- The triggered URL is legitimate and commonly used in development environments  
- No malicious behavior directly associated with the alert URL  
- Observed additional activity may indicate administrative or post-exploitation behavior but is unrelated to the triggered alert  

---

## 6. Conclusion

- No malicious activity associated with the requested URL  
- Alert classified as False Positive  

---

## Learning Notes

- Not all flagged URLs are malicious  
- Always validate domain context (e.g., GitHub repositories)  
- Separate alert validation from unrelated suspicious activity  

---