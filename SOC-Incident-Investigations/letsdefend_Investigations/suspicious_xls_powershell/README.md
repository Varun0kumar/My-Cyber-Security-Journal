# Suspicious XLS Malware Investigation (LetsDefend)

## Alert Details

* **Rule Name:** Detected Suspicious XLS File
* **Host:** Sofia (172.16.17.56)
* **File:** ORDER SHEET & SPEC.xlsm
* **Hash:** 7ccf88c0bbe3b29bf19d877c4596a8d4

---

## Summary

Investigation identified execution of an obfuscated PowerShell command on the endpoint. The decoded script revealed a downloader mechanism attempting to retrieve and execute a payload from multiple external domains.

Threat intelligence analysis using VirusTotal confirmed several domains as malicious. Sandbox analysis using ANY.RUN validated the behavior of the script.

Log analysis showed no successful communication with external C2 infrastructure.

---

## Key Findings

* Encoded PowerShell execution (`-EncodedCommand`)
* Obfuscated downloader behavior
* Multiple suspicious external domains identified
* No successful C2 communication observed
* No evidence of quarantine or remediation

---

## Final Verdict

👉 **True Positive – Malicious Activity Confirmed**

---

## Tools Used

* LetsDefend
* ANY.RUN
* VirusTotal
* CyberChef

---
