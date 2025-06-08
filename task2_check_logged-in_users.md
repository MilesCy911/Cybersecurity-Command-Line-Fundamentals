# 👥 Task 2: Check Logged-In Users

**Task Name:** Check Logged-In Users Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to check which users are currently logged into the system. Useful for detecting unauthorized access or verifying active user sessions during audits.

---

## 🧪 Command

### PowerShell
```powershell
Get-WmiObject -Class Win32_ComputerSystem
```

### CMD
```cmd
query user
```

### Bash
```bash
who
```

---

## 📝 Explanation

- **PowerShell:** Shows the currently logged-in user(s) on the system.
- **CMD:** `query user` lists users logged in locally or via remote sessions.
- **Bash:** `who` lists users currently logged into the system (including terminal sessions).

---

## 🔐 Why It Matters

- Helps **identify unauthorized users** logged into sensitive systems.
- Useful for **forensic investigation** (who was active at a certain time).
- Common step in **live incident response** to determine who is on a compromised machine.
