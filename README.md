# Active Directory Home Lab

## Overview

This project demonstrates the deployment of a small enterprise Active Directory environment using Windows Server 2022 and Windows 11 in Oracle VirtualBox. The lab simulates a corporate network where centralized identity management, security policies, role-based access control (RBAC), and file services are implemented and validated.

The project follows enterprise administration practices, including Active Directory Domain Services (AD DS), DNS, Group Policy, Organizational Units, Security Groups, domain-joined workstations, and departmental file shares secured with both Share and NTFS permissions.

---

## Objectives

- Deploy an Active Directory Domain Controller
- Configure DNS for internal name resolution
- Design an Organizational Unit structure
- Implement Role-Based Access Control (RBAC)
- Configure enterprise Group Policies
- Create and manage domain users and security groups
- Configure secure departmental file shares
- Join a Windows 11 workstation to the domain
- Validate authentication, authorization, and file access

---

## Technologies Used

- Windows Server 2022
- Windows 11 Pro
- Oracle VirtualBox
- Active Directory Domain Services
- DNS
- Group Policy
- SMB File Sharing
- NTFS Permissions
- Windows Networking
- Command Prompt
- PowerShell

---

## Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Domain Management
- DNS Configuration
- Organizational Unit Design
- User and Group Management
- Group Policy Management
- Role-Based Access Control (RBAC)
- SMB Share Configuration
- NTFS Permission Management
- Domain Join Operations
- Authentication & Authorization
- Enterprise Troubleshooting

---

## Lab Architecture

```
                    Internet
                        │
                 VirtualBox NAT
                        │
                ┌─────────────────┐
                │      DC01       │
                │ Windows Server  │
                │ AD DS + DNS     │
                │ 192.168.10.10   │
                └────────┬────────┘
                         │
                 Internal Network
                     (LABNET)
                         │
                ┌─────────────────┐
                │    CLIENT01     │
                │ Windows 11 Pro  │
                │ Domain Joined   │
                └─────────────────┘
```

---

## Features Implemented

### Active Directory

- Domain Controller Deployment
- Organizational Units
- Security Groups
- Domain Users
- Group Membership

### Group Policy

- Password Policy
- Account Lockout Policy
- Screen Lock Policy

### File Services

- Departmental File Shares
- Share Permissions
- NTFS Permissions
- Role-Based Access Control

### Client Management

- Windows 11 Domain Join
- Domain Authentication
- Group Policy Validation
- Network File Access Validation

---

## Validation Performed

The following functionality was successfully tested:

- Domain Controller communication
- DNS resolution
- Domain authentication
- User logon
- Group membership
- Group Policy application
- File share connectivity
- Department-based access control
- NTFS permissions
- Share permissions
- End-to-end RBAC validation

---

## Repository Structure

```
Active-Directory-Home-Lab/
│
├── README.md
├── docs/
├── Screenshots/
└── LICENSE
```

---

## Lessons Learned

During implementation several real-world administrative issues were encountered and resolved, including:

- Windows 11 installation requirements in virtual environments
- VirtualBox networking configuration
- DNS troubleshooting
- SMB Share permission troubleshooting
- NTFS permission validation
- Role-Based Access Control verification

Resolving these issues provided practical experience troubleshooting enterprise Windows environments rather than simply following deployment procedures.

---

## Author

**Kenyotta Eave**

Cybersecurity & IT Professional Portfolio

