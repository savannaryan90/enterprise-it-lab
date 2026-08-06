# Active Directory DNS Reverse Lookup Zone Configuration

## Business Scenario

> Enterprise DNS environments commonly use both forward and reverse lookup zones to support reliable name resolution. Forward lookup zones translate hostnames into IP addresses, while reverse lookup zones translate IP addresses back into hostnames. Reverse DNS is frequently used for troubleshooting, logging, security monitoring, and validating infrastructure communication.

---

## Project Objective

> Create and configure an Active Directory-integrated DNS Reverse Lookup Zone for the LAB environment. This allows administrators to identify hostnames from IP addresses and improves DNS visibility for troubleshooting and infrastructure management.

---

## Skills Demonstrated

* DNS Server Administration
* Active Directory Integrated DNS Configuration
* Reverse DNS Lookup Management
* DNS Zone Creation
* Secure Dynamic DNS Updates
* Windows Server Infrastructure Administration
* DNS Troubleshooting and Validation

---

| Component      | Details                        |
| -------------- | ------------------------------ |
| Cloud Provider | Microsoft Azure                |
| Server         | Windows Server 2022 Datacenter |
| Server Name    | LABDC01                        |
| Role           | Domain Controller + DNS Server |
| DNS Zone Type  | Reverse Lookup Zone            |
| Network ID     | 172.16.0.0/24                  |
| Domain         | homelab.local                  |
| Tools          | DNS Manager, nslookup          |

---

## Project Architecture

```text id="2v5f8a"
                    Windows Server 2022
                         LABDC01
                            │
                            │
                    DNS Server Role
                            │
          ┌─────────────────┴─────────────────┐
          │                                   │
          ▼                                   ▼
 Forward Lookup Zone                 Reverse Lookup Zone
 homelab.local                       172.16.0.0/24
          │                                   │
          │                                   │
Hostname → IP                      IP → Hostname
          │                                   │
          ▼                                   ▼
 LABDC01 → 172.16.0.4             172.16.0.4 → LABDC01
```

---

## Implementation Summary

### Phase 1 – Open DNS Manager

Accessed DNS management tools:

```
Server Manager
→ Tools
→ DNS
```

Expanded:

```
LABDC01
└── Reverse Lookup Zones
```

---

### Phase 2 – Create Reverse Lookup Zone

Created a new DNS zone:

1. Right-clicked:

```
Reverse Lookup Zones
```

2. Selected:

```
New Zone
```

3. Configured:

* Zone type:

  * Primary Zone

* Storage:

  * Store the zone in Active Directory

* Replication:

```
All DNS servers in this domain
```

---

### Phase 3 – Configure IPv4 Reverse Lookup

Selected:

```
IPv4 Reverse Lookup Zone
```

Configured network ID:

```
172.16.0
```

Enabled:

```
Allow only secure dynamic updates
```

Completed the wizard.

---

### Phase 4 – Test Reverse DNS Resolution

Tested reverse lookup using:

```powershell id="9j2pk4"
nslookup 172.16.0.4
```

Expected result:

```text id="8z4f6w"
LABDC01.homelab.local
```

This confirms that DNS can successfully map the server IP address back to the Domain Controller hostname.

---

## Validation

* Reverse Lookup Zone appears in DNS Manager.
* Zone is stored as an Active Directory-integrated DNS zone.
* Replication scope is configured correctly.
* Secure dynamic updates are enabled.
* Reverse DNS query successfully resolves LABDC01.
* DNS environment supports both forward and reverse name resolution.

---

## Challenges Encountered

### Reverse Lookup Zone Missing

**Possible causes:**

* Reverse zone was not automatically created during DNS setup.
* Manual DNS configuration was required.
* Incorrect network ID entered during zone creation.

**Resolution:**

Created the reverse lookup zone manually and validated resolution using `nslookup`.

---

## Useful Commands

Test reverse DNS lookup:

```powershell id="7x4c9m"
nslookup 172.16.0.4
```

Test DNS resolution:

```powershell id="3q7mz8"
Resolve-DnsName LABDC01
```

View DNS zones:

```powershell id="5k1n8p"
Get-DnsServerZone
```

View DNS records:

```powershell id="6m2q4v"
Get-DnsServerResourceRecord
```

---

## Best Practices

* Configure reverse lookup zones in enterprise DNS environments.
* Use Active Directory-integrated DNS zones for domain environments.
* Enable secure dynamic updates when using Active Directory DNS.
* Document DNS zones and network ranges.
* Validate both forward and reverse DNS resolution.

---

## Future Improvements

* Add additional DNS records for future servers and services.
* Configure DNS monitoring.
* Add secondary DNS servers for redundancy.
* Document Azure VNet DNS configuration.
* Automate DNS validation with PowerShell.

---

## Related Documentation

* Static IP Configuration
* DNS Integration Verification
* Domain Controller Role Verification
* DNS Troubleshooting Scenario
* Active Directory Domain Services Deployment
