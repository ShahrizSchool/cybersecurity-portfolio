# DNS Network Traffic Incident Analysis

## Objective
Analyze DNS and ICMP network traffic logs to determine why users were unable to access a website.

## Scenario
Users reported that they were unable to access `yummyrecipesforme.com` and received the error message **"destination port unreachable"** when attempting to load the page.

A network traffic log was provided showing DNS requests sent to a DNS server using UDP port 53. The log also showed ICMP responses indicating **"UDP port 53 unreachable"**, meaning the DNS server was not responding to DNS queries. Because the DNS request failed, the system could not resolve the domain name to an IP address, preventing the website from loading.

## Analysis Method
The provided network traffic log was examined to identify the protocol being used, the source and destination IP addresses, and the error messages returned in the ICMP responses.

## Key Finding
The DNS server responsible for resolving the domain name was unreachable on **UDP port 53**, causing DNS resolution to fail.

## Full Incident Report
Refer to the **Incident Report: Network Traffic Analysis** in this folder for the full investigation details.