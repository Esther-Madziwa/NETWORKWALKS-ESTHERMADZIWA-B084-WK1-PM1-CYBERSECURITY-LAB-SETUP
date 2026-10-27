# Networkwalks Cybersecurity Lab Setup: Home Testing Environment

This repository documents the structural configuration of a local cybersecurity and ethical hacking testing lab environment hosted on a personal computer/laptop as required by the Week 1 project criteria.

---

## 🛠️ Lab Overview & Architecture

The objective of this project is to build an isolated, secure, and fully functional virtual environment for conducting ethical hacking practices, penetration testing, and security analysis. 

### Core Components
* **Hypervisor:** VirtualBox (Latest Version)
* **Attacking Machine:** Kali Linux
* **Network Subnet:** `10.0.0.0/24`

---

## 💻 Configuration Details

### 1. Virtualization Base (VirtualBox)
* **Software:** VirtualBox hypervisor handles the virtualization of the infrastructure.
* **Guest Additions:** VirtualBox Guest Additions installed to facilitate host-to-guest integrations.
* **Convenience Settings:**
  * **Shared Clipboard:** Enabled (Bidirectional)
  * **Drag and Drop:** Enabled (Bidirectional)

### 2. Network Configuration
To maintain safety and control while preserving the necessary connectivity for updates and tool functionality, the network is built on a customized NATNetwork architecture.

* **Network Type:** NATNetwork
* **Internet Access:** Full external internet routing enabled via the NAT interface.

### 3. Kali Linux Deployment
* **Role:** Dedicated pentesting and attacking platform.
* **IP Assignment:** Static IP configuration setup (`10.0.0.2/24`).
* **Host Integration:** A dedicated shared directory mapping the host machine's `/downloads` folder to the Kali Linux environment for efficient tool and file transfer.

---

## 🚀 Steps to Replicate

### Step 1: Create the NATNetwork in VirtualBox
1. Navigate to **File** > **Tools** > **Network Manager** (or Preferences > Network depending on version).
2. Create a new **NAT Network**.
3. Set the Network CIDR to `10.0.0.0/24`.

### Step 2: Deploy and Optimize Kali Linux
1. Import or install the latest **Kali Linux** image.
2. Open VM Settings > **General** > **Advanced** and set **Shared Clipboard** and **Drag'n'Drop** to **Bidirectional**.
3. Go to **Network** > Attached to: **NAT Network** > Select the network created in Step 1.
4. Go to **Shared Folders** > Add a new folder path targeting your host's `/downloads` folder. Set it to auto-mount.

### Step 3: Configure Guest Operating System Network
1. Boot into Kali Linux.
2. Configure the network adapter interface manually to use a static IP topology (`10.0.0.2`).
3. Verify internet connectivity using `ping 8.8.8.8`.

---

## 🔍 Verification & Testing

- [x] Bidirectional copy-paste functioning successfully.
- [x] Shared folder `/downloads` accessible by the virtual machine.
- [x] Static IP address persistent on `10.0.0.2`.
- [x] External web access established for downloading updates and repositories.
