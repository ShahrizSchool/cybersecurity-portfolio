# Week 06 — Vulnerabilities & CVEs (Defense Thinking)

## Objective

This week focused on understanding how vulnerabilities are identified, categorized, and addressed from a defensive security perspective. The goal was to learn how security teams reason about risk using CVEs, vulnerability scanners, and cryptographic fundamentals, rather than performing hands-on exploitation.

## Vulnerability Awareness & Scanning

This week introduced the concept of vulnerabilities as weaknesses that can be exploited if left unpatched. Vulnerability scanning was explored as a defensive technique used to identify these weaknesses before they are abused.

Key ideas included:
- The difference between authenticated and unauthenticated scans
- How scan depth and accuracy change when credentials are available
- The role of internal versus external scanning in understanding an organization’s attack surface

This reinforced how defenders proactively assess systems instead of reacting after compromise.

## CVEs and Risk Assessment

A major focus of the week was learning how vulnerabilities are tracked and prioritized using standardized systems.

CVE (Common Vulnerabilities and Exposures) identifiers were introduced as a way to uniquely reference known vulnerabilities, while CVSS scores were used to understand severity and potential impact.

Through this process, I learned how defenders use CVEs to:
- Determine which systems are affected
- Assess risk based on severity scores
- Prioritize patching and remediation efforts

## Cryptography Fundamentals

This week also covered essential cryptographic concepts that support secure systems.

Topics included:
- The difference between plaintext and ciphertext
- Symmetric vs asymmetric encryption
- Public key cryptography concepts such as RSA and Diffie–Hellman
- Core security principles: authentication, integrity, confidentiality, and authenticity

Hashing was introduced as a one-way process commonly used for password storage and integrity verification, reinforcing why hashes differ fundamentally from encryption.

## Exploitation Basics (Conceptual)

Exploitation was approached at a conceptual level only, with an emphasis on understanding terminology rather than performing attacks.

The Metasploit Framework was explored to understand:
- How vulnerabilities, exploits, and payloads relate to each other
- The purpose of exploitation frameworks in validating security weaknesses
- Why defenders must understand exploitation mechanics to properly mitigate risk

Hands-on exploitation was intentionally limited to maintain a defensive learning focus.

## CVE Research: OpenSSH regreSSHion

As a hands-on exercise, I researched **CVE-2024-6387 (regreSSHion)**, a high-severity vulnerability affecting the OpenSSH `sshd` service. This activity involved analyzing the affected versions, understanding the potential impact, and reviewing mitigation and verification strategies from trusted sources.

This exercise reinforced how defenders analyze real-world vulnerabilities by combining vendor advisories, public databases, and security research.

(See `CVE-Research-(Hands-on).md` for the full CVE analysis.)

## Reflection

This week highlighted the importance of structured vulnerability analysis in defensive security. Rather than focusing on how attacks are executed, the emphasis was on understanding how vulnerabilities are discovered, assessed, and mitigated before exploitation occurs. Learning to interpret CVEs and CVSS scores helped solidify how defenders make informed decisions to reduce organizational risk.

## Resources Used

- TryHackMe — Cyber Security 101  
- TryHackMe — Cryptography & Hashing  
- TryHackMe — Metasploit Introduction  
- National Vulnerability Database (NVD)  
- OpenSSH Security Advisories  