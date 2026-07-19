\# Active Directory Domain Services



\## Overview



Active Directory Domain Services (AD DS) provides centralized identity and access management for Windows environments. In this lab, Windows Server 2022 was promoted to a Domain Controller, creating the \*\*corp.local\*\* domain. This enabled centralized authentication, authorization, DNS services, and policy management for all domain-joined systems.



\---



\# Objectives



The goals of this phase were to:



\- Install the Active Directory Domain Services role

\- Promote the server to a Domain Controller

\- Create a new Active Directory forest

\- Configure DNS integration

\- Verify successful domain deployment



\---



\# Server Configuration



| Setting | Value |

|----------|-------|

| Server Name | DC01 |

| Operating System | Windows Server 2022 |

| Domain Name | corp.local |

| Forest Functional Level | Windows Server 2016 (Default) |

| DNS | Installed with AD DS |



\---



\# Installing Active Directory Domain Services



The \*\*Active Directory Domain Services\*\* server role was installed using \*\*Server Manager\*\*.



During installation, the following components were included:



\- Active Directory Domain Services

\- Management Tools

\- DNS Server



Installing these components prepared the server for promotion to a Domain Controller.



\---



\# Domain Controller Promotion



After the AD DS role was installed, the server was promoted to a Domain Controller.



A new Active Directory forest was created with the following domain:



```

corp.local

```



During promotion, the following settings were configured:



\- New Forest

\- Domain Name: corp.local

\- DNS Server Installed

\- Global Catalog Enabled

\- Directory Services Restore Mode (DSRM) password configured



The server automatically restarted after the promotion process completed.



\---



\# DNS Integration



DNS was installed alongside Active Directory to support domain services.



DNS provides:



\- Name resolution

\- Domain controller location

\- Client authentication

\- Active Directory replication support



The Domain Controller was configured to use itself as its preferred DNS server.



\---



\# Validation



After the server restarted, several validation steps were performed.



Successful verification included:



\- Logging into the domain

\- Opening Active Directory Users and Computers

\- Opening DNS Manager

\- Confirming the \*\*corp.local\*\* domain existed

\- Verifying the Domain Controller appeared under the Domain Controllers organizational unit



These checks confirmed that the Domain Controller and Active Directory services were operating correctly.



\---



\# Why Active Directory?



Using Active Directory centralizes administration across an organization.



Benefits include:



\- Centralized user management

\- Centralized authentication

\- Simplified authorization

\- Group-based access control

\- Centralized security policy enforcement

\- Scalable management of users and computers



Without Active Directory, each workstation would require separate local user accounts and independent configuration, increasing administrative overhead and reducing security.



\---



\# Enterprise Best Practices Applied



The deployment followed several enterprise administration best practices:



\- Dedicated Domain Controller

\- Static IP addressing

\- Integrated DNS

\- Centralized authentication

\- New forest deployment

\- Separation of identity management from client systems



These practices provide a secure and scalable foundation for managing Windows environments.



\---



\# Summary



Deploying Active Directory Domain Services established the core identity infrastructure for the lab environment. By creating the \*\*corp.local\*\* domain and promoting \*\*DC01\*\* to a Domain Controller, the environment gained centralized authentication, DNS services, and the foundation required for Organizational Units, Security Groups, Group Policy, and domain-joined client management.

