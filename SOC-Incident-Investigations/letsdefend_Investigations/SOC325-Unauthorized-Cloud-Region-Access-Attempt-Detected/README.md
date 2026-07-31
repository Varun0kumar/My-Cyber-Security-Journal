# Unauthorized Cloud Region Access Attempt Investigation

## Alert Details

- **Event ID:** 303
- **Rule:** SOC325 - Unauthorized Cloud Region Access Attempt Detected
- **Source IP:** 134.**.**.**
- **Destination IP:** 52.**.**.**
- **Target Service:** AWS Services
- **Username:** test@letsdefend.io
- **Device Action:** Blocked

---

## Summary

A security alert was generated after multiple authentication attempts were detected against an AWS account from an unauthorized cloud region. Threat intelligence identified the source IP as malicious, while an earlier CTI report confirmed that the targeted account credentials had previously been exposed.

Cloud security controls blocked every authentication attempt, preventing unauthorized access to the AWS environment.

---

## Key Findings

- Multiple authentication attempts detected
- Login attempts originated from an unauthorized cloud region
- Source IP flagged as malicious by multiple security vendors
- CTI report confirmed previously compromised credentials
- HTTP 403 responses indicate blocked authentication attempts
- No successful login or endpoint compromise identified

---

## Analysis

The investigation correlated three independent sources of evidence:

- Authentication logs
- Threat intelligence
- Cyber Threat Intelligence (CTI) report

Although the credentials had been previously compromised, the organization's cloud region restrictions successfully prevented unauthorized access. No indicators of successful authentication or post-compromise activity were identified.

---

## Final Verdict

**True Positive – Unauthorized Cloud Region Access Attempt**

**Attack Status:** Blocked Successfully

---

## Tools Used

- LetsDefend SIEM
- VirusTotal
- LetsDefend Log Management
- Endpoint Security
- Email Security

---

## Recommendations

- Reset the affected user credentials immediately.
- Enable Multi-Factor Authentication (MFA) if not already enforced.
- Continue monitoring authentication attempts for the affected account.
- Review cloud region access policies and maintain geographic restrictions.
- Investigate any future login attempts using the compromised credentials.