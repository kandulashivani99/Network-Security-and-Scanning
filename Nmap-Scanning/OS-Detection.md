\# Nmap Operating System Detection



\## Objective

To identify the operating system of the authorized Metasploitable 2 test machine using Nmap OS fingerprinting.



\## Target Details

\- Target IP: `192.168.56.102`

\- Tool: Nmap 7.95



\## Command Used

```bash

sudo nmap -O 192.168.56.102 -oN \~/os-detection-results.txt

```



\## Results

\- Host status: Up

\- Open TCP ports: 23

\- Filtered TCP ports: 977

\- Exact operating system match: Not identified

\- OS detection reliability: Unreliable



\## Observations

\- Nmap attempted to identify the target using OS fingerprinting.

\- The scan did not find at least one open and one closed TCP port.

\- Nmap returned possible guesses involving VirtualBox, Slirp and QEMU.

\- These guesses were not confirmed operating system identifications.



\## Limitations

OS detection was inconclusive because the target did not provide the port-state conditions required for reliable fingerprinting.



\## Conclusion

Nmap OS detection was performed successfully, but an exact operating system could not be confirmed. The results demonstrate that OS fingerprinting depends on suitable network responses and scan conditions.



\## Lab Safety

The scan was conducted against the authorized Metasploitable 2 virtual machine in an isolated lab environment.

