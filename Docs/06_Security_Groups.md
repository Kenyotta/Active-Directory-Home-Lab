\# Security Groups



\## Purpose



Security Groups simplify identity and access management by allowing permissions to be assigned to groups instead of individual user accounts. This approach improves security, reduces administrative overhead, and supports scalable access control as an organization grows.



In this lab, Global Security Groups were created to represent each department and administrative role within the organization.



\---



\# Security Group Design



Each department and administrative team was assigned its own Global Security Group.



This design follows Microsoft's recommended practice of assigning permissions to groups rather than directly to user accounts.



As employees are hired, transferred, or leave the organization, administrators only need to update group membership instead of modifying permissions on individual resources.



\---



\# Security Groups Created



| Security Group | Purpose |

|---------------|---------|

| GG\_Domain\_Admins | Domain administrators |

| GG\_HelpDesk | Help Desk administrators |

| GG\_Executive\_Staff | Executive department users |

| GG\_Finance\_Staff | Finance department users |

| GG\_HR\_Staff | Human Resources users |

| GG\_IT\_Staff | Information Technology users |

| GG\_Marketing\_Staff | Marketing department users |

| GG\_Sales\_Staff | Sales department users |



\---



\# Group Configuration



All groups were configured using the following settings:



| Setting | Value |

|----------|-------|

| Group Scope | Global |

| Group Type | Security |



Global Security Groups were selected because they are the recommended group type for organizing users within a single Active Directory domain.



\---



\# Why Use Security Groups?



Managing permissions through groups provides several advantages:



\- Simplifies user administration

\- Supports the Principle of Least Privilege

\- Reduces configuration errors

\- Makes permission management more efficient

\- Supports future file share permissions

\- Simplifies Group Policy filtering



Rather than assigning permissions directly to individual users, access is granted to security groups. Users inherit permissions through their group membership.



\---



\# Enterprise Best Practice



This project follows Microsoft's recommended approach for identity management:



\*\*Users → Security Groups → Permissions\*\*



For example:



```

Ethan Carter

&#x20;       │

&#x20;       ▼

GG\_IT\_Staff

&#x20;       │

&#x20;       ▼

IT Shared Folder

```



This model improves scalability and makes future administration significantly easier.



\---



\# Validation



The following items were verified:



\- All security groups were successfully created.

\- Group Scope was configured as Global.

\- Group Type was configured as Security.

\- Groups appeared within the Groups Organizational Unit.

\- Naming conventions were applied consistently.



\---



\# Skills Demonstrated



\- Active Directory Administration

\- Security Group Management

\- Identity and Access Management (IAM)

\- Role-Based Access Control (RBAC)

\- Enterprise Infrastructure Design



\---



\# Screenshots



Include:



\- Creating a new security group

\- Security Group properties

\- Completed Groups Organizational Unit

