\# Lab Architecture



\## Overview



This lab simulates the core infrastructure of a small-to-medium enterprise Windows environment. The environment is hosted locally using Oracle VirtualBox and is designed to provide hands-on experience with Active Directory administration and enterprise systems management.



The initial deployment consists of a single Windows Server 2022 Domain Controller (`DC01`) running Active Directory Domain Services (AD DS) and DNS. Additional systems, including a Windows 11 client, will be integrated as the project progresses.



\---



\## Environment



| Component | Details |

|-----------|---------|

| Hypervisor | Oracle VirtualBox |

| Domain Controller | DC01 |

| Operating System | Windows Server 2022 |

| Domain | corp.local |

| Forest | corp.local |

| Server Roles | Active Directory Domain Services (AD DS), DNS |

| Client Operating System | Windows 11 (Planned) |



\---



\## Network Configuration



| Adapter | Purpose |

|----------|---------|

| NAT | Internet connectivity |

| Internal Network (LABNET) | Communication between lab systems |



\### Static Addressing



| Device | IP Address |

|---------|------------|

| DC01 | 192.168.10.10 |



\---



\## Active Directory Design



The Active Directory environment follows a structured Organizational Unit (OU) design to separate administrative accounts, departments, computers, and servers. Security groups are implemented using Global Security Groups to simplify permission management and support future expansion.



\---



\## Future Expansion



Planned additions include:



\- Windows 11 domain client

\- Group Policy Objects (GPOs)

\- File Server

\- Shared folders and NTFS permissions

\- Additional administrative tasks

\- PowerShell automation



\---



\## Skills Demonstrated



\- Windows Server Deployment

\- Network Configuration

\- Active Directory Design

\- DNS Configuration

\- Infrastructure Planning

