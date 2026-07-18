\# Group Policy



\## Purpose



Group Policy provides centralized management of user and computer settings within an Active Directory environment. It allows administrators to enforce security policies, standardize system configurations, and automate administrative tasks across domain-joined devices.



This phase of the project will focus on implementing Group Policy Objects (GPOs) to improve security, simplify administration, and create a consistent user experience.



\---



\# Objectives



The following Group Policy configurations are planned for this environment:



\- Password Policy

\- Account Lockout Policy

\- Desktop Restrictions

\- Windows Security Settings

\- Windows Update Configuration

\- User Environment Configuration

\- Administrative Templates

\- Group Policy Management



\---



\# Planned Group Policy Objects



| Group Policy | Purpose |

|--------------|---------|

| Default Domain Password Policy | Enforce password complexity and expiration |

| Account Lockout Policy | Protect against brute-force attacks |

| Desktop Restrictions | Standardize the desktop environment |

| Windows Update Policy | Configure update behavior |

| Control Panel Restrictions | Limit unauthorized system changes |

| Windows Defender Policy | Improve endpoint security |



\---



\# Planned OU Linking



Group Policy Objects will be linked to Organizational Units based on the systems or users they should affect.



Examples include:



\- Workstations OU

\- Departments OU

\- Administrative OU



This approach ensures policies are applied only where appropriate.



\---



\# Benefits of Group Policy



Implementing Group Policy provides several advantages:



\- Centralized administration

\- Consistent security settings

\- Reduced manual configuration

\- Improved compliance

\- Automated workstation configuration

\- Simplified enterprise management



\---



\# Validation



After implementation, the following items will be verified:



\- Group Policy Objects created successfully

\- Policies linked to the correct Organizational Units

\- Policies applied successfully to client computers

\- Results verified using `gpupdate` and `gpresult`



\---



\# Skills Demonstrated



Upon completion of this phase, the project will demonstrate:



\- Group Policy Management

\- Windows Security Administration

\- Active Directory Administration

\- Enterprise Policy Management



\---



\# Screenshots



To be added after implementation:



\- Group Policy Management Console

\- Password Policy configuration

\- Account Lockout Policy

\- Linked GPOs

\- Resultant Set of Policy (RSoP)

\- gpresult output

