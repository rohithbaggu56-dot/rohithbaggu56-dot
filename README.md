# 👋 Hi, I'm Rohith Baggu

I'm a **SOC Analyst (L1)** building real-world detection and incident response skills through hands-on home labs — running live attack simulations, SIEM configuration, malware detection pipelines, and documented investigations across Windows and Linux environments.

> 🔍 Actively seeking SOC Analyst (L1) / Security Analyst roles in India.

---

## 🎯 Objective

To join a SOC team as a Tier 1 Analyst and apply hands-on experience in alert triage, log analysis, threat detection, and incident documentation — contributing to a stronger defensive security posture from day one.

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

> All projects include real attack simulations, documented findings, IOCs, and MITRE ATT&CK mappings.

---

### 🏠 SOC Home Lab — Full Detection & Response Environment

My primary lab — a multi-VM environment (Windows 10, Ubuntu, Kali Linux) running Wazuh SIEM with Sysmon, VirusTotal API integration, and active response automation.

- 🔴 Simulated SSH & RDP brute force using Hydra — Wazuh active response auto-blocked attacker IP after threshold breach
- 🔴 Detected malicious file drop via Sysmon Event ID 11 — VirusTotal API returned positive verdict — `remove-threat.sh` auto-deleted file within 60 seconds
- 🔴 Tuned false positive suppression for Microsoft Edge (T1105) using custom `local_rules.xml` — improved alert fidelity without losing detection coverage
- 🔴 Deployed ModSecurity WAF with DVWA — simulated SQLi and XSS attacks, confirmed WAF blocking with rule-level logging
- 📌 MITRE: `T1110` Brute Force · `T1105` Ingress Tool Transfer · `T1059` Command & Scripting Interpreter · `T1190` Exploit Public-Facing Application

---

### 🔐 Wazuh SIEM — Hands-On SOC Lab (Windows & Linux)

End-to-end Wazuh deployment across Windows and Linux endpoints with Sysmon integration and custom detection rules.

- 🔴 Configured Sysmon on Windows 10 with custom XML ruleset — detected process creation, network connections, and file drops
- 🔴 Built custom Wazuh rules (IDs 554, 87105, 657, 553) for VirusTotal API active response pipeline
- 🔴 Correlated Windows Event IDs 4625, 4624, 4648 to identify failed logon patterns and lateral movement indicators
- 📌 MITRE: `T1078` Valid Accounts · `T1003` Credential Dumping · `T1105` Ingress Tool Transfer

---

### 🎣 Phishing Analysis — SOC Simulation Lab

SOC-style phishing triage workflow using simulated email samples — from initial alert to escalation decision.

- 🔴 Identified spoofed sender domain via header analysis — detected mismatched Reply-To and Return-Path fields
- 🔴 Extracted malicious URL — confirmed via VirusTotal and urlscan.io — redirected to credential harvesting page
- 🔴 Checked sender IP reputation via AbuseIPDB — flagged as known malicious source
- 🔴 Analyzed email headers using MXToolbox — confirmed SPF/DKIM failure indicating spoofed origin
- 📌 MITRE: `T1566.001` Spearphishing Attachment · `T1566.002` Spearphishing Link

---

### 📊 Log Analysis & Detection

Structured analysis of Windows and Linux logs focused on identifying suspicious activity from raw log data.

- 🔴 Identified failed logon patterns across Windows Event IDs 4625, 4740 — flagged account lockout as brute force indicator
- 🔴 Analyzed Linux `auth.log` for sudo escalation attempts and SSH login anomalies
- 🔴 Documented IOC extraction workflow: event ID → log field → indicator → classification
- 📌 MITRE: `T1110.001` Password Guessing · `T1078` Valid Accounts

---

### 🔍 Splunk SIEM — Detection Lab

Hands-on Splunk log analysis using SSH, DNS, HTTP, and Cloudflare logs to simulate SOC detection workflows.

- 🔴 Wrote SPL queries to detect SSH brute force: `index=main sourcetype=linux_secure "Failed password" | stats count by src_ip | where count > 10`
- 🔴 Identified high-frequency DNS queries — flagged as potential C2 beaconing pattern
- 🔴 Built Splunk dashboard for failed authentication monitoring across multiple log sources
- 📌 MITRE: `T1110` Brute Force · `T1071.004` DNS · `T1046` Network Service Scanning

---

### 🧾 Incident Investigation Report

SOC-style incident report documenting full investigation lifecycle — from alert intake to root cause and remediation.

- 🔴 Correlated alerts across SIEM, endpoint logs, and network traffic to reconstruct attacker timeline
- 🔴 Identified root cause, documented IOCs with hash values, IPs, and file paths
- 🔴 Produced remediation recommendations following SOC escalation workflow
- 📌 MITRE: ATT&CK techniques mapped per finding across all Kill Chain stages

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

- [TryHackMe](https://tryhackme.com/p/rohithbaggu56) — SOC Level 1, phishing analysis, log analysis, alert triage
- [LetsDefend](https://app.letsdefend.io/homepage) — Live SOC alerts: SQL injection, RDP brute force, malicious PowerShell, CVE exploitation, unauthorized VPN access
- [Forage](https://www.theforage.com) — Completed 7 cybersecurity job simulations including Commonwealth Bank SOC investigation

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
