# 🌐 DNS Scans with Nmap

## 🔹 Purpose
DNS (Domain Name System) resolution translates human-readable domain names (like `facebook.com`) into IP addresses.  
Nmap offers options to customize DNS servers, skip DNS resolution, or bypass host discovery. These options are useful for faster scanning, avoiding detection, or working around blocked services.

---

## 🔹 Commands Used

### 1. Using a Custom DNS Server
```bash
nmap facebook.com --dns-servers 1.1.1.1

nmap -n facebook.com

nmap -n -Pn facebook.com ```

### 2. Skipping DNS Resolution



