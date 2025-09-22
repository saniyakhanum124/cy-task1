# cy-task1
# Cyber Security Internship – Task 1  

*Task:* Scan the local network for open ports using Nmap and document the findings.  

---

## Objective
The purpose of this task is to *identify active hosts and their open ports* within the local network.  
This helps in understanding which services are exposed and evaluating potential security risks.  

---

## Tools Used
- *Nmap* → For scanning the network and detecting open ports.  
- *Command Prompt (Windows)* → To identify IP address and run Nmap.  
- *Wireshark* (optional, not used in this task).  


## Steps Performed
1. Installed Nmap on my system.
2. Identified my local IP range using the command:
   --ipconfig
3. Ran a TCP SYN scan using the command:
   --nmap -sS [REDACTED-IP]/24
4. Recorded the hosts, their open ports, and services.
5. Saved results in results.txt file using the command:
   --nmap -sS -oN results.txt [REDACTED-IP]/24
## 📊 Key Observations
### Host 1 → 192.168.xx.xx
- *Open Port:* 53/tcp (DNS Service)  
- *Risk:* Could be misused for DNS spoofing or amplification attacks if not secured.  

### Host 2 → 192.168.xx.xx
- *No open ports* (all scanned ports closed).  
- *Risk:* Low, safe configuration.  

### Host 3 → 192.168.xx.xx
- *Open Ports:*  
  - 135/tcp → MSRPC  
  - 139/tcp → NetBIOS-SSN  
  - 445/tcp → Microsoft-DS (SMB)  
  - 5357/tcp → WS-Discovery  

- *Risk:*  
  - RPC (135) and NetBIOS/SMB (139, 445) are commonly exploited by malware/ransomware (e.g., EternalBlue).  
  - WS-Discovery (5357) may leak device information.  
  - These should be restricted to trusted devices only.
  ## 🛡 Recommendations
1. *Restrict access* to risky ports (135, 139, 445, 5357) using firewall rules.(which i personally tried and its easy )
2. *Keep systems updated* with the latest security patches.
3. Use *strong authentication* where services must stay enabled.
4. Regularly *monitor open ports* to detect unauthorized changes.  
