# Requested T.I. URL Address – gitServer (Case 3)

## Alert Details

- **Event ID:** 20  
- **Rule:** SOC105 - Requested T.I. URL address  
- **Source IP:** 172.XX.XX.X 
- **Hostname:** gitServer  
- **Destination IP:** 151.XXX.XXX.XXX  
- **Destination Hostname:** raw.github.com  
- **Request URL:** https://raw.githubusercontent.com/django/django/master/setup.py  
- **User Agent:** Wget/1.19.4 (linux-gnu)  
- **Action:** Allowed  

---

## Summary

An alert was triggered due to a request to a Threat Intelligence (T.I.) flagged URL. Investigation focused on validating the reputation of the requested URL and analyzing endpoint activity.

---

## Key Findings

- Requested URL belongs to official GitHub repository (Django framework)  
- No strong malicious reputation identified  
- Request was successfully allowed and completed  
- Endpoint shows command-line activity using `wget`  
- Additional external script download (LinEnum.sh) observed (separate activity)  

---

## Final Verdict

**False Positive – Requested URL is legitimate and not malicious**

---

## Tools Used

- LetsDefend SIEM  
- VirusTotal  
- AnyRun
- URLhaus
---