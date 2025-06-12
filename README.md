**Penetration Test Report**  
**Client:** Allsafe Cybersecurity  
**Date:** 07/16/2023  
**Prepared by:** Mina Abskhron, Penetration Tester  

---

### Executive Summary
This report presents the results of a comprehensive penetration test performed against the network infrastructure of Allsafe Cybersecurity. The objective was to evaluate the organization's security posture by identifying vulnerabilities, simulating exploitation, and assessing potential impact.

---

### Objectives
- Identify vulnerabilities in the network and web applications.
- Test lateral movement and privilege escalation possibilities.
- Evaluate password strength and authentication mechanisms.
- Assess segmentation and access control across the network.

---

### Methodology
We used industry-standard tools and techniques in the following phases:
1. **Reconnaissance & Enumeration**: Mapped the /20 subnet and identified active hosts.
2. **Vulnerability Scanning**: Full port scan (1-65535) on identified systems.
3. **Exploitation**: Gained initial access through identified weak points.
4. **Post-Exploitation**: Privilege escalation, data access, and lateral movement.
5. **Reporting**: Documented findings with supporting screenshots.

Tools used included: Nmap, Nikto, John the Ripper, and manual testing scripts.

---

### Findings

#### 1. Open Ports & Remote Exploits
- **Port 1013**: Hosted a vulnerable web application (see below) which allowed remote code injection. This was used as the initial point of compromise.  
  ![Initial Web Exploit](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_3_img_1.png)

- **Port 2222**: Lateral movement was achieved from the compromised host. Lack of segmentation allowed pivoting.  
  ![Port 2222 Compromise](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_3_img_2.png)

- **Port 445 (SMB)**: Gained access to multiple Windows systems via known SMB vulnerabilities.  
  ![SMB Exploitation](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_4_img_1.png)

#### 2. Privilege Escalation
Using local exploits and weak configurations, administrative access was obtained on several machines. Escalation was supported by weak permissions and outdated software.  
  ![Privilege Escalation](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_5_img_2.png)

#### 3. Password Weaknesses
Password hashes were extracted and cracked using John the Ripper. Weak credentials were found such as `admin:123456`, indicating a lack of enforcement of strong password policies.  
  ![Password Cracking](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_1.png)

#### 4. Reconnaissance & Sensitive Data Discovery
System-level enumeration revealed various sensitive files and configurations. No password files were recovered, but user info and system blueprints were accessible.  
  ![Recon Evidence](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_6_img_3.png)

#### 5. Poor Network Segmentation
The flat network structure allowed unrestricted lateral movement between systems.  
  ![Network Segmentation](https://raw.githubusercontent.com/eldoktor1/Penetration-Test-Report/main/images/page_7_img_4.png)

---

### Recommendations
1. **Patch Management**: Apply critical security patches to all systems and applications.
2. **Network Segmentation**: Implement VLANs and firewall rules to limit cross-segment access.
3. **Harden Web Applications**: Conduct regular code reviews and audits. Deploy a WAF.
4. **Enforce MFA & Password Policy**: Require complex passwords and implement multi-factor authentication.
5. **Privilege Hardening**: Regularly audit user roles and remove unnecessary admin privileges.
6. **Monitoring & Logging**: Enable system logging and configure alerts for suspicious activity.

---

### Conclusion
Multiple critical vulnerabilities were identified and exploited, demonstrating the ability to compromise systems, escalate privileges, and access sensitive information. By acting on the above recommendations, Allsafe Cybersecurity can significantly improve its defenses.

---

**Contact:**  
Mina Abskhron  
Penetration Tester  
Allsafe Cybersecurity  
Email: mina.abskhron@example.com
