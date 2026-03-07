# SSH Authentication Logging & Firewall Hardening Lab

## Overview
This lab demonstrates how SSH authentication attempts are recorded in system logs and how firewall rules impact remote access to a Linux host.

Using a Kali Linux machine as the attacking system and an Ubuntu homelab machine as the target, I performed network scanning and SSH connection attempts while monitoring authentication logs on the target system. I also modified firewall rules using UFW (Uncomplicated Firewall) to observe how access to port 22 changes depending on the firewall configuration.

The goal of this lab was to understand how login attempts appear in logs and how firewall rules can be used to control access to services.

## Lab Environment
**Attacker Machine**
- Kali Linux  
- IP Address: `192.168.181.4`

**Target Machine**
- Ubuntu 22.04 (Homelab)  
- IP Address: `192.168.181.5`

**Tools Used**
- Nmap
- SSH
- UFW (Uncomplicated Firewall)
- Linux authentication logs (`auth.log`)

## Network Scanning

From the Kali machine, a SYN scan was performed against the Ubuntu target system to identify reachable services.

Initial results showed that all ports were filtered, which indicated that the firewall was blocking incoming connections.

![Nmap scan results](screenshots/nmap-scan.png)

## SSH Connection Attempts and Log Analysis

After confirming that SSH traffic could reach the system, an SSH connection attempt was made from the Kali machine.

The connection successfully reached the SSH service but authentication failed because the user `kali` does not exist on the Ubuntu system.

While these login attempts were being made, the authentication logs on the Ubuntu system were monitored.

![SSH Attempt](screenshots/ssh.png)

Log entries recorded during the SSH attempt:
```
Mar 6 20:50:19 sshd: Invalid user kali from 192.168.181.4 port 33406
Mar 6 20:50:26 sshd: check pass; user unknown
Mar 6 20:50:26 sshd: authentication failure; rhost=192.168.181.4
Mar 6 20:50:26 sshd: Failed password for invalid user kali from 192.168.181.4 port 33406
```

These entries show the attempted username, the time the commands were excuted, the source IP address of the connection, and the result of the authentication attempt. This type of logging is important for detecting unauthorized login attempts or brute-force activity.

![Authentication log entries](screenshots/auth-logs.png)

## Firewall Configuration (UFW)
The Ubuntu system used UFW (Uncomplicated Firewall) to control whether the SSH service could be accessed from other machines on the network.

When SSH traffic was allowed, the Kali machine was able to reach the SSH service. However, authentication still failed because the provided credentials were incorrect.

Once the rule was applied, the SSH connection attempts from Kali were no longer able to reach the service.

![UFW firewall rules](screenshots/ufw-rules.png)

## Security Observations
This lab demonstrates several important behaviors in a Linux environment. SSH authentication attempts are recorded in `/var/log/auth.log`, which provides visibility into failed login attempts and the IP address of the system making the request. Network scanning tools such as Nmap can help determine whether a service is reachable, while firewall rules control whether that service is accessible from other systems on the network.

Monitoring authentication logs and restricting remote access through firewall rules are key defensive practices for securing Linux systems.