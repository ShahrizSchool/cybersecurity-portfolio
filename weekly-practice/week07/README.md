# Week 07 — Web Foundations (HTTP & Sessions)

## Objective

This week focused on understanding how web applications communicate and manage authentication at a network level. The goal was to build a foundational, defensive understanding of HTTP, secure protocols, and session behavior by observing real traffic rather than relying solely on theoretical descriptions.

Instead of performing attacks, the emphasis was on learning how defenders and analysts interpret normal web behavior in order to recognize abnormal or insecure patterns later.

## Web Application Communication Basics

This week introduced how web applications operate across the client–server boundary. I explored how browsers interact with web servers using HTTP requests and responses, and how these interactions form the basis of all web application functionality.

Key ideas included:
- The role of the browser as the client and the web server as the responder
- How URLs are structured and interpreted by servers
- The separation between front-end components and back-end systems
- Why user-controlled inputs (such as URLs and form fields) must be handled securely

This reinforced how even basic web navigation relies on structured communication that can become a security risk if mishandled.

## HTTP Requests, Responses, and Methods

A major focus of the week was understanding the structure of HTTP messages and how they are used in practice.

Topics covered included:
- HTTP request and response structure (start line, headers, body)
- Common HTTP methods such as GET and POST and their intended use cases
- The significance of HTTP status codes, particularly successful responses and redirects
- How headers provide metadata that influences how requests and responses are processed

Understanding these fundamentals helped clarify how user actions in the browser translate into network-level behavior.

## Secure Protocols and Encrypted Communication

This week also explored how secure protocols protect web traffic and remote access.

Key protocols included:
- TLS and HTTPS for encrypted web communication
- SSH and secure file transfer mechanisms
- VPNs as a method for securely connecting networks over untrusted infrastructure

These topics reinforced the importance of encryption, authentication, and integrity in preventing interception or manipulation of data during transmission.

## JavaScript and Client-Side Behavior

JavaScript fundamentals were introduced to provide context for how modern web applications behave dynamically within the browser.

Rather than focusing on development, the emphasis was on:
- Understanding how JavaScript affects page behavior
- Recognizing how scripts trigger additional network requests
- Identifying why modern web applications generate significant background traffic

This helped explain why authentication flows can be harder to isolate on real-world websites.

## Hands-On Network Observation (Defensive Perspective)

As a hands-on exercise, I used browser developer tools to observe HTTP traffic before and after logging into websites. This analysis was performed on both a minimal test site and a real-world application.

Through this process, I observed that:
- Logging in is not a single request, but a sequence of requests and redirects
- Authentication is confirmed through server behavior after login, not just credential submission
- Real-world websites generate substantially more traffic after login, making analysis more complex

This exercise emphasized the importance of comparing behavior before and after authentication rather than attempting to understand every individual request.

(See `Hands-on-Web-Foundations.md` for detailed observations)

## Reflection

Week 7 highlighted how foundational web concepts directly impact security analysis. While HTTP and web protocols may appear simple at a high level, observing real traffic demonstrated how complexity increases quickly in modern applications.

Learning to interpret network behavior rather than individual requests reinforced a defensive mindset: understanding what “normal” looks like is essential before identifying vulnerabilities or misconfigurations. This week established a strong base for future topics involving sessions, authentication mechanisms, and web application security testing.

## Resources Used

- TryHackMe — Web Application Basics  
- TryHackMe — JavaScript Essentials  
- TryHackMe — Networking Essentials  
- TryHackMe — Secure Networking Protocols  
- Chrome DevTools Documentation  
