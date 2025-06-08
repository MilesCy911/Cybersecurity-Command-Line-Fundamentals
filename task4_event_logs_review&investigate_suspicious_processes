# 🗂️ Task 4: Event Logs Review & Investigate Suspicious Processes

**Task Name:** Review Event Logs and Investigate Suspicious Processes Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to review system event logs and investigate suspicious running processes. This task helps identify signs of compromise, persistence, or unauthorized activity on a system.

---

## 🧪 Command

### PowerShell
```powershell
# Launch Event Viewer GUI (manual review)
eventvwr.msc

# Investigate suspicious processes (extended process details)
Get-Process | Select-Object Name, Id, Path, StartTime | Format-Table -AutoSize
```

### CMD
```cmd
REM Event Viewer must be launched manually
eventvwr.msc

REM List running processes
tasklist /v
```

### Bash
```bash
# View system logs (requires sudo on many distros)
sudo journalctl -p warning..emerg --since "1 day ago"

# Investigate running processes with extended details
ps aux --sort=-%cpu
```

---

## 📝 Explanation

- **Event Logs:** Help detect suspicious login attempts, service crashes, privilege escalations, or malware persistence mechanisms.
- **Investigate Processes:** Shows which processes are consuming resources and may reveal suspicious binaries or processes running from unexpected paths.

---

## 🔐 Why It Matters

- Reviewing system event logs is essential for detecting **early signs of compromise**.
- Investigating suspicious processes helps discover **malware**, **unauthorized software**, or **malicious persistence**.
- A key step in both **routine auditing** and **incident response**.
