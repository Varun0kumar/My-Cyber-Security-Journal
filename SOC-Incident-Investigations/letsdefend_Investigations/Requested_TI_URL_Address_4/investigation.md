# Investigation Process – Requested T.I. URL Address (Case 4)

## 1. Initial Triage

Alert triggered for the following URL:

https://pssd-ltdgroup.com

---

## 2. Threat Intelligence Analysis

- Domain flagged by 14/94 vendors as malicious  
- URL flagged by 14/95 vendors as malicious  
- Indicates high likelihood of malicious infrastructure  

---

## 3. Log Analysis

Proxy logs confirm:

- Source: 172.XX.XX.XX (BillPRD)  
- Destination: 5.188.0.251  
- Request Method: HTTPS  
- Action: Allowed  

Firewall logs confirm:

- Same connection observed  
- Process associated with request:
  - Krankheitsmeldung_092020_07.xlsm  

---

## 4. Endpoint Analysis

- Suspicious file identified:
  - **MD5:** 14970ce0a3d03c46a4180db69866d0d1  
  - Detection: 47/66 vendors flagged as malicious  
- File is macro-enabled document (.xlsm)  
- Likely source of malicious network activity  

---

## 5. Analysis

- Endpoint executed a malicious macro-enabled file  
- File initiated outbound communication to malicious domain  
- Successful access to malicious infrastructure confirmed  
- Indicates potential compromise or malware execution  

---

## 6. Conclusion

- Malicious URL access confirmed  
- Endpoint activity correlates with malicious file execution  
- Alert classified as True Positive  

---

## Learning Notes

- Macro-enabled documents are common attack vectors  
- Correlating process + network logs is critical  
- Successful access increases severity of incident  

---