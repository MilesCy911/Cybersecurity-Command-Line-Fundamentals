# ⚙️ Task 3: Process & Open Ports Monitoring

**Task Name:** Monitor Running Processes and Open Ports Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to monitor active processes and open network ports. This helps detect suspicious or unauthorized processes and services listening on the system.

---

## 🧪 Command

### PowerShell
```powershell
# List running processes
Get-Process

# Check for open/listening ports
Get-NetTCPConnection | Where-Object {$_.State -eq "Listen"} | 
    Select-Object LocalAddress, LocalPort, OwningProcess | 
    Format-Table -AutoSize
```

### CMD
```cmd
REM List running processes
tasklist

REM Check for open/listening ports
netstat -an | findstr LISTEN
```

### Bash
```bash
# List running processes
ps aux

# Check for open/listening ports
ss -tulnp
```

---

## 📝 Explanation

- **Processes:** Helps identify suspicious or unauthorized processes (malware, persistence mechanisms).
- **Open ports:** Reveals services listening on the system, which can be used by attackers or indicate unexpected exposures.

---

## 🔐 Why It Matters

- Regular process and port monitoring is critical for detecting **early signs of compromise**.
- Helps validate system baseline — unexpected ports or processes can indicate **malware** or **unauthorized services**.
- Common step in **incident response** and **post-breach analysis**.
