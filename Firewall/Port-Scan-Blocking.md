\# Port Scan Blocking Using iptables



\## 1. Objective



To understand how Linux firewall rules can filter incoming network traffic and reduce exposure to unwanted connection attempts and port scanning.



\## 2. Tools Used



\- Kali Linux

\- iptables

\- Nmap

\- VirtualBox



\## 3. Firewall Configuration



The incoming firewall rules were configured using iptables.



\*\*Allow SSH traffic:\*\*



```bash

sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

```



\*\*Block Telnet traffic:\*\*



```bash

sudo iptables -A INPUT -p tcp --dport 23 -j DROP

```



The ACCEPT rule permits incoming SSH connections, while the DROP rule silently discards incoming TCP traffic destined for port 23.



\## 4. Verification of Firewall Rules



The configured rules were inspected using:



```bash

sudo iptables -L INPUT -n -v

```



The output confirmed the presence of:

\- TCP port 22 — ACCEPT

\- TCP port 23 — DROP



\## 5. Port Scan Blocking Concept



Port scanning is a technique used to identify open, closed, and filtered network ports.



A firewall can help defend against unwanted connection attempts by:

\- Blocking traffic to unnecessary ports.

\- Restricting access to permitted services.

\- Filtering incoming packets based on protocol and port.

\- Reducing the network services exposed to untrusted systems.



Nmap can be used from another machine to examine how a target responds to filtered connection attempts.



\## 6. Testing Limitation



An external Nmap verification scan was not completed because the Kali and Metasploitable2 virtual machines initially used different network configurations.



Therefore, the practical verified the firewall rules locally but did not demonstrate a successful external port-scan blocking test.



\## 7. Conclusion



This exercise provided practical knowledge of Linux firewall configuration using iptables. SSH traffic was permitted, while Telnet traffic was blocked. It demonstrated how firewall filtering rules can reduce unnecessary network exposure and improve host security.

