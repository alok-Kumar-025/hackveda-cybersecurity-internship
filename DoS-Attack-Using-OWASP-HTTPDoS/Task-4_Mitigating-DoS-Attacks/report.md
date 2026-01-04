# Task 4: Mitigating DoS Attacks

## Key Mitigation Techniques
- **Rate Limiting**: Restricts requests per IP (e.g., Nginx, Apache mod_evasive)
- **Web Application Firewall (WAF)**: Blocks malicious traffic (e.g., ModSecurity)
- **Load Balancers**: Distribute traffic across servers (e.g., HAProxy)
- **CDNs**: Absorb attack traffic before it hits origin (e.g., Cloudflare, AWS CloudFront)

## DoS Protection Tools
- **Open-source**: 
  - `fail2ban` – bans IPs with repeated abuse
  - `ModSecurity` – WAF for Apache/Nginx
- **Commercial**:
  - **Cloudflare** – DDoS protection at edge
  - **AWS Shield** – automatic DDoS mitigation
  - **Imperva** – enterprise-grade protection

## Key Takeaway
DoS attacks target **availability** — but with layered defenses (WAF + CDN + rate limiting), systems can stay resilient even under flood.
