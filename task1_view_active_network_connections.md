# 🛰️ Task 1: View Active Network Connections

**Task Name:** View Active Network Connections Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to identify all active TCP connections on the system, including local and remote addresses, port numbers, state, and owning process. This helps detect suspicious activity or monitor legitimate network usage.

---

## 🧪 Command

### PowerShell
```powershell
Get-NetTCPConnection | 
    Select-Object LocalAddress, LocalPort, RemoteAddress, RemotePort, State, OwningProcess | 
    Format-Table -AutoSize
```

### CMD
```cmd
netstat -ano
```

### Bash
```bash
ss -tulnp
```

---

## 📝 Explanation

- **PowerShell:** Displays active TCP connections with owning process info.
- **CMD:** `netstat -ano` lists all active connections and listening ports with process IDs.
- **Bash:** `ss -tulnp` is the modern replacement for `netstat`; shows TCP/UDP connections, listening ports, process info.

---

## 🔐 Why It Matters

- Useful for **detecting malware** or **unauthorized connections**.
- Helps **investigate suspicious processes** establishing external connections.
- A fundamental first step in **network forensics**.
