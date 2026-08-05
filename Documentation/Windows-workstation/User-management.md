# Workstation User Management

## Objective

Create and manage local user accounts on a Windows client workstation. This includes creating standard users, assigning administrator privileges, and configuring Remote Desktop Users for remote access.

---

## Prerequisites

- Windows client computer
- Local administrator account access
- Windows Pro, Enterprise, or Education edition (required for Remote Desktop hosting)
- Access to Computer Management or Windows Settings

---

## Environment

**Operating System:**
- Windows 11 Pro ARM
**Device Role:**
- Client workstation
**User Accounts:**
- Local Administrator account
- Standard User account
- Remote Desktop User account
**Tools:**
- Windows Settings
- Computer Management
- Local Users and Groups
---

## Procedure

1.  Open Local Users
	1. Go to Computer Management
	2. System Tools- Local Users & Groups- Users
2.  Creating Employee users
	1. Right click empty space in Users
	2. Select: New User
	3. Create: username, full name, description, password
	4. Uncheck: User must change password at login
	5. Leave Checked: User cannot change password (optional)
	6. Click: Create-Close
3. Create IT User
4. Employee Permissions
	1. Right-click username
	2. Click: properties
	3. Ensure employees are not administrators
5.  IT Permissions
	1. Right click helpdesk
	2. Click: properties
	3. For Member of click: add
	4. Type administrators
	5. click: check names-OK
6. Add Remote Desktop Users
	1. Computer Management-Local Users & groups-groups
	2. doubleclick: Remote desktop users
	3. Click add
	4. Type user name
	5. check names
	6. click: ok
---

## Verification

- New user accounts appear under Local Users and Groups.
- Administrator account can perform elevated tasks.
- Remote Desktop Users group contains the correct accounts.
- Users can sign in successfully.
- Permissions match the assigned role.

---

## References

- Microsoft Windows Local Users and Groups Documentation
- Microsoft Windows User Account Management Documentation
- Microsoft Remote Desktop Documentation
