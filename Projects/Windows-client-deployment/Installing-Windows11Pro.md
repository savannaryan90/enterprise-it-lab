# Installing Windows 11 Pro ARM using VMware Fusion

## Business Scenario

A small-to-medium business requires standardized employee workstations that can securely connect to centralized IT infrastructure. This project simulates the deployment of an enterprise Windows client device that will later be integrated with Active Directory for centralized user management, Group Policy administration, and endpoint troubleshooting.

---

## Project Objective

Deploy and configure a Windows 11 Pro ARM virtual machine using VMware Fusion on a MacBook Air M2 to create an enterprise-style client workstation for an Active Directory homelab environment.

The workstation will be used to practice real-world IT support tasks including domain joining, user authentication, Group Policy testing, software deployment, and troubleshooting.

---

## Skills Demonstrated

- Windows 11 Pro ARM deployment and configuration
- VMware Fusion virtualization
- Virtual machine resource management
- Windows system administration fundamentals
- Endpoint preparation for enterprise environments
- Installation of IT support and troubleshooting utilities
- Technical documentation and asset tracking

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Windows-11-Client/Install.png)

---

|Component|Details|
|---|---|
|Host|MacBook Air M2 (8GB RAM)|
|Hypervisor|VMware Fusion|
|Client|Windows 11 Pro ARM|
|Server|Windows Server 2022 Datacenter (LABDC01)|
|Cloud|Microsoft Azure Student Subscription|
|Installed Tools|7-Zip, CPU-Z, HWMonitor, Notepad++|

## Project Architecture

> Insert diagram showing:
> 
> MacBook Air M2  
> ↓  
> VMware Fusion  
> ↓  
> Windows 11 Pro ARM Client Workstation  
> ↓  
> Microsoft Azure  
> ↓  
> Windows Server 2022 Datacenter (LABDC01)

---

## Implementation Summary

### Phase 1

Created and configured a Windows 11 Pro ARM virtual machine using VMware Fusion on macOS.

- Installed Windows 11 Pro ARM.
- Completed initial operating system configuration.
- Applied Windows updates.
- Verified system functionality.

### Phase 2

Prepared the workstation with common IT support and troubleshooting tools.

Installed:

- **7-Zip**
  - Used for file compression and extraction tasks.
  - Commonly used when handling software packages, logs, and archived files.

- **CPU-Z**
  - Used to view processor, memory, and hardware information.
  - Useful during hardware troubleshooting and system verification.

- **HWMonitor**
  - Used to monitor hardware health information.
  - Helps identify overheating or hardware-related issues.

- **Notepad++**
  - Used for editing scripts, configuration files, logs, and technical documentation.

### Phase 3

Prepared the workstation for future enterprise integration.

- Configured the client as an endpoint device within the homelab environment.
- Prepared the system for future Active Directory domain joining.
- Verified compatibility with the Windows Server infrastructure.

---

## Validation

- Confirmed Windows 11 Pro ARM installation completed successfully.
- Verified VMware Fusion virtual machine functionality.
- Confirmed required IT support tools were installed.
- Verified workstation is ready for future Active Directory integration.

---

## Challenges Encountered

- Windows ARM compatibility required verifying application support before installation.
- Limited MacBook Air resources required careful allocation of virtual machine resources.
- Ensured installed tools were lightweight enough for the available hardware.


---

## Future Improvements

- Join the workstation to the Active Directory domain.
- Apply enterprise Group Policy configurations.
- Configure user authentication and permissions.
- Test common Help Desk troubleshooting scenarios.
- Expand endpoint management capabilities.

---
