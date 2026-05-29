# Week 3 – Linux as an Attack Surface

## Objective
Understand Linux systems as an attack surface by examining users, permissions, running processes, and system logs. The goal was to recognize how misconfigurations—not exploits—often enable privilege escalation and persistence.

## Topics Covered
- Linux user and group context
- File and directory permissions
- Process enumeration
- System services and daemons
- Log locations and security relevance

## Key Concepts

### Users and Privilege Context
Linux systems rely on user and group permissions to enforce security boundaries. Identifying the current user and associated groups provides immediate insight into potential privilege escalation paths. Excessive group membership, especially administrative groups, increases risk and attack surface.

### File and Directory Permissions
Linux permissions determine who can read, write, or execute files and directories. Misconfigured permissions are a common weakness, particularly when sensitive files or scripts are writable by non-privileged users.

Key observations:
- Directories require execute permissions to be accessed
- Private directories such as `.ssh` must restrict access to the owner
- Writable files executed by privileged users represent a serious risk

### Process Enumeration
Running processes reveal what services are active on a system and under which privilege level they operate. Many system services run as root and present high-value targets if misconfigured or vulnerable.

Process enumeration helps identify:
- Core system processes
- User shell sessions
- Network-facing services and background daemons

### System Logs
Linux systems maintain extensive logs that record authentication events, system behavior, and kernel activity. These logs are essential for detecting attacks, investigating incidents, and understanding system state over time.

## Security Observations
- Permissions misconfigurations are often more dangerous than missing patches
- Writable files executed by root can be abused for privilege escalation
- Root-owned services significantly expand the attack surface
- Authentication logs are critical for detecting brute-force and unauthorized access attempts
- Improper log permissions may allow attackers to hide malicious activity

## Hands-On Activities
- Enumerated user and group context to assess privilege levels
- Inspected file and directory permissions, including sensitive directories
- Enumerated running processes to identify root-owned services
- Located and reviewed key system log files in `/var/log`

## Artifacts
- TryHackMe_Week03_Notes.pdf
- Wireshark_Week03.pdf

## Summary
Week 3 reinforced Linux fundamentals through a security-focused lens. Rather than introducing new tools, the emphasis was on understanding how everyday Linux features like users, permissions, services, and logs can become attack vectors when misconfigured. This foundation is critical for later topics such as privilege escalation, persistence, and incident response.
