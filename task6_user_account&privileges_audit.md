# 👥 Task 6: User Account & Privileges Audit

**Task Name:** Audit User Accounts and Privileges Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to audit user accounts and privileges on the system. This helps identify unauthorized accounts, misconfigured privileges, and inactive users — all critical for cybersecurity auditing.

---

## 🧪 Command

### PowerShell
```powershell
# List local user accounts
Get-LocalUser | Select-Object Name, Enabled, LastLogon | Format-Table -AutoSize

# List members of the Administrators group
Get-LocalGroupMember -Group "Administrators"
```

### CMD
```cmd
REM List all local user accounts
net user

REM List members of the Administrators group
net localgroup administrators
```

### Bash
```bash
# List all user accounts (look at /etc/passwd file)
cat /etc/passwd

# List members of the sudo/admin group
getent group sudo
# If your distro uses 'wheel' instead of 'sudo':
getent group wheel
```

---

## 📝 Explanation

- **User Account Audit:** Helps detect unauthorized or dormant accounts.
- **Privileges Audit:** Critical for ensuring that only trusted accounts have administrative privileges.

---

## 🔐 Why It Matters

- **Privileged accounts** are a primary target for attackers.
- Misconfigured accounts and privileges can lead to **privilege escalation** or **unauthorized access**.
- Routine auditing is key to maintaining **least privilege** principles.
