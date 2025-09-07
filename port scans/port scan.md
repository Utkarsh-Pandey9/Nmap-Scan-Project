# 🌐 Nmap Port Scanning Commands

## 🔹 Purpose
Nmap (Network Mapper) is a powerful tool used to discover hosts and services on a network.  
Port scanning helps identify which ports are open on a target system.

---

## 🔹 Commands Explanation

1. **Scan a single port (Port 80)**  
   Checks if the HTTP port (80) is open on the target.

2. **Scan multiple specific ports (Ports 21, 22, 80)**  
   Checks if FTP (21), SSH (22), and HTTP (80) ports are open on the target.

3. **Scan a range of ports (Ports 1 to 100)**  
   Checks all ports from 1 to 100 to see which are open on the target.

---

## 🔹 Commands

```bash
nmap -p 80 <target-ip>
nmap -p 21,22,80 <target-ip>
nmap -p 1-100 <target-ip>
