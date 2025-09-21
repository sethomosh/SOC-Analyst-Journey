# Compliance Mapping — example to NIST CSF

**Objective:** map our mini policy to NIST CSF functions.

| NIST CSF Function | Policy Section | Controls / Notes |
|-------------------|----------------|------------------|
| Identify | asset inventory, risk register | maintain inventory of critical systems; update risk register quarterly |
| Protect | authentication & access control | MFA, RBAC, patching, config management |
| Detect | monitoring & logging | SIEM ingestion, IDS alerts, log retention 90 days |
| Respond | incident response & reporting | IR lifecycle, escalation to Security Lead |
| Recover | backups & recovery | nightly backups, RTO/RPO defined per critical asset |

**Recommendation:** Expand mapping into a spreadsheet for audit use.
