# 🌐 Nmap Advanced Recon & Enumeration Commands

## 🔹 Purpose
Nmap (Network Mapper) is a powerful reconnaissance and penetration testing tool leveraged for host discovery, port enumeration, and service fingerprinting.  
The commands below illustrate diverse scan vectors, including full TCP/UDP sweeps and multi-host enumeration.

---

## 🔹 Command Semantics

1. **Full TCP Port Sweep (`-p-`)**  
   Enumerates **all 65,535 TCP ports** on the target for exhaustive service mapping.

2. **Default SYN/Connect Scan (`nmap <target-ip>`)**  
   Conducts a standard scan against the **top 1,000 commonly used ports**, providing a rapid snapshot of exposed services.

3. **TCP Connect Scan (`-sT`)**  
   Initiates a full **TCP three-way handshake** to identify open TCP sockets; typically used when raw packet privileges are unavailable.

4. **UDP Scan (`-sU`)**  
   Probes for active **UDP services**, which often bypass stateful firewalls, albeit slower due to protocol constraints.

5. **Multi-Host Scan**  
   Targets multiple hosts concurrently by specifying a **comma-separated IP list**, enabling simultaneous enumeration.

---

## 🔹 Commands

```bash
nmap -p- <target-ip>
nmap <target-ip>
nmap -sT <target-ip>
nmap -sU <target-ip>
nmap <ip1>,<ip2>,<ip3>
