# 🛠️ Active Directory Setup (Josh Madakor Home Lab Style)

## 🎯 Overview
This document follows **Josh Madakor’s** guide on setting up a basic home lab with **Active Directory** running on **Windows Server 2019** inside **Oracle VirtualBox**, including how to create users with PowerShell.

Video: [Watch here](https://www.youtube.com/watch?v=Uu3kLgnbO74)

---

## 🔧 Tools & Versions
- **Hypervisor**: Oracle VirtualBox 7.x
- **OS ISO**: Windows Server 2019 Evaluation
- **RAM**: 2–4 GB
- **Disk**: 50 GB dynamically allocated
- **Networking**: Internal Network
- **Domain Name**: `mydomain.com`
- **Client OS** (for future use): Windows 10/11 (optional)

---

## 📦 Installation Steps

### 1. Create a New VM
- Name: `DC-Server`
- Version: Windows Server 2019 (64-bit)
- RAM: 2048–4096 MB
- Hard disk: 50 GB (VDI, dynamically allocated)
- Network Adapter: **Internal Network** (`intnet`)

### 2. Install Windows Server 2019
- Choose **Windows Server 2019 Standard (Desktop Experience)**
- Set admin password
- Install updates and reboot

---

## 🌐 3. Set Static IP Address

Inside the VM:

1. Open **Control Panel > Network and Sharing Center**
2. Set **IPv4** manually:
   - IP: `10.0.0.10`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: `10.0.0.1` *(or leave blank if only internal network)*
   - DNS: `127.0.0.1`

---

## 🖥️ 4. Install and Configure AD DS

Open **PowerShell (Admin)** and run:

```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
