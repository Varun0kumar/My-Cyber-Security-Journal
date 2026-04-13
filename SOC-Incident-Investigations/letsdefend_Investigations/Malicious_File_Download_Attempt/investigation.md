# Investigation Process – Malicious File/Script Download Attempt

## 1. Initial Triage

Alert triggered for malicious file:

INVOICE PACKAGE LINK TO DOWNLOAD.docm

---

## 2. Threat Intelligence Analysis

- File hash checked on VirusTotal  
- 38/66 vendors flagged the file as malicious  
- Confirms the file is malicious  

---

## 3. Log Analysis

- Download attempt identified from host 172.16.17.37  
- Device action: Blocked  
- Additional logs show connections to malicious URLs  

---

## 4. Endpoint Analysis

- Host: NicolasPRD  
- Suspicious terminal activity observed  
- Indicates possible post-infection or attacker interaction  

---

## 5. Email Analysis

- Phishing email identified:
  - Subject: Invoice  
  - Sender: aaronluo@cmail.carleton.ca  
- Attachment flagged as malicious (43/64 detections)  

---

## 6. Analysis

- Malicious file delivered via phishing email  
- Download attempt blocked successfully  
- Endpoint shows signs of suspicious activity  
- Possible compromise or attempted infection  

---

## 7. Conclusion

- Malicious file confirmed  
- Attack delivery vector identified (phishing)  
- Endpoint requires further investigation  

---

## Learning Notes

- Phishing emails are a common malware delivery method  
- Blocked downloads do not guarantee no compromise  
- Endpoint activity must be reviewed for confirmation  

---