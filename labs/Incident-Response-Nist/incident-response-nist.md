# Incident Response Analysis Using NIST Cybersecurity Framework (CSF)

## Summary
The organization experienced a Denial of Service (DoS) attack that compromised the internal network for two hours. During the incident, internal network traffic could not access network resources. The security team noticed that the network was not responding to normal traffic and identified a flood of ICMP packets. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services, and restoring critical network services.

After the event, the security team conducted an investigation and determined that a threat actor exploited an unconfigured firewall to flood the network with ICMP packets, resulting in the denial-of-service condition.

## Identify
The incident management team reviewed the network systems, tools, and access policies involved in the attack to identify gaps in security. The investigation revealed that an unconfigured firewall allowed malicious ICMP traffic into the network. This vulnerability enabled the attacker to overwhelm the internal network, preventing normal traffic from accessing network resources.

## Protect
To protect internal assets, the network security team implemented a new firewall rule to limit the rate of incoming ICMP packets. Source IP address verification was also configured to detect spoofed IP addresses within incoming ICMP traffic.

## Detect
To improve detection capabilities, the organization implemented network monitoring software to identify abnormal traffic patterns. Additionally, an IDS/IPS system was deployed to filter ICMP traffic based on suspicious characteristics and provide alerts for potential attacks.

## Respond
During the incident, the team blocked incoming ICMP packets and stopped non-critical network services to reduce the impact of the attack. As part of the response improvements, the organization plans to maintain firewall configurations regularly and implement network segmentation to limit the scope of future incidents.

## Recover
To recover from the incident, the team restored critical network services first, followed by non-critical services. Internal staff were notified about the service restoration process. The organization gradually returned systems to normal operation after confirming that the malicious traffic had been mitigated.