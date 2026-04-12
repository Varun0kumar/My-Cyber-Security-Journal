## Analyst Note

Alert investigated for requested Threat Intelligence URL activity.

Proxy logs show that host 172.16.17.47 (BillPRD) attempted to access the malicious URL http://115.99.150.132:56841/Mozi.m. Threat intelligence confirms that both the URL and destination IP are malicious.

Endpoint analysis identified a malicious file (MD5: 14970ce0a3d03c46a4180db69866d0d1) associated with a macro-enabled document, indicating potential compromise. Additional logs show prior communication with malicious infrastructure.

The request was blocked by security controls, preventing successful interaction with the malicious server.

- Real SOC Verdict: **True Positive** (Malicious activity detected and blocked)  
- LetsDefend Verdict: **False Positive** (No interaction with T.I. URL)

Recommendation: Endpoint should be isolated and further investigated.