# 🌐 Nmap Service & Version Detection

## 🔹 Purpose
Nmap can probe open ports to identify **running services and their versions**.  
This is crucial for vulnerability assessment and understanding the target’s software stack.

---

## 🔹 Commands Explanation

1. **Basic Service Version Detection (`-sV`)**  
   Performs service enumeration on open ports to determine the application name and version.

2. **Service Version Detection with Maximum Intensity on a Specific Port**  
   Uses `--version-intensity 9` to increase the thoroughness of version detection.  
   Targets a specific port (e.g., 21 for FTP).

---

## 🔹 Commands

```bash
# Basic service/version detection on all open ports
sudo nmap -sV <target-ip>

# Maximum intensity service/version detection on port 21
sudo nmap -sV --version-intensity 9 -p 21 <target-ip>
