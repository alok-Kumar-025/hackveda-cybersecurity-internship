## Task 4: Analyzing Captured Traffic

Captured network traffic using `tcpdump` and analyzed in Wireshark.  
Identified unencrypted HTTP POST request containing credentials in clear text:  
`user=test&pass=hackveda`.

This demonstrates a critical vulnerability: sensitive data transmitted over HTTP without encryption.

> Recommendation: Enforce HTTPS to protect user credentials from interception.
