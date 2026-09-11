<h1 align="center"> 
   🔐A Typical Cybersecurity Lab <br>
Setup
</h1>
<p align="center"
  <b>Building an isolated virtual lab for penetration testing and ethical hacking practice</b>
</p>

<p align="center">

<img src="https://img.shields.io/badge/Skill-Cybersecurity-111827?style=flat-square&labelColor=9f1239">

<img src="https://img.shields.io/badge/Ver-VirtualBox%207.2-2563eb?style=flat-square">

<img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-b45309?style=flat-square">

<img src="https://img.shields.io/badge/Skill-Linux-111827?style=flat-square">

<br>

<img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-0f766e?style=flat-square">

<img src="https://img.shields.io/badge/Penetration%20Testing-991b1b?style=flat-square">

<img src="https://img.shields.io/badge/Skill-Virtualization-111827?style=flat-square">

<img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github">

<img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white">

<br>

<img src="https://img.shields.io/badge/NetworkWalks-7f1d1d?style=flat-square">

<img src="https://img.shields.io/badge/Ethical%20Hacking-9a3412?style=flat-square">

<img src="https://img.shields.io/badge/Oluwatumilara%20Emmanuel%20Opakunbi-991b1b?style=flat-square">

</p>

<hr>

## 🎯 Project Overview
In this project, setting up a **virtual cybersecurity and penetration-testing laboratory** was achieved using VirtualBox and Kali Linux.

Creating a Lab ensures a controlled environment where cybersecurity tools are available, network scanning, reconnaissance, Vulnerability assessment, and other security-testing activity can be performed safely and repeatedly without any complications.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

<hr>

## 📌 Objectives
The main objectives of this project are to:
- Install and configure VirtualBox
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

<hr>

## 🛡️ Purpose of the Lab
  The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

  It can be used for activities such as:
  - Network reconnaissance
  - Port scanning
  - Vulnerability assessment
  - Packet analysis
  - Web security testing
  - Exploitation practice
  - Security-tool experimentation

⚠️ **Note**: This laboratory must only be used for systems that you own or have explicit permission to test. Do not use lab or its tools to attack unauthorized systems.

<hr>

 ## ⚙️Lab Configuration
 |🧩 Component	|⚙️ Configuration |
 |--------------|----------------- |
|🖥️ Host OS |	Windows 11|
|🧠 Host RAM |	16 GB|
|⚡ Processor |	Intel Core i5 |
|🧰 Hypervisor |	VirtualBox 7.2 |
|🐉 Security OS	| Kali Linux 2026.2 |
|🧠 Kali RAM |	2048 MB |
|🌐 Virtual Network |	NAT Network |
|📡 Network Address |	10.0.0.0/24 |
|🐧 Kali IP Address |	10.0.0.2/24 |
|🚪 Default Gateway |	10.0.0.1 |
|🌍 DNS Server |	8.8.8.8 |
|🔮 Future VM Range |	10.0.0.3–10.0.0.99 |

<hr>

## 🪜 Lab Setup Procedure
### Step 1. Install 7-Zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a `.7z` archive.

**Tool**: 7-Zip

<hr>

### Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

<hr>

### Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled
![image alt](https://github.com/TumilaraEmmanuel/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/25b27561d1bae073f4536419d956748a757feb64/1.png)

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.

<hr>

### Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:
```RAM: 2048 MB```

![image alt](https://github.com/TumilaraEmmanuel/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/132ac23c96118307fab555b9f2926e496650f8ba/2.png)

A shared folder was also configured for transferring required files between the host operating system and the Kali VM

<hr>

### Step 5. Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:

```IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

![image alt](https://github.com/TumilaraEmmanuel/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/8a4f400396518b1ec41a0ea466d99d0b5187dbee/3.png)

![image alt](https://github.com/TumilaraEmmanuel/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/8a4f400396518b1ec41a0ea466d99d0b5187dbee/4.png)

<hr>

### Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

```Clean Kali - Network Setup```
The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

<hr>

## 🔎 Lab Verification
|✅ Test|	🧾 Command	|🎯 Expected Result
|-------|-------------|--------------------|
|🌐 Check IP address	| `ip a`	|Correct Kali IP displayed|
|📡 Test gateway |	ping 10.0.0.1	|Successful replies|
|🌍 Test Internet connectivity |	ping 8.8.8.8 |	Successful replies|
|🔎 Test DNS resolution |	nslookup networkwalks.com |	Domain resolves|
|🧰 Verify Nmap |	nmap --version |	Nmap version displayed|
|🔄 Verify snapshot |	Restore snapshot and run ip a	| Baseline configuration restored|

#### Example Results

```IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

<hr>

## 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

### Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.
One workaround used during this lab was:
```sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0```
The network connection was then restarted/rebooted and connectivity was tested again.

Important: Network interface and connection names may differ between systems. Students should first identify their actual connection name before running an `nmcli` command.

<hr>

## 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:
### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking
I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned the importance of creating a clean snapshot **before performing risky or experimental activities**.

It serves as a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is a very important step in a professional cybersecurity project

<hr>

## 🔐 Security & Ethical Use

This laboratory set up is intended strictly for education purposes only.

<hr>

## 🔗 Tools & Resources

-**7-Zip**: https://7-zip.org/download.html
-**VirtualBox**: https://virtualbox.org/wiki/Downloads
-**Kali Linux**: https://kali.org/get-kali

<hr>

## 👤 Author

**Tumilara Emmanuel** 
Cybersecurity Intern B083

LinkedIn: https://linkedin.com/in/opakunbi-oluwatumilara-79a394210

<hr>

## 📌 Project Information

**Program Name**: Cybersecurity at Networkwalks | **Week**: 01 | **Project**: Cybersecurity & Pentesting Lab Setup | **Repository**: GitHub
