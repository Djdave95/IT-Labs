# IT-Labs
IT Home Labs – Active Directory, Group Policy, Desktop Support
# IT Home Labs Portfolio

## Lab 1: Active Directory & Desktop Support Home Lab

### Overview
Built a Windows Server Active Directory environment to support enterprise-style user and device management. This lab focused on directory services, DNS integration, organizational unit (OU) design, and secure user provisioning.

### Environment
- Hypervisor: VMware Workstation Pro  
- Server OS: Windows Server 2022  
- Domain: LAB.LOCAL  
- Services: Active Directory Domain Services (AD DS), DNS  
- Networking: Static IP configuration  

### What Was Configured
- Installed and configured Active Directory Domain Services  
- Promoted a Windows Server to a Domain Controller  
- Configured DNS for internal name resolution  
- Designed Organizational Unit (OU) structure  
- Created and managed domain users  
- Enforced Active Directory password complexity policies  

### Evidence
#### Active Directory Domain Context
![AD Domain](screenshots/lab1_ad_domain_context_menu.png)

Verified successful domain creation and administrative access by managing objects directly within the LAB.LOCAL domain.

#### Default Active Directory Containers
![Default AD Containers](screenshots/lab1_default_ad_containers.png)

Validated successful domain controller promotion by confirming the presence of default Active Directory containers within the LAB.LOCAL domain.

#### Organizational Unit (OU) Structure
![OU Structure](screenshots/lab1_ou_structure.png)

Created custom organizational units to logically separate users, computers, groups, and IT administration in accordance with Active Directory best practices.

#### Domain User Provisioning
![User Provisioning](screenshots/lab1_domain_user_provisioning.png)

Provisioned domain user accounts within a dedicated organizational unit while enforcing Active Directory password complexity policies.

### Skills Demonstrated
- Active Directory Administration  
- Identity & Access Management (IAM)  
- Windows Server Administration  
- DNS & Networking Fundamentals  
- Desktop Support Fundamentals  

### What I Learned
This lab reinforced the relationship between Active Directory and DNS, the importance of proper OU structure for scalable administration, and how password policies enforce security during user provisioning.
