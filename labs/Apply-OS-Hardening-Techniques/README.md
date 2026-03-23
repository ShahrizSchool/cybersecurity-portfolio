# Brute Force Attack & Malicious Redirect Analysis

## Objective
Analyze a compromised website scenario to identify the network protocols involved, document the incident, and recommend a remediation for a brute force attack.

## Scenario
A recipe website (yummyrecipesforme.com) was compromised after a former employee gained access using a brute force attack against a default admin password. Malicious JavaScript code was inserted into the website, prompting users to download an executable file and redirecting them to a malicious domain.

## Analysis Method
A sandbox environment was created to safely observe the suspicious behavior. Network traffic was analyzed using packet capture logs to identify DNS resolution and HTTP requests involved in the redirection and malware download.

## Key Findings
- The attacker used a brute force attack to access the admin panel
- Default credentials allowed unauthorized access
- Malicious JavaScript triggered a file download
- Users were redirected to a malicious domain
- DNS and HTTP protocols were used during the attack

## Impact
Customers downloading the malicious file experienced slow system performance and were redirected to a fraudulent website. This could lead to malware infections, data compromise, and reputational damage to the organization.

## Mitigation
Recommended security improvements include:
- Enforcing strong password policies
- Limiting login attempts
- Monitoring login activity
- Using a SIEM for alerting and detection

## Full Incident Report
See **security-incident-report.md** for detailed analysis.