<div align="center">

# 🔒 Cybersecurity Lab Environment Setup
### Building an isolated virtual lab for penetration testing and ethical hacking practice

[![Skill](https://img.shields.io/badge/Skill-Cybersecurity-red?style=for-the-badge&logo=shield&logoColor=white)](https://github.com)
[![Ver](https://img.shields.io/badge/Ver-Virtualbox_v7.2-blue?style=for-the-badge&logo=virtualbox&logoColor=white)](https://github.com)
[![Kali Linux](https://img.shields.io/badge/Kali_Linux-v2026.3-orange?style=for-the-badge&logo=kalilinux&logoColor=white)](https://github.com)
[![Skill](https://img.shields.io/badge/Skill-Linux-darkgrey?style=for-the-badge&logo=linux&logoColor=white)](https://github.com)
[![Network](https://img.shields.io/badge/Network-10.0.0.0%2F24-teal?style=for-the-badge&logo=cisco&logoColor=white)](https://github.com)
[![Penetration Testing](https://img.shields.io/badge/Penetration_Testing-Lab-black?style=for-the-badge&logo=letsencrypt&logoColor=white)](https://github.com)
[![Skill](https://img.shields.io/badge/Skill-Virtualization-red?style=for-the-badge&logo=vmware&logoColor=white)](https://github.com)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com)
[![NetworkWalks](https://img.shields.io/badge/NetworkWalks-Template-orange?style=for-the-badge&logo=network-wired&logoColor=white)](https://github.com)
[![Ethical Hacking](https://img.shields.io/badge/Ethical_Hacking-Practice-darkred?style=for-the-badge&logo=hackthebox&logoColor=white)](https://github.com)

</div>

---

## 🎯 Objectives
The main objectives of this laboratory project are to:
* Download and Install VirtualBox.
* Set up and configure the virtualization environment with VirtualBox.
* Create a NAT Network within the VirtualBox platform.
* Import, deploy, and configure the core Kali Linux virtual machine for pentesting.
* Assign Network information to the Kali Linux machine statically from the IP pool of the NAT Network
* Verify routing, DNS resolution, and endpoint communication.
* Create a shared folder to facilitate seamless file sharing between the virtual machine and the host.
* Create clean base snapshots for future lab exercises and disaster recovery.
* Document the complete deployment procedure professionally.

---

## ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration Details |
| :--- | :--- |
| 🖥️ Host OS | Windows 11 |
| 🧠 Host RAM | 32 GB |
| 🧰 Hypervisor | Oracle VirtualBox 7.2.22 |
| 🛡️ Primary VM / OS | Kali Linux |
| 🧠 VM RAM Allocation | 2048 MB |
| 🌐 Virtual Network Type | NAT Network |
| 📡 Network Address Range | 10.0.0.0/24 |
| 🐧 Assigned IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |

---

## 🪜 Lab Setup Procedure

### Step 1: Prepare the Hypervisor and Virtual Network
Download and install VirtualBox, then configure a dedicated virtual network to isolate lab traffic while allowing controlled communication between nodes within the lab environment.
* **Action:** Open VirtualBox $\rightarrow$ **Tools** $\rightarrow$ **Network** $\rightarrow$ **NAT Networks** (or Host-Only Networks).
* **Configuration:**
  * **Network Name:** `Lab-Net`
  * **IPv4 Prefix:** `10.0.0.0/24`
  * **DHCP Server:** Enabled

> 📸 **Placeholder for Image:** `images/01-network-setup.png`  
> *Description: VirtualBox NAT Network configuration showing the 10.0.0.0/24 IP prefix.*

---

### Step 2: Deploy and Configure the Virtual Machine
* **Action:** Import or create your virtual machine image.
* **Adapter Settings:** 
  * *Adapter 1:* Attached to **NAT Network** (`NATNetwork`)
  * *Promiscuous Mode:* Deny (or Allow All depending on sniffing needs)

> 📸 **Placeholder for Image:** `images/02-vm-settings.png`  
> *Description: VM Network Adapter settings mapping to the lab network.*

---

### Step 3: Configure Static IP and Network Parameters
Log into the machine and assign a static IP address to ensure stable referencing across future lab modules.
* **Commands used:**
  ```bash
  ip a
  sudo nano /etc/netplan/01-netcfg.yaml # (or standard interface configuration)
