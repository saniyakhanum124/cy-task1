# cy-task1
# Cyber Security Internship – Task 1  
**Task:** Scan the local network for open ports using Nmap and document the findings.

## Objective
Learn to discover open ports on devices in the local network to understand network exposure.

## Tools Used
- Nmap (TCP SYN scan)
- Optional: Wireshark (not used in this task)

## Steps Performed
1. Installed Nmap on my system.
2. Identified my local IP range using the command:
   --ipconfig
3. Ran a TCP SYN scan using the command:
   --nmap -sS [REDACTED-IP]/24
4. Recorded the hosts, their open ports, and services.
5. Saved results in results.txt file using the command:
   --nmap -sS -oN results.txt [REDACTED-IP]/24
## Key Observations
- Found hosts with open ports such as 53 (DNS), 135 (MSRPC), 139 (NetBIOS), 445 (Microsoft-DS), and 5357 (WS-Discovery).
- Majority of other ports were closed.
- These results highlight common services that could be potential targets if not secured.
