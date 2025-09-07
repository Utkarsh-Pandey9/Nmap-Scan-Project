# Nmap-Scan-Project
Hands-on pentesting project using Nmap and Wireshark on Metasploitable 2 in a VM environment.


# 🌐 Nmap & NSE Scans – Cybersecurity Reconnaissance & Testing

## 🔹 Overview
This repository showcases **hands-on experience with Nmap**, including advanced scanning techniques, service enumeration, vulnerability detection, and stealth scanning methods.  
These skills are crucial for roles such as **SOC Analyst, Penetration Tester, and Security Researcher**.  

The scans covered include:  
- Port scanning and service enumeration  
- OS detection  
- TCP and UDP scans  
- Wireshark verification of open ports  
- MAC address spoofing  
- Decoy scans  
- Idle Zombie scans  
- NSE-based brute-force attacks on FTP  
- Wildcard NSE scans for specific services  

---

## 🔹 Skills Demonstrated
- **Network scanning and reconnaissance** using Nmap and NSE  
- **Stealth scanning techniques**: Idle scans, decoy scans  
- **Service enumeration**: Identifying open ports, running services, and versions  
- **Vulnerability testing**: FTP brute-force, Telnet service checks  
- **Packet analysis**: Using Wireshark to verify open ports  
- **MAC spoofing** for anonymity during scans  
- **Scripting knowledge**: Using NSE scripts and wildcards (`*`) for comprehensive scans  
- **Metasploit usage**: Identifying zombie hosts for idle scans  

---

## 🔹 Highlights
1. **Port Scanning**: Comprehensive scans including all ports, selected ports, and port ranges.  
2. **Service & Version Detection**: Using `-sV` and intensity options to detect versions of running services.  
3. **OS Detection**: Using `-O` and `--osscan-guess` for operating system fingerprinting.  
4. **Stealth Techniques**: Decoy scans (`-D`), Idle Zombie scans (`-sI`) to avoid detection.  
5. **Packet Verification**: Using Wireshark to confirm open ports via SYN and SYN-ACK packets.  
6. **Credential Testing**: FTP brute-force using NSE scripts (`ftp-brute.nse`).  
7. **Wildcard NSE Scans**: Running all related scripts for Telnet (`telnet*`) and FTP (`ftp*`) services.  
8. **MAC Address Spoofing**: Random, custom, and vendor-based MAC spoofing during scans.  

---

## 🔹 Tools & Technologies
- **Nmap** – Network scanner and NSE scripting engine  
- **Wireshark** – Packet analysis tool  
- **Metasploit Framework** – Identifying idle zombie hosts  
- **Linux Commands** – Directory listing, grep, and file handling  


---

