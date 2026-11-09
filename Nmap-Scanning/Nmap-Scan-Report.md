\# Nmap Scanning Report



\## 1. Objective



The objective of this practical was to perform network scanning and analyze the security exposure of an authorized target system using Nmap. The assessment included TCP SYN scanning, UDP scanning, service version detection, and operating system detection.



\## 2. Lab Environment



| Parameter | Details |

|---|---|

| Scanning tool | Nmap 7.95 |

| Attacker machine | Kali Linux |

| Target machine | Metasploitable 2 |

| Target IP address | 192.168.56.102 |

| Network configuration | Isolated Host-Only Network |

| Scanning authorization | Own vulnerable lab VM |



\## 3. TCP SYN Scan



\*\*Command used:\*\*



```bash

sudo nmap -sS 192.168.56.102 -oN \~/tcp-scan-results.txt

```



\*\*Purpose:\*\*



The TCP SYN scan identifies open TCP ports by sending SYN packets and analyzing the target's responses. It is commonly called a half-open scan because it does not complete the full TCP three-way handshake.



\*\*Results:\*\*



\- Target host was up.

\- 23 open TCP ports were identified.

\- 977 TCP ports were reported as filtered.



\*\*Open TCP ports identified:\*\*



| Port | State |

|---|---|

| 21 | Open |

| 22 | Open |

| 23 | Open |

| 25 | Open |

| 53 | Open |

| 80 | Open |

| 111 | Open |

| 139 | Open |

| 445 | Open |

| 512 | Open |

| 513 | Open |

| 514 | Open |

| 1099 | Open |

| 1524 | Open |

| 2049 | Open |

| 2121 | Open |

| 3306 | Open |

| 5432 | Open |

| 5900 | Open |

| 6000 | Open |

| 6667 | Open |

| 8009 | Open |

| 8180 | Open |



\*\*Analysis:\*\*



The scan identified several exposed TCP services, including FTP, SSH, Telnet, HTTP, SMB, MySQL, PostgreSQL, and other services. The large number of filtered ports indicates that Nmap did not receive responses that allowed it to classify those ports as open or closed.



\## 4. UDP Scan



\*\*Command used:\*\*



```bash

sudo nmap -sU 192.168.56.102 -oN \~/udp-scan-results.txt

```



\*\*Purpose:\*\*



UDP scanning identifies services communicating through the User Datagram Protocol. UDP does not establish a connection in the same way as TCP, so some ports may remain classified as open|filtered when no response is received.



\*\*Results:\*\*



\- Target host was up.

\- 4 open UDP ports were identified.

\- 996 UDP ports were classified as open|filtered.



\*\*Open UDP ports identified:\*\*



| Port | Service |

|---|---|

| 53 | DNS |

| 111 | RPCbind |

| 137 | NetBIOS Name Service |

| 2049 | NFS |



\*\*Analysis:\*\*



The scan identified DNS, RPCbind, NetBIOS Name Service, and NFS as open UDP services. The 996 open|filtered results mean Nmap could not determine whether those ports were open or blocked because it did not receive a conclusive response.



\## 5. Service Version Detection



\*\*Command used:\*\*



```bash

sudo nmap -sV 192.168.56.102 -oN \~/service-version-results.txt

```



\*\*Purpose:\*\*



Service version detection identifies the services and, where possible, their software versions running on open ports. This information helps assess outdated services and potential security weaknesses.



\*\*Results:\*\*



| Port | Service | Detected version / information |

|---|---|---|

| 21 | FTP | vsftpd 2.3.4 |

| 22 | SSH | OpenSSH 4.7p1 Debian 8ubuntu1 |

| 23 | Telnet | Linux telnetd |

| 25 | SMTP | Postfix smtpd |

| 53 | DNS | ISC BIND 9.4.2 |

| 80 | HTTP | Apache 2.2.8 Ubuntu DAV/2 |

| 111 | RPCbind | RPCbind |

| 139 | NetBIOS/SMB | Samba smbd 3.X–4.X |

| 445 | SMB | Samba smbd 3.X–4.X |

| 512 | Remote execution | netkit-rsh rexecd |

| 513 | Remote login | rlogind |

| 514 | Remote shell | netkit-rshd |

| 1099 | Java RMI | GNU Classpath grmiregistry |

| 1524 | Bindshell | Metasploitable root shell |

| 2049 | NFS | Network File System |

| 2121 | FTP | ProFTPD 1.3.1 |

| 3306 | MySQL | MySQL 5.0.51a-3ubuntu5 |

| 5432 | PostgreSQL | PostgreSQL 8.3.0–8.3.7 |

| 5900 | VNC | VNC 3.3 |

| 6000 | X11 | Access denied |

| 6667 | IRC | UnrealIRCd |

| 8009 | AJP13 | Apache JServ Protocol |

| 8180 | HTTP | Apache Tomcat/Coyote JSP engine 1.1 |



\*\*Analysis:\*\*



The scan revealed multiple older service versions, including vsftpd 2.3.4, OpenSSH 4.7p1, Apache 2.2.8, MySQL 5.0.51a, and ProFTPD 1.3.1. Older software versions may contain known vulnerabilities and should be investigated further.



The presence of Telnet and remote shell services also highlights the importance of reviewing insecure protocols and unnecessary services.



Service version identification alone does not confirm that a vulnerability is exploitable. Further validation is required during vulnerability assessment.



\## 6. Operating System Detection



\*\*Command used:\*\*



```bash

sudo nmap -O 192.168.56.102 -oN \~/os-detection-results.txt

```



\*\*Purpose:\*\*



OS detection attempts to identify the target operating system by analyzing network responses and TCP/IP characteristics.



\*\*Results:\*\*



\- Target host was up.

\- 23 open TCP ports were detected.

\- 977 TCP ports were filtered.

\- Nmap reported that OS detection might be unreliable because it could not find at least one open and one closed port.

\- No exact operating system match was identified.



\*\*OS guesses reported by Nmap:\*\*



| Possible identification | Nmap confidence |

|---|---:|

| VirtualBox Slirp NAT bridge | 98% |

| AT\&T BGW210 | 95% |

| QEMU | 94% |



\*\*Analysis:\*\*



Nmap generated several possible operating-system or device guesses, but it did not identify the exact operating system. The warning about not finding both an open and a closed port indicates that the scan conditions were not ideal for reliable OS fingerprinting.



Therefore, these guesses must not be treated as confirmed operating-system identification.



\## 7. Overall Findings



| Scan type | Main findings |

|---|---|

| TCP SYN scan | 23 open TCP ports; 977 filtered |

| UDP scan | 4 open UDP ports; 996 open\\|filtered |

| Service version detection | Identified service names and versions across 23 TCP ports |

| OS detection | No exact OS match; results considered unreliable |



\### Important security observations



1\. Multiple network services were exposed on the target system.

2\. Several services were running older software versions that require further vulnerability investigation.

3\. Telnet and remote shell services represent potential security concerns because of their insecure communication characteristics.

4\. Database and file-sharing services such as MySQL, PostgreSQL, SMB, and NFS should be restricted to authorized systems.

5\. The OS detection result was inconclusive and requires more suitable scan conditions for reliable fingerprinting.



\## 8. Conclusion



The Nmap assessment successfully identified open TCP and UDP ports and gathered service version information from the Metasploitable 2 virtual machine.



The results demonstrated how network scanning can help identify exposed services, outdated software, and potential areas of security risk. The OS detection scan produced inconclusive results, showing that scan conditions can affect fingerprinting accuracy.



The findings will be used as a foundation for the next stage of the assessment: vulnerability scanning and severity analysis using Nessus or OpenVAS.



\## 9. Evidence



The following screenshots are associated with the practical:



\- `screenshots/tcp-scan.png` – TCP SYN scan results.

\- `screenshots/udp-scan.png` – UDP scan results.

\- `screenshots/service-version-detection.png` – Service version detection results.

\- `screenshots/os-detection.png` – OS detection results.



\*\*Lab safety:\*\* All active scanning activities were performed against the authorized Metasploitable 2 virtual machine within an isolated Host-Only lab network.

