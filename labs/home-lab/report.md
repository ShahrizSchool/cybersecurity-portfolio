# Home Lab Setup Report – Week 1

## Objective
Establish a baseline isolated lab environment and verify communication
between attacker and defender systems.

## Lab Architecture
- Two virtual machines on a host-only network
- Attacker VM: Kali Linux
- Defender VM: CyberSec (Ubuntu)

Host-only networking was selected to prevent exposure to the internet
while allowing controlled communication between systems.

## Connectivity Verification
Connectivity was verified using ICMP (ping) in both directions.
No scanning, probing, or exploitation was performed.

### Defender System
- IP Address: 192.168.56.101/24
- Network: VirtualBox Host-only
- Status: Connectivity verified

![Defender Ping](defender_ping.png)

### Attacker System
- OS: Kali Linux
- IP Address: 192.168.56.102/24
- Network: VirtualBox Host-only
- Status: Connectivity verified

![Attacker Ping](attacker_ping.png)

## Observations
- Each VM was assigned a unique IP address
- Traffic was limited to ICMP for validation purposes
- The setup mirrors real-world separation of trusted and untrusted systems

## Lab Status
Environment successfully established and ready for future security labs.