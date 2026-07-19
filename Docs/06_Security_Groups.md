# Security Groups

## Overview

Security Groups are a fundamental component of Active Directory that simplify access management by allowing permissions to be assigned to groups rather than individual users. This approach supports Role-Based Access Control (RBAC), reduces administrative overhead, and improves the scalability of the environment.

In this lab, department-specific security groups were created to manage access to shared resources and demonstrate enterprise access control practices.

---

# Objectives

The goals of this phase were to:

- Create department-based security groups
- Assign users to appropriate groups
- Prepare groups for Role-Based Access Control (RBAC)
- Simplify permission management
- Follow enterprise identity management best practices

---

# Security Groups Created

The following Global Security Groups were created within the **corp.local** domain:

| Group Name | Purpose |
|------------|---------|
| GG_IT_Staff | IT department users |
| GG_HR_Staff | Human Resources users |
| GG_Finance_Staff | Finance department users |

Each group represents a department within the organization and serves as the primary method for assigning access to shared resources.

---

# Group Scope

All groups were configured as:

- **Group Type:** Security
- **Group Scope:** Global

Global Security Groups are commonly used to organize users with similar job functions and are recommended for assigning permissions within a single Active Directory domain.

---

# Role-Based Access Control (RBAC)

Rather than assigning permissions directly to individual user accounts, permissions are assigned to security groups.

The access model follows this structure:

```
User
   │
   ▼
Security Group
   │
   ▼
Shared Resource
```

For example:

```
Ethan Carter
      │
      ▼
GG_IT_Staff
      │
      ▼
\\DC01\IT
```

This design allows administrators to grant or revoke access by changing group membership rather than modifying permissions on individual resources.

---

# Benefits of Security Groups

Using Security Groups provides several advantages:

- Simplifies permission management
- Supports Role-Based Access Control (RBAC)
- Reduces administrative effort
- Improves consistency
- Enhances security
- Scales efficiently as organizations grow

For example, when a new IT employee joins the company, adding the user to **GG_IT_Staff** automatically grants access to all resources assigned to that group.

---

# Enterprise Best Practices Applied

The following best practices were implemented:

- Department-based groups
- Global Security Groups for user accounts
- Group-based permission assignments
- Separation of users and permissions
- Consistent naming convention using the **GG_** prefix

These practices align with common enterprise Active Directory administration standards.

---

# Validation

After creating the security groups, Active Directory Users and Computers was used to verify:

- All groups were successfully created
- Groups appeared in the appropriate Organizational Units
- Group scope was configured as Global
- Group type was configured as Security

User membership was later validated during authentication and file access testing.

---

# Relationship to File Permissions

The security groups created during this phase were later used to control access to departmental file shares.

Examples include:

| Security Group | Resource |
|---------------|----------|
| GG_IT_Staff | IT Share |
| GG_HR_Staff | HR Share |
| GG_Finance_Staff | Finance Share |

This demonstrates how Active Directory groups integrate with Windows file permissions to provide centralized access management.

---

# Summary

Security Groups provide a scalable and efficient method for managing permissions in Active Directory. By assigning permissions to groups instead of individual users, the environment follows Role-Based Access Control principles, simplifies administration, and reflects common enterprise identity and access management practices.