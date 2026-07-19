\# Environment Setup



\## Overview



Before deploying Active Directory Domain Services (AD DS), a virtual enterprise environment was created using Oracle VirtualBox. The environment consists of two virtual machines connected through separate virtual networks to simulate a production Windows domain while maintaining Internet connectivity.



This section documents the deployment of the virtualization environment, installation of Windows Server 2022 and Windows 11, and the initial network configuration required to support Active Directory.



\---



\# Lab Environment



\## Host System



The lab was built on a Windows host computer using Oracle VirtualBox as the virtualization platform.



\## Virtualization Platform



\- Oracle VirtualBox 7.x

\- Windows Host Operating System



VirtualBox provides isolated virtual networking, allowing the domain controller and client workstation to communicate securely without affecting the physical home network.



\---



\# Virtual Machines



\## Domain Controller (DC01)



| Setting | Value |

|----------|-------|

| Operating System | Windows Server 2022 |

| Hostname | DC01 |

| Domain | corp.local |

| Memory | 4 GB RAM |

| Processor | 2 vCPUs |

| Storage | Virtual Hard Disk |

| Adapter 1 | NAT |

| Adapter 2 | Internal Network (LABNET) |



\---



\## Client Workstation (CLIENT01)



| Setting | Value |

|----------|-------|

| Operating System | Windows 11 Pro |

| Hostname | CLIENT01 |

| Memory | 4 GB RAM |

| Processor | 2 vCPUs |

| Storage | Virtual Hard Disk |

| Adapter 1 | NAT |

| Adapter 2 | Internal Network (LABNET) |



\---



\# Network Design



Two separate virtual network adapters were configured for each virtual machine.



\## NAT Adapter



Purpose:



\- Internet connectivity

\- Windows activation

\- Windows Updates

\- Software downloads



VirtualBox automatically assigns addresses within the:



```

10.0.2.0/24

```



network.



\---



\## Internal Network (LABNET)



Purpose:



\- Active Directory communication

\- DNS

\- Authentication

\- File sharing

\- Group Policy



Internal subnet:



```

192.168.10.0/24

```



The Internal Network isolates domain traffic from the physical home network while allowing secure communication between virtual machines.



\---



\# Windows Server Installation



Windows Server 2022 was installed on the first virtual machine and configured as the Domain Controller.



Initial configuration included:



\- Computer renamed to \*\*DC01\*\*

\- Static IPv4 address configured

\- Server updates installed

\- Initial administrative configuration completed



This server later hosted:



\- Active Directory Domain Services

\- DNS

\- File Services



\---



\# Windows 11 Installation



Windows 11 Pro was installed on the client workstation virtual machine.



Because VirtualBox does not fully emulate TPM and Secure Boot by default, Windows Setup required bypassing hardware requirement checks using registry modifications during installation.



Following installation:



\- Computer renamed to \*\*CLIENT01\*\*

\- Local administrator account created

\- Initial Windows configuration completed

\- Network adapters configured

\- Domain join completed after Active Directory deployment



\---



\# Network Configuration



\## Domain Controller



Static IP configuration:



| Setting | Value |

|----------|-------|

| IPv4 Address | 192.168.10.10 |

| Subnet Mask | 255.255.255.0 |

| Default Gateway | Not Required |

| Preferred DNS | Self (192.168.10.10) |



\---



\## Client Workstation



Static LABNET configuration:



| Setting | Value |

|----------|-------|

| IPv4 Address | 192.168.10.20 |

| Subnet Mask | 255.255.255.0 |

| Default Gateway | Not Required |

| Preferred DNS | 192.168.10.10 |



The NAT adapter remained configured automatically by VirtualBox to provide Internet access.



\---



\# Deployment Validation



Before installing Active Directory, the following validation steps were completed:



\- Virtual machines successfully booted

\- Internal networking verified

\- Static IP configuration confirmed

\- DNS configuration validated

\- Internet connectivity confirmed through the NAT adapter



These steps ensured the environment was correctly configured before deploying enterprise services.



\---



\# Challenges Encountered



Several deployment issues were encountered during the setup process.



\### Windows 11 Installation



Windows 11 hardware requirement checks prevented installation inside VirtualBox.



Resolution:



\- Applied Microsoft-supported registry bypass during Windows Setup for TPM, Secure Boot, and memory requirement checks.



\---



\### VirtualBox Boot Configuration



The Windows 11 virtual machine initially displayed a black screen after installation.



Resolution:



\- Corrected the virtual machine boot configuration.

\- Verified the virtual hard disk was selected as the primary boot device.

\- Reset the virtual machine to complete Windows Out-of-Box Experience (OOBE).



\---



\### Network Configuration



The client workstation initially received an APIPA (169.254.x.x) address on the internal adapter.



Resolution:



\- Configured a static IP address.

\- Assigned the Domain Controller as the preferred DNS server.

\- Verified connectivity using:



```

ping

```



and



```

nslookup

```



before joining the domain.



\---



\# Summary



The environment setup established a stable enterprise lab consisting of a Windows Server Domain Controller and a Windows 11 client connected through isolated virtual networking. This foundation provided the infrastructure required to deploy Active Directory, DNS, Group Policy, centralized authentication, and secure file services in later phases of the project.

