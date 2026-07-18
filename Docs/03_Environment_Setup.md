\# Environment Setup



\## Purpose



Before deploying Active Directory, a stable and properly configured Windows Server environment was prepared. This phase focused on creating the virtual infrastructure, configuring networking, and preparing the server for enterprise services.



A properly configured environment is critical because Active Directory relies on consistent networking, static IP addressing, and reliable server configuration.



\---



\## Environment Specifications



| Component | Configuration |

|----------|---------------|

| Hypervisor | Oracle VirtualBox |

| Virtual Machine | DC01 |

| Operating System | Windows Server 2022 Standard Evaluation |

| Computer Name | DC01 |

| Domain | corp.local (configured later) |



\---



\## Virtual Machine Configuration



The Domain Controller was deployed as a virtual machine using Oracle VirtualBox. The virtual machine provides an isolated environment that closely simulates enterprise infrastructure while remaining portable and easy to manage.



The VM was configured with sufficient resources to support Active Directory Domain Services (AD DS), DNS, and future lab expansion.



\---



\## Network Configuration



Two virtual network adapters were configured.



\### Adapter 1 – NAT



Purpose:



\- Internet connectivity

\- Windows Updates

\- Software downloads



\### Adapter 2 – Internal Network (LABNET)



Purpose:



\- Private communication between lab devices

\- Active Directory traffic

\- Domain communication

\- Future Windows 11 client connectivity



\---



\## Static IP Configuration



Because Domain Controllers should maintain a consistent network identity, the Internal Network adapter was assigned a static IPv4 address.



| Setting | Value |

|---------|-------|

| IP Address | 192.168.10.10 |

| Subnet Mask | 255.255.255.0 |

| Preferred DNS | 192.168.10.10 |



The NAT adapter remained configured for DHCP to maintain Internet access while keeping domain traffic isolated on the LABNET network.



\---



\## Validation



The following items were verified before Active Directory installation:



\- Windows Server installed successfully

\- Server renamed to DC01

\- Static IP address configured

\- Internet connectivity verified

\- Internal network operational

\- Server Manager functioning normally



\---



\## Key Takeaways



Establishing a stable server and network configuration before installing Active Directory helps ensure reliable domain services and reduces future configuration issues.



\---



\## Skills Demonstrated



\- Oracle VirtualBox Administration

\- Windows Server Deployment

\- Network Configuration

\- Static IP Addressing

\- Windows Server Administration



\---



\## Screenshots



Add screenshots for:



\- VirtualBox VM settings

\- Network adapter configuration

\- Windows network adapter settings

\- Static IPv4 configuration

\- Server Manager (Local Server)

