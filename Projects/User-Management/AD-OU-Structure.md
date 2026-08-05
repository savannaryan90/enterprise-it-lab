# Active Directory Organizational Unit (OU) Structure Design

## Business Scenario

> Organizations use Organizational Units (OUs) to organize Active Directory objects such as users, computers, servers, and groups into manageable sections. In an enterprise environment, administrators typically do not store all objects inside the default Active Directory containers. Instead, they design an OU structure that reflects business departments and administrative requirements. This improves organization, simplifies Group Policy management, and allows future delegation of administrative responsibilities.

---

## Project Objective

> Design and create an enterprise-style Organizational Unit (OU) structure within Active Directory. The goal is to create a logical framework for managing users, computers, servers, and groups while preparing the domain for future configuration tasks such as Group Policy, user management, and workstation administration.

---

## Skills Demonstrated

* Active Directory Organizational Unit Design
* Active Directory Users and Computers Management
* Directory Structure Planning
* Enterprise Identity Organization
* Active Directory Administration
* Group Policy Preparation
* Windows Server Administration
* Active Directory Object Management
* Technical Documentation

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/OU-Structure.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/Active-Directory-Users-Computers.png)

---

| Component         | Details                              |
| ----------------- | ------------------------------------ |
| Cloud Provider    | Microsoft Azure                      |
| Server            | Windows Server 2022 Datacenter       |
| Server Name       | LABDC01                              |
| Directory Service | Active Directory Domain Services     |
| Management Tool   | Active Directory Users and Computers |
| Structure Created | Organizational Units                 |

---

## Project Architecture

```text
                         Active Directory Domain
                                  │
                                  │
                             Company OU
                                  │
        ┌─────────────────────────┼─────────────────────────┐
        │                         │                         │
        ▼                         ▼                         ▼
      Users                   Computers                  Groups
        │                         │
        │                         │
 ┌──────┼──────┐             ┌────┴────┐
 │      │      │             │         │
HR     IT   Finance      Workstations Laptops
Sales Marketing

                                  │
                                  ▼
                              Servers
```

---

## Implementation Summary

### Phase 1 – Review Default Active Directory Structure

* Opened **Active Directory Users and Computers**.

* Expanded the Active Directory domain.

* Reviewed the default containers created during Domain Controller promotion:

  * Builtin
  * Computers
  * Domain Controllers
  * Users

* Identified the limitations of using default containers for enterprise management.

### Phase 2 – Create Enterprise OU Structure

* Created a top-level organizational unit to contain company resources.
* Enabled **Protect container from accidental deletion** to prevent accidental changes.
* Created additional organizational units for:

**Users**

* HR
* IT
* Finance
* Sales
* Marketing

**Computers**

* Workstations
* Laptops

**Groups**

**Servers**

This structure creates a scalable foundation for future Active Directory administration.

### Phase 3 – Prepare Active Directory for Management

* Verified all OUs were created in the correct location.
* Confirmed the hierarchy reflected an enterprise-style environment.
* Prepared the domain for future:

  * User account creation
  * Security group management
  * Group Policy configuration
  * Computer organization

---

## Validation

* Active Directory Users and Computers opened successfully.
* Domain structure was visible.
* Company OU was created successfully.
* Required organizational units were created.
* OUs appeared under the correct domain location.
* No errors occurred during OU creation.
* Structure was ready for future Active Directory object management.

---

## Challenges Encountered

* Understanding the difference between default Active Directory containers and Organizational Units.
* Designing an OU structure that balances organization and future scalability.
* Determining which objects should be separated into their own administrative areas.
* Avoiding unnecessary complexity while maintaining an enterprise-style design.

---

## Best Practices

* Design OU structure before creating large numbers of users or computers.
* Use OUs to support administrative tasks rather than simply creating folders.
* Enable accidental deletion protection on important OUs.
* Avoid placing enterprise objects directly into default containers.
* Design OUs with future Group Policy requirements in mind.

---

## Future Improvements

* Create user accounts and assign them to department OUs.
* Create security groups based on business roles.
* Join Windows 11 client devices to the domain.
* Apply Group Policy Objects to specific OUs.
* Configure delegated administration permissions.
* Expand OU structure as additional departments and services are added.

---

## Related Documentation

* Active Directory Domain Services Installation
* Domain Controller Promotion
* Domain Controller Role Verification
* User Account Management
* Security Group Management
* Group Policy Configuration
* Windows 11 Domain Join
