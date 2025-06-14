# Penetration Test Report

**Prepared by:** Mina Abskhron, Security Analyst  
**Date:** 07/16/2023  

---

## 📌 Executive Summary

This report summarizes a targeted penetration test conducted on a fictious company’s internal network. The objective was to simulate real-world attack scenarios, assess vulnerabilities, and evaluate the organization’s ability to detect, prevent, and respond to threats.

---

## 🎯 Objectives

- Discover internal and external vulnerabilities  
- Exploit weaknesses to gain unauthorized access  
- Test for lateral movement and privilege escalation  
- Provide actionable remediation steps  

---

## 🛠️ Methodology

### Tools Used
- Nmap for scanning  
- Metasploit for exploitation  
- John the Ripper for password cracking  
- Manual Bash scripting

### Phases
1. Reconnaissance  
2. Vulnerability Scanning  
3. Exploitation  
4. Privilege Escalation  
5. Lateral Movement  
6. Post-Exploitation Analysis  

---

## 🔍 Reconnaissance & Scanning

Performed host discovery and port scanning on target subnet.

![Nmap Results](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_3_img_1.png)  
![More Nmap Data](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_3_img_2.png)  
![Subnet Mapping](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_3_img_3.png)

> Result: Identified multiple hosts and open ports across various services including HTTP, SMB, and SSH.

---

## 🧨 Exploitation

Used discovered vulnerabilities for remote code execution via Metasploit.

![Exploit Setup](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_1.png)  
![Payload Injection](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_2.png)  
![Command Injection](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_3.png)  
![Shell Access](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_4.png)  
![Directory Access](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_5.png)

> Result: Gained initial shell access as an unprivileged user.

---

## 🔼 Privilege Escalation

Discovered readable SSH keys and used known exploits to elevate access.

![SSH Key Found](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_5_img_1.png)  
![Private Key Dump](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_5_img_2.png)

> Result: Privilege escalated to full system administrator.

---

## 🔐 Password Cracking

Found a way for a persistence and an opportunity to laterally move in the network.

![Hash Dump](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_1.png)  
![Password File](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_2.png)  
![Session Dump](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_3.png)  
![Kernel Info](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_4.png)  
![User/Group Permissions](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_5.png)



---

## 🔄 Lateral Movement

Used cracked credentials to pivot to additional systems via SMB and WinRM.

![Metasploit Pivoting](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_7_img_1.png)  
![Administrator Dump](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_7_img_2.png)  
![Credential Modules](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_7_img_3.png)  
![Lateral Exploit](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_7_img_4.png)

> Result: Expanded access to multiple Windows machines inside the environment.

---

## 🧾 Data Exposure

Located unencrypted files containing passwords and internal information.

![Secrets File](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_8_img_1.png)  
![Credential File](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_8_img_2.png)

---

## 🛡️ Recommendations

1. Patch outdated and vulnerable services  
2. Enforce strong password policies  
3. Limit user privileges using RBAC  
4. Disable unnecessary ports and services  
5. Apply network segmentation  
6. Monitor logs and configure alerts  

---

## ✅ Conclusion

The test uncovered multiple critical vulnerabilities allowing full system compromise, lateral movement, and sensitive data exposure. Mitigation steps are required immediately to improve Allsafe Cybersecurity’s posture.

---

**Prepared by:** Mina Abskhron  
**GitHub:** [@eldoktor1](https://github.com/eldoktor1)
