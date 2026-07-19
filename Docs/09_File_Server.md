# File Server

## Overview

Centralized file sharing is a core service provided by Windows Server in enterprise environments. By combining SMB file sharing with NTFS permissions and Active Directory Security Groups, administrators can control access to departmental resources while maintaining a scalable and secure access model.

In this lab, departmental file shares were created for the IT, Human Resources (HR), and Finance departments. Access was managed using Role-Based Access Control (RBAC), where permissions were assigned to Security Groups rather than individual users.

During implementation, a permissions issue was identified and resolved through systematic troubleshooting, providing practical experience with Windows file access management.

---

# Objectives

The goals of this phase were to:

- Create departmental shared folders
- Configure SMB file sharing
- Apply NTFS permissions
- Implement Role-Based Access Control (RBAC)
- Validate user access
- Troubleshoot and resolve file permission issues

---

# Folder Structure

The following departmental folders were created:

```
C:\Shares
│
├── IT
├── HR
└── Finance
```

Each folder represents a departmental network share that is accessible only to authorized users.

---

# SMB Shares

The folders were shared using Windows File and Storage Services.

| Share | Purpose |
|--------|---------|
| IT | Information Technology resources |
| HR | Human Resources documents |
| Finance | Financial records |

These shares allow authenticated domain users to access department-specific resources over the network.

---

# Share Permissions

The final Share permissions were configured as follows:

| Principal | Permission |
|-----------|------------|
| Everyone | Change |
| GG_IT_Staff | Change |
| GG_HR_Staff | Change |
| GG_Finance_Staff | Change |

Share permissions provide network-level access, while NTFS permissions determine what users can do once access is granted.

---

# NTFS Permissions

Access to each departmental folder was restricted using NTFS permissions.

Example configuration:

| Folder | Authorized Group | Permission |
|----------|-----------------|------------|
| IT | GG_IT_Staff | Modify |
| HR | GG_HR_Staff | Modify |
| Finance | GG_Finance_Staff | Modify |

This ensures users only have access to resources associated with their department.

---

# Role-Based Access Control (RBAC)

Permissions were assigned to Security Groups instead of individual user accounts.

The access model follows this structure:

```
User
   │
   ▼
Security Group
   │
   ▼
Department Folder
```

Example:

```
Ethan Carter
      │
      ▼
GG_IT_Staff
      │
      ▼
\\DC01\IT
```

This design simplifies administration and follows Microsoft's recommended Active Directory practices.

---

# Troubleshooting

## Issue

During validation, the IT user successfully authenticated to the domain but received an **Access Denied** message when attempting to create a file in the IT department share.

Authentication and group membership were functioning correctly, indicating that the issue was related to file sharing permissions rather than Active Directory.

---

## Investigation

Several diagnostic tools were used to isolate the issue.

### Verify Group Membership

```
whoami /groups
```

Confirmed that the authenticated user was a member of **GG_IT_Staff**.

---

### Verify NTFS Permissions

```
icacls C:\Shares\IT
```

Confirmed that the **GG_IT_Staff** Security Group had **Modify** permissions on the folder.

---

### Verify Share Permissions

```
net share
```

Reviewing the share configuration revealed that the Share permissions were more restrictive than the NTFS permissions, preventing authorized users from modifying files across the network.

---

# Resolution

The Share permissions were updated to allow the appropriate level of network access while NTFS permissions continued to enforce department-level authorization.

Final configuration:

- **Share Permissions:** Change
- **NTFS Permissions:** Modify

This configuration follows Microsoft's recommended practice of allowing Share permissions to provide broad network access while relying on NTFS permissions for detailed authorization.

---

# Validation

After correcting the Share permissions, the following tests were successfully completed.

## Ethan Carter (IT)

| Test | Result |
|------|--------|
| Domain Login | ✅ Success |
| Access IT Share | ✅ Success |
| Create test.txt | ✅ Success |
| Access HR Share | ❌ Access Denied |
| Access Finance Share | ❌ Access Denied |

These results confirmed that Role-Based Access Control was functioning correctly.

---

# Enterprise Best Practices Applied

The file server implementation follows several enterprise best practices:

- Centralized file storage
- Security Group–based permissions
- Least Privilege access
- Separation of Share and NTFS permissions
- Role-Based Access Control (RBAC)
- Systematic troubleshooting and validation

These practices improve security, simplify administration, and make the environment easier to maintain as the organization grows.

---

# Summary

The file server provides secure, centralized access to departmental resources through the integration of SMB file sharing, NTFS permissions, and Active Directory Security Groups. By diagnosing and resolving a Share permission issue during implementation, this phase demonstrates not only the configuration of enterprise file services but also the troubleshooting methodology used to identify and correct access control problems in a Windows Server environment.