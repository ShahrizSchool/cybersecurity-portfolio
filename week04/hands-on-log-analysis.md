# Week 04 — Hands-On Log Analysis

## Objective
The goal of this hands-on exercise was to analyze Linux authentication logs and identify suspicious activity by constructing a simple event timeline.

## Log Location
The authentication log analyzed in this exercise was:
`/var/log/syslog`

## Actions Performed
- Opened the authentication log using `cat` and `less`
- Simulated failed login attempts using incorrect credentials
- Observed how failed and successful authentication events were recorded
- Identified abnormal patterns based on event timing

## Evidence Screenshot
The following screenshot shows a portion of the authentication log containing failed and successful login events observed during this exercise:

![Authentication Log Evidence](./week04-auth-log.png)

## Timeline of Observed Events
2026-01-14 20:19:49 → Failed password authentication for user → indicates failed access attempt
2026-01-14 20:19:54 → Failed password authentication for user → repeated attempt, potential brute-force
2026-01-14 20:19:59 → Successful login for user → concerning if not expected after failures

## Analysis Notes
The close timing between multiple failed authentication attempts followed by a successful login is noteworthy. While these events were intentionally generated for this exercise, a similar pattern in a real environment could indicate unauthorized access.

This exercise demonstrates how authentication logs provide early indicators of compromise and support incident investigation through timeline reconstruction.
