# Enterprise Homelab

## Overview

This project documents my enterprise Windows homelab built on Proxmox VE. The goal is to simulate a real-world Active Directory environment used in enterprise organizations while keeping it isolated from my production home network.

The lab is designed for learning, testing, automation, security research, and documenting infrastructure deployments.

Current technologies include:

- Proxmox VE
- Windows Server 2025
- Active Directory Domain Services (AD DS)
- DNS
- DHCP
- Windows 11 Enterprise
- UniFi Network
- Internal Virtual Networking

---

## Lab Objectives

- Build an isolated enterprise Active Directory environment
- Configure DNS and DHCP services
- Deploy Windows 11 clients
- Automate workstation provisioning
- Implement Group Policy
- Deploy software using Active Directory
- Expand into Windows infrastructure and security technologies

---

# Architecture

> **Screenshot Placeholder**
>
> Add architecture diagram here.

```
                    Internet
                        │
                 UniFi Gateway
                        │
                  Home Network
                 192.168.1.0/24
                        │
                     vmbr0
                        │
                 Proxmox Server
                        │
      ┌─────────────────┴─────────────────┐
      │                                   │
      │                            Existing Services
      │
      │
 Windows Server 2025
 (Management NIC)
 192.168.1.238
      │
────────────────────────────────────────────────────────

vmbr1 (Internal Enterprise Network)

10.20.1.0/24

      │
      ├───────────────┐
      │               │
      │               │
DC01            WIN11-01
10.20.1.10       DHCP
```

---

## Current Infrastructure

| Server | Role | IP |
|---------|------|-------------|
| DC01 | Active Directory / DNS / DHCP | 10.20.1.10 |
| DC01 Management | Management Interface | 192.168.1.238 |
| WIN11-01 | Windows 11 Client | DHCP |

---

## Technologies

- Active Directory
- DNS
- DHCP
- Windows Server 2025
- Windows 11 Enterprise
- Proxmox VE
- UniFi
- VirtIO Drivers

---

## Current Progress

- [x] Install Proxmox
- [x] Deploy Windows Server 2025
- [x] Configure Active Directory
- [x] Configure DNS
- [x] Configure DHCP
- [x] Create isolated enterprise network
- [x] Join Windows 11 client to domain
- [x] Verify DHCP leases
- [ ] Windows Template
- [ ] Group Policy
- [ ] Software Deployment
- [ ] File Server
- [ ] WSUS
- [ ] Active Directory Certificate Services
- [ ] Windows LAPS

---

## Documentation

| Document | Description |
|-----------|-------------|
| Proxmox.md | Proxmox deployment |
| ActiveDirectory.md | Active Directory deployment |
| DNS.md | DNS configuration |
| DHCP.md | DHCP configuration |
| Troubleshooting.md | Issues encountered |

---

## Future Enhancements

- Group Policy
- Chrome Deployment
- 7-Zip Deployment
- PowerShell Automation
- File Server
- PKI
- Windows LAPS
- WSUS
- Wazuh Integration
- Sysmon
- Security Baselines

---

## Author

Akash Patel

Enterprise Infrastructure Homelab

<img width="1145" height="419" alt="image" src="https://github.com/user-attachments/assets/a2aa71db-f846-4fa3-a9ee-32ba569da678" />
