# Windows 11 Pro Workstation Configuration

## Business Scenario

A small-to-medium business requires properly configured employee workstations before they can be connected to company infrastructure. This project simulates the preparation of a Windows endpoint device by applying baseline configurations, security settings, updates, and documentation practices used by IT support teams.

The goal is to establish a stable Windows 11 client workstation that can later be integrated into the enterprise lab environment for Active Directory management, Group Policy testing, and endpoint troubleshooting.

---

## Project Objective

Configure Windows 11 Pro ARM after installation to establish a stable and usable client workstation for an enterprise home lab environment.

This includes applying baseline system settings, verifying hardware resources, configuring user preferences, securing the workstation, and preparing the endpoint for future IT administration tasks.

---

## Skills Demonstrated

- Windows 11 endpoint configuration
- VMware Fusion virtual machine management
- Windows system administration fundamentals
- Operating system updates and maintenance
- Hardware and resource verification
- Network configuration and troubleshooting
- Windows Security and Firewall configuration
- User account management
- System documentation practices
- Enterprise workstation preparation

---


|Component|Details|
|---|---|
|Host|MacBook Air M2 (8GB RAM)|
|Hypervisor|VMware Fusion|
|Client|Windows 11 Pro ARM|
|Server|Windows Server 2022 Datacenter (LABDC01)|
|Cloud|Microsoft Azure Student Subscription|
|Tools|Windows Settings, Control Panel, Task Manager, Device Manager, System Information, Command Prompt, PowerShell, Windows Update|

## Project Architecture

MacBook Air M2  
↓  
VMware Fusion  
↓  
Windows 11 Pro ARM Client Workstation  
↓  
Baseline Configuration and Security Settings  
↓  
Future Integration with Active Directory Domain (LABDC01)

---

## Implementation Summary

### Phase 1

Reviewed and verified the Windows 11 Pro ARM workstation configuration.

- Verified Windows edition, version, processor, and available memory.
- Documented virtual machine resource allocation.
- Confirmed administrator account access.
- Verified VMware Fusion integration features were functioning correctly.

### Phase 2

Configured baseline Windows workstation settings.

- Installed Windows updates and security patches.
- Configured system name using a consistent lab naming convention.
- Verified time zone and regional settings.
- Reviewed user account configuration and permissions.
- Adjusted power and performance settings for virtual machine usage.
- Verified Windows Security, Microsoft Defender, and Firewall status.

### Phase 3

Prepared the workstation for enterprise lab activities.

- Verified network connectivity using:
  - Windows Network Settings
  - ipconfig command
  - Command Prompt and PowerShell tools
- Configured File Explorer settings for administrative tasks.
- Installed required baseline applications and documented installed software.
- Created a system restore point before additional lab configuration changes.
- Recorded final workstation configuration details for documentation.

---

## Validation

- Confirmed Windows 11 Pro ARM installation is fully updated.
- Verified workstation name follows the lab naming convention.
- Confirmed VMware Fusion integration features are working correctly.
- Verified network connectivity and IP configuration.
- Confirmed Windows Defender and Firewall are enabled.
- Verified installed applications appear correctly.
- Confirmed system information matches documented configuration.
- Verified workstation is prepared for future Active Directory integration.

---

## Challenges Encountered

- Windows 11 ARM compatibility limitations required verifying application support before installation.
- Virtual machine performance was limited by the available MacBook Air M2 resources.
- Some enterprise tools and drivers may not fully support ARM architecture.
- Hardware information displayed inside the virtual machine represents virtualized resources rather than physical hardware.
- VMware Fusion features and compatibility may vary depending on version and Windows ARM support.

---

## Future Improvements

- Join the Windows client workstation to the Active Directory domain.
- Configure Group Policy-based workstation management.
- Deploy enterprise software through centralized management methods.
- Implement endpoint security configurations.
- Automate workstation configuration using PowerShell.
- Integrate additional Azure services for hybrid management.

---

