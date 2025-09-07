# 🌐 Checking Open Ports Using Nmap & Wireshark

## 🔹 Purpose
Sometimes Nmap cannot definitively determine whether a port is open due to **firewalls, packet filtering, or stealth configurations**.  
In such cases, we use Wireshark to **capture and analyze network packets** directly.  
By observing the TCP handshake between your system and the target, we can verify whether the port is truly open or closed.  
This method provides a **low-level, visual confirmation** of port status that complements Nmap scanning results.

---

## 🔹 Commands Explanation

1. **Scan a specific port with Nmap**  
   Sends a probe to the target port to check if it is open.

2. **Capture packets with Wireshark**  
   Observing the TCP handshake (SYN, SYN-ACK, ACK) indicates if the port is open.

3. **TCP Handshake Interpretation**  
   - If a **SYN** packet from your host is followed by a **SYN-ACK** from the target, the port is **open**.  
   - If there is a **RST** or no reply, the port is **closed or filtered**.

---

## 🔹 Commands

```bash
# Scan port 21 on target IP
nmap -p 21 <target-ip>

# Start Wireshark to capture packets
sudo wireshark
