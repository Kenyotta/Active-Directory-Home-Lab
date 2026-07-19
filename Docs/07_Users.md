\# Domain Users



\## Overview



User accounts represent the identities of individuals within an Active Directory environment. Rather than creating local accounts on each workstation, Active Directory centralizes user management, allowing authentication, authorization, and resource access to be controlled from the Domain Controller.



In this lab, representative users were created for multiple departments and assigned to department-specific security groups to demonstrate centralized identity management and Role-Based Access Control (RBAC).



\---



\# Objectives



The goals of this phase were to:



\- Create domain user accounts

\- Organize users within Organizational Units

\- Assign users to Security Groups

\- Implement Role-Based Access Control (RBAC)

\- Prepare users for authentication and file access testing



\---



\# User Accounts Created



The following domain users were created during this lab:



| User | Username | Department | Security Group |

|------|----------|------------|----------------|

| Ethan Carter | ecarter | IT | GG\_IT\_Staff |

| Sophia Reed | sreed | HR | GG\_HR\_Staff |

| Liam Turner | lturner | Finance | GG\_Finance\_Staff |



Each account represents a typical employee within the organization and is managed centrally through Active Directory.



\---



\# User Organization



Each user account was placed in the appropriate Organizational Unit (OU) based on department.



```

corp.local

│

├── IT

│     └── Ethan Carter

│

├── HR

│     └── Sophia Reed

│

└── Finance

&#x20;     └── Liam Turner

```



Organizing users by department simplifies administration and supports targeted Group Policy deployment.



\---



\# Group Membership



Each user was added to the appropriate department Security Group.



| User | Group Membership |

|------|------------------|

| Ethan Carter | Domain Users, GG\_IT\_Staff |

| Sophia Reed | Domain Users, GG\_HR\_Staff |

| Liam Turner | Domain Users, GG\_Finance\_Staff |



Using Security Groups instead of assigning permissions directly to users follows Microsoft's recommended administration model.



\---



\# Account Configuration



Each user account was configured with:



\- Unique username

\- Secure password

\- User must change password at first logon

\- Enabled account

\- Membership in the appropriate Security Group



These settings reflect common practices when provisioning new employees in an enterprise environment.



\---



\# Authentication Process



When a domain user signs in to a domain-joined workstation:



1\. The workstation contacts the Domain Controller.

2\. Active Directory validates the user's credentials.

3\. Group memberships are evaluated.

4\. Group Policy Objects (GPOs) are applied.

5\. The user receives access only to authorized resources.



This centralized authentication process ensures consistent security across all domain-joined systems.



\---



\# Role-Based Access Control (RBAC)



Access to resources is determined by Security Group membership rather than individual user permissions.



Example:



```

Ethan Carter

&#x20;     │

&#x20;     ▼

GG\_IT\_Staff

&#x20;     │

&#x20;     ▼

IT Department Share

```



This design simplifies administration by allowing access changes to be made through group membership instead of modifying resource permissions for individual users.



\---



\# Validation



The following validation steps were completed:



\- User accounts successfully created

\- Users placed in the correct Organizational Units

\- Group memberships verified

\- Users authenticated successfully to the domain

\- Password change at first logon completed

\- Successful access to authorized resources confirmed

\- Unauthorized access to restricted departmental resources denied



These tests verified that user provisioning and RBAC were functioning as intended.



\---



\# Enterprise Best Practices Applied



The user management process followed several enterprise best practices:



\- Unique user accounts for each employee

\- Department-based Organizational Units

\- Group-based permission management

\- Least Privilege access model

\- Centralized authentication

\- Standardized account provisioning



These practices improve security, simplify administration, and support future growth of the Active Directory environment.



\---



\# Summary



The creation of domain user accounts established centralized identity management within the Active Directory environment. By organizing users into departmental Organizational Units and assigning them to Security Groups, the lab demonstrates how enterprises implement secure, scalable authentication and authorization using Role-Based Access Control.

