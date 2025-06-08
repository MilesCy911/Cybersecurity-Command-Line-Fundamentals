# 🕵️‍♂️ Task 8: Hidden Files Detection & Running Process Audit

**Task Name:** Detect Hidden Files and Audit Running Processes Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to identify hidden files and perform a running process audit. These techniques help detect malware, rootkits, and unauthorized software.

---

## 🧪 Command

### PowerShell
```powershell
# Detect hidden files
Get-ChildItem -Path C:\ -Recurse -Force -ErrorAction SilentlyContinue | 
    Where-Object { $_.Attributes -match "Hidden" } | 
    Select-Object FullName, Attributes | Format-Table -AutoSize

# Audit running processes (with file path and process ID)
Get-Process | ForEach-Object {
    try {
        $_ | Select-Object Name, Id, Path
    } catch {
        $_ | Select-Object Name, Id
    }
} | Format-Table -AutoSize
```

### CMD
```cmd
REM Detect hidden files (basic, not recursive)
dir /a:h C:\

REM Audit running processes
tasklist /v
```

### Bash
```bash
# Detect hidden files (files starting with ".")
find / -type f -name ".*" 2>/dev/null

# Audit running processes
ps aux --sort=-%cpu
```

---

## 📝 Explanation

- **Hidden Files:** Malware and rootkits often use hidden files to evade detection.
- **Process Audit:** Auditing running processes helps discover malicious or unauthorized activity on the system.

---

## 🔐 Why It Matters

- Hidden files can indicate **stealthy malware** or **persistence mechanisms**.
- Regular process auditing is key to spotting **abnormal activity** or **resource abuse**.
- A fundamental technique in both **malware hunting** and **incident response**.
