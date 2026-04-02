# Investigation Process – IDOR Attack

## 1. Initial Triage

Alert triggered due to consecutive requests to the same endpoint.

Endpoint: /get_user_info/

## 2. Log Analysis

Observed multiple requests from same IP:

user_id=1
user_id=2
user_id=3
user_id=4
user_id=5

All responses returned: HTTP 200 OK

## 3. Analysis

- Sequential manipulation of user_id parameter
- Same source IP performing requests
- No access control enforcement observed

## 4. Conclusion
- IDOR attack confirmed
- Unauthorized data access successful

## Learning Notes
- IDOR involves broken access control
- HTTP 200 responses with different IDs indicate possible data exposure

---