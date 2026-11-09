\# SYN Flood Simulation and TCP Traffic Analysis



\## 1. Objective

To understand TCP SYN flooding, examine TCP connection establishment, and identify network traffic patterns that may indicate a SYN flood attack using Wireshark on Windows.



\## 2. Tools Used

\- Windows 11

\- Wireshark

\- PowerShell

\- Test-NetConnection



\## 3. Methodology

1\. Started packet capture on the Windows Wi-Fi interface.

2\. Generated normal TCP traffic using PowerShell.

3\. Applied Wireshark display filters to identify SYN and SYN-ACK packets.

4\. Examined TCP retransmissions and connection behavior.

5\. Reviewed TCP conversations to understand packet distribution.



\## 4. Wireshark Display Filters



\*\*Initial SYN packets\*\*

```text

tcp.flags.syn == 1 \&\& tcp.flags.ack == 0

```



\*\*SYN-ACK responses\*\*

```text

tcp.flags.syn == 1 \&\& tcp.flags.ack == 1

```



\*\*TCP retransmissions\*\*

```text

tcp.analysis.retransmission

```



\## 5. TCP Three-Way Handshake

\- SYN: Client initiates a connection.

\- SYN-ACK: Server acknowledges the request.

\- ACK: Client completes the handshake.



\## 6. SYN Flood Concept

A SYN flood is a denial-of-service technique in which an attacker sends numerous TCP SYN requests without completing the TCP three-way handshake. This can exhaust server resources and affect legitimate connections.



\## 7. Observation

TCP SYN packets were observed during normal network communication. SYN-ACK responses and TCP retransmissions were examined using Wireshark.



The captured traffic represents normal TCP traffic analysis. A SYN flood attack was not confirmed or generated during this practical.



\## 8. Conclusion

This practical helped understand TCP connection establishment, SYN packet behavior, retransmissions, and the characteristics associated with SYN flood attacks. Wireshark provides useful packet-level visibility for investigating suspicious TCP traffic.



\## 9. Defensive Measures

\- Enable SYN cookies.

\- Configure connection rate limiting.

\- Monitor unusual SYN traffic.

\- Use firewalls and intrusion detection systems.

\- Maintain network monitoring and logging.

