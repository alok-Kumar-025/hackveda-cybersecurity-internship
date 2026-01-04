# Task 2: Understanding OWASP HTTPDoS Tool

## What is OWASP HTTPDoS?
OWASP HTTPDoS is an open-source Denial of Service (DoS) testing tool developed under the OWASP (Open Web Application Security Project) umbrella. It is designed to simulate HTTP flood attacks by generating high volumes of concurrent HTTP requests to a target web server or application to test its resilience under stress.

## Key Features
- Generates **HTTP GET/POST floods**
- Supports configurable **number of threads** (concurrent requests)
- Allows setting **attack duration**
- Lightweight, written in **Python**
- Useful for **ethical testing** on localhost or authorized systems

## Installation Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/owasp/HTTPDoS.git
   ```
2. Navigate to directory:
   ```bash
   cd HTTPDoS
   ```
3. Install dependencies:
   ```bash
   pip3 install -r requirements.txt
   ```
   Note: The tool may require minor fixes (e.g., Python 3 syntax updates) on modern Kali Linux systems.
