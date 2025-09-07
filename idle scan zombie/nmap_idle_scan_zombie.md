# 🌐 Idle Zombie Scan Using Metasploit & Nmap

## 🔹 Purpose
Idle scans are an advanced stealth scanning technique in Nmap that allow you to **scan a target without sending packets directly from your own IP address**.  
This is particularly useful when:  
- You want to **avoid detection** by intrusion detection systems (IDS) or firewalls.  
- You need to perform reconnaissance **without leaving traces** in the target logs.  
- Your own IP might be blocked or monitored on the target network.  

The technique relies on a **third-party host (zombie)** with a predictable IP ID sequence. Nmap can use the zombie to probe the target on your behalf, making it extremely difficult for the target to trace the scan back to you.  

Using Metasploit helps **identify a suitable zombie host** on the network. Once a zombie with an **incremental sequence class** is found, Nmap can perform a stealth scan that appears to originate from the zombie instead of your machine.

The zombie must have an **incremental sequence class** for the scan to work reliably. Using this method, the target sees packets coming from the zombie, not the attacker, making detection very difficult.

---

## 🔹 Steps Explanation

1. **Open Metasploit Framework**  
   We use Metasploit to leverage its auxiliary modules for network reconnaissance. `sudo` is required because some network scanning modules need elevated privileges to send raw packets.

2. **Search for Idle IP Scanner Module**  
   This command finds modules capable of identifying idle hosts suitable for Nmap idle scans. The module automates the search for a zombie host in a network range.

3. **Use the Module**  
   Selects the module from search results (here `0` is the module number) to prepare it for configuration before running the scan.

4. **Show Module Options**  
   Displays all configurable parameters for the selected module. Important to check required fields, such as target IP range (RHOSTS) and verbosity settings.

5. **Set Target IP Range and Verbose Output**  
   RHOSTS specifies the network range in which to search for potential zombies.  
   Verbose mode allows us to see detailed information about each host, including IP ID sequence behavior.

6. **Run the Module to Identify Zombie**  
   Scans the network range to find hosts with a predictable IP ID sequence.  
   The goal is to locate a host with incremental sequence class, which can reliably act as a zombie for idle scanning. Only hosts with predictable sequences work because Nmap infers target responses using the IP ID field.

7. **Perform Idle (Zombie) Scan Using Nmap**  
   Use the identified zombie IP in Nmap with the `-sI` option.  
   Nmap sends SYN packets via the zombie and infers whether ports are open based on the IP ID sequence of the zombie.  
   This ensures that the target sees the scan as coming from the zombie, not the attacker, making it extremely stealthy.

---

## 🔹 Notes
- The zombie host must have a **predictable IP ID sequence**; otherwise, results may be unreliable.  
- Idle scans are one of the **stealthiest scanning techniques** because no packets originate from your IP.  
- Always have **explicit authorization** before scanning any network or host. Unauthorized scanning is illegal.  
- Use verbose mode (`-v`) with Nmap to see detailed interactions and verify the scan flow.

---

## 🔹 Commands

```bash
# Step 1: Open Metasploit Framework
sudo msfconsole

# Step 2: Search for Idle IP scanner module
search idle

# Step 3: Select the module
use 0

# Step 4: Show module options
show options

# Step 5: Set target IP range and enable verbose output
set RHOSTS 192.168.154.0-255
set VERBOSE true

# Step 6: Run the module to identify zombie
exploit

# Step 7: Perform Idle (Zombie) Scan using Nmap
sudo nmap -sI <zombie-ip> <target-ip>
