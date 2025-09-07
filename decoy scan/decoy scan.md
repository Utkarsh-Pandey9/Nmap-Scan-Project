# 🌐 Nmap Decoy Scanning

## 🔹 Purpose
Decoy scanning allows you to **mask your real IP address** by sending scan packets alongside decoy IPs.  
This technique helps:
- Obfuscate your actual scanning source.  
- Bypass simple intrusion detection systems (IDS) or firewalls.  
- Make it difficult for the target to trace back the scan.

---

## 🔹 Commands Explanation

1. **Random decoys (`-D RND:5`)**  
   Nmap generates **5 random decoy IPs** along with your scan to hide your real IP.

2. **Custom decoys (`-D ip1,ip2`)**  
   You can specify **custom decoy IP addresses** to mix with your scan.

> In both cases, `-sS` performs a **TCP SYN scan**.

---

## 🔹 Commands

```bash
# TCP SYN scan with 5 random decoys
sudo nmap -sS -D RND:5 <target-ip>

# TCP SYN scan with custom decoy IPs
sudo nmap -sS -D 1.1.1.1,2.2.2.2 <target-ip>
