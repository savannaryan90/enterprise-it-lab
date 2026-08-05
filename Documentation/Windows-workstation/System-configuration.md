# System Configuration

## Objective / Purpose

- Configure Windows 11 Pro ARM after installation to establish a stable and usable client workstation for the enterprise home lab environment.
- Apply baseline system settings, verify hardware resources, configure user preferences, and prepare the workstation for future IT administration tasks.
- Develop experience with Windows endpoint configuration, documentation, and troubleshooting practices used in enterprise environments.

---

## Prerequisites

- Windows 11 Pro ARM virtual machine successfully installed
- VMware Fusion installed and configured on the host system
- Administrator account available on the Windows virtual machine
- VMware Tools installed (recommended)
- Internet connectivity available
- Windows activated and updated with the latest patches

---

## Environment

Host: MacBook Air (M2, 8 GB RAM)  
Client: Windows 11 Pro ARM Virtual Machine  
Server: None (planned for future phases)  
Cloud: None

OS:

- Windows 11 Pro ARM

Tools:

- Windows Settings
- Control Panel
- Task Manager
- Device Manager
- System Information (msinfo32)
- Command Prompt
- PowerShell
- Windows Update

---

## Procedure

1. Review system specifications:
    - Open **Settings → System → About**
    - Verify Windows edition, version, processor, and installed RAM.
    - Record VM resource allocation for documentation.
2. Configure Windows Updates:
    - Open **Settings → Windows Update**
    - Check for available updates.
    - Install all security and feature updates.
    - Restart the system if required.
3. Configure system name:
    - Open **Settings → System → About**
    - Rename the device using an organized naming convention.
    - Restart the system to apply changes.
4. Configure time and regional settings:
    - Verify time zone.
    - Confirm correct date and time synchronization.
    - Configure regional format settings.
5. Configure user accounts:
    - Verify the local administrator account.
    - Create additional standard user accounts if needed for testing.
    - Review account permissions.
6. Configure power and performance settings:
    - Adjust power settings based on VM usage.
    - Verify performance settings are appropriate for lab workloads.
7. Configure privacy and security settings:
    - Review Windows Security settings.
    - Verify Microsoft Defender is enabled.
    - Review firewall status.
    - Configure basic security preferences.
8. Configure networking:
    - Verify the virtual network adapter is working.
    - Confirm internet connectivity.
    - Record IP configuration using:
        - ipconfig
        - Windows Network Settings
9. Configure File Explorer settings:
    - Enable visibility of file extensions if required.
    - Configure hidden file visibility for administrative tasks.
    - Review default file locations.
10. Install required baseline applications:

- Install approved utilities for the lab environment.
- Document installed software.

11. Create a system restore point:

- Enable System Protection.
- Create a restore point before major configuration changes.

12. Document final configuration:

- Record OS version.
- Record installed applications.
- Record system resources.
- Record configuration changes.

---

## Verification

- Confirm Windows 11 Pro ARM is fully updated.
- Verify system name follows the lab naming convention.
- Confirm VMware integration features are working correctly.
- Verify network connectivity using Windows Network Settings and command-line tools.
- Confirm Windows Security and Firewall are enabled.
- Confirm installed applications appear under Installed Programs.
- Verify system information matches the documented configuration.
- Confirm the workstation is ready for future enterprise lab phases.

---

## References

- Microsoft Windows 11 Documentation
- Microsoft Windows Security Documentation
- Microsoft Windows Update Documentation
- Microsoft System Configuration Documentation
- VMware Fusion Documentation
- VMware Fusion Support Documentation for Apple Silicon Macs
