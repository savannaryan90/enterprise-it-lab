# Active Directory Domain Services (AD DS) Installation

## Business Scenario

> Organizations rely on Active Directory Domain Services (AD DS) to centrally manage user identities, computers, security groups, authentication, and access to network resources. Before a Windows Server can function as a Domain Controller, the Active Directory Domain Services server role must first be installed. This project prepares the Windows Server infrastructure for centralized identity management within the enterprise lab.

---

## Project Objective

> Install the Active Directory Domain Services (AD DS) role on a Windows Server 2022 virtual machine hosted in Microsoft Azure. This establishes the foundation for promoting the server to a Domain Controller and implementing centralized authentication, authorization, and directory services.

---

## Skills Demonstrated

* Windows Server Administration
* Active Directory Domain Services (AD DS)
* Windows Server Roles and Features
* Server Manager Administration
* Identity Infrastructure Fundamentals
* Enterprise Server Configuration
* Microsoft Azure Virtual Machine Administration
* Windows Server Validation
* Basic Server Troubleshooting
* Technical Documentation

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/ADDS-Installation-Wizard.png)

> ![Enterprise IT Portfolio](../../01-Images/ActiveDirectory/ADDS-Installed.png)

---

| Component           | Details                          |
| ------------------- | -------------------------------- |
| Cloud Provider      | Microsoft Azure                  |
| Server              | Windows Server 2022 Datacenter   |
| Server Name         | LABDC01                          |
| Server Role         | Active Directory Domain Services |
| Management Tool     | Server Manager                   |
| Installation Method | Role-Based Installation          |

---

## Project Architecture

> *Architecture is documented as part of the Azure Networking Configuration project.*

---

## Implementation Summary

### Phase 1 – Server Preparation

* Verified the Windows Server virtual machine was operational.
* Confirmed administrator access to the server.
* Validated network connectivity and system readiness.

### Phase 2 – Active Directory Role Installation

* Opened Server Manager and launched the **Add Roles and Features Wizard**.
* Selected a role-based installation for the local server.
* Installed the **Active Directory Domain Services (AD DS)** server role.
* Added all required supporting features.

### Phase 3 – Installation Verification

* Confirmed the AD DS role installed successfully.
* Verified the role appeared within Server Manager.
* Confirmed the server was ready for Domain Controller promotion.
* Documented the installation for future infrastructure deployment.

---

## Validation

* Active Directory Domain Services installed successfully.
* Required supporting features installed without errors.
* Server Manager displayed the AD DS server role.
* Installation completed without warnings or failures.
* Server prepared for Domain Controller promotion.

---

## Challenges Encountered

* Understanding that installing the AD DS role does not automatically configure the server as a Domain Controller.
* Differentiating between server role installation and Active Directory forest/domain creation.
* Ensuring the server met all prerequisites before beginning installation.

---

## Future Improvements

* Promote the server to a Domain Controller.
* Create a new Active Directory forest and domain.
* Configure DNS integration.
* Design an Organizational Unit (OU) structure.
* Create users, groups, and service accounts.
* Implement Group Policy Objects (GPOs).

---

## Related Documentation

* Microsoft Azure Windows Server Deployment
* Azure Virtual Networking Configuration
* Remote Administration with Windows App (RDP)
* Domain Controller Promotion
