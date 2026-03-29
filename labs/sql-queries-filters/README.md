# SQL Filtering for Security Analysis

## Overview
This lab focuses on using SQL filtering techniques to investigate security-related data and retrieve specific employee information. The objective was to analyze login activity, identify suspicious behavior, and filter employee records using structured queries.

The lab demonstrates how SQL can be used in a defensive security context to narrow down large datasets and extract meaningful information.

## Objectives
- Investigate failed login attempts after business hours
- Retrieve login activity on specific dates
- Identify login attempts from outside a specific region
- Filter employees by department and office location
- Exclude employees from a specific department
- Practice using SQL filtering operators for analysis

## Skills Demonstrated
- SQL query construction
- Data filtering using `WHERE`
- Logical operators (`AND`, `OR`, `NOT`)
- Pattern matching using `LIKE`
- Security-focused log analysis
- Database investigation techniques

## Queries Covered
- After-hours failed login attempts
- Login attempts on specific dates
- Login attempts outside of Mexico
- Employees in Marketing (East offices)
- Employees in Finance or Sales
- Employees not in IT

## Tools Used
- Google Certificate Lab
- SQL
- Linux terminal environment

## Key Concepts
This lab focused on applying filtering logic to narrow results:
- `AND` to require multiple conditions
- `OR` to match either condition
- `NOT` to exclude values
- `LIKE` for pattern matching

## Security Relevance
Filtering database logs is a core skill in security analysis. These queries simulate real-world tasks such as:
- Detecting suspicious login attempts
- Identifying activity outside business hours
- Reviewing access from unexpected locations
- Filtering employee records during investigations

## Files
- `apply-filters-sql.md` — Full lab report with queries and explanations
- `screenshots/` — Query results 