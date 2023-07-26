# Penetration Test Report ✨🔍

### Objective 👋

This report presents the findings from an extensive penetration test conducted on the network infrastructure and systems at Allsafe Cybersecurity. The primary objective was to assess the security setup and identify potential vulnerabilities that could compromise critical data and systems.

### Methodology 🛠️

The assessment involved using a combination of network scanning tools and web application security scanners. These tools allowed us to explore the /20 subnet and meticulously check all 65535 ports on each system to leave no room for any overlooked security gaps.

### Findings 🚨

1. **Open Ports on Systems:**

   - Port 1013: A vulnerable website hosted on this port allowed remote code injection, leading to unauthorized access and lateral movement within the network.

   - Port 2222: Improper segmentation enabled lateral movement from the compromised system with port 1013 open to the machine with port 2222 open.

   - Windows Systems with Port 445: Leveraging the compromised machine with port 2222 open, access to Windows machines with port 445 open was gained, posing a serious security risk due to Windows SMB vulnerabilities.

2. **Privilege Escalation Opportunities:** Several systems exhibited privilege escalation flaws, providing unauthorized access to sensitive files and data.

3. **Password Cracking:** Weak passwords were uncovered on compromised systems, highlighting the need for multi-factor authentication (MFA) and strong password policies.

4. **System Reconnaissance:** Thorough surveying of compromised machines revealed sensitive files and potential areas for privilege escalation.

5. **Network Segmentation:** Improperly segregated network segments allowed for lateral movement, increasing the impact of potential breaches.

### Recommendations 🚀

- Apply security patches and updates promptly to fix known vulnerabilities and prevent potential exploits.

- Implement strong network segmentation to restrict unauthorized access and prevent lateral movement among different network segments.

- Conduct routine security audits and code reviews for web applications to find and patch holes that could allow for code injection and unauthorized access.

- Thoroughly analyze the compromised systems to spot any potential opportunities for privilege escalation and take immediate action to prevent them.

- Enforce strong password policies and consider implementing multi-factor authentication (MFA) to bolster the security of user accounts.

The identified vulnerabilities should be addressed promptly to enhance the network security and protect critical assets and data from potential cyber threats.

---
*Note: This is a high-level summary of the penetration test findings for Allsafe Cybersecurity.*
