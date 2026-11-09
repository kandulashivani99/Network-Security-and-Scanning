\# Firewall Configuration Using iptables



\## 1. Objective

To configure basic firewall rules using iptables in Kali Linux and understand how incoming network traffic can be allowed or blocked based on TCP port numbers.



\## 2. Environment

\- Operating System: Kali Linux

\- Firewall Utility: iptables

\- SSH Port: TCP 22

\- Telnet Port: TCP 23



\## 3. Initial Firewall Inspection



The existing INPUT chain was inspected using:



```bash

sudo iptables -L INPUT -n -v

sudo iptables -S INPUT

```



The initial INPUT policy was ACCEPT, and no custom INPUT rules were configured.



\## 4. Firewall Rule Configuration



\*\*Allow SSH traffic:\*\*



```bash

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

```



\*\*Block Telnet traffic:\*\*



```bash

sudo iptables -A INPUT -p tcp --dport 23 -j DROP

```



These rules allow incoming SSH connections and silently drop incoming Telnet connections.



\## 5. Verification



The configured rules were verified using:



```bash

sudo iptables -L INPUT -n -v

```



The output displayed:



| Protocol | Destination port | Action |

|---|---:|---|

| TCP | 22 | ACCEPT |

| TCP | 23 | DROP |



The SSH service was also checked using:



```bash

sudo systemctl status ssh

```



It was confirmed to be active and listening on TCP port 22.



\## 6. Security Analysis



\- SSH provides encrypted remote communication and is preferred over Telnet.

\- Telnet transmits credentials and data without encryption.

\- Blocking Telnet reduces the risk of credential exposure through plaintext network traffic.

\- Explicit firewall rules help control incoming network connections.



\## 7. Limitations



External Nmap verification of the firewall rules was not completed because Kali was using VirtualBox NAT networking while the Metasploitable2 machine was on a separate host-only network.



The Telnet rule was configured, but an external connection test was not performed.



\## 8. Conclusion



The practical demonstrated basic Linux firewall configuration using iptables. An incoming SSH allow rule and Telnet block rule were added and verified. This exercise provided practical understanding of port-based traffic filtering and the importance of encrypted remote access.

