\# Domain-Joined Client



\## Overview



A Windows 11 Pro workstation was deployed and joined to the \*\*corp.local\*\* Active Directory domain to validate centralized identity management, Group Policy application, DNS functionality, and Role-Based Access Control (RBAC).



Joining the workstation to the domain transformed it from a standalone computer into a managed enterprise endpoint capable of authenticating users through Active Directory and receiving centrally managed security policies.



\---



\# Objectives



The goals of this phase were to:



\- Deploy a Windows 11 virtual machine

\- Configure network settings

\- Join the workstation to the Active Directory domain

\- Validate domain authentication

\- Verify DNS functionality

\- Confirm Group Policy application

\- Test Role-Based Access Control (RBAC)



\---



\# Client Configuration



| Setting | Value |

|----------|-------|

| Operating System | Windows 11 Pro |

| Computer Name | CLIENT01 |

| Domain | corp.local |

| Domain Controller | DC01 |

| Preferred DNS Server | 192.168.10.10 |



\---



\# Network Configuration



The workstation was connected to two virtual network adapters.



\## NAT Adapter



Purpose:



\- Internet access

\- Windows Updates

\- Software downloads



\---



\## Internal Network (LABNET)



Purpose:



\- Active Directory communication

\- DNS

\- Authentication

\- SMB File Sharing

\- Group Policy



The workstation was configured to use the Domain Controller as its preferred DNS server to ensure proper domain name resolution.



\---



\# Domain Join Process



After network connectivity was verified, the workstation was joined to the \*\*corp.local\*\* domain.



The process included:



\- Specifying the Active Directory domain

\- Providing Domain Administrator credentials

\- Restarting the workstation

\- Logging in using a domain user account



Following the restart, the workstation became a managed member of the Active Directory environment.



\---



\# Domain Authentication



Authentication was validated using the \*\*Ethan Carter\*\* domain account.



Successful sign-in confirmed that:



\- CLIENT01 could communicate with DC01

\- Active Directory authentication was functioning

\- Domain credentials were accepted

\- User profile creation completed successfully



\---



\# DNS Validation



DNS functionality was verified to ensure the workstation could locate domain resources.



Validation included:



```

ping 192.168.10.10

```



```

nslookup corp.local

```



Successful responses confirmed that the Domain Controller was providing DNS services and that name resolution was functioning correctly.



\---



\# Group Policy Validation



Domain Group Policies were refreshed using:



```

gpupdate /force

```



Applied policies were verified with:



```

gpresult /r

```



Validation confirmed that:



\- Password Policy was applied

\- Account Lockout Policy was active

\- Screen Lock Policy was enforced

\- CLIENT01 successfully received domain Group Policy Objects



\---



\# Role-Based Access Control (RBAC) Validation



Role-Based Access Control was validated using departmental user accounts.



\## Ethan Carter (IT)



| Test | Result |

|------|--------|

| Domain Login | ✅ Success |

| Access IT Share | ✅ Success |

| Create test.txt | ✅ Success |

| Access HR Share | ❌ Access Denied |

| Access Finance Share | ❌ Access Denied |



\---



\## Sophia Reed (HR)



| Test | Result |

|------|--------|

| Domain Login | ✅ Success |

| Access HR Share | ✅ Success |

| Access IT Share | ❌ Access Denied |

| Access Finance Share | ❌ Access Denied |



\---



\## Liam Turner (Finance)



| Test | Result |

|------|--------|

| Domain Login | ✅ Success |

| Access Finance Share | ✅ Success |

| Access IT Share | ❌ Access Denied |

| Access HR Share | ❌ Access Denied |



These validation tests confirmed that access to shared resources was determined by Security Group membership and enforced through NTFS permissions, successfully implementing Role-Based Access Control (RBAC).



\---



\# Enterprise Concepts Demonstrated



This phase demonstrates several core enterprise administration concepts:



\- Domain Authentication

\- Centralized Identity Management

\- DNS Name Resolution

\- Group Policy Processing

\- SMB File Access

\- Security Group Authorization

\- Role-Based Access Control (RBAC)

\- Least Privilege



Together, these services provide a secure and centrally managed Windows environment.



\---



\# Validation Summary



The following functionality was successfully verified:



\- Windows 11 successfully joined the domain

\- Domain users authenticated successfully

\- DNS resolved domain resources

\- Group Policy Objects applied correctly

\- Departmental file shares were accessible only to authorized users

\- Unauthorized access attempts were denied

\- Role-Based Access Control functioned as designed



\---



\# Summary



The successful deployment of the Windows 11 domain-joined workstation demonstrates the complete integration of client systems into the Active Directory environment. Authentication, DNS, Group Policy, and file access controls were validated end-to-end, confirming that the lab accurately reflects the centralized management and security practices used in enterprise Windows networks.

