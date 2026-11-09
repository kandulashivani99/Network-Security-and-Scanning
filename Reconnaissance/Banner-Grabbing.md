\# Banner Grabbing – Active Reconnaissance



\## Objective

To identify running services, service versions, and banner information on the authorized Metasploitable 2 test machine.



\## Target

\- IP Address: `192.168.56.102`

\- Operating System: Linux (identified by Nmap)



\## Tool

Nmap 7.95



\## Command Used

```bash

sudo nmap -sV --script=banner 192.168.56.102

```



\## Key Findings



| Port | Service | Version |

|---|---|---|

| 21 | FTP | vsftpd 2.3.4 |

| 22 | SSH | OpenSSH 4.7p1 |

| 23 | Telnet | Linux telnetd |

| 25 | SMTP | Postfix smtpd |

| 53 | DNS | BIND 9.4.2 |

| 80 | HTTP | Apache 2.2.8 |

| 139/445 | SMB | Samba 3.X–4.X |

| 3306 | MySQL | 5.0.51a |

| 5432 | PostgreSQL | 8.3.0–8.3.7 |

| 5900 | VNC | Protocol 3.3 |

| 6667 | IRC | UnrealIRCd |

| 8180 | HTTP | Apache Tomcat |



\## Observations

\- Nmap identified multiple open TCP ports.

\- Service detection revealed software names and version information.

\- Banner information provided additional details about the running services.

\- Port 1524 exposed a service identified as a Metasploitable root shell. This is a serious security risk in the intentionally vulnerable test machine.

\- Several detected services use old software versions and require further security assessment.



\## Conclusion

Banner grabbing successfully identified running services and their versions on Metasploitable 2. The findings provide useful information for subsequent vulnerability assessment.



\## Lab Safety

All scanning was performed against the authorized, isolated Metasploitable 2 lab machine.

