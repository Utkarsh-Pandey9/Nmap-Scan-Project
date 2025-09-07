# 🌐 Running Service-Related Nmap Scripts Using Wildcards

## 🔹 Purpose
Nmap’s **Nmap Scripting Engine (NSE)** allows automated scanning of services to:  
- Enumerate service configurations.  
- Check for vulnerabilities.  
- Test for weak credentials.  

Using the wildcard `*` in the `--script` option allows you to **run all scripts that match a pattern** at once.  
This is very useful when you want a **comprehensive assessment of a service** quickly without specifying each script individually.

---

## 🔹 Telnet Scripts
- `telnet*` matches all NSE scripts whose names start with `telnet`.  
- Running these scripts can help you detect vulnerabilities, misconfigurations, and service details for Telnet servers.  
- Example usage focuses on port 23, the default Telnet port, for faster and more precise scanning.

---

## 🔹 FTP Scripts
- `ftp*` matches all NSE scripts whose names start with `ftp`.  
- Running these scripts automates FTP service testing, including:  
  - Brute-force attacks (`ftp-brute.nse`)  
  - Vulnerability checks  
  - Service enumeration  
- Targeting port 21, the default FTP port, improves scan efficiency and focuses the assessment.

---

## 🔹 Notes
- NSE scripts are written in **Lua**.  
- The `*` wildcard can be applied to **any service-specific NSE script** (e.g., `http*`, `smtp*`, `ssh*`).  
- Always scan **authorized systems only**, as some scripts can attempt login attempts or exploit vulnerabilities.  
- Use verbose mode (`-v`) for detailed output.  
- Using wildcards speeds up testing and ensures better coverage for a particular service.

---

## 🔹 Commands

```bash
# Run all Telnet-related NSE scripts on the target
nmap --script telnet* <target-ip>

# Run all Telnet-related NSE scripts specifically on port 23
nmap -p 23 --script telnet* <target-ip>

# Run all FTP-related NSE scripts on the target
nmap --script ftp* <target-ip>

# Run all FTP-related NSE scripts specifically on port 21
nmap -p 21 --script ftp* <target-ip>
