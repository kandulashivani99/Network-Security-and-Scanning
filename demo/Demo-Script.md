\# Task 2 – Network Security and Scanning

\## 5-Minute Project Demonstration Script



\### 1. Introduction (0:00–0:30)



Hello everyone. This is my demonstration for Task 2 of the Cybersecurity Internship, focused on Network Security and Scanning.



The objective of this task was to understand network reconnaissance, identify open ports and running services, perform vulnerability assessment, analyze network traffic using Wireshark, and explore firewall configurations.



My practical work was conducted using authorized lab environments and publicly available information.



\### 2. Reconnaissance (0:30–1:10)



First, I performed reconnaissance activities.



I used WHOIS to obtain domain registration information and Nslookup to identify DNS records and resolve domain names.



I also explored Google Dorking to understand how search operators can locate publicly indexed information, and Shodan to examine internet-facing services.



For active reconnaissance, I performed a ping sweep to identify reachable hosts in the lab network and banner grabbing to identify services and their versions.



\### 3. Nmap Scanning (1:10–2:00)



Next, I used Nmap to perform network scanning against my Metasploitable2 lab machine.



I performed:

\- TCP SYN scanning using `-sS`.

\- UDP scanning using `-sU`.

\- Service and version detection using `-sV`.

\- Operating system detection using `-O`.



The TCP scan identified 23 open ports, while the UDP scan identified four open UDP ports.



Service detection revealed several services, including FTP, SSH, Telnet, Apache, Samba, and MySQL.



The operating system detection attempt did not produce a definitive OS match, so I recorded that result as inconclusive.



\### 4. Vulnerability Assessment (2:00–3:00)



I used Nessus Essentials to conduct a vulnerability assessment against the Metasploitable2 machine.



The scan identified 68 vulnerability findings.



The results included critical, high, medium, and low severity findings.



Examples included:

\- VNC server using a weak password.

\- Apache Tomcat AJP vulnerability.

\- SSL/TLS protocol weaknesses.

\- Bind shell backdoor detection.

\- Telnet and rlogin security weaknesses.



I reviewed the findings and documented their potential impact and recommended remediation measures in my vulnerability assessment report.



\### 5. Wireshark Traffic Analysis (3:00–4:00)



I used Wireshark on Windows to observe and analyze network traffic.



I generated DNS traffic using Nslookup and examined DNS packets.



I also generated HTTP-related traffic and inspected the captured packets.



For TCP analysis, I examined SYN packets, SYN-ACK responses, and retransmissions using Wireshark display filters.



I documented the observations in separate traffic analysis reports.



Note: FTP credential capture and an actual SYN flood simulation were not completed. The SYN-related activity was limited to observing and analyzing TCP traffic.



\### 6. Firewall Configuration (4:00–4:40)



Finally, I explored firewall configuration using iptables in the Linux lab environment.



I inspected the existing INPUT chain and configured rules to allow TCP port 22 and block TCP port 23.



The firewall rules were verified using iptables commands.



External port-scan blocking was not independently verified, so I have documented this limitation in the project.



\### 7. Conclusion (4:40–5:00)



Through this task, I gained practical experience with reconnaissance, network scanning, vulnerability assessment, packet analysis, and firewall rule configuration.



I have organized the practical documentation, scan reports, analysis files, and screenshots in a GitHub project repository.



Thank you.

