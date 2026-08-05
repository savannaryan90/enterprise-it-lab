# Domain Controller Role Verification and Health Validation

## Business Scenario

> After deploying a Domain Controller, administrators must verify that critical Active Directory services are functioning correctly before introducing users, computers, Group Policy, and other enterprise resources. A Domain Controller depends on multiple integrated services including Active Directory Domain Services, DNS, Kerberos authentication, LDAP, SYSVOL, and NETLOGON. Validating these components helps prevent future issues such as domain join failures, authentication problems, Group Policy failures, and DNS-related errors.

---

## Project Objective

> Validate the health and configuration of the newly promoted Windows Server Domain Controller by confirming that Active Directory roles, domain authentication, DNS services, default directory structures, and system events are functioning correctly. This ensures the foundation is stable before continuing with additional Active Directory administration tasks.

---

## Skills Demonstrated

* Active Directory Domain Controller Validation
* Windows Server Administration
* DNS Verification and Troubleshooting
* Active Directory Users and Computers Management
* PowerShell Server Validation
* Event Viewer Analysis
* Windows Server Role Verification
* Domain Authentication Testing
* Enterprise Troubleshooting Methodology
* Post-Deployment Health Checks

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Domain-Controller-Verification.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/AD-Users-Computers.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/DNS-Verification.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Event-Viewer-Validation.png)

---

| Component         | Details                                               |
| ----------------- | ----------------------------------------------------- |
| Cloud Provider    | Microsoft Azure                                       |
| Server            | Windows Server 2022 Datacenter                        |
| Server Name       | LABDC01                                               |
| Server Role       | Domain Controller                                     |
| Directory Service | Active Directory Domain Services                      |
| DNS Service       | Active Directory Integrated DNS                       |
| Validation Tools  | Server Manager, PowerShell, DNS Manager, Event Viewer |

---

## Project Architecture

```text id="8k8qz2"
                         Microsoft Azure
                               │
                               │
                  Windows Server 2022 VM
                           LABDC01
                               │
                               │
                    Domain Controller Roles
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
        ▼                      ▼                      ▼
 Active Directory          DNS Server           Authentication
 Domain Services                                Services
        │                      │                      │
        │                      │                      │
        ▼                      ▼                      ▼
 Users, Computers        DNS Records          Kerberos / LDAP
 Groups                  Service Records       Domain Logins
 OUs                     _ldap._tcp            Secure Access
                               │
                               │
                         SYSVOL / NETLOGON
                               │
                               ▼
                    Group Policy Infrastructure
                         (Future Phase)
```

---

## Implementation Summary

### Phase 1 – Verify Domain Controller Roles

* Logged into LABDC01 using a domain administrator account.
* Opened Server Manager.
* Confirmed the expected server roles were present:

  * Active Directory Domain Services
  * DNS Server
  * File and Storage Services
* Verified that Domain Controller promotion completed successfully.

### Phase 2 – Validate Server Identity and Domain Authentication

* Opened PowerShell.
* Verified the server hostname:

```powershell
hostname
```

Expected result:

```text
LABDC01
```

* Verified domain authentication:

```powershell
whoami
```

Expected format:

```text
domain\administrator
```

* Confirmed authentication was occurring through the domain rather than only the local machine account.

### Phase 3 – Validate Active Directory and DNS Services

* Opened Active Directory Users and Computers.

* Verified default Active Directory containers existed:

  * Builtin
  * Computers
  * Domain Controllers
  * Users

* Opened DNS Manager.

* Reviewed Forward Lookup Zones.

* Confirmed domain DNS records were present.

### Phase 4 – Review System Health

* Opened Event Viewer.

* Reviewed:

  * Windows Logs → System

* Checked for repeated critical issues related to:

  * DNS
  * NTDS
  * NETLOGON

* Confirmed no recurring critical failures were present.

---

## Validation

* Active Directory Domain Services role verified.
* Domain Controller identity confirmed.
* Server naming convention validated.
* Domain authentication confirmed.
* Active Directory default containers present.
* DNS zones and records verified.
* System event logs reviewed for major service failures.
* Domain Controller confirmed ready for future configuration.

---

## Challenges Encountered

### DNS Service Record Resolution Warning

**Issue:**

Event ID:

```text
0x000003F6
```

Message:

```text
Name resolution for the name _ldap._tcp.dc._msdcs.homelab.local timed out after none of the configured DNS servers responded.
```

**Cause:**

The Domain Controller was unable to locate itself through DNS using Active Directory service records.

**Troubleshooting Steps:**

* Verified DNS configuration on the server.
* Confirmed DNS services were running.
* Reviewed Active Directory DNS records.
* Confirmed the Domain Controller was using the correct DNS server configuration.

---

### File and Storage Services Missing

**Issue:**

File and Storage Services did not appear as expected in Server Manager.

**Resolution:**

1. Opened Server Manager.
2. Selected:

   * Manage
   * Add Roles and Features
3. Selected:

   * Role-based or feature-based installation
4. Chose the local server.
5. Expanded:

   * File and Storage Services
6. Installed:

   * File Server

This restored the required File and Storage Services components.

---

## Helpful Commands

Verify server name:

```powershell
hostname
```

Verify domain authentication:

```powershell
whoami
```

---

## Best Practices

* Always validate a Domain Controller after promotion.
* Verify DNS functionality before creating users or Group Policies.
* Confirm domain authentication before joining client computers.
* Review Event Viewer after major infrastructure changes.
* Do not assume successful installation means all services are healthy.
* Document troubleshooting steps and resolutions for future reference.

---

## Future Improvements

* Create Organizational Units based on business departments.
* Configure security groups.
* Create user accounts.
* Join Windows 11 client devices to the domain.
* Implement Group Policy Objects.
* Configure file shares and NTFS permissions.
* Implement Active Directory security hardening.

---

## Related Documentation

* Active Directory Domain Services Installation
* Domain Controller Promotion
* Azure Windows Server Deployment
* Azure Virtual Networking Configuration
* DNS Configuration
* Organizational Unit Design
* User and Group Management
