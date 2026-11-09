# 🛡️ Network Security & Scanning

\<p align="center">   \<strong>Cybersecurity Internship — Task 2\</strong>\<br>   Network Reconnaissance | Vulnerability Assessment | Traffic Analysis | Firewall Security \</p>

\<p align="center">   \<img src="[https://img.shields.io/badge/Domain-Cybersecurity-0A66C2?style=for-the-badge](https://img.shields.io/badge/Domain-Cybersecurity-0A66C2?style=for-the-badge)" alt="Cybersecurity">   \<img src="[https://img.shields.io/badge/Focus-Network%20Security-198754?style=for-the-badge](https://img.shields.io/badge/Focus-Network%20Security-198754?style=for-the-badge)" alt="Network Security">   \<img src="[https://img.shields.io/badge/Environment-Lab%20Based-6F42C1?style=for-the-badge](https://img.shields.io/badge/Environment-Lab%20Based-6F42C1?style=for-the-badge)" alt="Lab Based">   \<img src="[https://img.shields.io/badge/Documentation-Markdown-black?style=for-the-badge](https://img.shields.io/badge/Documentation-Markdown-black?style=for-the-badge)" alt="Markdown"> \</p>

---

## 📌 Project Overview

This repository documents the practical implementation of **Network Security and Scanning**, completed as part of Task 2 of the Cybersecurity Internship.

The project focuses on understanding network reconnaissance, identifying open ports and running services, performing vulnerability assessments, analyzing network traffic, and configuring firewall rules.

Practical exercises were conducted using a controlled virtual lab environment and Windows-based tools.

The repository contains technical documentation, scan results, vulnerability analysis, packet-analysis observations, configuration details, and practical screenshots.

## 🎯 Project Objectives

- Understand passive and active network reconnaissance techniques.
- Discover reachable hosts and identify exposed network services.
- Perform TCP and UDP port scanning using Nmap.
- Identify service versions and attempt operating system detection.
- Assess vulnerabilities using Nessus Essentials.
- Capture and analyze DNS, HTTP-related, and TCP traffic.
- Understand firewall configuration and port access control.
- Document security findings and recommended remediation measures.

## 🧰 Tools & Technologies

| Tool               | Application                            |
| ------------------ | -------------------------------------- |
| Kali Linux         | Security testing environment           |
| Metasploitable2    | Vulnerable lab target                  |
| Nmap               | Network and port scanning              |
| Nessus Essentials  | Vulnerability assessment               |
| Wireshark          | Packet capture and traffic analysis    |
| iptables           | Linux firewall configuration           |
| WHOIS              | Domain registration lookup             |
| Nslookup           | DNS information gathering              |
| Google Dorking     | Search-engine reconnaissance           |
| Shodan             | Internet-exposed service discovery     |
| Windows PowerShell | Network traffic generation and testing |

---

## 📂 Repository Structure

```text
Network-Security-and-Scanning/
│
├── README.md
│
├── demo/
│   └── Demo-Script.md
│
├── Firewall/
│   ├── iptables-Rules.md
│   └── Port-Scan-Blocking.md
│
├── Nmap-Scanning/
│   ├── Nmap-Scan-Report.md
│   ├── OS-Detection.md
│   ├── Service-Version-Detection.md
│   └── TCP-UDP-Scanning.md
│
├── Reconnaissance/
│   ├── Banner-Grabbing.md
│   ├── Google-Dorking.md
│   ├── Nslookup.md
│   ├── Ping-Sweep.md
│   ├── Shodan.md
│   └── Whois.md
│
├── reports/
│   └── Screenshot-Inventory.csv
│
├── screenshots task 2/
│   └── Practical screenshots
│
├── Vulnerability-Assessment/
│   ├── Vulnerability-Analysis.md
│   └── Vulnerability-Scan-Report.md
│
└── Wireshark-Analysis/
    ├── DNS-Analysis.md
    ├── FTP-Analysis.md
    ├── HTTP-Analysis.md
    └── SYN-Flood-Analysis.md
```

---

## 🔍 Practical Activities

### 1. Network Reconnaissance

**Objective:** Gather information about domains, DNS records, publicly exposed services, and reachable hosts.

| Activity        | Description                                                 |
| --------------- | ----------------------------------------------------------- |
| WHOIS Lookup    | Examined domain registration information.                   |
| DNS Enumeration | Used Nslookup to resolve domain names.                      |
| Google Dorking  | Explored search operators for publicly indexed information. |
| Shodan Search   | Examined publicly discoverable internet-facing services.    |
| Ping Sweep      | Checked host reachability in the lab network.               |
| Banner Grabbing | Identified running services and their versions.             |

**Documentation:** [Explore Reconnaissance](Reconnaissance/)

### 2. Nmap Network Scanning

**Objective:** Identify open ports, discover network services, and examine the target's network exposure.

Target: `192.168.56.102` — Metasploitable2 lab machine.

| Scan Type         | Nmap Option | Purpose                                   |
| ----------------- | ----------- | ----------------------------------------- |
| TCP SYN Scan      | `-sS`       | Identify open TCP ports.                  |
| UDP Scan          | `-sU`       | Identify open or open-filtered UDP ports. |
| Service Detection | `-sV`       | Detect running services and versions.     |
| OS Detection      | `-O`        | Attempt operating system identification.  |

**Key Observations**

- 23 open TCP ports identified.
- 4 open UDP ports identified.
- Multiple services discovered, including FTP, SSH, Telnet, HTTP, Samba, and database services.
- OS detection was attempted but did not produce a definitive operating system match.

**Documentation:** [Explore Nmap Scanning](Nmap-Scanning/)

### 3. Vulnerability Assessment

**Objective:** Identify security weaknesses and evaluate their potential impact using Nessus Essentials.

**Assessment Details**

| Parameter      | Result            |
| -------------- | ----------------- |
| Target         | `192.168.56.102`  |
| Target System  | Metasploitable2   |
| Scanner        | Nessus Essentials |
| Hosts Scanned  | 1                 |
| Total Findings | 68                |
| Authentication | Failed            |

**Severity Summary**

| Severity           | Findings |
| ------------------ | -------: |
| Critical           |        9 |
| High               |        3 |
| Medium             |        6 |
| Low                |        2 |
| Remaining findings |       48 |

The remaining 48 findings have not been individually classified in the collected notes.

**Examples of Identified Vulnerabilities**

- VNC server password weakness.
- Apache Tomcat AJP vulnerability (Ghostcat).
- SSL version 2 and 3 protocol weaknesses.
- Bind shell backdoor detection.
- Samba security vulnerability.
- Unencrypted Telnet service.
- Weak Diffie-Hellman parameters.

**Documentation:**

- [Vulnerability Scan Report](Vulnerability-Assessment/Vulnerability-Scan-Report.md)
- [Vulnerability Analysis](Vulnerability-Assessment/Vulnerability-Analysis.md)

### 4. Wireshark Network Traffic Analysis

**Objective:** Capture and examine network packets to understand communication patterns and TCP behaviour.

**Activities Performed**

| Analysis                | Observation                                                    |
| ----------------------- | -------------------------------------------------------------- |
| DNS Analysis            | Generated and examined DNS query and response traffic.         |
| HTTP Analysis           | Generated HTTP-related traffic and inspected captured packets. |
| TCP SYN Analysis        | Observed TCP SYN packets.                                      |
| SYN-ACK Analysis        | Examined SYN-ACK responses.                                    |
| Retransmission Analysis | Examined TCP retransmission behaviour.                         |

**Important Scope Limitations**

- FTP capture was not completed.
- No plaintext FTP credentials were captured.
- An actual SYN flood was not generated; the work focused on TCP traffic observation and analysis.

**Documentation:** [Explore Wireshark Analysis](Wireshark-Analysis/)

### 5. Firewall Configuration

**Objective:** Understand Linux firewall rules and configure basic TCP port access control using iptables.

**Configured Rules**

```bash
# Allow SSH traffic
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Block Telnet traffic
sudo iptables -A INPUT -p tcp --dport 23 -j DROP
```

**Configuration Summary**

| Port | Service | Action |
| ---- | ------- | ------ |
| 22   | SSH     | ACCEPT |
| 23   | Telnet  | DROP   |

The configured INPUT chain rules were verified using iptables commands. External port-scan blocking was not independently verified.

**Documentation:** [Explore Firewall Configuration](Firewall/)

---

## 📸 Practical Screenshots

Screenshots documenting the practical activities are available in the repository.

[**📂 Browse All Practical Screenshots**](screenshots%20task%202/)

Examples:

| Activity                  | Screenshot                                                              |
| ------------------------- | ----------------------------------------------------------------------- |
| Nmap TCP SYN Scan         | [View Screenshot](screenshots%20task%202/tcp-syn-scan.png)              |
| UDP Scan                  | [View Screenshot](screenshots%20task%202/udp-scan.png)                  |
| Service Version Detection | [View Screenshot](screenshots%20task%202/service-version-detection.png) |
| Nessus Vulnerability Scan | [View Screenshot](screenshots%20task%202/nessus-vulnerability-scan.png) |
| DNS Packet Analysis       | [View Screenshot](screenshots%20task%202/dns-packets.png)               |
| Firewall Rules            | [View Screenshot](screenshots%20task%202/iptables-firewall-rules.png)   |

## 🎥 Demonstration

A demonstration script has been prepared to guide the practical walkthrough.

[**View Demo Script**](demo/Demo-Script.md)

The actual screen recording is pending and will be added after completion.

## 📚 Learning Outcomes

Through this practical task, I gained hands-on experience in:

- Passive and active network reconnaissance.
- Host discovery and network scanning.
- TCP and UDP port analysis.
- Service and version identification.
- Vulnerability assessment and risk interpretation.
- Network packet capture and traffic analysis.
- TCP communication and retransmission behaviour.
- Linux firewall configuration.
- Technical documentation and security reporting.

## ⚠️ Disclaimer

This repository is intended strictly for educational and cybersecurity training purposes.

Active scanning and security testing were performed against an authorized virtual lab environment. Public reconnaissance activities were limited to publicly available information.

The documented findings represent the observations from the practical exercises and do not constitute a production security audit.

---

\<p align="center">
&#x20; \<strong>Network Security & Scanning | Cybersecurity Internship – Task 2\</strong>\<br>
&#x20; Learning • Testing • Analyzing • Documenting
\</p>
