# Azure Active Directory Help Desk Lab

## Project Overview

This project simulates a real-world enterprise Active Directory environment hosted in Microsoft Azure. The lab was built to gain hands-on experience with common Help Desk, IT Support, and System Administration tasks including domain setup, DNS troubleshooting, user management, Group Policy, authentication, and enterprise resource access.

The environment includes:

- Windows Server Domain Controller
- Active Directory Domain Services
- DNS configuration
- Windows client domain join
- Organizational Units (OUs)
- User and Group management
- Account lockout troubleshooting
- Group Policy configuration
- File share permissions
- DNS failure troubleshooting
- RDP and remote administration

---

## Technologies Used

- Microsoft Azure
- Windows Server 2022
- Windows 10/11
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy
- Remote Desktop Protocol (RDP)
- PowerShell
- SMB File Sharing

---

## Lab Architecture

| Resource | Purpose |
|---|---|
| dc-1 | Domain Controller + DNS Server |
| client-1 | Domain-Joined Workstation |
| helpdesklab.local | Internal Active Directory Domain |
| hd-vnet | Azure Virtual Network |
| Servers-Subnet | Internal subnet for lab machines |

---

## Project Sections

- [Azure VM Deployment](#azure-vm-deployment)
- [Active Directory Domain Services Setup](#active-directory-domain-services-setup)
- [DNS Configuration and Domain Join Troubleshooting](#dns-configuration-and-domain-join-troubleshooting)
- [User and Group Management](#user-and-group-management)
- [Help Desk Scenarios](#help-desk-scenarios)
- [File Shares and Permissions](#file-shares-and-permissions)
- [Group Policy Configuration](#group-policy-configuration)

---

# Azure VM Deployment

## Objective

Deploy enterprise infrastructure inside Microsoft Azure.

## Tasks Completed

- Created Azure Resource Group
- Created Virtual Network and Subnet
- Deployed Windows Server 2022 VM
- Deployed Windows 10/11 Client VM
- Configured RDP access
- Verified VM networking

## Skills Learned

- Azure VM deployment
- Virtual networking
- Cloud infrastructure basics
- Remote administration

## Screenshots

### Azure Resource Group

Created a dedicated Azure Resource Group to organize all infrastructure resources for the Active Directory lab environment.

<img width="1687" height="544" alt="image" src="https://github.com/user-attachments/assets/840190e1-1ddc-471c-82af-fd17111acb3c" />

---

### Virtual Network and Subnet Configuration

Configured an internal Azure Virtual Network (`hd-vnet`) to allow communication between the Domain Controller and client workstation.

<img width="1683" height="555" alt="image" src="https://github.com/user-attachments/assets/e0099d95-9a01-4e1e-8170-242e37377b22" />

---

### Azure Virtual Machines

Deployed two virtual machines inside Microsoft Azure:

- `dc-1` — Windows Server 2022 Domain Controller
- `client-1` — Windows 10/11 Domain-Joined Client

Both systems were configured for remote administration and internal network communication.

<img width="1687" height="630" alt="image" src="https://github.com/user-attachments/assets/61894701-b61a-43db-b30c-dfa78a98ee53" />

---

### Remote Desktop Connectivity

Verified successful Remote Desktop Protocol (RDP) connectivity into the Azure virtual machines for remote administration and management.

<img width="400" height="472" alt="image" src="https://github.com/user-attachments/assets/a39bd0cd-73de-42fe-bbef-ac62bd395dfd" />

---

### Remote Administration Session

Successfully connected to the environment through RDP and verified workstation accessibility inside the enterprise lab environment.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/3a227e5f-cbf3-4473-b7fb-b0d2b44c38d8" />

---

### Internal Network Communication Verification

Verified internal network and DNS communication between systems using:

```powershell
nslookup helpdesklab.local
ping helpdesklab.local
ipconfig
```

This confirmed successful DNS resolution and communication between domain resources.

<img width="1915" height="1075" alt="image" src="https://github.com/user-attachments/assets/d775d484-eadb-462b-84a3-fc5190d44788" />

---

# Active Directory Domain Services Setup

## Objective

Install and configure Active Directory Domain Services.

## Tasks Completed

- Installed AD DS role
- Installed DNS role
- Promoted server to Domain Controller
- Created new forest:

```powershell
helpdesklab.local
```

- Verified Active Directory functionality
- Verified DNS integration

## Skills Learned

- Active Directory deployment
- Domain Controller setup
- DNS integration
- Enterprise identity infrastructure

## Screenshots

_Add screenshots here_

---

# DNS Configuration and Domain Join Troubleshooting

## Objective

Configure internal DNS communication and join the client workstation to the domain.

## Tasks Completed

- Configured client-1 to use dc-1 private IP as DNS server
- Verified DNS communication using:

```powershell
nslookup helpdesklab.local
```

```powershell
ping helpdesklab.local
```

- Joined client-1 to:

```powershell
helpdesklab.local
```

- Verified domain authentication
- Troubleshot DNS-related domain join issues

## Troubleshooting Scenario

An intentional DNS failure was created by configuring the client machine to use Google DNS:

```powershell
8.8.8.8
```

This caused:
- Domain resolution failures
- Internal resource access issues
- Active Directory communication problems

## Troubleshooting Performed

```powershell
ipconfig /all
```

```powershell
nslookup helpdesklab.local
```

```powershell
ipconfig /flushdns
```

## Resolution

Reconfigured client DNS settings to use the Domain Controller private IP address.

## Skills Learned

- DNS troubleshooting
- Domain joins
- Active Directory dependency analysis
- Network diagnostics
- Root cause analysis

## Screenshots

_Add screenshots here_

---

# User and Group Management

## Objective

Simulate enterprise identity management.

## Organizational Units Created

- HR
- IT
- Sales
- Workstations

## Users Created

| Name | Username |
|---|---|
| Sarah Johnson | sjohnson |
| Mike Chen | mchen |
| Emily Davis | edavis |

## Security Groups Created

- HR-Users
- IT-Admins
- Sales-Users

## Tasks Completed

- Added users to security groups
- Verified group memberships
- Practiced Role-Based Access Control (RBAC)

## Skills Learned

- User provisioning
- Group management
- Organizational Units
- RBAC concepts

## Screenshots

_Add screenshots here_

---

# Help Desk Scenarios

## Authentication vs Authorization

A domain user successfully authenticated but received the following Remote Desktop error:

```powershell
The connection was denied because the user account is not authorized for remote login.
```

### Resolution

- Verified domain authentication functionality
- Identified missing Remote Desktop permissions
- Added appropriate groups to Remote Desktop Users

---

## Account Lockout Troubleshooting

A user account was intentionally locked out after multiple failed login attempts.

### Troubleshooting Performed

```powershell
Search-ADAccount -LockedOut
```

```powershell
gpupdate /force
```

### Resolution

- Unlocked user account
- Reset user password
- Verified restored access

---

## Password Reset Scenario

Simulated a common enterprise Help Desk password reset request.

### Tasks Performed

- Reset user password in Active Directory
- Verified successful login
- Reviewed account status

---

## DNS Failure Scenario

Simulated enterprise DNS outage by configuring the client to use public DNS instead of internal Active Directory DNS.

### Symptoms

- Failed domain lookups
- Unable to resolve internal resources
- Domain communication failures

### Root Cause

Incorrect DNS server configuration.

### Resolution

Reconfigured client DNS to use internal Active Directory DNS server.

## Skills Learned

- Authentication troubleshooting
- Authorization troubleshooting
- Password resets
- DNS troubleshooting
- Help Desk workflows
- Root cause analysis

## Screenshots

_Add screenshots here_

---

# File Shares and Permissions

## Objective

Configure enterprise shared folders and permissions.

## Tasks Completed

- Created shared folders
- Configured SMB sharing
- Configured NTFS permissions
- Assigned group-based access
- Tested access with different users

## Skills Learned

- SMB shares
- NTFS permissions
- Group-based access control
- File share troubleshooting

## Screenshots

_Add screenshots here_

---

# Group Policy Configuration

## Tasks Completed

- Configured Account Lockout Policy
- Forced Group Policy updates
- Tested policy application

## Commands Used

```powershell
gpupdate /force
```

## Skills Learned

- Group Policy Management
- Enterprise security policy deployment
- Domain policy troubleshooting

## Screenshots

_Add screenshots here_

---

# Lessons Learned

This project provided hands-on experience with:

- Active Directory infrastructure
- DNS troubleshooting
- Domain authentication
- Group Policy
- Azure cloud infrastructure
- Enterprise networking
- User administration
- Access control
- Help Desk troubleshooting methodology

The lab reinforced how heavily enterprise environments depend on:

- DNS
- Centralized authentication
- Identity management
- Permissions
- Proper troubleshooting workflows

---

# Author

**Keanu Wilder**

