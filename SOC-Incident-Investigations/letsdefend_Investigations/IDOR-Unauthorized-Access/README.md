# IDOR Attack Investigation – WebServer1005

##Alert Details

- **Event ID:** 119  
- **Rule:** SOC169 - Possible IDOR Attack Detected  
- **Source IP:** 134.XXX.XXX.XXX  
- **Destination IP:** 172.XX.XX.XX  
- **Hostname:** WebServer1005  
- **Method:** POST  

---

## Summary

An Insecure Direct Object Reference (IDOR) attack was identified targeting the `/get_user_info/` endpoint. The attacker manipulated the `user_id` parameter to access multiple user records.

---

## Key Findings

- Multiple consecutive requests from same IP  
- `user_id` parameter manipulated (1 → 5)  
- All requests returned **HTTP 200 OK**  
- Indicates unauthorized access to user data  

---

## Final Verdict

👉 **True Positive – IDOR Attack (Successful Unauthorized Access)**

---

## Tools Used

- LetsDefend SIEM  
- Log Management  

---