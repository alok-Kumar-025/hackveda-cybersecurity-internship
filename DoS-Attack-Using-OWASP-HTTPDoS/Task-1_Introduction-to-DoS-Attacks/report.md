# Task 1: Introduction to Denial of Service (DoS) Attacks

## What is a DoS Attack?
A Denial of Service (DoS) attack is a malicious attempt to disrupt the normal traffic of a targeted server, service, or network by overwhelming it with a flood of illegitimate traffic. The goal is not to steal data, but to make the service **unavailable** to legitimate users.

## Core Security Principle Affected: Availability
DoS attacks directly violate the **Availability** pillar of the CIA Triad:
- **Confidentiality**: Keep data private → *not targeted*
- **Integrity**: Keep data accurate → *not targeted*
- **Availability**: Keep systems accessible → **TARGETED**

## Types of DoS Attacks
1. **SYN Flood**: Exploits TCP handshake by sending many SYN requests without completing the connection.
2. **HTTP Flood**: Sends massive HTTP GET/POST requests to exhaust server resources.
3. **UDP Flood**: Sends UDP packets to random ports, forcing the server to reply with "Destination Unreachable".
4. **Ping of Death**: Sends malformed or oversized ICMP packets to crash the system.
5. **Application-Layer Attacks**: Target specific app functions (e.g., login page) to exhaust logic/resources.

## Real-World Examples
- **GitHub (2018)**: Hit by 1.35 Tbps DDoS — largest recorded at the time (mitigated via DDoS protection service).
- **Dyn (2016)**: DNS provider attacked using Mirai botnet → took down Twitter, Netflix, Reddit.
- **AWS (2020)**: 2.3 Tbps attack absorbed using AWS Shield.

## Key Takeaways
- DoS = **service disruption**, not data theft.
- Modern attacks are often **DDoS** (Distributed DoS) using botnets.
- Always test **only on localhost or owned systems** (e.g., DVWA, local Apache).
- Mitigation includes: **rate limiting, CDNs, firewalls, WAFs**.

> ⚠️ **Ethical Note**: This task is for **educational & legal purposes only**. Never test on public/live systems without explicit permission.
