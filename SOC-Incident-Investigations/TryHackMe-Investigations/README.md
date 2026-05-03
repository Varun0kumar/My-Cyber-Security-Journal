# Introduction to Phishing – SOC Investigation (TryHackMe)

This project documents multiple phishing-related security alerts investigated using the TryHackMe SOC Simulator.

## Objective
To analyze inbound phishing emails and related network activity, validate threats using threat intelligence, and determine the impact based on available telemetry.

## Tools Used
- Splunk (SIEM)
- VirusTotal (Threat Intelligence)
- Hybrid Analysis
- ANY.RUN

## Investigation Summary

 8815 - Phishing Email - True Positive 
 8816 - Malicious URL Access (Blocked) - True Positive (Prevented) 
 8817 - Phishing Email (Impersonation) - True Positive 
 8818 - Onboarding Email - False Positive 

## Key Skills Demonstrated
- Phishing detection and analysis  
- Threat intelligence validation  
- Log analysis using SIEM  
- Identifying false positives  
- Writing structured SOC reports  

## Notes
- Some alerts did not generate logs in SIEM, which was documented as part of the investigation findings.
- Emphasis was placed on evidence-based analysis and avoiding assumptions.

## TryHackMe Progress
https://tryhackme.com/soc-sim/public-summary/a2f2da5e0cbbdfabaa9ef020a68844d6cd7db6fce3def1130f117626ea448e98ee41f3650d2cd297b90460e0cae46f43