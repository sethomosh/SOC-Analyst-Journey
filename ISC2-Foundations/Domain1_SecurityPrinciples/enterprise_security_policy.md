# Enterprise Security Policy — Mini (Sample)

**Purpose**  
This document defines baseline security requirements and controls to protect confidentiality, integrity, and availability (CIA) of company assets.

**Scope**  
Applies to all systems, networks, users, and data owned or managed by the organization.

## 1. governance & responsibilities
- **CISO / Security Lead**: overall ownership of security policy and risk register.
- **IT Manager**: enforce system patching, backups, asset inventory.
- **All employees**: follow acceptable use, MFA, and reporting procedures.

## 2. acceptable use
- Company devices must be used for work-related duties only.
- Unauthorized software downloads or use of unapproved cloud services is prohibited.

## 3. authentication & access control
- MFA is required for all remote access and privileged accounts.
- Least privilege enforced: role-based access for all systems (RBAC).
- Password policy: minimum 12 characters, complexity enforced, 90-day rotation.

## 4. patch & configuration management
- Critical patches applied within 7 days; high within 14 days; normal within 30 days.
- CIS benchmarks used for device hardening where available.

## 5. backups & recovery
- Nightly backups for critical servers; weekly full backups stored offsite.
- RTO and RPO defined per service (see Risk Register for critical service RTO/RPO).

## 6. incident response & reporting
- All security incidents reported immediately to Security Lead and IT Manager.
- IR lifecycle: identify → contain → eradicate → recover → lessons learned.

## 7. network & perimeter controls
- Firewalls must have deny-by-default rules; remote admin disabled from WAN.
- Network segmentation for sensitive systems (finance, customer data).

## 8. monitoring & logging
- Centralized logging (SIEM) for critical systems. Logs retained 90 days minimum.
- Alerts classified by severity and handled per SOC playbook.

## 9. training & awareness
- Annual mandatory security awareness training for all staff.
- Phishing simulations quarterly.

## 10. review cadence
- Policy reviewed annually or after significant incidents/changes.

*Document version:* 0.1  
*Author:* Omondi Seth Boy  
*Date:* $(date -I)

