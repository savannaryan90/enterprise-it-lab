# Remote Administration with Windows App (RDP)

## Business Scenario

> System administrators and IT support professionals frequently manage servers remotely rather than through direct physical access. Microsoft Azure supports secure remote administration using Remote Desktop Protocol (RDP), allowing administrators to configure, monitor, and troubleshoot Windows Server environments from virtually any location. This project establishes remote administrative access to the Azure-hosted Windows Server using Windows App on macOS.

---

## Project Objective

> Configure and validate remote administration of an Azure-hosted Windows Server 2022 virtual machine using Windows App and Remote Desktop Protocol (RDP). This enables efficient server management while developing practical experience with enterprise remote administration tools and workflows.

---

## Skills Demonstrated

* Microsoft Azure Administration
* Remote Desktop Protocol (RDP)
* Windows App Configuration
* Windows Server Remote Administration
* Azure Virtual Machine Management
* Remote Authentication
* Network Connectivity Verification
* Basic Remote Troubleshooting
* Enterprise Administration Workflows
* Technical Documentation

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Azure/Windows-app-Azure&Windows.png)

---

| Component         | Details                                  |
| ----------------- | ---------------------------------------- |
| Cloud Provider    | Microsoft Azure                          |
| Client Device     | MacBook Air (M2, macOS)                  |
| Remote Client     | Windows App                              |
| Server            | Windows Server 2022 Datacenter (LABDC01) |
| Connection Method | Remote Desktop Protocol (RDP)            |
| Authentication    | Local Administrator Account              |

---

## Project Architecture

> *Architecture is documented as part of the Azure Networking Configuration project.*

---

## Implementation Summary

### Phase 1 – Retrieve Connection Information

* Located the Azure virtual machine in the Azure Portal.
* Accessed the native RDP connection settings.
* Downloaded the Remote Desktop connection file.

### Phase 2 – Configure Windows App

* Opened Windows App on the macOS host.
* Created a new remote PC connection.
* Configured the connection using the Azure VM's public IP address and administrator credentials.
* Saved the connection for future administration.

### Phase 3 – Establish Remote Administration

* Connected to the Azure virtual machine using RDP.
* Authenticated with the local administrator account.
* Verified successful access to the Windows Server desktop.
* Confirmed the server was ready for ongoing administration and future infrastructure configuration.

---

## Validation

* Successfully connected to the Azure virtual machine using Windows App.
* Windows Server desktop loaded without errors.
* Administrator account authenticated successfully.
* Remote administrative tasks could be performed.
* Connection remained stable throughout the administration session.

---

## Challenges Encountered

* Understanding the relationship between Azure networking, Network Security Group (NSG) rules, and Remote Desktop connectivity.
* Verifying that the virtual machine was running and accessible before attempting a connection.
* Troubleshooting potential authentication and connectivity issues while establishing the initial remote session.

---

## Future Improvements

* Implement Azure Bastion to eliminate the need for a publicly exposed RDP port.
* Restrict Remote Desktop access using Network Security Group rules and trusted IP addresses.
* Configure multi-factor authentication for administrative access.
* Explore PowerShell remoting and Windows Admin Center for alternative remote management methods.
* Integrate Microsoft Entra ID authentication for enterprise identity management.

---

## Related Documentation

* Microsoft Azure Windows Server Deployment
* Azure Virtual Networking Configuration
* Windows Server Initial Configuration
* Active Directory Domain Services Installation
