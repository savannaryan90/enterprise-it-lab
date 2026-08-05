# Azure Virtual Networking Configuration

## Business Scenario

> Modern organizations rely on secure and segmented cloud networking to connect virtual machines and control access to enterprise resources. Microsoft Azure networking provides the foundation for communication between virtual machines, cloud services, and remote administrators. Understanding how Virtual Networks, Subnets, Network Interfaces, Network Security Groups, and Public IP addresses work together is essential for deploying secure and manageable cloud infrastructure.

---

## Project Objective

> Configure and understand the core Azure networking components required to support a Windows Server virtual machine. This project establishes secure network connectivity, enables remote administration, and builds foundational knowledge of Azure networking that will support future services such as Active Directory, DNS, and hybrid cloud environments.

---

## Skills Demonstrated

* Microsoft Azure Networking
* Virtual Network (VNet) Configuration
* Subnet Design
* Network Interface (NIC) Management
* Network Security Group (NSG) Configuration
* Public IP Address Configuration
* Remote Desktop Connectivity
* Network Security Best Practices
* Basic Cloud Infrastructure Administration
* Azure Resource Management

---

## Screenshots

> ![Enterprise IT Portfolio](../../01-Images/Azure/Virtual-Network.png)

> ![Enterprise IT Portfolio](../../01-Images/Azure/Network-Security-Group.png)

> ![Enterprise IT Portfolio](../../01-Images/Azure/Public-IP.png)

---

| Component         | Details                        |
| ----------------- | ------------------------------ |
| Cloud Provider    | Microsoft Azure                |
| Virtual Machine   | Windows Server 2022 Datacenter |
| Virtual Network   | WindowsLab-VNet                |
| Subnet            | 10.0.1.0/24                    |
| Network Interface | Azure Virtual NIC              |
| Security          | Network Security Group (NSG)   |
| Remote Access     | RDP (TCP 3389)                 |

## Project Architecture

```text
                           Internet
                               │
                               │
                        Public IP Address
                               │
                               │
                    Network Security Group
                   (Allows RDP - TCP 3389)
                               │
                               │
                     Network Interface (NIC)
                               │
                               │
                Virtual Network (WindowsLab-VNet)
                    Address Space: 10.0.0.0/16
                               │
                               │
                      Subnet: 10.0.1.0/24
                               │
                               │
              Windows Server 2022 VM (LABDC01)
```

---

## Implementation Summary

### Phase 1 – Virtual Network Configuration

* Reviewed Azure Virtual Network (VNet) architecture.
* Configured the virtual network to provide private communication for Azure resources.
* Verified the VNet was associated with the virtual machine.

### Phase 2 – Network Resource Configuration

* Configured the subnet used by the virtual machine.
* Verified the Azure Network Interface (NIC) was attached to the server.
* Confirmed the virtual machine received a private IP address within the assigned subnet.

### Phase 3 – Secure Remote Connectivity

* Configured a Public IP address for remote administration.
* Reviewed and verified Network Security Group (NSG) rules.
* Allowed Remote Desktop (TCP 3389) for administrative access.
* Verified secure Remote Desktop connectivity using Windows App.

---

## Validation

* Virtual machine connected to the Azure Virtual Network.
* Network Interface successfully associated with the virtual machine.
* Private IP address assigned within the configured subnet.
* Public IP address enabled for remote administration.
* Network Security Group rules allowed expected traffic.
* Remote Desktop connectivity verified successfully.

---

## Challenges Encountered

* Understanding how Azure networking components interact to provide connectivity.
* Differentiating the responsibilities of Virtual Networks, Subnets, Network Interfaces, and Network Security Groups.
* Balancing accessibility for remote administration with security best practices.
* Learning Azure's layered networking model compared to traditional on-premises networking.

---

## Future Improvements

* Replace unrestricted RDP access with more secure access methods such as Azure Bastion.
* Implement Network Security Group rules that restrict administrative access by IP address.
* Add additional subnets to simulate enterprise network segmentation.
* Explore Azure Virtual Network peering.
* Integrate hybrid networking between Azure and on-premises lab environments.

---

## Related Documentation

* Microsoft Azure Windows Server Deployment
* Azure Resource Group Configuration
* Remote Desktop (Windows App) Configuration
* Active Directory Domain Services Deployment (Future)
