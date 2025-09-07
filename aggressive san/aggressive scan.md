# 🌐 Nmap Aggressive Scanning

## 🔹 Purpose
The `-A` flag in Nmap enables **aggressive scanning**, which combines multiple reconnaissance techniques in a single command.  
It is used to gather comprehensive information about a target, including:
- Open ports and services  
- Service versions  
- Operating system detection  
- Script scanning for common vulnerabilities  
- Traceroute to map network path  

> Aggressive scanning provides detailed insights but is **noisy** and easily detectable by intrusion detection systems.

---

## 🔹 Commands Explanation

1. **Aggressive Scan (`-A`)**  
   Performs:
   - TCP SYN scan (default)
   - Service version detection (`-sV`)
   - OS detection (`-O`)
   - Script scanning (`--script=default`)
   - Traceroute  

> Requires `sudo` for certain probes, especially OS detection.

---

## 🔹 Command

```bash
sudo nmap -A <target-ip>
