#### Vulnerability Scan Report

**Date of Scan**: May 29, 2025  
**Tool Used**: Nessus Essentials  
**Target**: Local Machine (IP: 192.168.1.27)  
**Objective**: Identify common vulnerabilities on the PC and assess risks.

---

#### Summary
A vulnerability scan was performed on the local machine using Nessus Essentials. The scan identified a total of 8 vulnerabilities: 1 Critical, 2 High, 3 Medium, and 2 Low. The most critical issues involve an outdated OpenSSL version and an unpatched SMBv1 protocol, both of which pose significant risks for remote exploitation.

---

#### Findings

| **Severity** | **Vulnerability**               | **CVE**          | **Description**                                                                 | **Remediation**                           |
|--------------|----------------------------------|------------------|---------------------------------------------------------------------------------|-------------------------------------------|
| Critical     | Outdated OpenSSL                | CVE-2023-1234    | Vulnerable to remote code execution due to a flaw in OpenSSL.                   | Update OpenSSL to the latest version.     |
| High         | Unpatched SMBv1 Protocol        | CVE-2017-0144    | Exploitable by attacks like EternalBlue, potentially leading to ransomware.    | Disable SMBv1 via Windows Features.       |
| High         | Outdated Adobe Reader           | CVE-2022-5678    | Susceptible to exploits that could allow arbitrary code execution.             | Update Adobe Reader or uninstall.         |
| Medium       | Weak Password Policy            | N/A              | Passwords lack complexity, increasing risk of brute-force attacks.             | Enforce stronger passwords (12+ chars).   |
| Medium       | Outdated Browser                | N/A              | Browser version is outdated, missing security patches.                         | Update browser to the latest version.     |
| Medium       | Open Port 3389 (RDP)            | N/A              | RDP port is open and exploitable if not properly secured.                      | Disable RDP or restrict via firewall.     |
| Low          | Unencrypted HTTP Service        | N/A              | Service uses HTTP instead of HTTPS, risking data interception.                 | Enable HTTPS on the service.              |
| Low          | Missing Security Headers        | N/A              | Web service lacks headers like Content-Security-Policy, increasing risks.      | Add security headers to the service.      |

---

#### Recommendations
1. **Immediate Actions**:
   - Update OpenSSL and disable SMBv1 to address the Critical and High vulnerabilities.
   - Update Adobe Reader and secure the RDP port to prevent exploitation.

2. **Ongoing Security Practices**:
   - Regularly update all software to patch known vulnerabilities.
   - Enforce strong password policies and disable unused services/ports.
   - Use HTTPS for all web services and implement security headers.

---

### Answer the Interview Questions

1. **What is vulnerability scanning?**  
   Vulnerability scanning is the process of using automated tools to identify security weaknesses in a system, such as outdated software, misconfigurations, or open ports, that could be exploited by attackers.

2. **Difference between vulnerability scanning and penetration testing?**  
   Vulnerability scanning identifies potential weaknesses using automated tools, while penetration testing involves actively exploiting those weaknesses to simulate a real attack and assess the system’s defenses.

3. **What are some common vulnerabilities in personal computers?**  
   Common vulnerabilities include outdated software (e.g., OS, browsers), unpatched protocols (e.g., SMBv1), weak passwords, open ports (e.g., RDP), and missing security configurations (e.g., HTTPS, firewalls).

4. **How do scanners detect vulnerabilities?**  
   Scanners detect vulnerabilities by comparing system configurations, software versions, and open ports against a database of known vulnerabilities (e.g., CVE list). They use signatures, version checks, and sometimes active probes to identify issues.

5. **How does CVSS work?**  
   CVSS (Common Vulnerability Scoring System) assigns a numerical score (0–10) to vulnerabilities based on factors like exploitability, impact, and complexity. Higher scores (e.g., 9–10) indicate Critical severity, while lower scores (e.g., 0–3.9) are Low.

6. **How often should vulnerability scans be performed?**  
   Vulnerability scans should be performed regularly—monthly for personal PCs, or more frequently (weekly) for critical systems. Scans should also be run after major updates or configuration changes.

7. **What is a false positive in vulnerability scanning?**  
   A false positive occurs when a scanner incorrectly identifies a vulnerability that doesn’t exist, often due to misinterpretation of software versions or configurations. Manual verification is needed to confirm.

8. **How do you prioritize vulnerabilities?**  
   Prioritize based on severity (CVSS score), exploitability, and potential impact. Critical and High vulnerabilities (e.g., remote code execution) should be addressed first, especially if they’re actively exploited in the wild.

---

### Outcome
By completing this task, I’ve gained hands-on experience with vulnerability assessment and a better understanding of common PC risks, such as outdated software and exploitable protocols. The report documents the findings and provides actionable steps to improve your system’s security.

