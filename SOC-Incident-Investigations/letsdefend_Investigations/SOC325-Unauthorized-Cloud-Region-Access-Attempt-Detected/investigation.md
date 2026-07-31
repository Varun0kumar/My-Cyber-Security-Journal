# Investigation Process – Unauthorized Cloud Region Access Attempt

## 1. Initial Triage

Reviewed the security alert and identified repeated authentication attempts against an AWS account.

Alert Details:

- Source IP: 134.209.145.73
- Destination: AWS Services
- Username: test@letsdefend.io
- Device Action: Blocked
- Response Code: HTTP 403

The alert was generated because multiple login attempts originated from a cloud region configured as unauthorized.

---

## 2. Threat Intelligence

Checked the source IP address using VirusTotal.

Findings:

- 4 security vendors flagged the IP address as malicious.
- The IP address has previous malicious reputation.

Additionally, a Cyber Threat Intelligence (CTI) report received two days before the alert confirmed that the account credentials for **test@letsdefend.io** had been exposed.

Conclusion:

The authentication attempts are highly suspicious due to the combination of malicious IP reputation and previously compromised credentials.

---

## 3. Log Analysis

Reviewed authentication logs for source IP **134.209.145.73**.

Observations:

- Multiple login attempts were recorded.
- Every authentication request was blocked.
- No successful authentication events were identified.

Conclusion:

Security controls successfully prevented unauthorized access.

---

## 4. Endpoint Analysis

Reviewed the destination endpoint.

Destination:

- AWS Services (52.15.206.21)

Findings:

- No suspicious endpoint activity.
- No evidence of compromise.
- No post-authentication actions observed.

---

## 5. Analysis Conclusion

- Multiple authentication attempts detected.
- Login originated from an unauthorized cloud region.
- Source IP has malicious reputation.
- CTI report confirmed compromised credentials.
- All authentication attempts were blocked.
- No successful account compromise observed.

Final Verdict:

**True Positive – Unauthorized Cloud Region Access Attempt**