# Lab Architecture

## Overview

This lab was designed to simulate a small enterprise Active Directory environment using Oracle VirtualBox. The environment consists of a Windows Server 2022 Domain Controller and a Windows 11 client workstation connected through an isolated internal network while maintaining Internet connectivity through a separate NAT adapter.

This dual-network design allows the virtual machines to communicate securely with one another while still providing Internet access for software installation and updates.

---

# Environment Architecture

```
                     Internet
                         │
                    NAT Network
                    (10.0.2.0/24)
                         │
          ┌──────────────┴──────────────┐
          │                             │
     Windows Server                Windows 11
        DC01                        CLIENT01
          │                             │
          └──────────────┬──────────────┘
                         │
                Internal Network
                  LABNET
              192.168.10.0/24
                         │
                 Active Directory
                  DNS Services
                  File Shares
                  Group Policy
```

---

# Virtual Machines

## Domain Controller

| Component | Configuration |
|------------|---------------|
| Operating System | Windows Server 2022 |
| Hostname | DC01 |
| Domain | corp.local |
| Roles Installed | Active Directory Domain Services, DNS |
| Network Adapter 1 | NAT |
| Network Adapter 2 | Internal Network (LABNET) |
| Internal IP Address | 192.168.10.10 |

---

## Client Workstation

| Component | Configuration |
|------------|---------------|
| Operating System | Windows 11 Pro |
| Hostname | CLIENT01 |
| Domain Membership | corp.local |
| Network Adapter 1 | NAT |
| Network Adapter 2 | Internal Network (LABNET) |
| DNS Server | 192.168.10.10 |

---

# Network Configuration

## NAT Network

Purpose:

- Internet connectivity
- Windows Updates
- Software installation
- External communication

Example Addressing:

```
10.0.2.x
```

This network is automatically provided by Oracle VirtualBox.

---

## Internal Network (LABNET)

Purpose:

- Domain communication
- DNS queries
- Authentication
- File sharing
- Group Policy
- Secure communication between virtual machines

Network:

```
192.168.10.0/24
```

Devices:

| Device | IP Address |
|---------|------------|
| DC01 | 192.168.10.10 |
| CLIENT01 | DHCP (assigned from LABNET) |

---

# Active Directory Architecture

The Domain Controller provides several enterprise services to the Windows 11 client.

### Authentication

Users authenticate against Active Directory rather than using local workstation accounts.

---

### DNS

The Domain Controller hosts DNS for the corp.local domain and resolves both domain resources and Internet names through forwarding.

---

### Group Policy

Security settings are centrally managed and automatically applied to domain-joined systems.

Examples include:

- Password Policy
- Account Lockout Policy
- Screen Lock Policy

---

### File Services

Departmental file shares are hosted on DC01.

Access is controlled through:

- Security Groups
- Share Permissions
- NTFS Permissions

---

# Organizational Structure

The Active Directory environment contains separate Organizational Units (OUs) for administrative organization.

Departments include:

- IT
- Human Resources
- Finance
- Sales
- Executive

Each department contains its own users and associated security groups.

---

# Security Model

The environment follows Microsoft's recommended Role-Based Access Control (RBAC) model.

Rather than assigning permissions directly to users:

```
User
   ↓
Security Group
   ↓
Folder Permission
```

This design improves scalability, simplifies administration, and follows the Principle of Least Privilege.

---

# Communication Flow

When a user signs in to the Windows 11 workstation:

1. CLIENT01 contacts DC01.
2. Active Directory authenticates the user.
3. DNS resolves domain resources.
4. Group Policy is applied.
5. Security group membership is evaluated.
6. Authorized network shares become accessible.

This centralized workflow ensures consistent authentication and authorization across the environment.

---

# Design Considerations

Several design decisions were made to reflect enterprise best practices:

- Separate NAT and Internal Network adapters
- Static IP addressing for the Domain Controller
- Centralized DNS
- Role-Based Access Control (RBAC)
- Organizational Units for administrative delegation
- Group-based permissions instead of user-based permissions
- Centralized security management through Group Policy

---

# Summary

The architecture provides a realistic representation of a small enterprise Active Directory deployment. By separating Internet connectivity from internal domain communication and centralizing identity, policy, and resource management, the environment demonstrates the core infrastructure commonly found in production Windows networks.