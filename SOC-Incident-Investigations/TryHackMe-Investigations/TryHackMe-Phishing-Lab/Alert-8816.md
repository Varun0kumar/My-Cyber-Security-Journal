# Alert 8816 – Access to Malicious URL Blocked

## Summary
Internal host attempted to access a blacklisted malicious URL, which was blocked by the firewall.

## Analysis
- URL flagged as phishing
- Destination IP associated with suspicious activity

## Threat Intelligence
- URL and IP flagged on VirusTotal

## SIEM Findings
No additional logs found

## Conclusion
True Positive – Prevented

## Analyst Note
The connection attempt to a malicious URL was successfully blocked by the firewall. No further activity observed. Monitoring of the source host is recommended.