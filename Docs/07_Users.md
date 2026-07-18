\# User Management



\## Purpose



User accounts provide individuals with authenticated access to domain resources such as workstations, file shares, applications, and network services. Proper user account management is essential for maintaining security, enforcing organizational policies, and supporting day-to-day business operations.



This phase focused on creating standardized user accounts, organizing them within departmental Organizational Units (OUs), and assigning appropriate security group memberships based on job responsibilities.



\---



\# User Provisioning Strategy



Users were created within their respective departmental Organizational Units rather than the default \*\*Users\*\* container.



This approach provides several advantages:



\- Simplifies administration

\- Supports future Group Policy deployment

\- Improves organizational structure

\- Makes delegated administration easier

\- Supports enterprise scalability



\---



\# Naming Convention



A consistent naming convention was adopted to simplify administration and improve account identification.



| Attribute | Format | Example |

|----------|---------|---------|

| Username | First initial + Last Name | ecarter |

| Display Name | First Name Last Name | Ethan Carter |

| User Principal Name (UPN) | username@corp.local | ecarter@corp.local |



Consistent naming conventions improve administrative efficiency and reduce the likelihood of duplicate or inconsistent accounts.



\---



\# Administrative Accounts



Administrative accounts are separated from standard user accounts to support the Principle of Least Privilege.



Rather than performing daily activities with privileged credentials, administrators use dedicated administrative accounts only when elevated permissions are required.



Example:



| Standard Account | Administrative Account |

|-----------------|------------------------|

| keave | adm\_keave |



This separation helps reduce the risk of accidental system changes and limits exposure if a standard user account is compromised.



\---



\# Group Membership



Users were assigned to department-specific Global Security Groups based on their job function.



Examples include:



| Department | Security Group |

|------------|----------------|

| IT | GG\_IT\_Staff |

| Human Resources | GG\_HR\_Staff |

| Finance | GG\_Finance\_Staff |

| Marketing | GG\_Marketing\_Staff |

| Sales | GG\_Sales\_Staff |

| Executive | GG\_Executive\_Staff |



This implementation supports Role-Based Access Control (RBAC), allowing permissions to be managed through security groups rather than individual user accounts.



\---



\# Benefits of Group-Based Administration



Managing users through security groups provides several advantages:



\- Simplified permission management

\- Easier onboarding and offboarding

\- Reduced administrative effort

\- Improved security

\- Consistent access control



As employees change roles, administrators only need to modify group membership rather than reconfigure permissions across multiple resources.



\---



\# Validation



The following items were verified:



\- User accounts created successfully

\- User accounts placed in the correct Organizational Units

\- Naming conventions applied consistently

\- User Principal Names configured correctly

\- Security group memberships verified



\---



\# Skills Demonstrated



\- Active Directory User Administration

\- Identity Management

\- User Provisioning

\- Role-Based Access Control (RBAC)

\- Enterprise Account Management



\---



\# Screenshots



Include:



\- Creating a new user

\- Completed user properties

\- Department Organizational Unit with users

\- User added to a security group

\- Administrative account example

