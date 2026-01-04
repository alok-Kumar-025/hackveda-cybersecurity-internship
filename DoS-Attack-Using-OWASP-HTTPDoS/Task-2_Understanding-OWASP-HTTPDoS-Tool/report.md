# Task 2: Understanding OWASP HTTPDoS Tool

## What is OWASP HTTPDoS?
OWASP HTTPDoS is described as an open-source Denial of Service (DoS) testing tool under OWASP, designed to simulate HTTP flood attacks by generating high volumes of concurrent HTTP requests to test server resilience.

> ⚠️ **Note**: The official `OWASP/HTTPDoS` GitHub repository is **not publicly available** (returns 404). Therefore, I used a **standard, open-source alternative** that demonstrates the same concept.

## Alternative Tool Used: HULK (HTTP Unbearable Load King)
- GitHub: https://github.com/grafov/hulk  
- Written in Go (Python version outdated)  
- Simulates HTTP flood attacks effectively  
- Ethical, educational, and runs on localhost

## Practical Execution
1. Started Apache web server:
   ```bash
   sudo systemctl start apache2
   ```
2. Created test page:
   ```
      echo "<h1>Apache is Running – DoS Target Ready</h1>" | sudo tee /var/www/html/index.html
   ```
3. Ran HULK attack:
   ```
   cd ~/hulk
   ./hulk -site http://127.0.0.1
   ```
## Key Observations
- 1023 concurrent connections established
- Over 169,000 requests sent successfully
- Server remained up but under heavy load — demonstrating DoS impact
> 🔒 Ethical Compliance: All testing performed on localhost only. No external systems targeted.
