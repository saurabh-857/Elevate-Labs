### Task 5: Packet Capture Report Using Wireshark

#### Objective
The task was to capture live network packets, identify basic protocols and traffic types using Wireshark, and document the findings. The deliverables include a packet capture (capture.pcapng) file and this report summarizing the protocols identified.

#### Tools Used
- **Wireshark (free)**: Used for capturing and analyzing network traffic.

#### Steps Followed
1. Installed Wireshark on the system.
2. Started capturing packets on the active network interface.
3. Generated traffic by browsing a website and pinging a server.
4. Stopped the capture after approximately one minute.
5. Filtered packets by protocol (e.g., HTTP, DNS, TCP).
6. Identified at least 5 different protocols in the capture.
7. Exported the capture as a capture.pcapng file.
8. Summarized the findings and packet details in this report.

#### Findings
The packet capture revealed a variety of network traffic, with the following protocols identified:

1. **ICMP (Internet Control Message Protocol)**: Observed in packets 1–8, used for ping requests and replies (e.g., `Echo (ping) request id=0x0800, seq=1/256`).
2. **ARP (Address Resolution Protocol)**: Seen in packets 9–12 and 34-35, used for mapping IP addresses to MAC addresses (e.g., `Who has 192.168.242.123? Tell 192.168.242.38`).
3. **TCP (Transmission Control Protocol)**: Found in packets 13–19 and 24–33, used for reliable data transfer, including HTTP traffic (e.g., `57982 → http(80) [SYN] Seq=0 Win=64240 Len=0 MSS=1460`).
4. **DNS (Domain Name System)**: Identified in packets 20–23, used for domain name resolution (e.g., `Standard query 0xA5C5 AAAA google.com`).
5. **HTTP (Hypertext Transfer Protocol)**: Observed in packets 27 and 29, used for web browsing (e.g., `GET / HTTP/1.1`).

#### Packet Details
- **Total Packets Captured**: 35 packets (as shown in the capturecapture.pcapng).
- **Time Span**: The capture lasts approximately 36 seconds.
- **Source/Destination IPs**:
  - Primary local IP: `192.168.242.123` (my device).
  - Common destination IPs: `142.251.43.110` (Google), `192.168.242.38` (local network).
- **Traffic Types**:
  - Ping traffic (ICMP): Packets 1–8, showing successful ping requests and replies.
  - Web browsing (HTTP/TCP): Packets 13–19 and 24–33, showing TCP handshake and HTTP GET requests to `google.com`.
  - DNS queries (DNS): Packets 20–23, resolving `google.com` to IP addresses.
  - ARP requests/replies: Packets 9–12 and 34-35, facilitating local network communication.

#### Summary
The packet capture successfully captured diverse network traffic, including ICMP, ARP, TCP, DNS, and HTTP protocols. The traffic primarily consisted of ping requests, DNS queries for domain resolution, and HTTP requests for web browsing. The capture was exported as a capture.pcapng file for further analysis if needed. This exercise enhanced hands-on packet analysis skills and protocol awareness.

#### Outcome
Achieved hands-on experience in packet analysis and gained a deeper understanding of network protocols and their roles in communication.

