Firewalls & Network Security# Host Hardening

## Overview
This project focuses on strengthening Windows systems by configuring group policies, securing unused ports, applying patches, and enhancing security with Windows Defender.

## Key Features
1. **Group Policy Management**: Configure password policies (e.g., complexity, expiration) and AUP logon messages.
2. **Securing Ports**: Block unused ports (e.g., DNS and Kerberos) using the Windows Firewall and verify with `nmap`.
3. **Patch Management**: Install and verify system updates using PowerShell.
4. **Windows Defender**: Enable real-time protection, schedule weekly scans, and configure file scanning policies.

## Lab Steps
1. **Group Policies**:
   - Open Group Policy Management Console:
     ```bash
     gpmc.msc
     ```
   - Create password policies (90-day expiration, 8-character minimum, complexity enabled).
   - Set logon messages: "Unauthorized use of this system is strictly prohibited..."
2. **Secure Ports**:
   - Use `nmap` to find open ports:
     ```bash
     nmap -F <target-IP>
     ```
   - Block ports 53 and 88 using Windows Firewall inbound rules.
3. **Apply Patches**:
   - Verify installed patches:
     ```bash
     Get-Hotfix -id KB2919355
     ```
   - Install prerequisite patches and confirm installation.
4. **Windows Defender**:
   - Enable real-time protection and configure weekly full scans every Tuesday at 3:00 AM.
   - Set file scanning for all downloads and update virus definitions.

## Tools Used
- **Group Policy Management Console**: For password and logon policies.
- **Windows Firewall**: To block unnecessary ports.
- **PowerShell**: To manage and verify patches.
- **Windows Defender**: To enable and configure system protection.

## Learning Objectives
- Secure Windows hosts using group policies and port management.
- Develop patching and verification skills.
- Mitigate threats by configuring Windows Defender for proactive scans.

## Documentation
Refer to the [Firewalls & Network Security](https://github.com/StephVergil/Firewalls-Network-Security/blob/main/Host%20Hardening.docx)  for full details.
