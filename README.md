# 👋 Hi, I'm Rohith Baggu

I'm a SOC Analyst (L1) who learns by doing. My home lab runs live attack simulations against real machines, brute force, malware drops, and web application attacks, and I detect, investigate, and document everything the way a real SOC workflow demands.

Currently looking for SOC Analyst (L1)/Security Analyst roles.

---

## 🎯 Objective

To join a SOC team as a Tier 1 Analyst and contribute from day one using hands-on experience in alert triage, log analysis, SIEM rule writing, and incident documentation built entirely through self-driven lab work.

---

## 🛡️ Core Skills

| Detection & Analysis | Tools & Platforms | Frameworks |
|---|---|---|
| Alert Triage & Escalation | Splunk, Wazuh, Elastic | MITRE ATT&CK |
| Log Analysis (Windows & Linux) | Sysmon, Windows Event Viewer | Cyber Kill Chain |
| Phishing Investigation & IOC Extraction | Wireshark, tcpdump, Nmap | Pyramid of Pain |
| Incident Documentation & Reporting | Kali Linux, pfSense | NIST CSF |
| SIEM Rule Writing & Tuning | VirusTotal, urlscan.io, AbuseIPDB | OWASP Top 10 |
| Brute Force & Malware Detection | MXToolbox, ModSecurity WAF | |

---

## 🧑‍💻 Projects

All projects involve real attack simulations run in my home lab, with documented findings, IOCs, and MITRE ATT&CK mappings.


### 🏠 SOC Home Lab – Full Detection & Response Environment

My main lab environment. Three VMs (Windows 10, Ubuntu, Kali Linux) running Wazuh SIEM with Sysmon, VirusTotal API integration, and automated active response.

- 🔴 Ran SSH and RDP brute force attacks using Hydra. Wazuh detected the threshold breach and automatically blocked the attacker IP through active response
- 🔴 Dropped a test malware file onto the Windows machine. Sysmon Event ID 11 caught the file creation, VirusTotal flagged it as malicious, and remove-threat.sh deleted it within 60 seconds
- 🔴 Microsoft Edge was triggering T1105 alerts as false positives. Wrote a custom local_rules.xml suppression rule to eliminate the noise without reducing detection coverage
- 🔴 Set up ModSecurity WAF in front of DVWA and simulated SQL injection and XSS attacks. Confirmed WAF blocking with rule-level logging on each block
- 📌 MITRE: `T1110` Brute Force · `T1105` Ingress Tool Transfer · `T1059` Command & Scripting Interpreter · `T1190` Exploit Public-Facing Application

---

### 🔐 Wazuh SIEM – Hands-On Lab (Windows & Linux)

Full Wazuh deployment across Windows and Linux with Sysmon integration and VirusTotal API active response pipeline.

- 🔴 Deployed Sysmon on Windows 10 with a custom XML config to capture process creation, network connections, and file drop events
- 🔴 Configured the VirusTotal API active response pipeline in Wazuh. Wrote remove-threat.sh to automatically delete files on a positive malware verdict
- 🔴 Correlated Windows Event IDs 4625, 4624, and 4648 to detect failed logon sequences and flag lateral movement patterns
- 📌 MITRE: `T1078` Valid Accounts · `T1105` Ingress Tool Transfer · `T1059` Command & Scripting Interpreter

---

### 🎣 Phishing Analysis – SOC Simulation Lab

Worked through phishing triage the way it happens in a real SOC: alert intake, header analysis, IOC extraction, tool lookups, verdict, escalation.

- 🔴 Spotted a spoofed sender domain by checking email headers. Reply-To and Return-Path did not match the claimed sender
- 🔴 Pulled the embedded URL, ran it through VirusTotal and urlscan.io, and confirmed it redirected to a credential harvesting page
- 🔴 Checked the sender IP on AbuseIPDB and it came back flagged as a known malicious source
- 🔴 Ran the headers through MXToolbox and confirmed SPF and DKIM both failed, indicating the email was spoofed
- 📌 MITRE: `T1566.001` Spearphishing Attachment · `T1566.002` Spearphishing Link

---

### 📊 Log Analysis & Detection

Raw Windows and Linux log analysis focused on reading event data directly and identifying what is suspicious without relying on SIEM alerts.

- 🔴 Found repeated Event ID 4625 failures followed by a 4740 account lockout and flagged it as a brute force pattern
- 🔴 Went through Linux auth.log manually and identified sudo escalation attempts alongside abnormal SSH login activity
- 🔴 Built a personal IOC extraction workflow: event ID to log field to indicator to classification
- 📌 MITRE: `T1110.001` Password Guessing · `T1078` Valid Accounts

---

### 🔍 Splunk SIEM – Detection Lab

Log analysis in Splunk using SSH, DNS, HTTP, and Cloudflare data to practice writing real detection queries and building dashboards.

- 🔴 Wrote SPL to catch SSH brute force: `index=main sourcetype=linux_secure "Failed password" | stats count by src_ip | where count > 10`
- 🔴 Noticed a source IP sending abnormally high DNS query volume and flagged it as a potential C2 beaconing pattern
- 🔴 Built a dashboard tracking failed authentication events across multiple log sources for ongoing monitoring
- 📌 MITRE: `T1110` Brute Force · `T1071.004` DNS · 
---

### 🧾 Incident Investigation Report

End-to-end incident documentation following a SOC investigation workflow, from first alert to root cause and remediation.

- 🔴 Pulled correlated alerts from SIEM, endpoint logs, and network traffic and reconstructed the attacker timeline
- 🔴 Documented all IOCs including file hashes, IP addresses, and file paths in a structured report
- 🔴 Wrote remediation recommendations following the escalation workflow a real Tier 1 analyst would use
- 📌 MITRE: ATT&CK techniques mapped per finding across Kill Chain stages

---

> 📂 **[View All Projects, Incident Reports & Detection Rules → SOC Home Lab](https://github.com/rohithbaggu56-dot/Home-SOC-Lab-Detection-Log-Analysis)**

---

## 🛠️ Tools & Technologies

### 🔌 SIEM
![Splunk](https://img.shields.io/badge/Splunk-000000?style=for-the-badge&logo=splunk&logoColor=white)
![Elastic](https://img.shields.io/badge/Elastic-005571?style=for-the-badge&logo=elastic&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-005DAC?style=for-the-badge&logo=wazuh&logoColor=white)

### 🌐 Network & Firewall
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![tcpdump](https://img.shields.io/badge/tcpdump-F5A623?style=for-the-badge)
![Nmap](https://img.shields.io/badge/Nmap-0E83CD?style=for-the-badge)
![pfSense](https://img.shields.io/badge/pfSense-212121?style=for-the-badge&logo=pfsense&logoColor=white)
![ModSecurity WAF](https://img.shields.io/badge/ModSecurity_WAF-CC0000?style=for-the-badge)

### 🖥️ Operating Systems
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)

### 🔍 Security & Monitoring
![Windows Event Viewer](https://img.shields.io/badge/Windows_Event_Viewer-2F7DE1?style=for-the-badge)
![Sysmon](https://img.shields.io/badge/Sysmon-E65100?style=for-the-badge)
![Linux Log Analysis](https://img.shields.io/badge/Linux_Log_Analysis-333333?style=for-the-badge)
![Process Monitoring](https://img.shields.io/badge/Process_Monitoring-4CAF50?style=for-the-badge)
![DVWA](https://img.shields.io/badge/DVWA-8B0000?style=for-the-badge)

### 🔎 Threat Intelligence & IOC Tools
![VirusTotal](https://img.shields.io/badge/VirusTotal-394EFF?style=for-the-badge)
![urlscan.io](https://img.shields.io/badge/urlscan.io-FF6600?style=for-the-badge)
![AbuseIPDB](https://img.shields.io/badge/AbuseIPDB-CC0000?style=for-the-badge)
![MXToolbox](https://img.shields.io/badge/MXToolbox-0078D7?style=for-the-badge)

### 🧠 Frameworks
![MITRE ATT&CK](https://img.shields.io/badge/MITRE_ATT%26CK-FF0000?style=for-the-badge)
![Cyber Kill Chain](https://img.shields.io/badge/Cyber_Kill_Chain-1A1A2E?style=for-the-badge)
![Pyramid of Pain](https://img.shields.io/badge/Pyramid_of_Pain-FF6B35?style=for-the-badge)
![NIST CSF](https://img.shields.io/badge/NIST_CSF-00558C?style=for-the-badge)
![OWASP Top 10](https://img.shields.io/badge/OWASP_Top_10-000000?style=for-the-badge&logo=owasp&logoColor=white)

---

## 🧪 Labs & Platforms

- [TryHackMe](https://tryhackme.com/p/rohithbaggu56)
- [LetsDefend](https://app.letsdefend.io/homepage)
- Forage

---

## 🎓 Certifications

![Google Cybersecurity](https://img.shields.io/badge/Google_Cybersecurity_Professional-4285F4?style=for-the-badge&logo=google&logoColor=white)
![Microsoft Cybersecurity Analyst](https://img.shields.io/badge/Microsoft_Cybersecurity_Analyst-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![TryHackMe SOC Level 1](https://img.shields.io/badge/TryHackMe-SOC_Level_1-212C42?style=for-the-badge&logo=tryhackme&logoColor=white)
![IBM Ethical Hacking](https://img.shields.io/badge/IBM_Ethical_Hacking_Open_Source_Tools-054ADA?style=for-the-badge&logo=ibm&logoColor=white)

---

## 🌐 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rohithbaggu)
[![TryHackMe](https://img.shields.io/badge/TryHackMe-212C42?style=for-the-badge&logo=tryhackme&logoColor=white)](https://tryhackme.com/p/rohithbaggu56)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rohithbaggu56@gmail.com)
