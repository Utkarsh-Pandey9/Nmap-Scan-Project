# 🌐 Nmap Scanning Using an IP List

## 🔹 Purpose
When targeting multiple hosts, Nmap allows scanning through a predefined list of IP addresses.  
This approach is efficient for network-wide reconnaissance or when dealing with large sets of targets.

---

## 🔹 Commands Explanation

1. **Create a list of target IPs (`iplist.txt`)**  
   You can create a plain text file containing all target IPs, one per line. This file will be used by Nmap to iterate through the targets.

2. **Scan all IPs from the list (`-iL`)**  
   Nmap reads the file and performs the scan on each IP sequentially.

---

## 🔹 Commands

```bash
# Create a file and add IPs
cat > iplist.txt
192.168.1.10
192.168.1.20
192.168.1.30
# Press Ctrl+C to save and exit

# Scan all IPs from the list
nmap -iL iplist.txt
