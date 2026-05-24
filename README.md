# 🖥️ Azure Active Directory Help Desk Lab

---

## 📌 Overview
This project simulates real-world Active Directory administration and help desk troubleshooting tasks within a Windows Server and Azure environment. The lab focuses on configuring domain services, troubleshooting domain join issues, managing users and groups, resolving account lockouts, and applying Group Policy settings commonly handled by IT support specialists and system administrators.

The goal of this project is to build hands-on experience with identity management, authentication troubleshooting, Windows administration, and enterprise support workflows.

---

## 🎯 Objectives
- Configure Active Directory Domain Services
- Troubleshoot domain join issues
- Manage users and security groups
- Resolve account lockout issues
- Configure Group Policy settings
- Practice real-world help desk workflows

---

## 🧰 Technologies Used
- Microsoft Azure
- Windows Server 2022
- Windows 10/11
- Active Directory
- DNS
- PowerShell

---

## 🏗️ Environment Setup
- Domain Controller VM
- Client VM
- Virtual Network
- DNS Configuration
- Domain Connectivity

---

## ⚙️ Project Configuration Steps
### Step 1 - Create Azure Resources
Configured Azure virtual machines and networking.

📸 Screenshot here

### Step 2 - Configure Domain Controller
Configured DNS settings and prepared the server for Active Directory installation.

📸 Screenshot here

### Step 3 - Install Active Directory Domain Services
Installed AD DS and promoted the server to a Domain Controller.

📸 Screenshot here

### Step 4 - Join Client Machine to Domain
Configured client DNS settings and joined the system to the domain.

📸 Screenshot here

---

## 🛠️ Help Desk Scenarios

### Scenario 1 - Domain Join Troubleshooting

#### Problem
Client machine was unable to join the Active Directory domain.

#### Troubleshooting
- Verified DNS configuration
- Tested network connectivity
- Reviewed IP settings using ipconfig /all
- Confirmed Domain Controller communication

#### Root Cause
Incorrect DNS configuration prevented domain resolution.

#### Resolution
Updated DNS settings to use the Domain Controller IP address and successfully joined the domain.

#### Skills Learned
- DNS troubleshooting
- Domain join troubleshooting
- Network diagnostics
- Windows networking

📸 Screenshot here

---

### Scenario 2 - User & Group Management

#### Problem
New employees required access to company resources based on department roles.

#### Troubleshooting
- Created Active Directory users
- Configured security groups
- Assigned users to department groups
- Verified account permissions

#### Root Cause
Users and security groups had not been configured for role-based access management.

#### Resolution
Configured Active Directory users and groups to align with organizational access requirements.

#### Skills Learned
- User administration
- Security group management
- Access control
- Identity management

📸 Screenshot here

---

### Scenario 3 - Account Lockout Troubleshooting

#### Problem
User was unable to log in after multiple failed password attempts.

#### Troubleshooting
- Reviewed Active Directory Users and Computers
- Verified account lockout status
- Checked password policy configuration
- Tested user authentication

#### Root Cause
Account was locked due to repeated failed login attempts.

#### Resolution
Unlocked the user account and verified successful login access.

#### Skills Learned
- Account lockout troubleshooting
- Active Directory administration
- Authentication troubleshooting
- User support

📸 Screenshot here

---

### Scenario 4 - Group Policy Configuration

#### Problem
The organization required standardized security and desktop settings across domain computers.

#### Troubleshooting
- Opened Group Policy Management Console
- Created and linked Group Policy Objects
- Applied policy configurations
- Verified policy updates on client systems

#### Root Cause
Domain systems lacked centralized configuration management.

#### Resolution
Configured and applied Group Policy settings successfully across domain devices.

#### Skills Learned
- Group Policy Management
- Windows administration
- Enterprise configuration management
- Security policy configuration

📸 Screenshot here

---

## 🧠 Key Help Desk Skills Demonstrated
- Active Directory Administration
- DNS Troubleshooting
- Group Policy Management
- User & Group Administration
- Authentication Troubleshooting
- Windows Server Administration
- Root Cause Analysis
- Technical Documentation

---

## 📖 Lessons Learned
This project improved my understanding of Active Directory administration and enterprise help desk workflows within Azure and Windows Server environments. I gained hands-on experience configuring domain services, troubleshooting authentication issues, managing users and groups, resolving account lockouts, and applying Group Policy configurations commonly used in enterprise IT operations.

The lab also strengthened my troubleshooting methodology, documentation practices, and system administration skills.

---

## 🚀 Future Improvements
- Configure Multi-Factor Authentication (MFA)
- Implement Azure AD Connect
- Add PowerShell automation scripts
- Configure advanced Group Policy settings
