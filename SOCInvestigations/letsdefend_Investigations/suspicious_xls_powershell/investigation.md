# Investigation Process

## Alert Details

* **Rule Name:** Detected Suspicious XLS File
* **Host:** Sofia (172.16.17.56)
* **File:** ORDER SHEET & SPEC.xlsm
* **Hash:** 7ccf88c0bbe3b29bf19d877c4596a8d4

---

## 1. Initial Triage

Started investigation on host Sofia.

* Reviewed processes, network activity, and browsing history
* No suspicious activity identified
* Pivoted to terminal history for deeper inspection

---

## 2. Suspicious Discovery

A PowerShell command using `-EncodedCommand` was identified:

```
PowerShell -ENCOD IAAgAHMAZQB0AC0ASQBUAEUATQAgAHYAYQByAGkAQQB...
```

This indicates obfuscated execution, commonly used in malware.

---

## 3. Script De-obfuscation

The encoded command was decoded using CyberChef.

### Observed Behavior:

* Enforces TLS 1.2 communication
* Creates hidden directory in user profile
* Defines payload (`Stwk31v.exe`)
* Contains multiple external URLs
* Downloads payload using WebClient
* Executes payload via WMI

---

## 4. Malware Analysis

### Static Analysis

File hash was analyzed using VirusTotal.

* File flagged as malicious
* Multiple vendors detected suspicious behavior

---

### Dynamic Analysis

Behavior validated using ANY.RUN sandbox.

* Confirmed downloader functionality
* Observed execution flow of the script

---

## 5. Threat Intelligence

Extracted domains were analyzed:

* Some domains flagged as malicious
* Identified associated IP addresses:

  * 3.33.251.168
  * 45.63.105.20
  * 103.224.212.212
  * 194.53.148.33

---

## 6. Log Correlation

Searched Log Management using:

* Domains
* IP addresses

### Result:

* No outbound communication detected
* Indicates payload download likely failed

---

## 7. Key Insight

Initial investigation showed no findings, but deeper analysis of terminal history revealed malicious activity.

This highlights the importance of investigating beyond standard logs.

---
