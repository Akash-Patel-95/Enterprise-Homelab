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
---
---

***JUNE 29, 2026***

# Group Policy Software Installation Issue

## Issue

Software assigned through **Group Policy Software Installation** did not install on domain-joined Windows clients after reboot.

---

## Symptoms

- Group Policy applied successfully.
- Software package appeared under **Software Installation**.
- `gpresult /r /scope computer` confirmed the GPO was applied.
- Software never appeared in **Installed Apps** after restart.

---

## Root Cause

The MSI package was added using a **local file system path** instead of a network share.

**Incorrect:**

```text
C:\Shares\Software\7-Zip\7z2602-x64.msi
```

During computer startup, client computers cannot access the server's local **C:** drive. As a result, the Group Policy Software Installation client-side extension could not locate the MSI package.

---

## Resolution

Removed the software package from the Group Policy Object and recreated it using a **UNC network path**.

**Correct:**

```text
\\25-SRV-OH-01\Software\7-Zip\7z2602-x64.msi
```

After updating Group Policy and restarting the workstation, the software installed successfully during computer startup.

---

## Lesson Learned

- Always use **UNC network paths (`\\Server\Share\...`)** when deploying software through Group Policy.
- Never use local file system paths such as `C:\...` for software deployment.
- Verify Group Policy application using:

```powershell
gpresult /r /scope computer
```

- Computer Configuration software installations are processed during **system startup**, not after a user logs on.

---

## Validation

The issue was resolved after correcting the package source.

- ✅ Group Policy applied successfully
- ✅ Workstation processed the Software Installation policy during startup
- ✅ 7-Zip installed automatically
- ✅ Application appeared under **Installed Apps**
- ✅ No manual installation was required

---
