# Active Directory User Account Management

## Business Scenario

> Organizations rely on centralized identity management to control how employees and administrators access company resources. Active Directory user accounts represent employees, administrators, and service identities within an enterprise environment. IT administrators manage the account lifecycle by creating users, organizing them into appropriate Organizational Units, assigning security group memberships, and maintaining secure authentication practices.

---

## Project Objective

> Create and organize Active Directory user accounts to simulate a realistic enterprise environment. This project establishes employee and administrator identities that will later be used for domain authentication, security group assignments, workstation access, Group Policy testing, and resource permission management.

---

## Skills Demonstrated

* Active Directory User Account Management
* Identity and Access Management (IAM)
* Active Directory Users and Computers Administration
* User Lifecycle Management
* Security Group Assignment
* Organizational Unit Management
* Administrative Account Best Practices
* Role-Based Access Control (RBAC)
* PowerShell Active Directory Commands
* Enterprise Help Desk Administration Concepts

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/User-Accounts-ADUC.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/User-Group-Membership.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Admin-Account.png)

---

| Component         | Details                              |
| ----------------- | ------------------------------------ |
| Cloud Provider    | Microsoft Azure                      |
| Server            | Windows Server 2022 Datacenter       |
| Server Name       | LABDC01                              |
| Directory Service | Active Directory Domain Services     |
| Management Tool   | Active Directory Users and Computers |
| User Types        | Employees and Administrators         |
| Authentication    | Domain-Based Authentication          |

---

## Project Architecture

```text id="r4v0j3"
                    Active Directory Domain
                              │
                              │
                        Enterprise OU
                              │
             ┌────────────────┴────────────────┐
             │                                 │
             ▼                                 ▼
          Users                             Groups
             │                                 │
      ┌──────┴──────┐                         │
      │             │                         │
      ▼             ▼                         ▼
 Administrators  Employees            Security Groups
      │             │                         │
      │             │                         │
      │       ┌─────┼─────┬─────┐             │
      │       │     │     │     │             │
      ▼       ▼     ▼     ▼     ▼             ▼
 Admins     HR    IT  Sales Finance      GG_Employees
      │                                      │
      ▼                                      ▼
GG_IT_Admins                         Department Access

Future:
Users → Groups → Permissions → Resources
```

---

## Implementation Summary

### Phase 1 – Prepare User Locations

* Opened **Active Directory Users and Computers**.
* Navigated to the appropriate Organizational Units:

```text
Enterprise
└── Users
    ├── Administrators
    └── Employees
```

* Verified the OU structure created previously was ready for user organization.

---

### Phase 2 – Create Employee Accounts

* Created user accounts under department-specific employee locations.
* Entered user information:

  * First name
  * Last name
  * User logon name

Created users to simulate multiple business departments:

* HR

* IT

* Sales

* Finance

* Configured initial passwords.

* Completed the user creation wizard.

* Verified accounts were enabled.

---

### Phase 3 – Create Administrative Accounts

* Created separate administrative accounts instead of using the built-in Administrator account for daily administrative tasks.

Example:

```text
Username:
savanna.admin
```

* Added administrative users to appropriate security groups:

```text
GG_IT_Admins
Domain Admins (when required)
```

* Maintained membership in:

```text
Domain Users
```

* Followed enterprise practices by separating standard user accounts from administrative accounts.

---

### Phase 4 – Configure User Security Practices

* Disabled the built-in Guest account.
* Verified users were stored in the correct Organizational Units.
* Confirmed security group memberships using the **Member Of** tab.

---

## Validation

* Active Directory Users and Computers opened successfully.
* Users appeared in the correct Organizational Units.
* Employee and administrator accounts were created successfully.
* Accounts were enabled and available for authentication.
* Security group memberships were verified.
* Administrative accounts were separated from normal user accounts.
* Environment was prepared for future domain client authentication.

---

## Challenges Encountered

### Using the Built-In Administrator Account

**Issue:**

Initially used the default Administrator account for administrative activities.

**Resolution:**

* Moved away from using the built-in account as a daily administrator account.
* Created separate named administrative accounts.
* Assigned administrative permissions through security groups.

This follows enterprise security practices by making administrative activity traceable to individual accounts.

---

## Useful Commands

List all Active Directory users:

```powershell
Get-ADUser -Filter *
```

View a specific user:

```powershell
Get-ADUser username
```

View user group memberships:

```powershell
Get-ADPrincipalGroupMembership username
```

---

## Best Practices

* Create separate standard and administrative accounts.
* Avoid using built-in Administrator accounts for daily activities.
* Assign permissions through security groups instead of directly to users.
* Follow consistent username naming conventions.
* Organize users into department-based Organizational Units.
* Document account creation and access changes.
* Follow the principle of least privilege.

---

## Future Improvements

* Join Windows 11 client devices to the Active Directory domain.
* Test domain authentication using employee accounts.
* Configure password policies through Group Policy.
* Create onboarding and offboarding procedures.
* Automate user creation with PowerShell.
* Implement account lockout testing and troubleshooting scenarios.

---

## Related Documentation

* Active Directory Organizational Unit Design
* Active Directory Group Structure and Management
* Active Directory Security Groups
* Windows 11 Domain Join
* Group Policy Configuration
* PowerShell Active Directory Automation
