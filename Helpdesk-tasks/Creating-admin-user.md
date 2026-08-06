# HD-002 – Create a Local Administrator Account

## Ticket Information

| Field           | Value                   |
| --------------- | ----------------------- |
| **Ticket ID**   | HD-002                  |
| **Category**    | User Account Management |
| **Priority**    | Medium                  |
| **Status**      | Completed               |
| **Environment** | Windows 11 Pro          |
| **Reported By** | IT Administrator        |
| **Technician**  | Help Desk               |

---

## User Request

> A local administrator account was required to provide administrative access for system management while keeping the primary user account as a standard user. This follows the principle of using separate accounts for administrative tasks.

---

## Initial Assessment

Before creating the account, verify:

* The request is authorized.
* An administrator account does not already exist.
* The account name follows the organization's naming convention.
* The computer has sufficient administrative privileges to create local accounts.

---

## Procedure

1. Open **Local Users and Groups**.

```text
lusrmgr.msc
```

2. Navigate to:

```text
Local Users and Groups
└── Users
```

3. Right-click **Users** and select:

```text
New User...
```

4. Enter the account information:

* Username
* Full Name
* Description
* Strong password

5. Configure password options as required.

6. Select **Create**.

7. Open the new user's **Properties**.

8. Select the **Member Of** tab.

9. Click **Add**.

10. Add the account to:

```text
Administrators
```

11. Select **OK** and close the dialog boxes.

---

## Verification

* Confirm the new account appears under **Users**.
* Verify the account is enabled.
* Confirm membership in the **Administrators** group.
* Sign in with the new account (optional) to verify administrative access.

---

## Resolution

A dedicated local administrator account was successfully created and added to the local **Administrators** group. The account can now be used for administrative tasks without using the primary user account.

---

## Best Practices

* Use separate administrator and standard user accounts.
* Follow a consistent naming convention (e.g., `firstname.admin`).
* Assign administrator rights only when necessary.
* Use strong passwords.
* Keep the built-in **Administrator** account disabled or reserved as a break-glass account when appropriate.

---

## Skills Demonstrated

* Windows account administration
* Local user management
* Administrative privilege assignment
* Principle of Least Privilege (PoLP)
* Windows security best practices

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Users/Admin-User.png)

---

## Related Documentation

* Windows User Management
* Windows Security Best Practices
* Local Users and Groups
* Active Directory User Management (Enterprise Lab)
