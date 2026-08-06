# Helpdesk Ticket

**Ticket ID:** HD-001
**Category:** Account Management
**Priority:** High
**Status:** Closed
**Technician:** *Your Name*
**Date Opened:** August 6, 2026
**Date Closed:** August 6, 2026

---

## User Information

**User Type:** Student

**Department:** College of Engineering

**Contact Method:** Phone

---

## Issue Summary

Student reports being unable to sign in to their university-issued Windows laptop before class. After multiple unsuccessful login attempts, they receive the message:

> "The referenced account is currently locked out and may not be logged on to."

---

## Initial Assessment

Verified the student's identity using university identification procedures. Confirmed that no widespread authentication outages had been reported.

---

## Troubleshooting Steps

1. Collected the username and confirmed the exact error message.
2. Verified network connectivity to ensure the device could communicate with the domain controller.
3. Opened **Active Directory Users and Computers (ADUC)**.
4. Located the user's account.
5. Confirmed the account was locked due to multiple failed authentication attempts.
6. Unlocked the account.
7. Reset the user's password to a temporary password.
8. Enabled **"User must change password at next logon."**
9. Instructed the student to sign in using the temporary password.
10. Verified successful login and password change.

---

## Root Cause

The account was automatically locked after exceeding the organization's failed login threshold, likely due to repeated incorrect password attempts.

---

## Resolution

* Account unlocked.
* Password reset.
* User successfully authenticated.
* Password changed by the user.
* Access restored.

---

## Verification

* User successfully logged into Windows.
* Access to Outlook and Microsoft 365 confirmed.
* No additional authentication issues observed.

---

## Knowledge Base Reference

**KB-001:** Reseting a Locked Active Directory User Account

---

## Time Metrics

**Response Time:** 3 minutes

**Resolution Time:** 10 minutes

**Total Ticket Time:** 13 minutes

---

## Escalation

**Required:** No

---

## Customer Communication

> Hello,
>
> Your account was locked after multiple unsuccessful login attempts. I have unlocked your account and provided a temporary password. After signing in, you'll be prompted to create a new password. Please let us know if you experience any further issues.
>
> Thank you,
> IT Helpdesk

---

