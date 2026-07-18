\# File Server



\## Purpose



File servers provide centralized storage for organizational data while allowing administrators to control access through NTFS permissions and Active Directory Security Groups. Centralized file storage improves collaboration, simplifies backups, and enhances data security.



This phase of the project will focus on deploying a Windows Server file share infrastructure that integrates with Active Directory.



\---



\# Objectives



The following objectives are planned for this phase:



\- Create departmental shared folders

\- Configure NTFS permissions

\- Configure Share permissions

\- Implement Security Group-based access control

\- Test user access

\- Validate least privilege access



\---



\# Planned Folder Structure



```

D:\\Shares

│

├── Executive

├── Finance

├── HR

├── IT

├── Marketing

└── Sales

```



\---



\# Planned Permissions



Permissions will be assigned using Active Directory Security Groups rather than individual user accounts.



| Shared Folder | Security Group |

|--------------|----------------|

| Executive | GG\_Executive\_Staff |

| Finance | GG\_Finance\_Staff |

| HR | GG\_HR\_Staff |

| IT | GG\_IT\_Staff |

| Marketing | GG\_Marketing\_Staff |

| Sales | GG\_Sales\_Staff |



This approach follows Microsoft's recommended practice of assigning permissions to groups instead of directly to users.



\---



\# Security Considerations



The file server implementation will follow the Principle of Least Privilege by granting users access only to the resources required for their job responsibilities.



Administrative access will remain restricted to authorized administrator accounts.



\---



\# Validation



After implementation, the following items will be verified:



\- Shared folders created successfully

\- NTFS permissions configured correctly

\- Share permissions configured correctly

\- Users can access authorized folders

\- Unauthorized access is denied

\- Security Group permissions function as expected



\---



\# Skills Demonstrated



Upon completion of this phase, this project will demonstrate:



\- Windows File Services

\- NTFS Permissions

\- Share Permissions

\- Active Directory Security Groups

\- Access Control

\- Enterprise File Server Administration



\---



\# Screenshots



To be added after implementation:



\- File Server Manager

\- Shared folder configuration

\- NTFS Security tab

\- Share permissions

\- User access verification

