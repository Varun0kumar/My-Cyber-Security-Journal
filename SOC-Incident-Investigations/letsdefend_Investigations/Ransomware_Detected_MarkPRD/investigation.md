# Investigation Report – Ransomware Detected

## 1. Initial Triage

The alert was triggered due to detection of a suspicious file:

- File Name: ab.exe  
- Hash: 0b486fe0503524cfe4726a4022fa6a68  
- Device Action: Allowed  

---

## 2. Threat Intelligence Analysis

- The file hash was analyzed using VirusTotal  
- 60 out of 72 vendors flagged the file as malicious  
- Identified as Avaddon ransomware  

This confirms the file is highly malicious and associated with ransomware activity.

---

## 3. Endpoint Analysis

- Host: MarkPRD (172.XX.XX.XX)  
- Execution of ab.exe confirmed  
- Malicious process activity observed  

Execution of ransomware indicates a high probability of system compromise.

---

## 4. Log Analysis

- Logs show suspicious activity associated with the endpoint  
- Events observed across different timelines  

This supports the likelihood of malicious behavior.

---

## 5. Correlation Analysis

- Malicious file execution aligns with suspicious logs  
- Strong correlation between detection and endpoint behavior  
- Indicates active ransomware infection scenario  

---

## 6. Conclusion

- Malicious file confirmed  
- Execution confirmed  
- Endpoint likely compromised  
- Risk of encryption and further malicious activity  

---

## 7. Final Verdict

**True Positive** – Ransomware Execution Confirmed

---

## 8. Learning Outcome

- Ransomware alerts must be treated as high severity  
- Execution significantly increases impact  
- Correlation between logs and endpoint is critical  

---