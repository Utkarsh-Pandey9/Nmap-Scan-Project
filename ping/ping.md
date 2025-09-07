# 🖧 Ping Scan

## 🔹 Purpose
The **ping command** is used to test connectivity between the attacker (Kali Linux) and the target (Metasploitable 2).  
It sends ICMP Echo Requests and checks if the target replies with Echo Replies.

---

## 🔹 Command Used
```bash
ping 192.168.1.10(ip of your target machine)

## 🔹 Expected Outcome

- If the target is **alive and reachable**, it will respond with `Reply from 192.168.1.10` messages.  
- If the target is **unreachable**, you may see `Request timed out`.  
