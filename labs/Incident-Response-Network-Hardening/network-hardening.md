# Security Risk Assessment Report

## Part 1: Select up to three hardening tools and methods to implement
Three hardening tools the organization can use to address the vulnerabilities found include:

- Password policies  
- Firewall maintenance  
- Multifactor authentication (MFA)  

### Password Policies
Password policies define rules such as an 8–15+ character minimum with complexity requirements including uppercase letters, lowercase letters, numbers, and symbols. They also prevent users from reusing old passwords and lock accounts after a set number of failed login attempts.

### Firewall Maintenance
Firewall maintenance entails regularly checking and updating security configurations to stay ahead of potential threats and ensure proper traffic filtering.

### Multifactor Authentication (MFA)
Multifactor authentication (MFA) requires users to verify their identity in two or more ways to access a system or network. MFA methods include one-time passwords (OTP), fingerprint verification, PIN numbers, and other authentication factors.

## Part 2: Explain your recommendations
### Password Policies
Password policies help prevent attackers from gaining access to systems. Enforcing strong password complexity, preventing password reuse, and locking accounts after multiple failed attempts make brute force attacks more difficult and reduce the risk of unauthorized access.

### Firewall Maintenance
Firewall maintenance should be performed regularly to detect and prevent abnormal network activity. Blocking unwanted traffic helps protect against attacks such as DDoS. Firewall rules should define allowed and denied protocols such as TCP, UDP, and ICMP, as well as specify which ports are permitted. Outdated rules should be reviewed and removed, and configurations should follow the principle of least privilege.

### Multifactor Authentication (MFA)
Multifactor authentication (MFA) acts as an additional layer of security because it requires more than one method of authentication to verify a user’s identity. Even if a password is compromised, threat actors cannot access the system without bypassing the additional authentication factor. MFA also reduces risks associated with password sharing.