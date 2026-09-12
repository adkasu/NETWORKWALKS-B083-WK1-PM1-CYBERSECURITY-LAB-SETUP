# NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-blue)
![VirtualBox](https://img.shields.io/badge/Hypervisor-VirtualBox-blue)
![Cybersecurity](https://img.shields.io/badge/Focus-Cybersecurity-red)
![Status](https://img.shields.io/badge/Status-Completed-success)

## Project Overview

This project documents the deployment, configuration, and validation of a Kali Linux cybersecurity laboratory using Oracle VirtualBox.

A pre-built Kali Linux VirtualBox image was imported into Oracle VirtualBox rather than performing a manual installation from an ISO image.

The purpose of this project is to establish a controlled virtual environment for practical learning in cybersecurity, network security, penetration testing, vulnerability assessment, traffic analysis, security monitoring, and other security-testing activities that can be performed safely and repeatedly.

---

## Project Objectives

The objectives of this project are to:

* Deploy Kali Linux using a pre-built VirtualBox image.
* Configure the Kali Linux virtual machine.
* Verify the allocated hardware resources.
* Configure and validate network connectivity.
* Verify the Kali Linux operating system.
* Confirm that Kali is running inside VirtualBox.
* Update the Kali Linux system.
* Document the laboratory setup.
* Establish a foundation for future cybersecurity projects.

---

## Lab Environment

| Component              | Configuration              |
| ---------------------- | -------------------------- |
| Host Operating System  | Windows 10                 |
| Hypervisor             | VirtualBox 7.2.16 r174877  |
| Guest Operating System | Kali Linux  2026.2         |
| Deployment Method      | Pre-built VirtualBox Image |
| CPU                    |       1Core                |
| RAM                    |        2GB                 |
| Storage                |        20GB                |
| Network Mode           |    NAT Network             |
| Lab Status             |    Operational             |

---

## Architecture

The initial laboratory consists of a Windows host running Kali Linux as a virtual machine through Oracle VirtualBox.

```text
                    Internet
                       |
                       |
                +--------------+
                | Windows Host |
                +--------------+
                       |
                 VirtualBox
                       |
                +--------------+
                |  Kali Linux  |
                |     VM       |
                +--------------+
                       |
                Virtual Network
```

Future versions of this laboratory may include additional virtual machines to create an isolated cybersecurity testing environment.

---

## Deployment Method

### Pre-built VirtualBox Image

Instead of installing Kali Linux manually from an ISO image, a pre-built Kali Linux VirtualBox image was imported into Oracle VirtualBox.

The general deployment process was:

1. Obtain the Kali Linux pre-built VirtualBox image.
2. Extract the downloaded archive.
3. Open Oracle VirtualBox.
4. Import/open the Kali Linux virtual machine.
5. Review the VM hardware configuration.
6. Configure the network adapter.
7. Start the virtual machine.
8. Verify the operating system.
9. Test network connectivity.
10. Update the operating system.

---

## VirtualBox Configuration

The following VM parameters were configured:

```text
VM Name:
[Enter VM name]

Operating System:
Kali Linux

CPU:
[Enter CPU allocation]

Memory:
[Enter RAM allocation]

Storage:
[Enter disk allocation]

Network Adapter:
[Enter adapter]

Network Mode:
[Enter NAT / Bridged / Host-Only]
```

### VM Configuration Screenshot

![image alt](https://github.com/adkasu/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/Virtualbox%20setup.jpg?raw=true)

---

## Kali Linux Verification

The following commands were used to verify the Kali Linux environment.

### Current User

```bash
whoami
```

### System Information

```bash
hostnamectl
```

### Operating System

```bash
cat /etc/os-release
```

### Virtualization Environment

```bash
systemd-detect-virt
```

The virtualization check should identify VirtualBox as the virtualization environment.

### System Information Screenshot

![image alt](screenshots/03-kali-system-information.png)

---

## Network Configuration

The Kali Linux network configuration was examined using:

```bash
ip addr
```

The routing table was checked using:

```bash
ip route
```

These commands were used to identify:

* Network interfaces
* IP address
* Subnet
* Default gateway
* Routing information

### Network Configuration Screenshot

(https://github.com/adkasu/NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/bb41c8d57d52327cd4265a132dac660543d87bc2/VirtualBox_kali-linux-systeminfo.png)

---

## Network Connectivity Testing

Connectivity was tested using ICMP.

### IP Connectivity

```bash
ping -c 4 8.8.8.8
```

### DNS Resolution

```bash
ping -c 4 google.com
```

The tests were used to determine whether:

1. The Kali VM had network connectivity.
2. The default route was functioning.
3. DNS resolution was working.

### Connectivity Test

![Network Connectivity Test](screenshots/05-network-connectivity-test.png)

---

## System Update

The Kali Linux package repositories were updated using:

```bash
sudo apt update
```

Available packages were then upgraded using:

```bash
sudo apt upgrade
```

### System Update Screenshot

![Kali System Update](screenshots/07-kali-system-update.png)

---

## Screenshots

### Kali Linux Desktop

![Kali Linux Desktop](screenshots/02-kali-desktop.png)

### Virtualization Verification

![Virtualization Verification](screenshots/06-virtualization-verification.png)

---

## Troubleshooting

Issues encountered during the laboratory setup will be documented in:

`documentation/troubleshooting.md`

Potential areas include:

* Virtual machine boot issues
* Network connectivity problems
* DNS resolution problems
* Insufficient VM resources
* VirtualBox network adapter issues
* Kali package update issues

---

## Lessons Learned

This project provided practical experience with:

* Virtual machine deployment
* Oracle VirtualBox
* Kali Linux
* Linux system administration
* Linux networking
* Virtual networking
* Basic network troubleshooting
* Cybersecurity laboratory preparation
* Technical documentation

Detailed lessons learned are documented in:

`notes/lessons-learned.md`

---

## Future Improvements

The laboratory will be expanded to support additional cybersecurity exercises.

Planned activities include:

### Network Security

* Network scanning
* Port and service enumeration
* Firewall testing
* Network segmentation
* Packet analysis

### Vulnerability Assessment

* Vulnerability scanning
* Service enumeration
* Controlled exploitation
* Vulnerability documentation

### Traffic Analysis

* Wireshark
* TCP/IP analysis
* DNS analysis
* HTTP/HTTPS analysis
* Suspicious traffic identification

### SOC and Blue Team

* Log analysis
* IOC identification
* MITRE ATT&CK mapping
* Incident investigation
* Security monitoring

### Multi-VM Cybersecurity Lab

Future versions may include:

```text
                    Internet
                       |
                 VirtualBox
                       |
          +------------+------------+
          |            |            |
       Kali Linux   Windows VM   Linux VM
       Attacker       Target       Server
          |            |            |
          +------------+------------+
                 Isolated Lab
```

---

## Security Disclaimer

This laboratory is intended strictly for authorized cybersecurity education, research, and testing.

Security testing should only be performed against systems, applications, networks, and devices for which appropriate authorization has been obtained.

---

## Author

**Kabiru Adio**

Network Engineer | Network Security | Telecommunications | Cybersecurity

This repository documents my practical learning journey in network engineering, network security, and cybersecurity.

---

## Project Status

**Status:** Completed

**Next Project:** Kali Linux Network Scanning Lab
