# Cybersecurity Incident Report: SYN Flood Attack

## Section 1: Identify the type of attack that may have caused this network interruption
One potential explanation for the website's connection timeout error message is a network-level denial-of-service attack. The logs show that a malicious attacker with source IP 203.0.113.0 is targeting the web server with a SYN flood attack.

## Section 2: Explain how the attack is causing the website to malfunction
When website visitors try to establish a connection with the web server, a three-way handshake occurs using the TCP protocol:

1. The source IP sends a SYN (synchronize) packet to the web server, asking if it is receiving.  
2. The web server responds by sending back a SYN-ACK, which acknowledges the client's request and synchronizes the server's sequence numbers.  
3. Finally, the client responds with an ACK, which confirms both sides have established a connection and are ready to communicate.  

When a malicious actor sends a large number of SYN packets at once, the server attempts to acknowledge all the requests. However, there are too many for the server to handle, causing failures to normal traffic.

The logs indicate that source IP 203.0.113.0 was able to establish a connection once, but after the attacker flooded the server with SYN requests, the excessive traffic blocked normal requests and caused the server to become unresponsive.

This negatively impacts the servers and the company because normal traffic is unable to function while the servers are down. This can also affect the company's reputation and financial performance.

To prevent denial-of-service attacks in the future, especially SYN flood attacks, the firewall can be updated to limit the number of SYN requests per second from the same IP address. Load balancers can also be added to distribute traffic across multiple servers.