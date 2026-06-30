![Platform](https://img.shields.io/badge/Platform-Proxmox-blue)
![Windows Server](https://img.shields.io/badge/Windows_Server-2025-0078D6)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow)
![License](https://img.shields.io/badge/License-MIT-green)

## Latest Updates
### June 29, 2026

- ✅ Windows 11 Enterprise Template (Sysprep)
- ✅ Proxmox VM Template & Cloning
- ✅ Organizational Units (OU) Structure
- ✅ Active Directory Security Groups
- ✅ SMB Software Repository
- ✅ Share & NTFS Permissions
- ✅ Network Drive Mapping
- ✅ Group Policy Object (GPO) Configuration
- ✅ 7-Zip Software Deployment via Group Policy
- ✅ Group Policy Software Deployment Troubleshooting

### Upcoming

- ⏳ Google Chrome Deployment
- ⏳ VS Code Deployment
- ⏳ Wazuh Agent Deployment
- ⏳ PowerShell Automation


# Enterprise Homelab

An enterprise-style Windows infrastructure lab built on **Proxmox VE** to simulate a real-world Active Directory environment. This project serves as a hands-on platform for learning enterprise system administration, infrastructure automation, Windows networking, and security best practices.

> **Note**
>
> This environment is hosted on my personal home lab for educational and testing purposes. The Active Directory environment is isolated from my production home network using an internal Proxmox virtual network while maintaining a separate management interface for administration.

---

# Project Roadmap

## Phase 1 – Core Infrastructure

* [x] Install Proxmox VE
* [x] Deploy Windows Server 2025
* [x] Configure Active Directory Domain Services (AD DS)
* [x] Configure DNS
* [x] Configure DHCP
* [x] Create an isolated enterprise network
* [x] Join Windows 11 client to the domain
* [x] Verify DHCP lease assignment

## Phase 2 – Endpoint Management

- [x] Create Windows 11 Enterprise Template (Sysprep)
- [x] Convert VM into a Proxmox Template
- [x] Deploy Windows clients from template
- [x] Configure Organizational Units (OU)
- [x] Configure Security Groups
- [x] Configure SMB File Shares
- [x] Configure Share & NTFS Permissions
- [x] Map Network Drives
- [x] Configure Group Policy Objects (GPO)
- [x] Deploy 7-Zip using Group Policy Software Installation (MSI)
- [ ] Deploy additional software (Chrome, VS Code, VLC)
- [ ] PowerShell deployment automation

## Phase 3 – Enterprise Services

* [ ] Windows Server Update Services (WSUS)
* [ ] Windows LAPS
* [ ] Active Directory Certificate Services (AD CS)
* [ ] PowerShell automation
* [ ] File Server
* [ ] DFS Namespace

## Phase 4 – Security & Monitoring

- [x] Deploy Wazuh SIEM
- [x] Install Wazuh Agent on Windows Server 2025
- [ ] Deploy Wazuh Agents to Windows Clients
- [ ] Sysmon
- [ ] Windows Event Forwarding (WEF)
- [ ] Microsoft Defender
- [ ] Security Baselines
- [ ] Centralized Event Monitoring

---

# Overview

This repository documents the design, deployment, and maintenance of my enterprise Windows homelab built on Proxmox VE.

The primary objective is to recreate a small enterprise Active Directory environment while documenting each deployment step, configuration, and troubleshooting process. Rather than simply installing services, this repository focuses on understanding how Windows infrastructure components interact in a production-like environment.

Current technologies include:

* Proxmox VE 9.2.2
* Windows Server 2025
* Active Directory Domain Services (AD DS)
* DNS
* DHCP
* Windows 11 Enterprise
* UniFi Networking
* Internal Virtual Networking (Proxmox Linux Bridge)
* Wazuh SIEM with a Windows Server 2025 agent for monitoring
---

# Lab Objectives

* Build an isolated enterprise Active Directory environment
* Configure enterprise DNS and DHCP services
* Deploy and domain join Windows 11 clients
* Automate workstation provisioning
* Implement Group Policy management
* Deploy software using Group Policy
* Document deployment procedures and troubleshooting
* Expand into enterprise Windows infrastructure and security technologies

---

# Architecture

> **Architecture Diagram**

<img width="1197" height="1314" alt="Enterprise Homelab Architecture" src="https://github.com/user-attachments/assets/63ad6194-fe4c-4dae-ae61-b7b47fbb59aa" />

---

# Current Environment

| Hostname     | Role                            | IP Address    | Network                     |
| ------------ | ------------------------------- | ------------- | --------------------------- |
| 25-SRV-OH-01 | Domain Controller, DNS, DHCP    | 10.20.1.10    | Internal Enterprise Network |
| 25-SRV-OH-01 | Management Interface            | 192.168.1.238 | Home Network                |
| WIN11-01     | Domain-Joined Windows 11 Client | DHCP          | Internal Enterprise Network |
| WIN11-02     | Domain-Joined Windows 11 Client | DHCP          | Internal Enterprise Network |
| WIN11-03     | Domain-Joined Windows 11 Client | DHCP          | Internal Enterprise Network |

---

# Technologies

## Virtualization

- Proxmox VE
- VirtIO Drivers

### Windows Administration

- Group Policy Management
- Group Policy Software Installation
- SMB Software Repository
- Windows Installer (MSI) Deployment

## Microsoft Technologies

- Windows Server 2025
- Active Directory Domain Services
- DNS
- DHCP
- Organizational Units (OU)
- Security Groups
- SMB File Shares
- Windows 11 Enterprise

## Networking

- UniFi Network
- Enterprise Virtual Network
- SMB File Sharing

## Security

- Wazuh SIEM
---

# Repository Structure

```text
Enterprise-Homelab
│
├── README.md
|
├── docs
│   ├── proxmox_network config.md
│   ├── ActiveDirectory.md
│   ├── DNS.md
│   ├── DHCP.md
│   ├── Windows11-Template.md
│   ├── OrganizationalUnits.md
│   ├── FileShares.md
│   ├── GroupPolicy.md
│   └── Troubleshooting.md
│
└── images
```

---

# Documentation


🔗 **[Proxmox Network Config](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/proxmox_network%20config.md)** |
🔗 **[ActiveDirectory](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/ActiveDirectory.md)** |
🔗 **[DHCP](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/DHCP.md)** |
🔗 **[Windows11 Template](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/Troubleshootin.md)** - Coming soon |
🔗 **[Organizational Units](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/Troubleshootin.md)** - Coming soon |
🔗 **[File Shares](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/Troubleshootin.md)** - Coming soon |
🔗 **[Group Policy](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/Troubleshootin.md)** - Coming soon |
🔗 **[Troubleshooting](https://github.com/Akash-Patel-95/Enterprise-Homelab/blob/main/docs/Troubleshootin.md)** |


## Author

**Akash Patel**

Enterprise Infrastructure • Windows Administration • Active Directory • Proxmox

