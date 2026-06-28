# Troubleshooting

## Issue 1

Windows client received APIPA address

169.254.x.x

### Root Cause

DHCP request not reaching the server.

### Resolution

Verified Proxmox networking using static IP addresses before troubleshooting DHCP.

---

## Issue 2

Unable to contact DHCP Server

### Root Cause

Client network configuration and previous static lease configuration required verification.

### Resolution

Verified:

- vmbr1 connectivity
- DHCP Scope
- DHCP Bindings
- Static communication
- DNS
- Interface configuration

---

## Issue 3

Lost RDP access

### Cause

Management adapter removed during testing.

### Resolution

Re-enabled management NIC on vmbr0 while keeping internal enterprise network on vmbr1.

---

## Lessons Learned

Always verify Layer 2 communication using static IP addresses before troubleshooting DHCP.

Verify DHCP bindings before assuming server configuration issues.

Maintain a dedicated management interface for infrastructure servers.
