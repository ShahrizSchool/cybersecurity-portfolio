# Week 08 — Databases, Burp Suite & Web Application Design Flaws

## Objective

This week focused on understanding how databases support web applications and how insecure design decisions create real-world vulnerabilities. The goal was to move from observing web communication (Week 07) to analyzing how applications process data behind the scenes.

Rather than focusing on exploitation, the emphasis was on understanding how defenders identify insecure behavior in database interactions, application logic, and server-side validation. The hands-on lab reinforced how small validation failures can cascade into larger systemic risks.

## SQL and Database Foundations

This week began with structured database fundamentals. I explored how relational databases store and manage structured information, and how web applications rely on these systems to handle user accounts, products, transactions, and authentication data.

Key ideas included:

- The structure of relational databases (tables, rows, columns)
- Primary keys and foreign keys for linking records
- CRUD operations (Create, Read, Update, Delete)
- SQL query structure and common clauses such as WHERE, GROUP BY, and ORDER BY
- Logical and comparison operators used to filter data

Understanding how SQL works clarified how user input eventually becomes database queries — and why improper handling of input can lead to serious vulnerabilities.

## Web Proxy Analysis with Burp Suite

This week introduced practical web traffic inspection using Burp Suite Community Edition.

Instead of observing traffic passively (as in Week 07), I actively intercepted and analyzed HTTP requests and responses in a controlled lab environment.

Core tools explored:

- Proxy: Intercepting live HTTP traffic  
- Repeater: Modifying and resending requests  
- Intruder: Automating repeated requests for testing behavior  
- Decoder: Interpreting encoded data such as Base64 and JWT tokens  

This shifted my understanding from theoretical HTTP structure to interactive request analysis. I was able to observe how modifying parameters changes server behavior and how servers respond to unexpected inputs.

## Application Design Flaws

This week introduced formal vulnerability categories aligned with the OWASP Top 10 framework.

Concepts studied included:

- Security Misconfiguration: Unsafe defaults or exposed services  
- Software Supply Chain Failures: Risks from outdated or compromised dependencies  
- Cryptographic Failures: Incorrect or missing encryption  
- Insecure Design: Logical flaws embedded into system architecture  

This connected the hands-on findings to recognized industry standards.

## Hands-On Web Application Analysis

As a practical exercise, I analyzed OWASP Juice Shop within my homelab using Burp Suite.

Through structured observation and controlled request modification, I identified several insecure behaviors:

- Client-side validation that could be manipulated
- Excessive data exposure in API responses
- Authorization weaknesses when referencing object IDs
- Business logic flaws involving numeric validation
- Hidden functionality accessible through predictable identifiers

Rather than focusing on bypassing controls, I documented how each issue resulted from missing server-side validation or improper access control enforcement.

Each finding demonstrated how application security depends on strict validation, minimal data exposure, and consistent authorization checks.

(See `Burpsuite-Handson.md` for detailed observations and screenshots.)

## Reflection

Observing how database interactions, tokens, object references, and request parameters influence server behavior made the risks of insecure design much clearer.

This week reinforced that many vulnerabilities are not advanced exploits, they are the result of missing validation, improper authorization, or misplaced trust.

Understanding how these flaws emerge from everyday design decisions strengthened my defensive mindset and prepared me for deeper web application security analysis.

## Resources Used
- TryHackMe — SQL Fundamentals  
- TryHackMe — Burp Suite: The Basics  
- TryHackMe — OWASP Top 10 (Application Design Flaws)  
- OWASP Juice Shop (Home Lab)  
- Burp Suite Community Edition  