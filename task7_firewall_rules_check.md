# 🔥 Task 7: Firewall Rules Check

**Task Name:** Check Active Firewall Rules Across PowerShell, CMD, and Linux Bash

## 📌 Objective  
Use the command line to review active firewall rules. This helps ensure that only authorized ports and services are allowed, reducing attack surface.

---

## 🧪 Command

### PowerShell
```powershell
Get-NetFirewallRule | Where-Object {$_.Enabled -eq "True"} | 
    Select-Object DisplayName, Direction, Action, Profile | 
    Format-Table -AutoSize
```

### CMD
```cmd
REM View basic firewall status
netsh advfirewall show allprofiles

REM View current firewall rules
netsh advfirewall firewall show rule name=all
```

### Bash
```bash
# View firewall rules (for ufw - Uncomplicated Firewall)
sudo ufw status verbose

# For systems using iptables:
sudo iptables -L -v -n
```

---

## 📝 Explanation

- Reviewing firewall rules helps ensure that **only necessary services and ports are allowed**.
- Detects **misconfigurations** or **unauthorized firewall changes**.

---

## 🔐 Why It Matters

- Firewall misconfigurations are a common cause of **data breaches**.
- Firewall rules should reflect **current security policies** and be monitored regularly.
- A critical step in both **security hardening** and **incident response**.
