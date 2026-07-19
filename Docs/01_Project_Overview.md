\# Project Overview



\## Objective



The objective of this project was to design, deploy, and validate a small enterprise Active Directory environment that demonstrates the core responsibilities of a Windows Server administrator. The lab focuses on centralized identity management, authentication, authorization, security policy enforcement, and secure resource access using Microsoft Active Directory Domain Services (AD DS).



Rather than simply installing Windows Server, this project simulates the deployment of a corporate network where users, departments, security groups, Group Policy Objects (GPOs), and shared resources are managed from a centralized domain controller.



\---



\# Project Scope



This lab includes the deployment and configuration of the following enterprise technologies:



\- Windows Server 2022 Domain Controller

\- Active Directory Domain Services (AD DS)

\- Domain Name System (DNS)

\- Organizational Units (OUs)

\- Security Groups

\- Domain User Accounts

\- Group Policy

\- SMB File Services

\- NTFS Permissions

\- Windows 11 Domain-Joined Client



\---



\# Business Scenario



A fictional organization requires a centralized directory service to manage employee identities, departmental resources, and security policies.



The organization consists of multiple departments including:



\- Information Technology (IT)

\- Human Resources (HR)

\- Finance



Each department requires:



\- Dedicated user accounts

\- Department-specific security groups

\- Controlled access to shared folders

\- Centralized password policies

\- Consistent workstation security settings



Instead of configuring each workstation individually, administrators manage the environment from a single domain controller using Active Directory and Group Policy.



\---



\# Project Goals



The primary goals of this project were to:



\- Deploy a functional Active Directory domain.

\- Configure centralized authentication and authorization.

\- Organize directory objects using Organizational Units.

\- Implement Role-Based Access Control (RBAC).

\- Secure departmental file shares using Share and NTFS permissions.

\- Apply enterprise security policies through Group Policy Objects.

\- Join a Windows 11 workstation to the domain.

\- Validate user authentication and resource access.



\---



\# Enterprise Concepts Demonstrated



This project demonstrates several core Windows Server administration concepts commonly used in enterprise environments.



\### Identity Management



Active Directory provides centralized management of users, groups, and computers.



\### Authentication



Users authenticate against the domain controller rather than maintaining separate local accounts on every workstation.



\### Authorization



Access to resources is determined by group membership and assigned permissions instead of assigning permissions directly to individual users.



\### Role-Based Access Control (RBAC)



Departmental security groups are used to simplify permission management and improve scalability.



\### Centralized Administration



Administrative tasks such as password policies, workstation security, and account management are performed centrally from the domain controller.



\---



\# Expected Outcomes



Upon completion of this project, the environment successfully demonstrated:



\- Centralized domain authentication

\- DNS name resolution

\- Organizational Unit management

\- User and group administration

\- Group Policy deployment

\- Secure departmental file sharing

\- Domain workstation integration

\- Validation of authentication and authorization controls



\---



\# Skills Developed



This project provided practical experience in:



\- Windows Server Administration

\- Active Directory Administration

\- DNS Configuration

\- Organizational Unit Design

\- Security Group Management

\- Group Policy Management

\- SMB File Sharing

\- NTFS Permission Management

\- Domain Administration

\- Enterprise Troubleshooting

\- Role-Based Access Control (RBAC)

\- Windows Client Management



\---



\# Summary



This lab demonstrates the deployment of a functional enterprise Active Directory environment that closely reflects real-world Windows domain administration. By integrating identity management, security policies, and controlled access to shared resources, the project provides hands-on experience with the technologies and administrative practices commonly used in corporate IT environments.

