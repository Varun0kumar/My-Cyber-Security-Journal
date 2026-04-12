# Investigation Process – Requested T.I. URL Address (Case 2)

## 1. Initial Triage

Alert triggered for a request to a Threat Intelligence flagged URL:

http://115.99.150.132:56841/Mozi.m

---

## 2. Threat Intelligence Analysis

- URL flagged as malicious by multiple vendors  
- Destination IP (115.99.150.132) identified as malicious  
- Indicates potential command-and-control (C2) infrastructure  

---

## 3. Log Analysis

Proxy logs confirm:

- Source: 172.16.17.47 (BillPRD)  
- Destination: 115.99.150.132  
- Request Method: GET  
- Device Action: Blocked  

Additional firewall logs show prior communication with malicious domain:
- https://pssd-ltdgroup.com  

---

## 4. Endpoint Analysis

- Suspicious file detected:
  - **MD5:** 14970ce0a3d03c46a4180db69866d0d1  
  - Detection: 47/66 vendors flagged as malicious  
- File associated with macro-enabled document:
  - Krankheitsmeldung_092020_07.xlsm  

---

## 5. Analysis

- Endpoint shows indicators of compromise (IOC)  
- Malicious file likely initiated outbound communication  
- Attempted connection to malicious infrastructure detected  
- Security control successfully blocked the request  

---

## 6. Conclusion

- Malicious activity confirmed on endpoint  
- Outbound request to malicious server attempted  
- No successful interaction due to security control blocking  

**Real SOC Perspective:**  
- This represents a True Positive due to confirmed malicious behavior and attempted C2 communication  

**LetsDefend Platform Perspective:**  
- Classified as False Positive because the request was blocked and no interaction with the T.I. URL occurred  

---

## Learning Notes

- Blocked traffic can still indicate compromise  
- Endpoint + network correlation is critical  
- Lab environments may require strict rule-based interpretation  

---