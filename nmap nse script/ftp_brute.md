# 🌐 FTP Brute-Force Scan Using Nmap

## 🔹 Purpose
Nmap’s **Nmap Scripting Engine (NSE)** can automate attacks such as brute-forcing login credentials on services like FTP.  
This method is useful to:  
- Test weak or default credentials on FTP servers.  
- Identify security misconfigurations.  
- Gather valid login information for penetration testing.  

In this example, the target is **Metasploitable 2**, which has default credentials for learning and practice.  
By using an FTP brute-force script, we can find valid credentials without manually guessing usernames and passwords.

---

## 🔹 Steps Explanation

1. **List FTP-Related Scripts**  
   We first list all NSE scripts related to FTP to identify which scripts can help with enumeration or brute-forcing:  
   `ls /usr/share/nmap/scripts/ | grep ftp`  

2. **Run FTP Brute-Force Script**  
   Using `ftp-brute.nse` with Nmap allows us to automate login attempts on the FTP service:  
   - `-p 21` specifies the FTP port.  
   - `-T5` sets the timing template to aggressive for faster scanning.  
   The output provides **valid credentials** (`user:user`) for the target system.

3. **Connect to FTP Using Obtained Credentials**  
   Once we have the credentials, we can log into the FTP server using the standard FTP client:  
   - Username: `user`  
   - Password: `user`  
   This confirms the brute-force attack successfully retrieved working login information.

---

## 🔹 Notes
- Only perform brute-force tests on **authorized targets**. Unauthorized brute-forcing is illegal.  
- Metasploitable 2 is intentionally vulnerable and designed for **learning and testing purposes**.  
- The timing template `-T5` is aggressive; use lower values (`-T2` or `-T3`) for stealthier scans.  
- NSE scripts are written in **Lua** and can be customized if needed.  

---

## 🔹 Commands

```bash
# List all FTP-related NSE scripts
ls /usr/share/nmap/scripts/ | grep ftp

# Run FTP brute-force scan on port 21
nmap --script ftp-brute.nse -p 21 <target-ip> -T5

# Connect to FTP using obtained credentials
ftp <target-ip>
# Username: user
# Password: user
