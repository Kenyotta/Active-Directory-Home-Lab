# Organizational Units

## Overview

Organizational Units (OUs) provide a logical structure for organizing users, computers, and other Active Directory objects. Rather than storing every object in the default containers, OUs allow administrators to group resources by department or function, making management, delegation, and Group Policy deployment significantly easier.

In this lab, Organizational Units were created to reflect the departmental structure of a small enterprise.

---

# Objectives

The goals of this phase were to:

- Create a structured Organizational Unit hierarchy
- Organize users by department
- Organize workstations and servers
- Prepare the environment for Group Policy deployment
- Improve administrative organization and scalability

---

# Organizational Unit Structure

The following Organizational Units were created within the **corp.local** domain:

```
corp.local
│
├── IT
├── HR
├── Finance
├── Sales
├── Executive
├── Users
├── Workstations
└── Servers
```

This structure separates administrative objects into logical containers while allowing policies to be targeted to specific departments.

---

# Departmental OUs

## IT

The IT Organizational Unit contains users responsible for managing the organization's technology infrastructure.

Typical responsibilities include:

- Systems Administration
- Network Administration
- Help Desk
- Security Administration

---

## Human Resources (HR)

The HR Organizational Unit contains users responsible for employee records, hiring, onboarding, and personnel management.

Separating HR users helps ensure that sensitive information is protected through department-specific permissions and policies.

---

## Finance

The Finance Organizational Unit contains users responsible for financial operations.

This separation allows financial resources to be secured independently from other departments.

---

## Sales

The Sales Organizational Unit provides a location for users responsible for customer engagement and business development.

Separate administration enables future department-specific policies if required.

---

## Executive

The Executive Organizational Unit represents leadership accounts that may require additional security policies or administrative controls in larger enterprise environments.

Although no specialized policies were implemented in this lab, the OU demonstrates planning for future scalability.

---

# Infrastructure OUs

## Users

The Users Organizational Unit provides a centralized location for standard user accounts that are not department-specific.

---

## Workstations

The Workstations Organizational Unit is used to organize domain-joined client computers.

This separation simplifies:

- Computer management
- Group Policy deployment
- Security configuration
- Administrative delegation

---

## Servers

The Servers Organizational Unit provides a dedicated location for Windows Server systems within the domain.

Although the current environment contains a single Domain Controller, separating servers into their own OU reflects enterprise best practices and supports future expansion.

---

# Benefits of Organizational Units

Using Organizational Units provides several administrative advantages:

- Logical organization of Active Directory objects
- Simplified Group Policy deployment
- Easier administrative delegation
- Improved scalability
- Better separation of departments
- Reduced administrative complexity

---

# Enterprise Best Practices Applied

The Organizational Unit design follows several Microsoft Active Directory best practices:

- Separate users from computers
- Organize resources by department
- Plan for future growth
- Create a scalable hierarchy
- Avoid storing production objects in default containers
- Prepare the environment for Group Policy targeting

---

# Validation

After creating the Organizational Units, Active Directory Users and Computers was used to verify:

- All OUs were successfully created
- Organizational hierarchy matched the intended design
- Departmental containers were available for user and computer objects
- The structure supported future policy deployment

---

# Summary

The Organizational Unit structure establishes a logical and scalable framework for managing Active Directory objects. By separating departments, users, workstations, and servers into dedicated containers, the environment becomes easier to administer, supports targeted Group Policy deployment, and aligns with common enterprise Active Directory design practices.