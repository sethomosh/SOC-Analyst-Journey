# DAC / MAC / RBAC Lab

## objective
demonstrate discretionary (dac), mandatory (mac-like enforcement via apparmor/seLinux notes), and role-based access control (rbac) using linux permissions and an example ad/azure group-based workflow.

---

## lab 1 — linux (DAC / RBAC basics)

### environment
- ubuntu vm (or wsl) recommended
- tools: sudo, useradd, groupadd, chmod, chown, setfacl, getfacl

### steps (commands to run)
1. create users & groups
   - `sudo groupadd analysts`
   - `sudo groupadd auditors`
   - `sudo useradd -m -G analysts alice`
   - `sudo useradd -m -G auditors bob`

2. create project folder and set ownership
   - `sudo mkdir -p /srv/project_data`
   - `sudo chown root:analysts /srv/project_data`
   - `sudo chmod 770 /srv/project_data`

3. create a file as alice (simulate)
   - `sudo -u alice bash -c 'echo "sensitive data" > /srv/project_data/report.txt'`

4. verify bob cannot read
   - `sudo -u bob cat /srv/project_data/report.txt`  # should be denied

5. use setfacl for finer control (discretionary)
   - `sudo setfacl -m u:bob:r /srv/project_data/report.txt`
   - verify: `sudo -u bob cat /srv/project_data/report.txt`  # now allowed

### outcomes (what to document)
- show `ls -l /srv` and `getfacl /srv/project_data/report.txt`
- screenshot: permission denied for bob before ACL, and success after ACL

---

## lab 2 — MAC notes (applicable concepts)
- explain mandatory access controls: seLinux / apparmor overview (not enabling by default here)
- sample commands (if seLinux enabled):
  - `sestatus` (check)
  - reference: map a service domain to a stricter policy (document only if you run it)

---

## lab 3 — RBAC with Active Directory / Azure AD (high-level steps)

### option A: local AD lab (windows server)
(assumes a Windows Server VM with AD DS installed)
- create groups:
  - `New-ADGroup -Name "FinanceReaders" -GroupScope Global -PassThru`
- create users:
  - `New-ADUser -Name "charlie" -AccountPassword (ConvertTo-SecureString "P@ssw0rd!" -AsPlainText -Force) -Enabled $true`
- add user to group:
  - `Add-ADGroupMember -Identity "FinanceReaders" -Members "charlie"`
- apply GPO / file share ACLs to grant access to finance share only for FinanceReaders

### option B: azure ad / office365 (recommended trial)
- create groups via azure portal or azure cli:
  - `az ad group create --display-name FinanceReaders --mail-nickname financereaders`
- create user and add to group via portal/cli
- assign role-based access to resource (example: storage blob data reader) or map group to on-prem share via hybrid join

### outcomes to document
- screenshot of group membership
- screenshot of file share ACLs or azure role assignment
- explanation: least privilege, separation of duties, group-managed access

---

## evidence to include in repo
- `artifacts/linux_permissions_before.png`
- `artifacts/linux_permissions_after.png`
- `artifacts/ad_group_membership.png` (or azure portal)
- `configs.txt` with exact commands you ran

