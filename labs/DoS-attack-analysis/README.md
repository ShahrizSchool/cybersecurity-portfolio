# SYN Flood Network Attack Analysis

## Objective
Analyze network traffic logs to determine the cause of a website outage and identify the type of network attack.

## Scenario
A travel agency's website became unavailable and returned a connection timeout error. Network monitoring alerts indicated abnormal traffic directed at the web server. Packet analysis showed a large number of TCP SYN requests coming from a single unfamiliar IP address, overwhelming the server.

## Analysis Method
The provided Wireshark TCP/HTTP logs were reviewed to identify abnormal connection behavior, TCP handshake patterns, and repeated SYN requests from a single source.

## Key Findings
The web server was experiencing a SYN flood attack, a type of Denial-of-Service (DoS) attack. The attacker sent a large number of TCP SYN packets without completing the handshake, causing the server to allocate resources and become overwhelmed.

## Impact
The server became unresponsive to legitimate traffic, preventing employees and customers from accessing the website. This disruption could negatively affect business operations, reputation, and revenue.

## Mitigation
Potential mitigation strategies include:
- Implementing firewall rules to limit SYN requests
- Enabling SYN flood protection
- Using load balancers to distribute traffic

## Full Incident Report
Refer to the **network-attack.md** file in this folder for detailed analysis.