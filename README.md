
# Active Directory Simulation - Discernx Consult

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called **Discernx Consult**. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

**DISCERNX CONSULT** is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (IT Department)
- 1 x Windows 8 Client PC (HR Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.1)
   ↓
Switch
 ┌──────┬─────────────┬
 │      │             │          
Server  PC1 (Win 8)   PC2 (Win 8) 

```

| Device        | IP Address      | Role                        |
|---------------|----------------|-----------------------------|
| Windows Server| 10.0.2.15  | AD Domain Controller (DC)   |
| Windows 8 PC  | DHCP    | Client (IT)           |
| Windows XP PC | DHCP    | Client (Human Resources)              |

---

## Domain Configuration

- **Domain Name**: `discernxtech.org`
- **Server Name**: `DISCERNXTECH`
- **Static IP**: `10.0.2.15`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
DiscernxTech.org
├── OU: IT Department
│   └── Users: Rapheal.IT
    

├── OU: HR Department
│   └── Users: Derrick.HR
```

---


## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `Disable Shutdown Ability`
- **Linked to**: OU: IT Department
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `Task Menu and Task Bar System` > `Remove and prevent access to shutdown, restart,sleep and Hibernate commands` 
  - `Security Filtering` > `Find all` > `Rapheal.IT`
  - Set **"Remove all access to shut down: Deny all access"** to **Enabled**

Result: Shut Down, Restart, Sleep, and Hibernate commands disabled for all users in the **IT OU**.
---

## Screenshots

- [Linking Window 8.1 to domain](https://github.com/Oluwafunsho-Hub/SETTING-UP-AN-ACTIVE-DIRECTORY-USING-WINDOWS-SERVER-AND-TWO-WINDOWS-8.1-CLIENTS/blob/main/Screenshots/Linking%20Windows%208.1%20to%20the%20server.png)
- [Seedorf Domain Setup](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Seedorf_Domain.PNG)
- [Seedorf Domain Activation Page](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Seedorf_Domain_Activation_Page.PNG)
- [Creation of OU](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Creation_of_OU.PNG)
- [List of Organization Unit](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Organization_Unit.PNG)
- [Creation of Groups](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Creation_of_Group.PNG)
- [Creation of Users](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Creation_of_users.PNG)
- [Creation of new GPO](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Creation_of_new_GPO.PNG)
- [GPO modification](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/GPO_modification.PNG)
- [Linking GPO to Domain](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Linking_GPO_to-Domain.PNG)
- [Deployment Configuration](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Deployment_Configuration.PNG)
- [Result of denied access to shutdown](https://github.com/saheed-tech/A-small-Active-Directory-IAM-lab-using-Windows-Server-and-two-Windows-8.1-clients/blob/main/Screenshots/Denial_Access_to_Shutdown.PNG)

---

  
