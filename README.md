<div align="center">

# 🔐 Cybersecurity Lab Environment Setup
### Building an isolated virtual lab for penetration testing and ethical hacking practice

[![Skill](https://img.shields.io/badge/Skill-Cybersecurity-red?style=for-the-badge&logo=shield&logoColor=white)](https://github.com)
[![Ver](https://img.shields.io/badge/Ver-Virtualbox_v7.2-blue?style=for-the-badge&logo=virtualbox&logoColor=white)](https://github.com)
[![Kali Linux](https://img.shields.io/badge/Kali_Linux-v2026.3-orange?style=for-the-badge&logo=kalilinux&logoColor=white)](https://github.com)
[![Skill](https://img.shields.io/badge/Skill-Linux-darkgrey?style=for-the-badge&logo=linux&logoColor=white)](https://github.com)
[![Network](https://img.shields.io/badge/Network-10.0.0.0%2F24-teal?style=for-the-badge&logo=cisco&logoColor=white)](https://github.com)
[![Penetration Testing](https://img.shields.io/badge/Penetration_Testing-Lab-black?style=for-the-badge&logo=letsencrypt&logoColor=white)](https://github.com)
[![Skill](https://img.shields.io/badge/Skill-Virtualization-red?style=for-the-badge&logo=vmware&logoColor=white)](https://github.com)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com)
[![NetworkWalks](https://img.shields.io/badge/NetworkWalks-orange?style=for-the-badge&logo=network-wired&logoColor=white)](https://github.com)
[![Ethical Hacking](https://img.shields.io/badge/Ethical_Hacking-Practice-darkred?style=for-the-badge&logo=hackthebox&logoColor=white)](https://github.com)

</div>

---

## 📌 Project Overview
This project details the deployment of a virtual penetration-testing lab using Oracle VirtualBox and Kali Linux. Designed as a controlled, repeatable environment, it facilitates safe network scanning and vulnerability analysis. Built on an isolated private network, the architecture easily accommodates additional target machines for advanced security drills

---

## 🎯 Objectives
The main objectives of this project are to:
- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private NAT Network for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM from the NAT Network Pool.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing. It can be used for activities such as:
- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

> ⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---

## 🏗️ Lab Architecture
Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration Details |
| :--- | :--- |
| 🖥️ Host OS | Windows 11 |
| 🧠 Host RAM | 32 GB |
| 🧰 Hypervisor | Oracle VirtualBox 7.2.22 |
| 🐉 Security OS | Kali Linux v2026.3 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

## 🪜 Lab Setup Procedure

### Step 1. Install 7-Zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.
* **Tool:** 7-Zip

---

### Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.
![Installing VirtualBox ](images/1-screenshot-installing-virtualbox.png)
> *Description: Oracle VirtualBox hypervisor installation files.*

---

### Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.
* **Configuration:**
  * **Network Name:** `NatNetwork`
  * **IPv4 Prefix:** `10.0.0.0/24`
  * **DHCP:** Enabled
  * **IPv6:** Disabled

* **Note:** A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity. This will allow future attacker and target VMs to communicate within the lab.

> 📸 **Placeholder for Image:** `images/3-screenshot-kali-linux.png`  
> *Description: VirtualBox NAT Network configuration showing the 10.0.0.0/24 IP prefix.*

---

### Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.
The VM network adapter was configured as follows:
* **Adapter 1:**
  * Attached to: NAT Network
  * Network: `NatNetwork`
  * Adapter Type: Intel PRO/1000 MT Desktop
* **Allocations:**
  * RAM: 2048 MB

A shared folder was also configured for transferring required files between the host operating system and the Kali VM.

> 📸 **Placeholder for Image:** `images/4-screenshot-kali-network-settings.png`  
> *Description: VM Network Adapter and system settings mapping to the lab network.*

---

### Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.
* **Example configuration:**
  * **IP Address:** `10.0.0.2`
  * **Subnet Mask:** `255.255.255.0`
  * **Gateway:** `10.0.0.1`
  * **DNS:** `8.8.8.8`

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

---

## Step 6. Enabling clipboad and file Drag and Drop freatures

> 📸 **Placeholder for Image:** `images/4-screenshot-kali-linux.png`  
> *Description: Enabling Seamless filesharing between VM and Host*

---

### Step 7. Create a shared folder
After completing the initial configuration, a VirtualBox snapshot was created.
* **Snapshot Name:** `Clean Kali - Network Setup`

The snapshot represents the clean baseline of the laboratory. If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

---

### Step 8. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.
* **Snapshot Name:** `Clean Kali - Network Setup`

The snapshot represents the clean baseline of the laboratory. If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

---

## 🔎 Lab Verification

Verify that your environment functions properly using the commands below:

| ✅ Test | 🧾 Command | 🎯 Expected Result |
| :--- | :--- | :--- |
| 🌐 Check IP address | `ip a` | Correct Kali IP displayed |
| 📡 Test gateway | `ping 10.0.0.1` | Successful replies |
| 🌍 Test Internet connectivity | `ping 8.8.8.8` | Successful replies |
| 🔎 Test DNS resolution | `nslookup networkwalks.com` | Domain resolves |
| 🧰 Verify Nmap | `nmap --version` | Nmap version displayed |
| 🔄 Verify snapshot | *Restore snapshot and run `ip a`* | Baseline configuration restored |

### Example Results
* **IP Address:** `10.0.0.2/24`
* **Gateway:** `10.0.0.1`
* **DNS:** `8.8.8.8`

---

## 🐞 Problems Encountered & Solutions
Documenting problems is an important part of the project.

### Problem 1. Internet Connectivity After Static IP Configuration
After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.
* **Workaround used:**
  ```bash
  sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
