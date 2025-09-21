# Incident Report — TEMPLATE

**Incident ID:** IR-2025-09-21-001  
**Title:** suspected ransomware / file encryption  
**Reported by:** <name>  
**Date/time discovered:** 2025-09-21T14:00Z  
**Severity:** High

## Summary
Short summary of what happened and immediate impact.

## Timeline
| time | action | actor | notes |
|------|--------|-------|-------|
| 14:00 | alert triggered | SOC | SIEM rule ID: 1234 |
| 14:05 | initial triage | SOC Analyst | confirmed encrypted file extensions |
| 14:10 | containment | IT Ops | isolated host13 from network |
| ... | ... | ... | ... |

## Evidence collected
- disk image: host13-disk.dd (sha256: ...)
- syslog extract: host13_syslog_20250921.log
- sample encrypted file: invoice1.locked

## Root Cause
- summary of root cause analysis (e.g., unpatched SMB vulnerability)

## Remediation & Recovery
- immediate remediation actions taken
- restore steps performed & verification results

## Recommendations
- patch schedule changes
- detection rule adjustments
- training / policy updates

## Attachments
- links to artifacts/ (screenshots, logs, pcaps)

