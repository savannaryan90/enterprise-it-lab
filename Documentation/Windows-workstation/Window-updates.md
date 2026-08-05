# Window Updates

## Objective / Purpose

- Configure Windows Update to ensure the Windows 11 Pro ARM client workstation remains secure, stable, and up to date.
- Develop experience managing operating system patching, security updates, and maintenance procedures used in enterprise IT environments.
- Establish a repeatable update process for maintaining Windows endpoints in the home lab.

---

## Prerequisites

- Windows 11 Pro ARM virtual machine installed and configured
- Administrator account access
- Active internet connection
- Windows Update service enabled
- VMware Fusion networking configured and operational

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
- Windows Update
- Control Panel
- Task Manager
- Command Prompt
- PowerShell
- Event Viewer

---

## Procedure

1. Open Windows Update settings:
    - Navigate to **Settings → Windows Update**.
2. Check for available updates:
    - Select **Check for updates**.
    - Allow Windows to scan for available updates.
3. Install available updates:
    - Install security updates.
    - Install quality updates.
    - Install driver updates when appropriate.
4. Restart the virtual machine:
    - Restart Windows when required to complete update installation.
5. Verify update history:
    - Navigate to **Settings → Windows Update → Update history**.
    - Review successfully installed updates.
6. Configure update preferences:
    - Review active hours.
    - Configure restart notifications.
    - Review advanced update settings.
7. Verify Windows Update services:
    - Open Services.
    - Confirm Windows Update services are running.
8. Document update status:
    - Record the Windows version.
    - Record the latest installed update.
    - Record any update-related issues.

---

## Verification

- Confirm Windows Update reports that the system is up to date.
- Verify the latest security and quality updates are installed.
- Review update history for successful installations.
- Confirm the system restarts normally after updates.
- Verify Windows version and build information using:
    - Settings → System → About
    - winver command
- Confirm applications and VMware integration features continue working after updates.

---

## Common Issues

- Windows 11 ARM updates may vary from standard x64 Windows updates due to architecture differences.
- Large feature updates may require additional VM storage space.
- Updates may temporarily affect VMware integration features or installed applications.
- Limited host resources (8 GB RAM) may increase update installation time.
- Some driver updates may not be available or may be managed differently in a virtual machine environment.
- Failed updates may require troubleshooting using Windows Update logs, restart procedures, or update repair tools.

---

## References

- Microsoft Windows Update Documentation
- Microsoft Windows 11 Update Documentation
- Microsoft Windows Update Troubleshooting Documentation
- Microsoft Windows Security Update Guide
- VMware Fusion Documentation
