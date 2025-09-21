# BC/DR Plan — Mini

## Purpose
Define backup routines, RTO/RPO targets and restore steps for critical services.

## Critical Services & Targets
| service | owner | rto | rpo | backup frequency | backup location |
|--------:|-------|----:|----:|-----------------:|-----------------|
| database | IT Manager | 4h | 1h | continuous transaction log + nightly snapshot | offsite/cloud |
| web server | Web Lead | 4h | 1h | nightly snapshot | offsite/cloud |
| file shares | Operations | 8h | 4h | incremental daily | offsite/cloud |

## Backup Procedures
- use versioned backups; verify snapshots daily
- store 3 retention copies (daily/weekly/monthly)
- encrypt backups at rest and in transit

## Restore Steps (example: web server)
1. validate backup hash & integrity
2. restore to isolated VLAN or test environment
3. verify service start and integrity checks (checksum)
4. promote to production after 2 successful health checks

## Test Schedule
- weekly restore test for non-critical systems
- monthly full restore test for critical systems (document results)

