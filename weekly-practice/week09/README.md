# Week 09 — Authentication, Authorization & Access Control

## Objective

This week focused on understanding how identity systems control access in modern applications. The goal was to learn the difference between authentication and authorization, and how failures in these systems can lead to serious security issues such as broken access control.

Instead of focusing on exploitation, the emphasis was on understanding how identity, permissions, and monitoring work together to protect systems.

## Identity and Access Concepts

Applications rely on several core components to manage users and permissions.

Key concepts include:

Identity – a unique account that represents a user in a system.

Authentication – verifying that a user is who they claim to be.

Authorization – determining what actions that user is allowed to perform.

Accountability – recording activity so security teams can see who performed actions and when.

Understanding these layers helps explain how applications enforce access control and why failures in these systems are dangerous.

## Access Control Failures

One of the most common security risks is **Broken Access Control**, which occurs when applications fail to properly enforce authorization checks.

A common example is **Insecure Direct Object Reference (IDOR)**, where a user can modify an identifier in a request to access another user's data.

These issues occur when servers trust client requests without verifying permissions, which can expose sensitive information or allow unauthorized actions.

## Hands-On Access Control Modeling

As a practical exercise, I created a simple **RBAC (Role-Based Access Control)** and **ABAC (Attribute-Based Access Control)** model.

The RBAC model assigned permissions to roles such as doctor, nurse, and lab technician rather than to individual users. This approach simplifies permission management and reduces the risk of misconfigured access rights.

The ABAC model demonstrated how access decisions can also be based on attributes such as clearance level, department, or manager status.

This exercise showed how organizations structure permissions to maintain security while keeping systems manageable.

## Reflection

This week clarified the difference between authentication and authorization and how both are necessary to protect systems. Even when authentication is secure, missing authorization checks can still expose sensitive data.

Learning about RBAC and ABAC helped illustrate how organizations manage permissions at scale and why strong access control enforcement is critical for application security.

## Resources Used

TryHackMe — OWASP Top 10: IAAA Failures  
TryHackMe — SOC Fundamentals  
TryHackMe — Search Skills