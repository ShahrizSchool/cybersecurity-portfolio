# Nmap Hands-on Practice Lab  
## Week 5 — Nmap Mini Report

**Tool:** Nmap  
**Supporting Tool:** Wireshark  

## Lab Environment

- **Ubuntu CyberSec VM:** NAT network  
- **Kali Linux VM:** Host-only network  
- **Scanning Context:** Self-scanning / peer VM scanning only  
- **Scope:** Controlled virtual lab (no external targets)

## Overview

This lab focused on practicing reconnaissance and port scanning techniques using Nmap within a controlled virtual lab environment. Scans were performed against my own Ubuntu CyberSec VM configured with NAT, and against a Kali Linux VM when both systems were placed on a host-only network. Wireshark was used alongside Nmap to observe and validate what was happening at the packet level.

## Network Context

### NAT Configuration (Ubuntu VM)

- NAT limits visibility to the VM itself  
- No other hosts are discoverable  
- **Expected result:** only one reachable IP address  

### Host-Only Configuration (Ubuntu ↔ Kali)

- Both VMs share an isolated internal network  
- Allows direct communication between the two VMs  
- Still isolated from external systems  

## Host-Only Network Scans With Wireshark (Ubuntu ↔ Kali)

To better understand how Nmap scan types translate into real network traffic, Wireshark was used to capture packets during host-only network scans between the Ubuntu CyberSec VM and the Kali Linux VM.

### 1. Host Discovery (`-sn`)

A ping scan was performed to identify active hosts on the host-only subnet.

**Findings:**

- Four hosts were detected as online  
- Two hosts corresponded to:
  - Ubuntu CyberSec VM  
  - Kali Linux VM  
- The additional two hosts were identified as:
  - VirtualBox host-only adapter (host system)  
  - VirtualBox DHCP service  

![Host discovery results](screenshots/host-discovery.png)

### 2. TCP Connect Scan (`-sT -F`) with Wireshark Analysis

A TCP connect scan against the Kali VM was performed while capturing traffic in Wireshark.

**Findings:**

- The Ubuntu VM initiated TCP connections by sending SYN packets to the target ports  
- Kali responded with RST packets, indicating that the destination ports were closed  
- No full three-way handshake (SYN → SYN/ACK → ACK) was observed  
- Wireshark confirmed that connection attempts were actively refused rather than silently dropped  

**Explanation:**

- A full TCP handshake only completes when a service is actively listening on the target port  
- Since no services were running on the scanned ports, Kali correctly reset the connections  
- This behavior demonstrates how closed ports appear at the packet level and explains why the handshake did not complete  

![TCP connect scan Wireshark capture](screenshots/tcp-connect-wireshark.png)

### 3. UDP Scan (`-sU`) with Wireshark Analysis

A UDP scan was performed and analyzed using Wireshark.

**Findings:**

- Most UDP probes resulted in ICMP “Port Unreachable” messages  
- No UDP services were confirmed as open  
- This reinforces the unreliable nature of UDP scanning and the need for packet-level inspection to interpret results accurately  

![UDP scan Wireshark capture](screenshots/udp-scan-wireshark.png)

## Nmap Practice

### 1. Host Discovery (Ubuntu VM — NAT)

- **`-sL` (List Scan)**  
  - Listed targets without scanning  
  - **Result:** One IP address listed (the Ubuntu VM)

- **`-sn` (Ping Scan)**  
  - Host discovery only  
  - **Result:** One host detected as up

- **`-Pn` (Treat Hosts as Online)**  
  - Skipped host discovery and scanned ports directly  
  - **Result:** One host up; all 1000 common TCP ports reported as closed or ignored

### 2. TCP Scanning (Ubuntu VM — NAT)

- **`-sT` (TCP Connect Scan)**  
  - Full three-way handshake when applicable  
  - **Result:** One host up; all scanned TCP ports closed  

- **`-sS` (TCP SYN Scan)**  
  - Half-open scan  
  - **Result:** One host up; all scanned TCP ports closed  

### 3. UDP Scanning (Ubuntu VM — NAT)

- **`-sU` (UDP Scan)**  
  - **Result:**
    - Port `5353/udp` reported as open|filtered  
    - Service identified as `zeroconf`  
    - All other UDP ports closed  

### 4. Service & OS Detection (Ubuntu VM — NAT)

- **`-O` (OS Detection)**  
  - OS detection attempted but inconclusive due to multiple matching fingerprints  

- **`-sV` (Service Version Detection)**  
  - Scan completed successfully but no service versions were identified  

- **`-A` (Aggressive Scan)**  
  - Combined OS detection, version detection, scripts, and traceroute  
  - Produced the same inconclusive results  

## Conclusion

This lab helped me connect what Nmap reports on the screen with what is actually happening on the network. While running scans between my Ubuntu CyberSec VM and Kali VM on a host-only network, I initially expected to see full TCP handshakes, but Wireshark showed that most connection attempts were immediately reset. After analyzing the packets, it became clear that this was because no services were listening on the target ports, not because the scans were failing.

Using Wireshark alongside Nmap made the results much easier to understand. Instead of just trusting the scan output, I could see the SYN packets being sent and the RST responses coming back, which explained why connections never fully completed. This confirmed that the ports were closed and that the network itself was functioning as expected.

Overall, this exercise showed why packet capture is important during reconnaissance. Nmap provides a high-level view, but Wireshark explains *why* those results occur. Seeing both together made TCP and UDP scan behavior much clearer.
