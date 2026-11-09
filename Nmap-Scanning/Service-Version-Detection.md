\# Nmap Service Version Detection



\## Objective

To identify the services and software versions running on open ports of the authorized Metasploitable 2 test machine.



\## Target Details

\- Target IP: `192.168.56.102`

\- Tool: Nmap 7.95



\## Command Used

```bash

sudo nmap -sV 192.168.56.102 -oN \~/service-version-results.txt

```



\## Scan Results



| Port | Service | Version |

|---|---|---|

| 21 | FTP | vsftpd 2.3.4 |

| 22 | SSH | OpenSSH 4.7p1 |

| 23 | Telnet | Linux telnetd |

| 25 | SMTP | Postfix smtpd |

| 53 | DNS | ISC BIND 9.4.2 |

| 80 | HTTP | Apache 2.2.8 |

| 139/445 | SMB | Samba 3.X–4.X |

| 1099 | Java RMI | GNU Classpath grmiregistry |

| 1524 | Bind shell | Metasploitable root shell |

| 2121 | FTP | ProFTPD 1.3.1 |

| 3306 | MySQL | MySQL 5.0.51a |

| 5432 | PostgreSQL | PostgreSQL 8.3.0–8.3.7 |

| 5900 | VNC | Protocol 3.3 |

| 6667 | IRC | UnrealIRCd |

| 8009 | AJP13 | Apache Jserv |

| 8180 | HTTP | Apache Tomcat/Coyote JSP engine 1.1 |



\## Observations

\- Nmap detected 23 open TCP ports.

\- Multiple services were identified with their software versions.

\- Several services use older software versions and should be investigated for known security weaknesses.

\- Port 1524 was identified as a Metasploitable root shell.

\- Nmap identified the host as a Unix/Linux system.



\## Conclusion

Service version detection successfully identified the software and versions associated with open ports. This information helps security analysts identify potentially outdated services and plan further vulnerability assessments.



\## Lab Safety

Scanning was performed against the authorized Metasploitable 2 virtual machine in an isolated lab environment.

