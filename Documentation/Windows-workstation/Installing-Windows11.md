# Installing Windows 11 Pro for Workstation Using VM

## Objective  
  
Install Windows 11 Pro ARM as a virtual machine using VMware Fusion on a macOS host to create the foundation for an enterprise Windows homelab.
  
---  
  
## Background  
  
A virtual machine (VM) allows multiple operating systems to run on a single physical computer by sharing hardware resources through a hypervisor. VMware Fusion provides virtualization on macOS and supports Windows 11 ARM on Apple Silicon Macs.  
  
Installing Windows in a virtual environment allows enterprise administration tasks to be practiced without affecting the host operating system. 
  
---  
  
## Prerequisites  
  
- VMware Fusion installed  
- Windows 11 ARM installation media  
- Sufficient disk space  
- Internet connection  
- TPM enabled within the virtual machine
  
---  
  
## Procedure  
  
1.  Create Virtual Machine
	1. Created a new virtual machine in VMware Fusion using the Windows 11 ARM installation image.
2.  Configure Virtual Hardware
	1. Configured memory, processor allocation, storage size, and virtual TPM before starting the installation.
3.  Install Windows
	1. Completed the Windows installation wizard and selected Windows 11 Pro.
4. Complete Initial Setup
	1. Configured region, keyboard layout, local user account, and completed the Windows Out-of-Box Experience (OOBE).
5. Install VMware Tools
	1. Installed VMware Tools to improve graphics performance, mouse integration, display resizing, and clipboard functionality.
  
---  
  
## Verification  
  
- Windows boots successfully.  
- Desktop loads without errors.  
- Network connectivity is available.  
- VMware Tools installed successfully.  
- Display resolution automatically adjusts to the VM window.
  
---  
  
## Issues
- Windows 11 ARM installation requires compatible virtualization software and hardware support.
- Some x64 Windows applications may rely on emulation and may have reduced performance or compatibility issues.
- VMware Fusion support for Windows 11 ARM differs from traditional Intel-based Windows virtual machines.
- Virtual machine performance is limited by host resources, including available RAM, CPU cores, and storage capacity.
- Network adapters, display drivers, and integration features may require VMware Tools installation after Windows setup.
- Windows activation may require a valid Windows license and Microsoft account depending on the deployment method.
- Some enterprise management tools, drivers, or security software may not support ARM architecture.
---
## References
- Microsoft Windows 11 ARM Documentation
- Microsoft Windows 11 Installation Documentation
- VMware Fusion Documentation
- VMware Fusion Support Documentation for Apple Silicon Macs
- Microsoft Windows System Requirements Documentation

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Windows-11-Client/Install.png)

---
