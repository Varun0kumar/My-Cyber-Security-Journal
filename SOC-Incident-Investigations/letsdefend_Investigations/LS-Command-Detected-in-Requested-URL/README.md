# Command Injection Alert Investigation

## Alert Details

- **Event ID:** 117  
- **Rule:** SOC167 - LS Command Detected in Requested URL  
- **Hostname:** EliotPRD  
- **Source IP:** 172.XX.XX.XX  
- **Destination IP:** 188.XXX.XX.XX  

---

## Summary

Alert triggered due to detection of "ls" keyword in the requested URL. Upon analysis, it was determined that the keyword was part of a legitimate string ("skills") and not an actual command injection attempt.

---

## Key Findings

- No malicious payload identified  
- "ls" present as substring in "skills"  
- No suspicious endpoint activity  
- No relevant malicious logs found  

---

## Final Verdict

  **False Positive – No Command Injection Detected**