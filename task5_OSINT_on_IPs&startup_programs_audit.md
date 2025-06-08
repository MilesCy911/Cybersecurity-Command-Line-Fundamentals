# 🌐 Task 5: OSINT on IPs & Startup Programs Audit

**Task Name:** Perform OSINT on IP Addresses and Audit Startup Programs Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to perform basic OSINT (Open Source Intelligence) on IP addresses, and audit startup programs that run when the system boots. These techniques help investigate potential threats and persistence mechanisms.

---

## 🧪 Command

### PowerShell
```powershell
# Perform DNS lookup on IP address
nslookup <IP_address>

# Audit startup programs
Get-CimInstance -ClassName Win32_StartupCommand | Select-Object Name, Command, Location | Format-Table -AutoSize
```

### CMD
```cmd
REM Perform DNS lookup on IP address
nslookup <IP_address>

REM List startup programs (partial)
wmic startup get caption, command
```

### Bash
```bash
# Perform DNS lookup on IP address
nslookup <IP_address>

# List user and system autostart services (Linux varies by distro)
sudo systemctl list-unit-files --type=service --state=enabled

# Check for startup scripts (cron jobs)
crontab -l
sudo cat /etc/crontab
```

---

## 📝 Explanation

- **OSINT (nslookup):** Helps map IPs to domains and understand external connections.
- **Startup Programs:** Critical for identifying **malware persistence** or **unauthorized autostart entries**.

---

## 🔐 Why It Matters

- OSINT tools like `nslookup` are used in **network investigation** and **threat hunting**.
- Startup programs are a common **persistence mechanism** used by attackers.
- Regular auditing helps detect **malicious autostarts** or **abnormal connections**.
