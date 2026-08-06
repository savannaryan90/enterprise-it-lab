# Windows App Remote Desktop Configuration for Windows 11 VM

## Business Scenario

> In an enterprise environment, IT support technicians frequently use remote access tools to troubleshoot, configure, and maintain employee workstations without requiring physical access to the device. This project simulates remote administration of a Windows endpoint using Remote Desktop Protocol (RDP) from a macOS administrator workstation.

---

## Project Objective

> Configure and validate Remote Desktop access from a MacBook Air using Windows App to connect to a Windows 11 Pro ARM virtual machine hosted in VMware Fusion. The goal was to practice endpoint remote administration, user authentication, network troubleshooting, and common Help Desk troubleshooting workflows.

---

## Skills Demonstrated

* Configured Remote Desktop access on a Windows client workstation.
* Used Windows App to establish RDP connections.
* Identified system usernames and IP addresses using PowerShell.
* Troubleshot Remote Desktop connection failures.
* Diagnosed RDP error code 0x204.
* Verified Windows Remote Desktop Services.
* Reviewed Windows Firewall rules.
* Troubleshot VMware Fusion virtual networking.
* Updated remote connection settings after IP address changes.
* Applied endpoint networking best practices.

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/Windows-App-Connection.png)

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/RDP-Error-0x204.png)

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/Successful-RDP-Connection.png)

---

| Component            | Details                                                      |
| -------------------- | ------------------------------------------------------------ |
| Host                 | MacBook Air M2                                               |
| Hypervisor           | VMware Fusion                                                |
| Client               | Windows 11 Pro ARM                                           |
| Server               | Windows Server 2022 Datacenter Azure VM (future integration) |
| Remote Access Method | Remote Desktop Protocol (RDP)                                |
| Software             | Windows App, PowerShell                                      |
| Cloud                | Microsoft Azure (future domain integration)                  |

---

## Project Architecture

> Insert diagram here.

```
MacBook Air M2
│
├── VMware Fusion
│   │
│   └── Windows 11 Pro ARM Client VM
│       │
│       ├── Remote Desktop Enabled
│       ├── Windows Remote Desktop Services
│       └── Private IP Address
│
└── Windows App (macOS)
        │
        └── RDP Connection
             │
             ▼
        Windows 11 VM Desktop
```

---

## Implementation Summary

### Phase 1 - Configure Windows Remote Desktop

* Installed Windows App on macOS.
* Enabled Remote Desktop on the Windows 11 Pro ARM virtual machine.
* Identified the Windows username using PowerShell.
* Retrieved the VM IP address using `ipconfig`.
* Configured Windows App with the correct connection information.

---

### Phase 2 - Establish Remote Connection

* Added the Windows VM as a PC connection inside Windows App.
* Configured user credentials.
* Connected successfully through Remote Desktop.
* Verified remote access functionality.

---

### Phase 3 - Troubleshoot RDP Connectivity Issue

* Encountered RDP error code `0x204`.
* Verified Remote Desktop Services using:

```powershell
Get-Service TermService
```

* Checked Windows Firewall Remote Desktop permissions.
* Reviewed VMware Fusion network adapter settings.
* Identified that the VM IP address had changed.
* Updated the Windows App connection with the current IP address.
* Successfully restored remote access.

---

## Validation

* Confirmed Windows App successfully connected to the Windows 11 VM.
* Verified Remote Desktop Services were running.
* Confirmed the correct Windows username was used for authentication.
* Verified the VM IP address matched the Windows App connection.
* Successfully accessed the Windows desktop remotely.
* Tested remote administration functionality.

---

## Challenges Encountered

[Windows App RDP Connection Failure](../Troubleshooting/Windows%20App%20RDP%20Connection%20Failure.md)

---

## Future Improvements

* Configure a static IP address for the Windows client VM.
* Integrate the workstation into the Active Directory domain.
* Configure domain-based authentication instead of local accounts.
* Use Group Policy to manage Remote Desktop settings.
* Document remote support workflows for enterprise Help Desk scenarios.

---

## Related Documentation

* VMware Fusion Networking Configuration
* Windows 11 Client Workstation Setup
* Windows App Remote Desktop Connection Troubleshooting
* Network Configuration and IP Addressing
* Enterprise Remote Administration
