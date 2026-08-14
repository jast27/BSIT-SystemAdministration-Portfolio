# Week 03 – Enterprise Server Deployment and Operating System Installation

## Project Overview

This Week 3 project focuses on deploying and configuring a clean Ubuntu Server virtual machine for enterprise use. The project covers the installation and configuration of Ubuntu Server, server verification, BIOS and UEFI comparison, and the Ubuntu boot process.

## Learning Objectives

- Explain the purpose of an operating system in an enterprise environment.
- Differentiate BIOS and UEFI firmware.
- Explain the stages of the computer boot process.
- Compare Windows Server, Ubuntu Server, and Rocky Linux.
- Install Ubuntu Server in a virtual machine.
- Configure essential server settings.
- Enable secure remote administration using SSH.
- Verify server functionality.
- Document installation procedures.

## VM Specifications

| Component | Configuration |
|---|---|
| Name | Ubuntu-Server-Week03 |
| RAM | 4 GB |
| CPU | 2 Virtual Processors |
| Storage | 40 GB (VDI/VMDK) |
| Network | NAT (or Bridged if instructed) |
| Optical Drive | Ubuntu Server ISO |

## Installation Summary

The Ubuntu Server installation followed the required Week 3 configuration:

1. Select English as the installation language.
2. Select the appropriate keyboard layout, such as English (US).
3. Configure the network using DHCP unless instructed otherwise.
4. Record the assigned IP address.
5. Set the hostname to server01.
6. Create a non-root administrative user.
7. Select Guided – Use Entire Disk.
8. Record the partition scheme, file system, and disk size.
9. Select Install OpenSSH Server.
10. Do not install additional packages unless instructed.
11. Complete the installation and restart the virtual machine.
12. Remove the installation ISO if prompted and log in.

## Configuration Summary

| Configuration | Details |
|---|---|
| Hostname | server01 |
| User Account | Non-root administrative account |
| Network | DHCP |
| IP Address | Assigned IP address |
| Storage | Guided – Use Entire Disk |
| SSH | OpenSSH Server |
| Additional Packages | None unless instructed |

## Verification Results

### 1. Login Verification

Log in using the non-root administrative account created during installation.

<img width="1920" height="1080" alt="Task 1" src="https://github.com/user-attachments/assets/add90b05-90b9-455b-8544-b1c748fdd134" />


### 2. Hostname Verification

Command used: `hostname`

Expected hostname: `server01`

<img width="1920" height="1080" alt="Task 2" src="https://github.com/user-attachments/assets/69183d3c-84a2-4049-9945-e022f8487739" />

### 3. IP Address Verification

Command used: `ip addr`

<img width="1920" height="1080" alt="Task 3" src="https://github.com/user-attachments/assets/cd380b7e-faa9-47d1-8a5c-dd91d3d2d119" />


### 4. Internet Connectivity Verification

Command used: `ping -c 4 google.com`

<img width="1920" height="1080" alt="Task 4" src="https://github.com/user-attachments/assets/857bf5df-6251-4c52-b9e5-41f358469c05" />

### 5. System Update Verification

Commands used: `sudo apt update` and `sudo apt upgrade -y`

<img width="1920" height="1080" alt="Task 5" src="https://github.com/user-attachments/assets/98232f4c-cea3-4998-9e76-cc32183c49e9" />


### 6. SSH Service Verification

Command used: `systemctl status ssh`

The SSH service should show `active (running)`.

<img width="1920" height="1080" alt="Task 6" src="https://github.com/user-attachments/assets/0f3d3c72-a066-4e09-bb34-31ce4a5ebc3c" />


## BIOS vs UEFI Highlights

| Category | BIOS | UEFI |
|---|---|---|
| Definition | Legacy firmware interface | Modern firmware interface |
| Boot Process | Traditional boot-sector based process | Uses firmware boot managers |
| Disk Support | Commonly associated with MBR limitations | Supports GPT and larger storage |
| Partition Style | MBR | GPT |
| Security | More limited | Supports Secure Boot |
| Advantages | Simple and compatible with legacy systems | Better support for modern hardware and storage |
| Disadvantages | Limited storage, partitioning, and security features | More complex and less suitable for some legacy systems |
| Modern Usage | Mostly legacy systems | Standard on modern computers |

## Embedded Boot Process Flowchart

The Ubuntu boot process follows this sequence:

Power On → BIOS/UEFI Initialization → Boot Device Detection → Boot Loader (GRUB) → Linux Kernel → init/systemd → Services Start → Login Prompt

<img width="983" height="1593" alt="Ubuntu Boot Process drawio" src="https://github.com/user-attachments/assets/3b0193d6-5843-4554-a000-9c2ecb68452f" />


## Challenges Encountered

During the installation and configuration process, the following challenges were encountered:

- Configuring the virtual machine with the required specifications.
- Properly configuring the network connection.
- Setting the correct hostname.
- Configuring the disk using the required installation option.
- Verifying the SSH service after installation.
- Checking the server's connectivity and system status.

## Reflection

This Week 3 project provided practical experience in installing and configuring an Ubuntu Server in a virtualized environment. The activity helped me understand that server deployment requires careful configuration of the virtual machine, network settings, hostname, administrative account, storage, and SSH service.

The verification tasks were an important part of the project because they provided evidence that the server was functioning correctly after installation. Commands such as hostname, ip addr, ping -c 4 google.com, sudo apt update, sudo apt upgrade -y, and systemctl status ssh helped verify the server's identity, network configuration, Internet connectivity, system updates, and SSH service.

I also learned about the differences between BIOS and UEFI and how firmware is connected to the operating system boot process. Understanding the sequence from power-on to BIOS/UEFI initialization, boot device detection, GRUB, the Linux kernel, systemd, and services helped me understand what happens before the login prompt appears.

Another important lesson from this activity was the importance of technical documentation. Recording the installation process and providing verification screenshots makes the configuration easier to understand and reproduce. Overall, this project improved my skills in Linux server administration, virtualization, system verification, troubleshooting, and technical documentation.

## References

- UEFI Forum – UEFI Specifications: https://uefi.org/specifications
- Microsoft Learn – UEFI Mode vs. Legacy BIOS Mode: https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/boot-to-uefi-mode-or-legacy-bios-mode
- Microsoft Learn – Secure Boot: https://learn.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-secure-boot
- Ubuntu Documentation: https://documentation.ubuntu.com/
- Red Hat Documentation: https://docs.redhat.com/
