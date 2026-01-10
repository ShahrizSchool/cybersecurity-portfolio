# Week 2 – Networking & Web Fundamentals

## Objective
Learn how network traffic flows when visiting a website and understand what information is exposed at the network level from a security perspective.

## Topics Covered
- DNS resolution
- TCP vs UDP
- Common service ports
- HTTP vs HTTPS
- TCP three-way handshake

## Key Concepts

### TCP vs UDP
- TCP is connection-oriented and requires session establishment.
- Uses a three-way handshake (SYN → SYN/ACK → ACK).
- Guarantees ordered and reliable delivery (or reports failure).
- Higher overhead due to reliability mechanisms.

- UDP is connectionless with no session establishment.
- Does not guarantee delivery or ordering.
- Fire-and-forget data transmission.
- Lower overhead than TCP.

### Security Notes
- TCP scans reveal services through handshake responses.
- UDP services are harder to enumerate and monitor.
- DNS uses UDP for speed, increasing spoofing risk.

## Common Ports and Risks
- 22 (SSH): Remote administration, brute-force risk.
- 53 (DNS): Name resolution, spoofing and amplification attacks.
- 80 (HTTP): Unencrypted web traffic, sniffing risk.
- 443 (HTTPS): Encrypted web traffic, metadata and certificate misconfiguration risk.
- 445 (SMB): Windows file sharing, lateral movement and ransomware risk.
- 3389 (RDP): Remote desktop, full system access if exposed.

## Hands-On (Wireshark)
- Captured DNS A-record queries and responses.
- Observed TCP three-way handshakes on ports 80 and 443.
- Confirmed HTTP traffic is visible in plaintext.
- Verified HTTPS encrypts payload data while exposing metadata during TLS negotiation.

## Artifacts
- Wireshark_week02.pdf
- TryHackMe_week02.pdf

## Summary
This week built foundational understanding of how network communication works and how attackers and defenders analyze network traffic.
