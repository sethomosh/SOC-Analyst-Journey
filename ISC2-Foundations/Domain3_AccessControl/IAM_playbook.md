# IAM Playbook — Account Lifecycle & Policies

## objective
document standardized provisioning, change, and deprovision processes with approvals, justification, and audit trails.

## account lifecycle
1. **request/provision**
   - requester fills form with business justification
   - manager approval required
   - create account: username, assign groups/roles, set initial MFA
   - document ticket ID and provisioning agent

2. **change / privilege elevation**
   - temporary elevation via JIT (just-in-time) or approval workflow (time-limited)
   - require reason, start/end time, and reviewer

3. **review**
   - quarterly access review: managers verify group membership and privileges
   - automated reports from directory (last login, privilege count)

4. **suspend / deprovision**
   - immediate suspend on termination or compromise
   - 90-day retention for account recovery (policy dependent)
   - final deletion after retention period with audit entry

## policies & controls
- password policy: minimum length & complexity, rotation policy (if required)
- mandatory MFA on all externally accessible & privileged accounts
- separation of duties: example mapping for finance & ops
- privileged access management (PAM) recommended for admin roles

## playbook artifacts
- sample access request template (ticket id, justification, manager approval)
- sample access review CSV output
- sample audit log snippet (who changed group membership + timestamp)

