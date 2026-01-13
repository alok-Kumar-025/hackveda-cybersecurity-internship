# Man in the Middle Attack using ARPSPOOFING

## Task 1: Setting up the Lab Environment

### Setup Overview
- **Attacker Machine**: Parrot OS (installed via VMware Workstation Player)  
- **Victim Machine**: Windows 11 Host (running local HTTP server via VS Code Live Server)  
- **Network Mode**: NAT (local traffic only — ethical and safe)  
- **Tools Installed**: `dsniff`, `wireshark`, `ettercap` (for ARP spoofing)

### Steps Performed

1. Installed **VMware Workstation Player** on Windows 11 host machine.

2. Downloaded and imported the official **Parrot OS virtual machine image** from [parrotsec.org](https://www.parrotsec.org/).

3. Booted Parrot OS VM and logged in successfully.

4. Updated system packages:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

5. Installed required security tools:
  ```bash
  sudo apt install dsniff wireshark -y
  ```

6. Verified that ettercap is pre-installed (used as the ARP spoofing tool, standard in Parrot OS):
  ```bash
  ettercap -h
  ```

7. Set up the victim environment on Windows 11:
- Created a simple HTML test page (index.html) with a login form
- Hosted it locally using VS Code Live Server on http://127.0.0.1:5500
- Confirmed accessibility from browser

8. Confirmed network connectivity between Parrot OS (attacker) and Windows 11 (victim) using ping and IP inspection.

   🔐 All activities performed in a closed, local lab environment. No external systems were targeted. Ethical compliance maintained throughout.
