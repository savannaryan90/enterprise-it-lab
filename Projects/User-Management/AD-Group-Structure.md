# Active Directory Group Structure and Management

## Business Scenario

> Organizations use Active Directory groups to simplify access management and administration. Instead of assigning permissions, policies, and resources to individual users, administrators organize users into groups based on job responsibilities, departments, and security requirements. This role-based approach improves scalability, reduces administrative overhead, and follows common enterprise identity management practices.

---

## Project Objective

> Create and organize an Active Directory group structure that supports role-based access management. This project establishes a foundation for assigning permissions, managing resources, and implementing security policies without requiring administrators to configure access for each individual user.

---

## Skills Demonstrated

* Active Directory Group Management
* Role-Based Access Control (RBAC) Concepts
* Security Group Organization
* Active Directory Users and Computers Administration
* Group Naming Standards
* Identity and Access Management Fundamentals
* Windows Server Administration
* PowerShell Active Directory Commands
* Enterprise Directory Organization

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Groups-OU-Structure.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Security-Groups.png)

---

| Component          | Details                              |
| ------------------ | ------------------------------------ |
| Cloud Provider     | Microsoft Azure                      |
| Server             | Windows Server 2022 Datacenter       |
| Server Name        | LABDC01                              |
| Directory Service  | Active Directory Domain Services     |
| Management Tool    | Active Directory Users and Computers |
| Group Organization | Security Groups, Distribution Groups |

---

## Project Architecture

```text id="y8i9qv"
                    Active Directory Domain
                              │
                              │
                         Enterprise OU
                              │
                              │
                         Groups OU
                              │
              ┌───────────────┴───────────────┐
              │                               │
              ▼                               ▼
       Security Groups              Distribution Groups
              │                               │
              │                               │
     Access Control / RBAC          Email Communication
     File Permissions               Announcements
     Resource Access                Notifications
```

---

## Implementation Summary

### Phase 1 – Prepare Group Organization

* Opened **Active Directory Users and Computers**.
* Navigated to the previously created Groups OU.
* Reviewed the purpose of separating groups from user and computer objects.
* Created additional organizational units for group management:

```
Groups
│
├── Security Groups
│
└── Distribution Groups
```

### Phase 2 – Organize Active Directory Groups

* Created a dedicated location for security-related groups.

* Organized groups based on their purpose:

  * Security Groups for permissions and access control.
  * Distribution Groups for communication purposes.

* Applied consistent naming practices to improve administration and identification.

### Phase 3 – Prepare for Role-Based Access Management

* Established a structure for future group creation.
* Prepared the environment for:

  * Department-based security groups.
  * File share permissions.
  * Group Policy targeting.
  * Resource access management.

---

## Validation

* Groups OU exists in Active Directory.
* Security Groups and Distribution Groups organizational units were created successfully.
* Group structure appears in the correct Active Directory location.
* No errors occurred during group organization.
* Structure is prepared for future user and permission assignments.

---

## Challenges Encountered

* Understanding the difference between Active Directory groups and Organizational Units.
* Determining the best structure for organizing groups in a scalable environment.
* Reviewing warnings when moving groups between locations in Active Directory.
* Ensuring changes would not affect production resources.

---

## Useful Commands

View Active Directory groups using PowerShell:

```powershell
Get-ADGroup -Filter *
```

---

## Best Practices

* Assign permissions to groups instead of individual users.
* Create groups before assigning resource permissions.
* Use clear and consistent naming conventions.
* Separate security groups from distribution groups.
* Design groups based on business roles and responsibilities.
* Follow the principle of least privilege when assigning access.

---

## Future Improvements

* Create department-based security groups.
* Add users to appropriate role-based groups.
* Configure NTFS and file share permissions using groups.
* Implement Group Policy filtering using security groups.
* Create administrative groups for delegated management.
* Automate group creation using PowerShell.

---

## Related Documentation

* Active Directory Organizational Unit Design
* User Account Management
* File Share and NTFS Permissions
* Group Policy Configuration
* PowerShell Active Directory Automation
