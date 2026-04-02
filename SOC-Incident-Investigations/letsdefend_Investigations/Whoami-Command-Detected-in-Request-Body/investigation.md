# Investigation Process – Command Injection (RCE)

## 1. Initial Triage

Alert triggered due to "whoami" detected in request body:

POST /video/?c=whoami

This indicates possible command injection.

---

## 2. Threat Intelligence

- Source IP: 61.177.172.87  
- Flagged by multiple vendors → suspicious  

---

## 3. Endpoint Analysis

Observed process execution:

- ls → root  
- whoami → root  
- uname → root  
- cat /etc/passwd  

Timeline matches alert time.

---

## 4. Terminal History

Commands executed:

- ls  
- whoami  
- uname  
- cat /etc/passwd  

Confirms attacker activity.

---

## 5. Log Analysis

POST parameters show injected commands:

- ?c=whoami  
- ?c=ls  
- ?c=uname  
- ?c=cat /etc/passwd  
- ?c=cat /etc/shadow  

---

## 6. Conclusion

- Command injection confirmed  
- Successful execution  
- Root-level compromise  
- Host contained  

---

## Learning Notes

- POST parameters can carry command injection payloads  
- Root execution = full compromise  
- Correlation of logs + endpoint = strongest evidence  