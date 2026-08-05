# Active Directory Security Group Creation and Role-Based Access Control

## Business Scenario

> Organizations use Active Directory Security Groups to simplify access management and enforce role-based access control (RBAC). Instead of assigning permissions directly to individual users, administrators assign users to security groups based on job responsibilities. These groups can then be granted access to files, applications, systems, and administrative resources. This approach improves security, scalability, and consistency across an enterprise environment.

---

## Project Objective

> Create and organize Active Directory Security Groups to support role-based access control within the enterprise lab environment. This project establishes a structured group management system that will later be used for file permissions, resource access, administrative delegation, and security policy implementation.

---

## Skills Demonstrated

* Active Directory Security Group Management
* Role-Based Access Control (RBAC)
* Active Directory Users and Computers Administration
* Global Security Group Configuration
* Group Naming Standards
* Identity and Access Management Concepts
* Windows Server Administration
* PowerShell Active Directory Commands
* Enterprise Access Management Practices

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Security-Groups-OU.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Security-Group-Properties.png)

---

| Component         | Details                              |
| ----------------- | ------------------------------------ |
| Cloud Provider    | Microsoft Azure                      |
| Server            | Windows Server 2022 Datacenter       |
| Server Name       | LABDC01                              |
| Directory Service | Active Directory Domain Services     |
| Management Tool   | Active Directory Users and Computers |
| Group Type        | Security Groups                      |
| Group Scope       | Global                               |

---

## Project Architecture

```text id="6x3jmg"
                    Active Directory Domain
                              │
                              │
                       Enterprise OU
                              │
                              │
                         Groups OU
                              │
                              │
                   Security Groups OU
                              │
        ┌──────────────┬──────────────┬──────────────┐
        │              │              │              │
        ▼              ▼              ▼              ▼
 GG_IT_Admins    GG_HelpDesk    GG_IT_Users    GG_Employees
        │
        │
        ├──────────────┬──────────────┬──────────────┐
        │              │              │
        ▼              ▼              ▼
    GG_HR        GG_Sales       GG_Finance


Future Usage:
Users → Security Groups → Resources

Example:
Employee Account
        │
        ▼
Department Security Group
        │
        ▼
File Share / Application Access
```

---

## Implementation Summary

### Phase 1 – Access Group Structure Preparation

* Opened **Active Directory Users and Computers**.
* Navigated to:

```text id="91nqf4"
Enterprise
└── Groups
    └── Security Groups
```

* Verified the Security Groups OU was available for group organization.

### Phase 2 – Create Security Groups

* Created new Active Directory Security Groups.
* Configured each group with:

**Group Scope**

* Global

**Group Type**

* Security

Created the following groups:

| Security Group | Purpose                                                     |
| -------------- | ----------------------------------------------------------- |
| GG_IT_Admins   | IT administrators with elevated management responsibilities |
| GG_HelpDesk    | Help Desk personnel requiring support permissions           |
| GG_IT_Users    | General IT users and technical staff                        |
| GG_Employees   | Standard employee access group                              |
| GG_HR          | Human Resources department access                           |
| GG_Sales       | Sales department access                                     |
| GG_Finance     | Finance department access                                   |

### Phase 3 – Validate Group Configuration

* Opened group properties.
* Verified:

  * Group Scope: Global
  * Group Type: Security
* Confirmed groups were stored inside the Security Groups OU.
* Prepared groups for future user assignments and resource permissions.

---

## Validation

* Security Groups OU created successfully.
* All required security groups created.
* Group scope configured as Global.
* Group type configured as Security.
* Groups stored in the correct Active Directory location.
* Environment prepared for future permission assignments.

---

## Challenges Encountered

* Initially created groups without a dedicated Security Groups OU.
* Reorganized groups into a dedicated OU to improve administration and documentation clarity.
* Determined appropriate naming conventions to make group purpose immediately identifiable.
* Ensured groups were designed around business roles rather than individual users.

---

## Useful Commands

View all Active Directory groups:

```powershell id="k0quq6"
Get-ADGroup -Filter *
```

View members of a specific group:

```powershell id="m48x0h"
Get-ADGroupMember "GG_IT_Admins"
```

---

## Best Practices

* Assign permissions to groups instead of individual users.
* Use naming conventions that clearly identify group purpose.
* Use Global Security Groups for organizing users based on roles.
* Document the purpose of every security group before assigning permissions.
* Follow the principle of least privilege when granting access.
* Avoid creating groups without a defined business purpose.

---

## Future Improvements

* Create user accounts and assign users to appropriate security groups.
* Configure NTFS and file share permissions using security groups.
* Implement delegated administration through security groups.
* Create additional department and application-based security groups.
* Automate security group creation and management with PowerShell.

---

## Related Documentation

* Active Directory Organizational Unit Design
* Active Directory Group Structure and Management
* User Account Creation and Management
* File Share and NTFS Permissions
* Group Policy Configuration
* PowerShell Active Directory Automation
