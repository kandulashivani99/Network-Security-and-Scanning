\# Nmap TCP and UDP Scanning



\## Objective

To identify open TCP and UDP ports on the authorized Metasploitable 2 test machine.



\## Target

\- IP Address: `192.168.56.102`

\- Tool: Nmap 7.95



\## TCP SYN Scan



\### Command

```bash

sudo nmap -sS 192.168.56.102 -oN \~/tcp-scan-results.txt

```



\### Results

\- Host status: Up

\- Open TCP ports: 23

\- Filtered TCP ports: 977



\### Important Open Ports

21 (FTP), 22 (SSH), 23 (Telnet), 25 (SMTP), 53 (DNS), 80 (HTTP), 139 (SMB), 445 (SMB), 3306 (MySQL), 5432 (PostgreSQL), 5900 (VNC), 6667 (IRC), and 8180 (HTTP).



\## UDP Scan



\### Command

```bash

sudo nmap -sU 192.168.56.102 -oN \~/udp-scan-results.txt

```



\### Results

\- Host status: Up

\- Open UDP ports: 4

\- Open|filtered UDP ports: 996



\### Open UDP Ports

\- 53 – DNS

\- 111 – RPCbind

\- 137 – NetBIOS Name Service

\- 2049 – NFS



\## TCP vs UDP Comparison



| TCP Scan                              | UDP Scan |

| Uses connection-oriented TCP          | Uses connectionless UDP |

| Used SYN scan (`-sS`)                 | Used UDP scan (`-sU`) |

| 23 open ports                         | 4 open ports |

| Faster response in this test          | Many ports returned no response |



\## Conclusion

Nmap successfully identified open TCP and UDP ports on the Metasploitable 2 machine. The results reveal several exposed services that can be investigated further during vulnerability assessment.



\## Lab Safety

All scans were conducted against the authorized, isolated Metasploitable 2 virtual machine.

