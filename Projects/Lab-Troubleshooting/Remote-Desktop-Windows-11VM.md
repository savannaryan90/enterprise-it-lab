# Windows App Remote Desktop Connection to Windows 11 VM

## Objective

Configure Remote Desktop Protocol (RDP) access from macOS Windows App to a Windows 11 Pro ARM virtual machine running in VMware Fusion. This allows remote administration of the client workstation and simulates common enterprise remote support workflows.

---

## Prerequisites

### Virtual Machines Used

| Component         | Details                       |
| ----------------- | ----------------------------- |
| Host              | MacBook Air M2                |
| Client VM         | Windows 11 Pro ARM            |
| Hypervisor        | VMware Fusion                 |
| Connection Method | Remote Desktop Protocol (RDP) |

### Software

* Windows App (macOS)
* VMware Fusion
* Windows PowerShell
* Windows Remote Desktop Services

---

## Environment

**Host:** MacBook Air (M2, 8 GB RAM)
**Client:** Windows 11 Pro ARM Virtual Machine
**Server:** Windows Server 2022 Datacenter Azure VM (future domain environment)
**Cloud:** Microsoft Azure
**Tools:**

* Windows App
* PowerShell
* VMware Fusion
* Windows Network Settings

---

# Procedure

## 1. Install Windows App

1. Open the Mac App Store.
2. Search for **Windows App**.
3. Install and open the application.

---

## 2. Enable Remote Desktop on Windows 11 VM

1. Start the Windows 11 Pro ARM virtual machine.
2. Open:

```
Start Menu → Settings → System → Remote Desktop
```

3. Enable Remote Desktop.
4. Confirm the Remote Desktop prompt.

---

## 3. Identify Windows Username

1. Open PowerShell as Administrator.
2. Run:

```powershell
whoami
```

Example output:

```
it-workstation\server01
PS C:\Users\Server01>
```

Record the username:

```
server01
```

This account will be used when connecting through Windows App.

---

## 4. Identify Windows VM IP Address

In PowerShell run:

```powershell
ipconfig
```

Locate:

```
IPv4 Address
```

Example:

```
192.168.120.128
```

Record this IP address.

---

## 5. Configure Windows App on macOS

1. Open Windows App.
2. Select:

```
+ → Add PC
```

3. Configure:

PC Name:

```
Windows VM IP Address
```

Example:

```
192.168.120.128
```

4. Add user account:

* Username
* Password

5. Save the connection.

---

## 6. Connect Using Remote Desktop

1. Double-click the created PC connection.
2. Accept the connection prompt.
3. Verify the Windows desktop loads inside Windows App.

---

# Verification

Successful configuration was confirmed when:

* Windows App successfully connected to the Windows 11 VM.
* The Windows desktop loaded through the RDP session.
* Keyboard and mouse input worked correctly.
* Remote administration was possible from macOS.

---

# Troubleshooting

## Problem: Windows App Unable to Connect

### Error

```
0x204
```

### Symptoms

* Windows App was configured with the correct credentials.
* Connection attempt failed.
* Remote Desktop session could not be established.

---

## Possible Causes

* Remote Desktop service not running.
* Windows Firewall blocking RDP.
* VMware Fusion network configuration preventing communication.
* Windows VM IP address changed.
* Incorrect saved IP address in Windows App.

---

# Diagnostic Steps

## Step 1 - Verify Remote Desktop Service

Open PowerShell:

```powershell
Get-Service TermService
```

Expected:

```
Status: Running
```

If stopped:

```powershell
Start-Service TermService
```

---

## Step 2 - Check Windows Firewall

1. Open:

```
Windows Defender Firewall
```

2. Select:

```
Allow an app through firewall
```

3. Confirm:

```
Remote Desktop
```

is allowed on:

```
Private Networks
```

---

## Step 3 - Verify VMware Fusion Networking

1. Shut down the Windows VM.
2. Open VMware Fusion settings.
3. Select:

```
Network Adapter
```

4. Confirm:

```
Share with Mac
```

is selected.

---

## Step 4 - Verify Current IP Address

In Windows PowerShell:

```powershell
ipconfig
```

Compare the current IPv4 address with the address saved in Windows App.

If the address changed:

* Update the Windows App connection.
* Reconnect.

---

# Root Cause

The Windows 11 VM received a different IP address from VMware Fusion networking. Windows App was attempting to connect to the previous IP address, causing the RDP connection failure.

---

# Resolution

1. Checked the current Windows VM IP address:

```powershell
ipconfig
```

2. Updated the Windows App PC connection with the new IP address.

3. Reconnected successfully through Remote Desktop.

---

# Verification After Fix

Confirmed:

* Windows App connected successfully.
* Windows desktop loaded remotely.
* Remote Desktop functionality worked correctly.

---

# Prevention

## Configure a Static IP Address

A static IP prevents the Windows VM address from changing.

Steps:

1. Record current network information:

```powershell
ipconfig
```

Record:

* IPv4 address
* Subnet mask
* Default gateway
* DNS server

2. Open:

```
Network Settings
→ Advanced Network Settings
→ More Network Adapter Options
```

3. Right-click Ethernet adapter.

4. Select:

```
Properties
→ Internet Protocol Version 4 (TCP/IPv4)
```

5. Change:

```
Obtain IP Address Automatically
```

to:

```
Use the following IP address
```

6. Enter the previously recorded network information.

---

## Commands Used

Check username:

```powershell
whoami
```

Check IP address:

```powershell
ipconfig
```

Check Remote Desktop service:

```powershell
Get-Service TermService
```

Start Remote Desktop service:

```powershell
Start-Service TermService
```

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/Windows-App-Connection.png)

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/RDP-Error-0x204.png)

> ![Enterprise IT Portfolio](../../01-Images/Remote-Desktop/Successful-RDP-Connection.png)

---

