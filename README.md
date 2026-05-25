# 🖥️ Azure Active Directory Help Desk Lab

## 📌 Overview
This project simulates real-world Active Directory administration and help desk troubleshooting tasks within a Windows Server and Azure environment. The lab focuses on configuring domain services, troubleshooting domain join issues, managing users and groups, resolving account lockouts, and applying Group Policy settings commonly handled by IT support specialists and system administrators.

The goal of this project is to build hands-on experience with identity management, authentication troubleshooting, Windows administration, and enterprise support workflows.

## 🎯 Objectives
- Configure Active Directory Domain Services
- Troubleshoot domain join issues
- Manage users and security groups
- Resolve account lockout issues
- Configure Group Policy settings
- Practice real-world help desk workflows

## 🧰 Technologies Used
- Microsoft Azure
- Windows Server 2022
- Windows 10/11
- Active Directory
- DNS
- PowerShell

## 🏗️ Environment Setup
- Domain Controller VM
- Client VM
- Virtual Network
- DNS Configuration
- Domain Connectivity

## ⚙️ Project Configuration Steps
### Step 1 - Create Azure Resources
Configured Azure virtual machines and networking.
<img width="1687" height="544" alt="Screenshot 2026-05-23 015512" src="https://github.com/user-attachments/assets/6c2309b0-30a4-4b49-99b8-483bb55dca94" />
<img width="769" height="375" alt="image" src="https://github.com/user-attachments/assets/668e766a-f1d1-452b-a2fe-a5a19334d305" />
### Step 2 - Configure Domain Controller
Configured DNS settings and prepared the server for Active Directory installation.
<img width="772" height="648" alt="image" src="https://github.com/user-attachments/assets/c2ea64fb-4cdc-4bb7-81c2-334746ff9835" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ff979277-5f7d-4b18-b08a-d124a124dc06" />
### Step 3 - Install Active Directory Domain Services
Installed AD DS and promoted the server to a Domain Controller.

<img width="340" height="244" alt="Screenshot 2026-05-23 021650" src="https://github.com/user-attachments/assets/5e1e7d41-4052-4f79-b5b0-9ae4c9838773" />
<img width="745" height="327" alt="image" src="https://github.com/user-attachments/assets/a5b86c62-9928-4fe9-b809-b95788ee90cc" />

### Step 4 - Join Client Machine to Domain
Configured client DNS settings and joined the system to the domain.
<img width="896" height="696" alt="image" src="https://github.com/user-attachments/assets/80bab558-d6fc-42a5-9d30-d681fed0a78e" />

---

## 🛠️ Help Desk Scenarios

### Scenario 1 - Domain Join Troubleshooting

#### Problem
`edavis` was unable to access the `helpdesklab.local` domain on `client-1` because the client machine could not successfully communicate with the Domain Controller.

#### Troubleshooting
- Verified DNS configuration on `client-1`
- Tested network connectivity between `client-1` and `dc-1`
- Reviewed IP settings using `ipconfig /all`
- Confirmed Domain Controller communication using `ping dc-1`
- Reviewed domain join configuration settings

#### Root Cause
Incorrect DNS configuration prevented the client machine from resolving and communicating with the `helpdesklab.local` domain controller.
### Client DNS Configuration

<img width="361" height="463" alt="image" src="https://github.com/user-attachments/assets/6dac0cb3-504e-4e23-90bb-4b11949d3ef9" />
<img width="802" height="636" alt="image" src="https://github.com/user-attachments/assets/8895aaea-d09b-4518-90ad-ae71b7f27f91" />
<img width="567" height="630" alt="image" src="https://github.com/user-attachments/assets/550fadd5-d028-401b-b852-577e464c40f3" />

### Command Prompt DNS Check
<img width="1085" height="910" alt="image" src="https://github.com/user-attachments/assets/90685dce-743f-4852-b3de-b3f9ef3b730f" />
<img width="950" height="580" alt="image" src="https://github.com/user-attachments/assets/1a912beb-94d4-415a-8a88-084d47489eee" />

### Domain Join Success
<img width="410" height="465" alt="image" src="https://github.com/user-attachments/assets/f2386d3a-d9f8-4c6e-8fc9-226cdcaba4dd" />

#### Resolution
Updated DNS settings to use the Domain Controller IP address and successfully joined the domain.

#### Skills Learned
- DNS troubleshooting
- Domain join troubleshooting
- Network diagnostics
- Windows networking
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

### Active Directory Groups & Users:
<img width="585" height="326" alt="image" src="https://github.com/user-attachments/assets/b2167836-7a09-4282-9d3c-f513903aaaf4" />
<img width="559" height="330" alt="image" src="https://github.com/user-attachments/assets/19dd7993-e7e6-41ed-9d5d-af8df40543e9" />
<img width="603" height="321" alt="image" src="https://github.com/user-attachments/assets/58e72e6a-55ae-44d8-b7f5-4242351db097" />

### User Group Membership
Shows users assigned to appropriate department groups.

<img width="400" height="451" alt="image" src="https://github.com/user-attachments/assets/226f794a-a25b-4f93-a14a-791dbc958b81" />
<img width="396" height="451" alt="image" src="https://github.com/user-attachments/assets/c2850378-91cb-4793-97f6-a5d4e8d1594a" />
<img width="398" height="452" alt="image" src="https://github.com/user-attachments/assets/ba02931e-7270-4aa6-bbc1-b8597e76b0ab" />

#### Resolution
Configured Active Directory users and groups to align with organizational access requirements.

#### Skills Learned
- User administration
- Security group management
- Access control
- Identity management
---

### Scenario 3 - Account Lockout Troubleshooting

#### Problem
`sjohnson` was unable to log into the `helpdesklab.local` domain after multiple failed password attempts on `client-1`.

#### Troubleshooting
- Reviewed the user account within Active Directory Users and Computers
- Verified account lockout status
- Checked password policy configuration
- Reviewed authentication and login attempts
- Tested user authentication after remediation

#### Root Cause
The `sjohnson` account became locked due to repeated failed login attempts that triggered the domain account lockout policy.

### Locked User Account
Shows the user account locked within Active Directory Users and Computers.
<img width="545" height="506" alt="image" src="https://github.com/user-attachments/assets/80e0e66a-dbf8-4ba6-89ff-61d02e06ae6d" />

### Unlocking with AD:

<img width="1114" height="841" alt="image" src="https://github.com/user-attachments/assets/e6ba07d3-db84-4afc-b0f6-613610ece160" />

### Unlocking with Powershell:

<img width="848" height="438" alt="image" src="https://github.com/user-attachments/assets/34176cd8-ae3c-458d-bb47-72fa6bc84216" />

#### Resolution
Unlocked the user account and verified successful login access.

#### Skills Learned
- Account lockout troubleshooting
- Active Directory administration
- Authentication troubleshooting
- User support
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

### New GPO Created
Creation of the `Company Password Policy` Group Policy Object.
<img width="829" height="518" alt="image" src="https://github.com/user-attachments/assets/fc8c582f-5c37-4c1f-acad-ab4285446798" />
### Password Policy Configured
Configured minimum password length policy within the Group Policy Management Editor.
<img width="1193" height="774" alt="image" src="https://github.com/user-attachments/assets/0be34577-7da9-4c88-a0f1-91fe1c718770" />
### Linked GPO
Shows the `Company Password Policy` linked to the `helpdesklab.local` domain.

<img width="444" height="409" alt="image" src="https://github.com/user-attachments/assets/5b2d8831-376a-4b2c-91a9-cfc09dd190ef" />
<img width="360" height="199" alt="image" src="https://github.com/user-attachments/assets/2ebd481a-746f-4e24-9179-92e804182ea8" />

### GPUpdate Success
Verified successful Group Policy deployment on `client-1` using `gpupdate /force`.
<img width="725" height="274" alt="image" src="https://github.com/user-attachments/assets/361f8478-06e6-4e7f-ad84-6d5398384e7b" />

#### Resolution
Configured and applied Group Policy settings successfully across domain devices.

#### Skills Learned
- Group Policy Management
- Windows administration
- Enterprise configuration management
- Security policy configuration
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

## 📖 Lessons Learned
This project improved my understanding of Active Directory administration and enterprise help desk workflows within Azure and Windows Server environments. I gained hands-on experience configuring domain services, troubleshooting authentication issues, managing users and groups, resolving account lockouts, and applying Group Policy configurations commonly used in enterprise IT operations.

The lab also strengthened my troubleshooting methodology, documentation practices, and system administration skills.

## 🚀 Future Improvements
- Configure Multi-Factor Authentication (MFA)
- Implement Azure AD Connect
- Add PowerShell automation scripts
- Configure advanced Group Policy settings
