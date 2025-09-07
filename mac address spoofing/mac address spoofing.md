# 🌐 MAC Address Spoofing with Nmap

## 🔹 Purpose
MAC address spoofing allows you to **change the source MAC address** of your network interface while performing scans.  
This is useful for:
- Hiding your real hardware address.  
- Bypassing MAC-based filtering on networks.  
- Testing security mechanisms that rely on MAC addresses.  

---

## 🔹 Commands Explanation

1. **Random MAC address (`--spoof-mac 0`)**  
   Nmap generates a **random MAC address** for the scan.

2. **Custom MAC address (`--spoof-mac <MAC>`)**  
   You can specify a **custom MAC address** of your choice.

3. **MAC address by vendor (`--spoof-mac <vendor>`)**  
   Nmap assigns a MAC address **matching a specific vendor**, e.g., Dell, Cisco, etc.

> In all cases, `-p21` targets port 21 (FTP) on the target IP.

---

## 🔹 Commands

```bash
# Random MAC address
nmap --spoof-mac 0 -p 21 <target-ip>

# Custom MAC address
nmap --spoof-mac 44:44:44:44:44:44 -p 21 <target-ip>

# MAC address from a specific vendor (e.g., Dell)
nmap --spoof-mac Dell -p 21 <target-ip>
