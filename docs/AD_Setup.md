# Component Name (e.g., Active Directory Setup)

## 🔧 Tools & Versions
- OS: Windows Server 2022
- Tools: Active Directory Domain Services, DNS
- Version: [Tool/Version Info]

## 📦 Installation Steps
1. Downloaded and installed Windows Server ISO
2. Promoted to Domain Controller with `cyberlab.local`
3. Added DNS and DHCP roles
4. Created users and OUs

### 🖼️ Screenshots
> _Include screenshots of GUI steps, like AD install wizard, or user creation_

## 🔑 Configuration
- OU structure:
  - `/Users/Engineering`
  - `/Users/HR`
- GPOs applied:
  - Password complexity
  - Logon hours

### 🧪 Commands Used
```powershell
Install-WindowsFeature -Name AD-Domain-Services
