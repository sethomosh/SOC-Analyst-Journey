# Incident Response Playbook — Mini (Template)

## Purpose
Standardized steps for triaging, containing, eradicating and recovering from security incidents. Use this playbook for initial SOC-level response.

## Roles
- **Responders:** SOC Analyst (Tier 1) — initial triage and containment
- **Escalation:** SOC Lead / Incident Manager — decisions, communications
- **Forensics:** Forensics Analyst — evidence handling & analysis
- **IT Ops:** System Admin / Network Admin — remediation & restores
- **Communications:** PR / Legal — external comms if needed

## IR lifecycle (summary)
1. **Identify** — validation of alert; collect initial context (source IP, host, user, timestamp).
2. **Triage** — severity rating (low/med/high/critical); gather logs, capture memory/disk if needed.
3. **Contain** — isolate host(s), block IPs, disable compromised accounts.
4. **Eradicate** — remove malware, revoke credentials, patch vulnerabilities.
5. **Recover** — restore systems from clean backups, validate integrity, bring services online.
6. **Lessons Learned** — post-incident report, update playbooks, adjust detections.

## Triage Checklist (Tier 1)
- confirm alert source (SIEM rule id, alert time, alerts correlated)
- identify affected host(s): hostname, IP(s), user accounts
- note observable indicators: filenames, process names, network connections
- collect relevant logs (syslog, windows event logs, auth logs, firewall logs)
- set severity and notify Incident Manager if severity >= high

## Containment Quick Actions
- isolate host from network (make it offline or apply firewall block)
- remove privileged sessions
- change passwords for affected accounts (use centralized password reset)
- block malicious IPs on perimeter firewall or WAF
- snapshot disk/memory (if forensic preservation required)

## Evidence Handling & Chain-of-Custody
- label all evidence (host, date/time, collector)
- record collector name and collection method
- store images/hashes in secure storage with access control
- sample chain-of-custody entry:
  - Item: host01-disk-image.dd
  - Collected by: <name>
  - Date/time: 2025-09-21T15:30:00Z
  - Hash (SHA256): <sha256sum>
  - Storage location: secure-evidence/repo/

## Containment → Eradication commands (examples)
- linux isolate (block network):
  - `sudo iptables -A INPUT -s <malicious_ip> -j DROP`
  - or `sudo ifdown eth0` (use with caution)
- stop malicious process:
  - `sudo pkill -f suspicious_process`
- collect logs:
  - `sudo tar -cvzf /tmp/host01_logs_20250921.tar.gz /var/log/auth.log /var/log/syslog /var/log/messages`

## Recovery (backup restore quick steps)
- validate backup integrity (check hash)
- restore to isolated environment first, test services
- apply patches/updates and harden configuration
- monitor restored host for anomalous activity for 72 hours

## Post Incident Tasks
- create incident_report (use template incident_report_TEMPLATE.md)
- run root cause analysis and update risk register
- update detection rules in SIEM and generate test alerts

