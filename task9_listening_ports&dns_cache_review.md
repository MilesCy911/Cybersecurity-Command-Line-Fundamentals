# 🌐 Task 9: Listening Ports & DNS Cache Review

**Task Name:** Scan Listening Ports and Review DNS Cache Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to identify services listening on network ports and review the DNS cache. These techniques support network forensics, threat hunting, and malware investigation.

---

## 🧪 Command

### PowerShell
```powershell
# Scan listening ports and associated processes
Get-NetTCPConnection -State Listen | 
    Select-Object LocalAddress, LocalPort, OwningProcess | 
    Format-Table -AutoSize

# Review DNS cache
Get-DnsClientCache
```

### CMD
```cmd
REM Scan listening ports
netstat -an | findstr LISTENING

REM Review DNS cache
ipconfig /displaydns
```

### Bash
```bash
# Scan listening ports
sudo ss -tulnp

# Review DNS cache (varies by system; many Linux distros use systemd-resolved)
sudo systemd-resolve --statistics
# Alternative if using dnsmasq:
sudo cat /var/cache/dnsmasq
# Alternative if using nscd:
sudo nscd -g
```

---

## 📝 Explanation

- **Listening Ports:** Helps detect unauthorized or unexpected services listening for incoming connections.
- **DNS Cache:** Useful for identifying recent domain lookups made by the system, which can reveal **malware communications** or **phishing activity**.

---

## 🔐 Why It Matters

- Malware often opens listening ports for **C2 (Command & Control)** purposes.
- Reviewing DNS cache can uncover **malicious domain queries** made by compromised systems.
- Both techniques are important in **network forensics**, **threat hunting**, and **incident response**.
