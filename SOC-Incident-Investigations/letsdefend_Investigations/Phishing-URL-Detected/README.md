# Phishing URL Investigation – EmilyComp

## Alert Details

- **Event ID:** 86  
- **Rule:** SOC141 - Phishing URL Detected  
- **Source IP:** 172.XX.XX.XX  
- **Destination IP:** 91.XXX.XXX.X  
- **Hostname:** EmilyComp  
- **User:** ellie  
- **Request URL:** http://mogagrocol.ru/wp-content/plugins/akismet/fv/index.php  

---

## Summary

A phishing URL detection alert was triggered for the domain `mogagrocol.ru`. Investigation revealed that the endpoint accessed a malicious URL, leading to the execution of a Trojan malware on the system.

---

## Key Findings

- URL flagged as malicious (**15/95 detections on VirusTotal**)  
- Suspicious command execution using **rundll32.exe with mshtml**  
- Malware **KBDYAK.exe** downloaded and executed  
- File detected as malicious (**66/72 detections – Trojan**)  
- Outbound connections to multiple malicious IP addresses  
- Evidence of prior exposure to suspicious emails  

---

## Final Verdict

👉 **True Positive – Phishing URL Led to Trojan Infection (Host Compromised)**  

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- ANY.RUN  

---