# 🌐 Nmap OS Detection Commands

## 🔹 Purpose
Nmap can attempt to identify the **operating system** running on a target host.  
OS detection is useful in penetration testing to understand the target environment and tailor attacks or assessments accordingly.

---

## 🔹 Commands Explanation

1. **Basic OS Detection (`-O`)**  
   Enables Nmap’s operating system fingerprinting to identify the OS type of the target host.

2. **Aggressive OS Guessing (`--osscan-guess`)**  
   Combines OS detection with aggressive heuristics to improve accuracy.  
   Requires `sudo` for certain probes and enhanced detection.

---

## 🔹 Commands

```bash
# Basic OS detection
nmap -O <target-ip>

# OS detection with aggressive guessing
sudo nmap -O --osscan-guess <target-ip>
