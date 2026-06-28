# DHCP

## Scope

10.20.1.0/24

## Address Pool

10.20.1.100

↓

10.20.1.200

## DNS

10.20.1.10

## Domain

homelab.local

## Validation

Verified

- DHCP Lease
- DNS Registration
- Client Communication

Scope Options > **Note**
>
> This DHCP scope is configured for an isolated internal lab network (`10.20.1.0/24`). Since the lab is connected to an internal Proxmox bridge (`vmbr1`) with no upstream router, **DHCP Option 003 (Router/Default Gateway)** is intentionally left unconfigured.
>
> As a result, lab clients can communicate with the Domain Controller, DNS, and other internal resources, but they do not have Internet access. This design keeps the enterprise lab isolated from the production/home network while allowing Active Directory, DNS, and DHCP services to function normally.
<img width="1139" height="350" alt="image" src="https://github.com/user-attachments/assets/bc6518ef-e52b-417a-b942-c277b2e6ae55" />


DHCP Scope
<img width="1134" height="350" alt="image" src="https://github.com/user-attachments/assets/52801604-d8c3-45c0-97fd-fba960a0c54d" />


Address Lease
<img width="1136" height="351" alt="image" src="https://github.com/user-attachments/assets/8a76948c-c08c-4426-824a-2d5d4620ff25" />
