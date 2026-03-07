# Week 10 — SSH Log Analysis & Firewall Hardening

## Objective
This week I revisited several previous labs and combined them into a single exercise to strengthen my understanding of network scanning, authentication logging, and firewall behavior.

Using my Kali Linux machine as the attacking system and my Ubuntu homelab as the target, I attempted SSH connections while monitoring system logs and adjusting firewall rules with UFW (Uncomplicated Firewall).

The goal was to observe how authentication attempts appear in system logs and how firewall rules affect connectivity.

## Lab Environment
Attacker Machine: Kali Linux  
Target Machine: Ubuntu 22.04 Homelab  
Tools Used:
- Nmap
- SSH
- UFW (Uncomplicated Firewall)
- auth.log

## What I Expected
Before running the lab, I expected two different behaviors depending on the firewall configuration.

When SSH traffic was **allowed**, I expected that my Kali machine would be able to reach the SSH service on port 22. However, without valid credentials I expected the login attempt to fail.

When SSH traffic was **denied**, I expected that the connection would fail and the service would appear unreachable.

## Nmap Port Scan
From Kali I performed a SYN scan against the homelab system.

This scan checks which ports are reachable on the target machine.
![Nmap scan results](screenshots/nmap-scan.png)

## SSH Login Attempt
After confirming SSH was reachable, I attempted to connect to the system.

Since the user `kali` does not exist on the target system, the authentication attempt failed.

![SSH login attempt](screenshots/ssh-login.png)

## Monitoring Authentication Logs
While attempting the login from Kali, I monitored the authentication logs on the Ubuntu homelab machine.

The logs recorded multiple failed authentication attempts.

Example log entries:
```
Mar 6 20:50:19 sshd: Invalid user kali from 192.168.181.4 port 33406
Mar 6 20:50:26 sshd: check pass; user unknown
Mar 6 20:50:26 sshd: authentication failure; rhost=192.168.181.4
Mar 6 20:50:26 sshd: Failed password for invalid user kali from 192.168.181.4 port 33406
```

These logs show how the SSH service records unauthorized login attempts and identifies the source IP address.

![Authentication logs](screenshots/auth-logs.png)

## Firewall Hardening with UFW
To control SSH access, I modified firewall rules using UFW.

When SSH was allowed, the connection attempt reached the server but failed due to incorrect credentials.
When SSH was denied, the connection attempt could not reach the service.

![UFW firewall rules](screenshots/ufw-rules.png)

## What I Learned
This lab helped reinforce several important defensive concepts.

First, I saw how failed login attempts appear in authentication logs and how administrators can use these logs to identify suspicious behavior.

Second, I observed how firewall rules directly control whether services are reachable from other machines.

Finally, combining Nmap scanning, SSH attempts, log monitoring, and firewall configuration helped me better understand how attackers and defenders interact with systems in real environments.

Redoing and combining these labs helped strengthen my understanding of how network services, authentication systems, and firewall protections work together.