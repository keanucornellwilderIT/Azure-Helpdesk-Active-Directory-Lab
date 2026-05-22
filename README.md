# ☁️ Azure Active Directory Help Desk Lab

## 📌 Project Overview
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

# 🖥️ Technologies Used

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

# 🏗️ Lab Architecture

| Resource | Purpose |
|---|---|
| dc-1 | Domain Controller + DNS Server |
| client-1 | Domain-Joined Workstation |
| helpdesklab.local | Internal Active Directory Domain |
| hd-vnet | Azure Virtual Network |
| Servers-Subnet | Internal subnet for lab machines |

---

# 📂 Project Sections

- [Azure VM Deployment](#azure-vm-deployment)
- [Active Directory Domain Services Setup](#active-directory-domain-services-setup)
- [DNS Configuration](#dns-configuration)
- [Domain Join Troubleshooting](#domain-join-troubleshooting)
- [User & Group Management](#user--group-management)
- [Authentication vs Authorization](#authentication-vs-authorization)
- [Account Lockout Troubleshooting](#account-lockout-troubleshooting)
- [DNS Failure Troubleshooting](#dns-failure-troubleshooting)
- [File Shares & Permissions](#file-shares--permissions)
- [Group Policy Configuration](#group-policy-configuration)
- [Lessons Learned](#lessons-learned)

---

# ☁️ Azure VM Deployment

## Objective
Deploy enterprise infrastructure inside Microsoft Azure.

## Tasks Completed
- Created Azure Resource Group
- Created Virtual Network & Subnet
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
_Add screenshots here_

---

# 🏢 Active Directory Domain Services Setup

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

# 🌐 DNS Configuration

## Objective
Configure internal DNS communication between client and Domain Controller.

## Tasks Completed
- Configured client-1 to use dc-1 private IP as DNS server
- Verified DNS communication using:

```powershell
nslookup helpdesklab.local
```

```powershell
ping helpdesklab.local
```

## Skills Learned
- DNS troubleshooting
- Internal name resolution
- Active Directory dependencies
- Network diagnostics

## Screenshots
_Add screenshots here_

---

# 🖥️ Domain Join Troubleshooting

## Objective
Join Windows client to Active Directory domain.

## Tasks Completed
- Joined client-1 to:
  
```powershell
helpdesklab.local
```

- Verified domain authentication
- Troubleshot DNS-related domain join issues

## Skills Learned
- Domain joins
- Authentication workflows
- DNS dependency analysis
- Enterprise workstation management

## Screenshots
_Add screenshots here_

---

# 👥 User & Group Management

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

# 🔐 Authentication vs Authorization

## Scenario
Successfully authenticated domain users but received:

```powershell
The connection was denied because the user account is not authorized for remote login.
```

## Troubleshooting
- Verified domain authentication worked
- Identified missing Remote Desktop permissions
- Added security groups to Remote Desktop Users

## Skills Learned
- Authentication vs Authorization
- Remote Desktop permissions
- Enterprise access control

## Screenshots
_Add screenshots here_

---

# 🔒 Account Lockout Troubleshooting

## Scenario
Simulated user account lockout after multiple failed login attempts.

## Tasks Completed
- Configured Account Lockout Policy using Group Policy
- Locked user account intentionally
- Investigated account status
- Unlocked account in Active Directory
- Reset user password

## Commands Used

```powershell
Search-ADAccount -LockedOut
```

```powershell
gpupdate /force
```

## Skills Learned
- Group Policy
- Account lockout troubleshooting
- Password resets
- Help Desk recovery workflows

## Screenshots
_Add screenshots here_

---

# 🌐 DNS Failure Troubleshooting

## Scenario
Simulated enterprise DNS outage by changing client DNS server to Google DNS:

```powershell
8.8.8.8
```

## Symptoms
- Failed domain resolution
- Unable to locate Active Directory domain
- RDP hostname failures
- Internal resource access issues

## Troubleshooting Performed

```powershell
nslookup helpdesklab.local
```

```powershell
ipconfig /all
```

```powershell
ipconfig /flushdns
```

## Root Cause
Client was configured to use public DNS instead of internal Active Directory DNS server.

## Resolution
Reconfigured client DNS to use Domain Controller private IP.

## Skills Learned
- DNS troubleshooting
- Root cause analysis
- Enterprise network diagnostics
- Active Directory dependencies

## Screenshots
_Add screenshots here_

---

# 📁 File Shares & Permissions

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

# ⚙️ Group Policy Configuration

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

# 🧠 Lessons Learned

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

The lab helped reinforce how heavily enterprise environments depend on:
- DNS
- centralized authentication
- identity management
- permissions
- proper troubleshooting workflows

---

# 🚀 Future Improvements

- Add mapped network drives
- Configure printers
- Add DHCP
- Configure Entra ID hybrid integration
- Add Intune integration
- Add PowerShell automation
- Add monitoring & alerts
- Create automated user provisioning scripts

---

# 📎 Author

**Keanu Wilder**

- IT Support & Cloud Enthusiast
- Building hands-on enterprise and cloud infrastructure labs
- Focused on Help Desk, System Administration, and Cloud Engineering
