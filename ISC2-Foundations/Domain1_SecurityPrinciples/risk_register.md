# Risk Register (sample)

| id | asset | threat | likelihood (1-5) | impact (1-5) | risk score (LxI) | mitigation | owner | rto | rpo |
|----|-------|--------|------------------:|-------------:|-----------------:|-----------|------|----:|----:|
| R1 | web-server | unpatched vuln -> remote code exec | 4 | 5 | 20 | apply critical patches within 7 days; WAF; monitor IDS | IT Manager | 4h | 1h |
| R2 | user-devices | phishing -> credential theft | 4 | 4 | 16 | MFA, phishing training, email filtering | Security Lead | 24h | n/a |
| R3 | db-server | data exfiltration via exposed port | 3 | 5 | 15 | network segmentation, strict firewall rules, DB encryption at rest | IT Manager | 4h | 1h |

**risk scoring:** likelihood x impact (1 low — 5 high). Prioritize scores >= 12.
