# IR Tabletop Exercise — Ransomware Simulation (Sample)

## Objective
Run a low-complexity tabletop sim to exercise decision-making and communication for a suspected ransomware incident.

## Scenario
- Date/time: 2025-09-22 10:00
- Trigger: multiple hosts reporting "file encryption" alert detected by endpoint monitoring; user reports unable to open files.
- Initial indicators: file extension change to .locked, process 'encryptor' seen on memory snapshot, increase in outbound SMB traffic.

## Participants & Roles
- Incident Manager: <name>
- SOC Analyst(s): <name>
- Forensics: <name>
- IT Ops: <name>
- Communications / Legal: <name>

## Timeline (Sample)
1. 10:00 — Alert received; SOC analyst validates.
2. 10:05 — Triage: identify affected hosts (host12, host13), severity = high.
3. 10:10 — Containment: isolate hosts, block suspicious IP ranges.
4. 10:30 — Forensic snapshot taken (disk + memory).
5. 11:00 — Decide to restore from backups for host12 (RTO = 4h).
6. 14:30 — Host restored, tested, services validated.
7. 16:00 — Lessons learned meeting: root cause found (outdated SMB patch) → schedule emergency patching.

## Playbook Outputs (deliverables)
- incident_report: timeline + evidence + remediation steps  
- updated IR_playbook entry for ransomware (containment & recovery steps)  
- action items for patching and backup policy adjustments

## Observations & Metrics
- time-to-detect: < 10m
- time-to-contain: < 30m
- time-to-recover: depends on backup speed (RTO target 4h)

