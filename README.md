# Firewalls & Network Security: Host Hardening

## Overview

This project focuses on applying advanced host hardening techniques to strengthen Windows systems. By implementing group policies, securing unused ports, managing patches, and configuring Windows Defender, this project aims to enhance the overall security posture of the system and mitigate vulnerabilities effectively.

---

## Key Features

1. **Group Policy Management**:
   - Configure password policies, including complexity, expiration, and length requirements.
   - Display Acceptable Use Policy (AUP) logon messages to deter unauthorized access.

2. **Port Security**:
   - Identify and block unused or vulnerable ports (e.g., DNS and Kerberos) using Windows Firewall.
   - Verify port closure using network scanning tools like `nmap`.

3. **Patch Management**:
   - Install critical updates and verify patch status using PowerShell.
   - Apply prerequisite patches to maintain compatibility and system performance.

4. **Windows Defender Configuration**:
   - Enable real-time protection to monitor system activity continuously.
   - Schedule weekly full-system scans and configure file scanning policies to detect malicious files effectively.

---

## Lab Steps

### **1. Configure Group Policies**

- Open the Group Policy Management Console:
  ```bash
  gpmc.msc
  ```
- Configure password policies:
  - Maximum Password Age: 90 days.
  - Minimum Password Length: 8 characters.
  - Password Complexity: Enabled.
- Set AUP logon message:
  - Message: "Unauthorized use of this system is strictly prohibited. All activities are monitored and logged."

### **2. Secure Unused Ports**

- Use `nmap` to identify open ports:
  ```bash
  nmap -F <target-IP>
  ```
- Block ports 53 (DNS) and 88 (Kerberos) using Windows Firewall:
  - Open Windows Firewall with Advanced Security.
  - Create inbound rules to block the specified ports.
- Verify port closure by re-running `nmap` scans.

### **3. Apply Patches**

- Check for installed patches:
  ```bash
  Get-Hotfix -id KB2919355
  ```
- Install prerequisite patches using PowerShell or manual download.
  - Example: KB2919442 must be installed before KB2919355.
- Confirm installation:
  ```bash
  Get-Hotfix -id KB2919355
  ```

### **4. Configure Windows Defender**

- Enable real-time protection:
  - Open Windows Defender Security Center and enable all protection features.
- Schedule weekly scans:
  - Set scan day: Tuesday.
  - Set scan time: 3:00 AM.
- Configure file scanning:
  - Enable scanning of all downloaded files and applications before execution.
  - Ensure virus definitions are updated automatically.

---

## Tools Used

1. **Group Policy Management Console**:
   - Manage and enforce password and logon policies.

2. **Windows Firewall**:
   - Block unnecessary ports and manage inbound/outbound traffic rules.

3. **PowerShell**:
   - Verify installed patches and manage updates programmatically.

4. **Windows Defender**:
   - Provide real-time protection and scheduled scanning capabilities.

5. **Nmap**:
   - Detect and verify open ports for enhanced network security.

---

## Learning Objectives

1. **Implement Group Policies**:
   - Learn to enforce strong password policies and set logon messages for compliance.

2. **Harden Network Security**:
   - Secure unused ports and monitor network activity to prevent unauthorized access.

3. **Develop Patch Management Skills**:
   - Apply and verify system updates to maintain security and performance.

4. **Enhance Endpoint Protection**:
   - Configure Windows Defender for proactive malware detection and prevention.

---

## Practical Applications

1. **Regulatory Compliance**:
   - Meet organizational and legal requirements by enforcing group policies and displaying logon disclaimers.

2. **Threat Mitigation**:
   - Reduce attack surfaces by closing unused ports and applying security patches.

3. **Endpoint Security**:
   - Strengthen system defenses with advanced configurations in Windows Defender.

---

## Resources

1. [Host Hardening Lab Guide](https://github.com/StephVergil/Firewalls-Network-Security/blob/main/Host%20Hardening.docx)
2. **Microsoft Documentation**:
   - [Group Policy Overview](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/group-policy/group-policy-overview)
   - [Windows Firewall with Advanced Security](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
4. **PowerShell Resources**:
   - [PowerShell for Patch Management](https://learn.microsoft.com/en-us/powershell/)
5. **Nmap Documentation**:
   - [Nmap Official Site](https://nmap.org/)

---

## Conclusion

This project demonstrates how to apply host hardening techniques to enhance the security of Windows systems. By combining group policy enforcement, port management, patching, and endpoint protection, organizations can achieve a more secure and resilient IT environment.

---

## Disclaimer

This project was conducted in a controlled environment. Implementing these techniques on production systems should adhere to organizational policies and compliance requirements.

---

