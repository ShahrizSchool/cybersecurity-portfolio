# Week 05 — Recon & Scanning (Nmap)

## Overview
This week focused on reconnaissance and network scanning fundamentals, with an emphasis on understanding how hosts and services are discovered at the network level. I explored both the theoretical side of scanning and the practical behavior of Nmap scans in a controlled lab environment.

## What I Did This Week
- Reviewed core networking concepts and protocols relevant to scanning and reconnaissance
- Learned how Nmap performs host discovery, port scanning, and service detection
- Practiced multiple Nmap scan types in a safe home lab setup
- Used Wireshark alongside Nmap to observe scan behavior at the packet level
- Analyzed why certain scans complete or fail based on service availability and network configuration

## Hands-on Experience
- Performed host discovery scans on NAT and host-only networks
- Compared list scans, ping scans, TCP connect scans, and UDP scans
- Observed TCP SYN, RST, and ICMP responses using Wireshark
- Verified how closed ports and non-listening services affect scan results

## Key Takeaways
- A full TCP three-way handshake only occurs when a service is actively listening
- Closed ports actively refuse connections rather than silently dropping them
- Wireshark provides valuable context that explains Nmap scan output

## Artifacts
- Nmap Hands-on Practice Lab
- Wireshark packet captures (screenshots)
- TryHackMe notes covering networking concepts and Nmap basics

This week helped solidify how reconnaissance works in practice and how scan results map directly to network behavior.
