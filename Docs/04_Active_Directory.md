\# Active Directory Domain Services



\## Purpose



Active Directory Domain Services (AD DS) provides centralized authentication, authorization, and identity management for Windows-based enterprise environments. By promoting the server to a Domain Controller, the lab gained the ability to centrally manage users, computers, groups, and security policies.



This phase established the foundation of the enterprise environment by deploying a new Active Directory forest and configuring the server as the first Domain Controller.



\---



\# Installing Active Directory Domain Services



Active Directory Domain Services was installed using Server Manager through the \*\*Add Roles and Features Wizard\*\*.



The following server roles were installed:



\- Active Directory Domain Services (AD DS)

\- DNS Server

\- Group Policy Management



The required management tools were installed automatically during the role installation.



\---



\# Domain Controller Promotion



After the AD DS role was installed, the server was promoted to the first Domain Controller in a new Active Directory forest.



\### Forest Configuration



| Setting | Value |

|----------|-------|

| Forest Root Domain | corp.local |

| NetBIOS Name | CORP |

| Forest Functional Level | Windows Server 2016 |

| Domain Functional Level | Windows Server 2016 |



\---



\# Domain Controller Configuration



The following services were configured during promotion:



\- Domain Name System (DNS)

\- Global Catalog (GC)

\- SYSVOL

\- Active Directory Database (NTDS)



The server was configured as the first Global Catalog within the forest to provide authentication and directory lookup services.



\---



\# DNS Configuration



DNS was installed alongside Active Directory and configured automatically during Domain Controller promotion.



DNS provides:



\- Name resolution

\- Active Directory service location

\- Domain authentication support



Following installation, the \*\*corp.local\*\* Forward Lookup Zone was created automatically.



\---



\# Validation



After the server restarted, the following items were verified:



\- Active Directory Users and Computers opened successfully.

\- DNS Manager displayed the corp.local zone.

\- The server authenticated using the CORP domain.

\- Server Manager reported the AD DS role as installed.

\- Domain Controller promotion completed successfully.



\---



\# Why Active Directory Matters



Active Directory provides centralized administration for enterprise environments.



Instead of maintaining separate local accounts on every workstation, administrators manage identities from a single location. This allows organizations to implement consistent security policies, simplify user administration, and control access to network resources.



\---



\# Skills Demonstrated



\- Active Directory Domain Services

\- Windows Server Administration

\- Domain Controller Deployment

\- DNS Administration

\- Identity and Access Management

\- Enterprise Infrastructure Deployment



\---



\# Screenshots



Include screenshots of:



\- Add Roles and Features Wizard

\- AD DS installation complete

\- Promote this server to a Domain Controller

\- Domain Controller Options

\- Active Directory Users and Computers

\- DNS Manager

\- Server Manager after promotion

