# Investigation Report – Malicious Attachment Detected (SOC114)

## 1. Initial Triage

- Event ID: 45  
- Rule: SOC114 - Malicious Attachment Detected - Phishing Alert  
- Source Email: accounting@cmail.carleton.ca  
- Destination Email: richard@letsdefend.io  
- Subject: Invoice  
- Device Action: Allowed  

The alert indicates delivery of a phishing email containing a potentially malicious attachment.

---

## 2. Email & Attachment Analysis

- The email contains an attachment (MD5: c9ad9506bcccfaa987ff9fc11b91698d)  
- File is flagged as malicious by multiple vendors (36/63) on VirusTotal  
- Threat classification: Trojan malware  

- Attachment delivery URL:
  https://download.cyberlearn.academy/download/download?url=https://files-ld.s3.us-east-2.amazonaws.com/c9ad9506bcccfaa987ff9fc11b91698d.zip  

- The file was also flagged as malicious on Hybrid Analysis  

Conclusion: The email is confirmed as a phishing attempt delivering malware.

---

## 3. Log Analysis

- Endpoint involved: 172.16.17.45  

- Observed outbound connection:
  http://andaluciabeach.net/image/network.exe  

- The URL is flagged as malicious (14/91 vendors on VirusTotal)  

Conclusion: The endpoint attempted to download or communicate with a malicious payload.

---

## 4. C2 Communication Analysis

- Identified Command and Control (C2) IP:
  70.38.21.234  

- This indicates communication with attacker-controlled infrastructure  

Conclusion: Presence of C2 communication confirms active compromise behavior.

---

## 5. Endpoint Analysis

- Suspicious activity detected on endpoint 172.16.17.45  

- Malicious process execution:
  JuicyPotato.exe  

- File flagged as malicious (57/69 vendors)  
- Known as privilege escalation / exploitation tool  

Conclusion: Endpoint shows clear signs of compromise and post-exploitation activity.

---

## 6. Attack Flow (Kill Chain Mapping)

1. Initial Access → Phishing email with malicious attachment  
2. Execution → User opens attachment → malware executed  
3. Privilege Escalation → JuicyPotato.exe executed  
4. Command & Control → Communication with 70.38.21.234  
5. Impact → Endpoint compromise  

---

## 7. Response Actions

- Isolate endpoint 172.16.17.45 from the network  
- Block malicious domain:
  andaluciabeach.net  
- Block C2 IP:
  70.38.21.234  
- Remove malicious files and processes  
- Perform full system malware scan  
- Reset user credentials associated with the system  
- Conduct further forensic analysis  

---

## 8. Detection Opportunities

- Detect phishing emails with suspicious attachments  
- Alert on file hashes flagged as malicious by threat intelligence  
- Monitor outbound traffic to known malicious domains  
- Detect execution of privilege escalation tools (e.g., JuicyPotato.exe)  
- Correlate email + endpoint + network activity  

---

## 9. Conclusion

- Phishing email successfully delivered malicious attachment  
- Malware executed on endpoint  
- Communication with malicious URL and C2 server observed  
- Endpoint compromise confirmed  

---

## 10. Final Verdict

True Positive – Phishing Email Leading to Malware Execution and C2 Communication