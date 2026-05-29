# Hands-On — RBAC / ABAC Model

## Role-Based Access Control (RBAC)

RBAC assigns permissions to roles rather than directly to individual users.  
Users are then assigned to roles.

### Roles

- Doctor  
- Nurse  
- Lab Technician  

### Permissions

- Write Orders  
- Read Orders  
- Read Labs  
- Write Labs  

### Role Permissions

**Doctor**
- Write Orders  
- Read Orders  
- Read Labs  

**Nurse**
- Read Orders  
- Read Labs  

**Lab Technician**
- Write Labs  
- Read Labs  

### Explanation

This model improves security and scalability because permissions are attached to roles instead of individuals. If multiple employees share the same job function, I can assign them to a role rather than manually granting permissions to each person.

This reduces misconfiguration risk and helps prevent unauthorized actions such as privilege escalation or improper data modification.

## Attribute-Based Access Control (ABAC)

ABAC makes access decisions based on attributes instead of fixed roles.

### Example Attributes

- Clearance Level  
- Manager Status  
- Department  
- Employee Type  

Access is granted using logical rules based on attribute values.

### Example Rule

IF:
- Clearance Level = High  
- Manager = Yes  
- Department = Finance  

THEN:
- Access to specific financial records is granted  

### Explanation

Unlike RBAC, ABAC evaluates multiple conditions dynamically. This allows more granular and context-aware access control decisions.

RBAC and ABAC can work together. RBAC provides structured role assignment, while ABAC adds flexible policy enforcement based on real-time attributes. It is not an either/or model — combining both can strengthen access control architecture.