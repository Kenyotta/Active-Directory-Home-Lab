\# Organizational Units



\## Purpose



Organizational Units (OUs) provide a logical structure for organizing users, computers, and administrative resources within Active Directory. Proper OU design simplifies administration, supports delegated management, and enables targeted Group Policy deployment.



The OU hierarchy in this lab was designed to resemble the structure of a small-to-medium enterprise while following Active Directory best practices.



\---



\# Organizational Unit Design



The Active Directory environment was organized into dedicated Organizational Units to separate administrative resources, departments, computers, and servers.



This design improves scalability, simplifies administration, and prepares the environment for future Group Policy implementation.



\---



\# Organizational Structure



```

corp.local

│

├── Admin

│   ├── Domain Admins

│   └── Help Desk

│

├── Departments

│   ├── Executive

│   ├── Finance

│   ├── Human Resources

│   ├── IT

│   ├── Marketing

│   └── Sales

│

├── Groups

│

├── Servers

│

├── Service Accounts

│

├── Test Accounts

│

└── Workstations

&#x20;   ├── Desktops

&#x20;   └── Laptops

```



\---



\# Design Decisions



Several best practices were incorporated into the OU structure.



\## Administrative Separation



Administrative accounts were separated from standard user accounts.



This approach supports the Principle of Least Privilege by allowing privileged accounts to be managed independently from everyday user accounts.



\---



\## Departmental Organization



Each department was assigned its own Organizational Unit.



Benefits include:



\- Easier user administration

\- Simplified permission management

\- Department-specific Group Policies

\- Better scalability as the organization grows



\---



\## Computer Organization



Computer objects will be placed into dedicated Workstation and Server Organizational Units.



Separating computers by role allows Group Policy Objects (GPOs) to target desktops, laptops, and servers independently.



\---



\## Service Accounts



A dedicated OU was created for service accounts.



Separating service accounts from standard user accounts simplifies administration and supports stronger security practices.



\---



\## Test Accounts



A Test Accounts OU was created to safely validate configurations, permissions, and Group Policy changes without affecting production-style user accounts.



\---



\# Validation



The Organizational Unit hierarchy was verified by:



\- Confirming all OUs were successfully created

\- Verifying the hierarchy within Active Directory Users and Computers

\- Confirming administrative and departmental separation

\- Reviewing the structure for future scalability



\---



\# Best Practices Applied



\- Logical OU hierarchy

\- Administrative account separation

\- Department-based organization

\- Dedicated computer Organizational Units

\- Support for future Group Policy deployment

\- Scalable enterprise design



\---



\# Skills Demonstrated



\- Active Directory Administration

\- Organizational Unit Design

\- Enterprise Planning

\- Identity Management

\- Infrastructure Organization



\---



\# Screenshots



Include:



\- Root OU hierarchy

\- Admin OU

\- Department OUs

\- Workstations OU

\- Complete Organizational Unit structure

