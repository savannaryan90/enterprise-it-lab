# Installing VMware Fusion Tools

## Prerequisites
- VMware Fusion installed on the MacBook Air (Apple Silicon/M2) 
- Windows 11 Pro ARM virtual machine created and running 
- Windows user account with local administrator privileges 
- Active internet connection

---

## Environment
Host: MacBook Air (M2, 8 GB RAM)
Client Windows 11 Pro ARM Virtual Machine
Server:None (planned for future phases)
Cloud: none
OS:
Tools:

---
## Procedure

1. Start the Windows 11 Pro ARM virtual machine in VMware Fusion. 
2. Sign in to Windows using an administrator account. 
3. In VMware Fusion, open the virtual machine menu:
- Select **Virtual Machine** 
- Select **Install VMware Tools** (or **Reinstall VMware Tools** if already installed) 
1. If prompted, allow VMware Fusion to connect the VMware Tools installer media to the virtual CD/DVD drive. 
2. In Windows, open File Explorer. 
3. Navigate to the mounted VMware Tools virtual CD drive. 
4. Run the VMware Tools installer. 
5. Follow the installation wizard: 
	- Accept the license agreement 
	- Use the default installation options unless a specific feature is required 
	- Complete the installation 
6. Restart the Windows virtual machine when prompted. 
7. After reboot, allow Windows a few minutes to detect and configure VMware virtual hardware drivers. 
8. Confirm VMware Tools services are running: 
	- Open Task Manager 
	- Select the Services tab 
	- Verify VMware-related services are running

---


## Verification
- Confirm VMware Tools is installed: - Open **Control Panel → Programs → Programs and Features** - Verify VMware Tools appears in the installed programs list - 
- Confirm improved VM integration: - Test dynamic resolution resizing - Test mouse movement between macOS and Windows without pointer capture issues -
- Verify VMware Tools service: - Open **Services.msc** - Confirm VMware Tools service is running
--- 
## References
- VMware Fusion Documentation 
- VMware Tools Documentation 
- Microsoft Windows 11 ARM Documentation

---

## Screenshots 

>  ![Enterprise IT Portfolio](../../../01-Images/VMware/Tools-Install.png)

