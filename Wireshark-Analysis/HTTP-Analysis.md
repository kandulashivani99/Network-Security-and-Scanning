# HTTP Traffic Analysis Using Wireshark

## 1. Objective

To generate web-related network traffic and examine the captured packets using Wireshark.

## 2. Tools Used

- Wireshark
- Windows PowerShell
- curl

## 3. Practical Procedure

1. Opened Wireshark on the Windows system.
2. Selected the active network interface and started packet capture.
3. Used PowerShell to generate web requests using the `curl` command.
4. Observed the generated network traffic in Wireshark.
5. Examined the captured packets and their communication details.
6. Reviewed the available packet information to understand web-related network communication.

## 4. Wireshark Analysis

The captured traffic was examined to understand the communication between the local system and the remote web server.

The analysis focused on:

- Source and destination IP addresses.
- Source and destination ports.
- TCP communication.
- Web-related request and response traffic.
- Protocol information visible in the captured packets.

For HTTP traffic, Wireshark can use the following display filter:

```text
http
```

For HTTPS/TLS traffic, the following filter can be used:

```text
tls
```

HTTPS encrypts application data, so the actual HTTP request and response content generally cannot be read directly from an ordinary packet capture.

## 5. Observations

Web-related traffic was generated from Windows PowerShell and examined in Wireshark.

The packet capture provided an opportunity to study network communication, including TCP connections and the protocol information available in the captured packets.

The visibility of application-layer details depends on whether the captured communication uses HTTP or encrypted HTTPS.

## 6. Result

Web-related traffic was generated and examined using Wireshark. The practical demonstrated how packet analysis can help understand communication between a client and a web server.

## 7. Conclusion

This experiment provided practical exposure to network traffic analysis using Wireshark. It helped demonstrate the importance of understanding TCP communication and the differences between unencrypted HTTP and encrypted HTTPS traffic.

## 8. Evidence

![HTTP Packet Capture](../screenshots%20task%202/http-packets.png)

*Figure 1: Web-related packets observed in Wireshark.*

![HTTP Traffic Generation](../screenshots%20task%202/http-traffic-generation.png)

*Figure 2: Web traffic generation using Windows PowerShell.*
