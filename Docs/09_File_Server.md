\# File Server



\# Enterprise File Server \& Role-Based Access Control



\## 🎯 Objective



Implement an enterprise-style Windows File Server using Active Directory security groups, NTFS permissions, and shared folders to enforce Role-Based Access Control (RBAC) and the Principle of Least Privilege.



\---



\# Lab Overview



In this phase of the Active Directory lab, departmental shared folders were created and secured using both Share Permissions and NTFS Permissions.



Rather than assigning permissions directly to individual users, Active Directory security groups were used to centrally manage access to departmental resources.



This approach reflects common enterprise best practices for Windows Server administration.



\---



\# Folder Structure



```text

C:\\

└── Shares

&#x20;   ├── HR

&#x20;   ├── IT

&#x20;   └── Finance

```



\---



\# Shared Folders



| Share | Purpose |

|--------|---------|

| HR | Human Resources department files |

| IT | Information Technology department files |

| Finance | Finance department files |



\---



\# Share Permissions



Each shared folder was configured with the following Share Permission:



| Principal | Permission |

|-----------|------------|

| Everyone | Read |



\## Why?



Share permissions were intentionally kept simple.



Access control is enforced through NTFS permissions, which provide more granular security and follow Microsoft's recommended best practice.



\---



\# NTFS Permissions



\## HR Folder



| Principal | Permission |

|-----------|------------|

| SYSTEM | Full Control |

| Administrators | Full Control |

| CREATOR OWNER | Full Control (Subfolders and files only) |

| GG\_HR\_Staff | Modify |



\---



\## IT Folder



| Principal | Permission |

|-----------|------------|

| SYSTEM | Full Control |

| Administrators | Full Control |

| CREATOR OWNER | Full Control (Subfolders and files only) |

| GG\_IT\_Staff | Modify |



\---



\## Finance Folder



| Principal | Permission |

|-----------|------------|

| SYSTEM | Full Control |

| Administrators | Full Control |

| CREATOR OWNER | Full Control (Subfolders and files only) |

| GG\_Finance\_Staff | Modify |



\---



\# Security Concepts Demonstrated



This lab demonstrates several core Windows Server security concepts:



\- Role-Based Access Control (RBAC)

\- Principle of Least Privilege

\- NTFS Permissions

\- Share Permissions

\- Permission Inheritance

\- Explicit Permissions

\- Active Directory Security Groups

\- Departmental Access Control



\---



\# Enterprise Design Decisions



\## Role-Based Access Control (RBAC)



Access was assigned to Active Directory security groups instead of individual users.



Benefits include:



\- Easier administration

\- Simplified onboarding and offboarding

\- Centralized permission management

\- Reduced administrative overhead



\---



\## Principle of Least Privilege



Each department only has access to the resources required to perform its job functions.



Examples:



\- HR users cannot access Finance files.

\- Finance users cannot access IT files.

\- IT users cannot access HR files.



This minimizes unauthorized access and reduces organizational risk.



\---



\## Permission Inheritance



Permission inheritance was disabled for each departmental folder.



Inherited permissions were converted into explicit permissions before configuration.



This allows each department to maintain its own security configuration without inheriting unnecessary permissions from the parent folder.



\---



\# Skills Demonstrated



\- Windows Server Administration

\- Active Directory Administration

\- File Server Configuration

\- NTFS Permission Management

\- Share Permission Configuration

\- Security Group Administration

\- Role-Based Access Control (RBAC)

\- Principle of Least Privilege

\- Enterprise Access Management



\---



\# Outcome



Successfully implemented a secure enterprise file server using Active Directory security groups and NTFS permissions.



Departmental shared folders were configured to ensure users receive access only to the resources required for their job role while protecting sensitive organizational data.



This implementation follows Microsoft Windows Server administration best practices and demonstrates practical experience with enterprise file server deployment and access control.

