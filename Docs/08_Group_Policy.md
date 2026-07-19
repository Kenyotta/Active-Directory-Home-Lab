# Group Policy

## Overview

Group Policy is a feature of Microsoft Active Directory that enables administrators to centrally manage security settings, user configurations, and computer policies across an entire domain. Rather than configuring each workstation individually, Group Policy Objects (GPOs) allow consistent settings to be automatically applied to domain-joined computers and users.

In this lab, several security-focused Group Policies were configured to simulate common enterprise security standards.

---

# Objectives

The goals of this phase were to:

- Configure domain-wide security policies
- Enforce password complexity requirements
- Configure account lockout protection
- Apply workstation security settings
- Validate successful Group Policy deployment

---

# Group Policies Configured

The following security policies were implemented within the **corp.local** domain.

| Policy | Purpose |
|----------|---------|
| Password Policy | Enforce strong passwords |
| Account Lockout Policy | Protect against password guessing attacks |
| Screen Lock Policy | Secure unattended workstations |

These policies were configured using the **Group Policy Management Console (GPMC)** and applied at the domain level.

---

# Password Policy

A domain password policy was configured to strengthen account security.

The policy included:

- Password complexity enabled
- Minimum password length enforced
- Password history maintained
- Maximum password age configured

These settings help reduce the risk of weak or reused passwords and support enterprise security best practices.

---

# Account Lockout Policy

An account lockout policy was implemented to protect against brute-force password attacks.

The policy included:

- Account lockout threshold
- Lockout duration
- Lockout counter reset period

When a user exceeds the configured number of failed sign-in attempts, the account is temporarily locked until the defined lockout period expires or an administrator resets the account.

---

# Screen Lock Policy

A workstation security policy was configured to automatically lock inactive sessions.

The policy requires users to re-authenticate after the screen saver activates, reducing the risk of unauthorized access to unattended systems.

This control is commonly implemented in enterprise environments to protect sensitive information.

---

# Centralized Management

One of the primary benefits of Group Policy is centralized administration.

Instead of configuring security settings on every workstation individually, administrators create a single Group Policy Object that is automatically applied to all applicable domain-joined systems.

Benefits include:

- Consistent security configuration
- Reduced administrative effort
- Faster policy deployment
- Improved compliance
- Simplified management

---

# Group Policy Processing

When a domain user signs in:

1. The workstation authenticates with the Domain Controller.
2. Applicable Group Policy Objects are identified.
3. Policies are downloaded from the Domain Controller.
4. Security settings are applied.
5. User access is granted based on authentication and authorization.

This automated process ensures every domain-joined workstation maintains a consistent security baseline.

---

# Validation

After configuring the policies, the client workstation was updated using:

```
gpupdate /force
```

Policy application was verified using:

```
gpresult /r
```

Validation confirmed:

- Password policy successfully applied
- Account lockout policy active
- Screen lock policy enforced
- Client received domain Group Policy successfully

These checks verified that centralized policy management was functioning correctly.

---

# Enterprise Best Practices Applied

The Group Policy configuration follows several enterprise security best practices:

- Centralized policy management
- Strong password enforcement
- Protection against brute-force attacks
- Automatic workstation locking
- Consistent security configuration across all domain devices

Using Group Policy reduces configuration drift and ensures all domain-joined systems follow the organization's security standards.

---

# Business Value

Implementing Group Policy provides organizations with:

- Improved security
- Reduced administrative overhead
- Standardized workstation configurations
- Faster deployment of security controls
- Easier compliance with organizational policies

These capabilities make Group Policy one of the most valuable management tools in Windows Server environments.

---

# Summary

Group Policy provides centralized management of security and configuration settings throughout the Active Directory environment. By enforcing password requirements, account lockout protection, and workstation security from the Domain Controller, the lab demonstrates how enterprise administrators maintain consistent security across domain-joined systems while reducing administrative complexity.