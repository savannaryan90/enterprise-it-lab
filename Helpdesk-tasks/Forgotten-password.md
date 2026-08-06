# HD-001 – User Unable to Log In (Forgotten Password)

## Ticket Information

| Field           | Value              |
| --------------- | ------------------ |
| **Ticket ID**   | HD-001             |
| **Category**    | Account Management |
| **Priority**    | Medium             |
| **Status**      | Resolved           |
| **Environment** | Windows 11 Pro     |
| **Reported By** | End User           |
| **Technician**  | Help Desk          |

---

## User Report

> The user reported they were unable to sign in to their Windows account after forgetting their password. Multiple login attempts failed, preventing access to the desktop and applications.

---

## Initial Assessment

Before resetting the password, basic troubleshooting was performed to rule out common user errors.

Questions asked:

* Is the password definitely incorrect?
* Is **Caps Lock** enabled?
* Is the correct username being used?
* Has the account been disabled?
* Has the account been locked?

---

## Symptoms

* User unable to sign in.
* Windows rejects password.
* Desktop cannot be accessed.
* User states password has been forgotten.

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Users/New-Password-workstation.png)

---

## Root Cause

The user had forgotten their Windows account password. No issues were found with the account status or system authentication.

---

## Resolution

1. Open **Local Users and Groups**.

```
lusrmgr.msc
```

2. Navigate to:

```
Users
```

3. Locate the affected user account.

4. Right-click the account.

5. Select:

```
Set Password
```

6. Assign a temporary password.

7. Instruct the user to sign in.

8. Recommend changing the temporary password after successful login.

---

## Verification

* User successfully authenticated.
* Windows desktop loaded normally.
* User regained access to applications and files.
* No additional authentication issues observed.

---

## Prevention

* Encourage the use of strong, memorable passwords.
* Recommend using a password manager.
* Configure password policies appropriate for the environment.
* Document password reset procedures for Help Desk staff.

---

## Commands / Tools Used

| Tool                   | Purpose                     |
| ---------------------- | --------------------------- |
| `lusrmgr.msc`          | Open Local Users and Groups |
| Local Users and Groups | Reset user password         |

---

## Skills Demonstrated

* User authentication troubleshooting
* Windows account management
* Password reset procedures
* Root cause analysis
* End-user communication
* Verification of successful resolution

---

## Screenshots

> Add screenshots of:
>
> * Windows login failure
> * Local Users and Groups console
> * Password reset dialog
> * Successful user login

---

## Related Documentation

* Windows User Management
* Active Directory User Management *(future domain environment)*
* Password Policy Documentation
* Account Lockout Troubleshooting

---

As your lab evolves and your Windows 11 client joins the domain, you can create a second version of this ticket (for example, **HD-008 – Reset Active Directory User Password**) using **Active Directory Users and Computers (ADUC)** instead of `lusrmgr.msc`. Showing both local-account and domain-account support demonstrates progression from standalone Windows support to enterprise Active Directory administration.
