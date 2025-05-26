### Practical Report: Scanning IP 192.168.83.37 for Open Ports with TCP SYN Scan  
**Date and Time:** Monday, May 26, 2025  
**Author:** Saurabh Soni

#### Objective  
In this practical session, I aimed to identify open ports on the device with IP address 192.168.83.37 using a TCP SYN scan to assess its network exposure. This exercise helps me understand potential vulnerabilities that could be exploited, enhancing my network security skills.

#### Tools Used  
- **Nmap** (free): A network scanning tool to detect open ports and services.  
- **Wireshark** (optional): For capturing and analyzing network packets (not used in this specific scan).  

#### Procedure (Steps Performed)  
I followed these steps during the practical:  
1. **Installed Nmap**: I confirmed Nmap 7.95 was already installed on my system.  
2. **Identified Target IP**: The IP address for scanning was 192.168.83.37, a single host, so no range was needed.  
3. **Performed a TCP SYN Scan**: I ran the following Nmap command in my terminal to perform a stealthy TCP SYN scan:  
   ```bash  
   nmap -sS -oN scan.txt 192.168.83.37  
   ```  
   The `-sS` flag ensured a TCP SYN scan, which is stealthier as it doesn’t complete the TCP handshake. The scan completed quickly with a latency of 0.0018 seconds.  
4. **Recorded Results**: The scan showed port 53 (TCP) was open on 192.168.83.37, running the "domain" service (DNS).  
5. **Analyzed with Wireshark (Optional)**: I didn’t use Wireshark this time, but I could have captured DNS traffic on port 53 for further analysis.  
6. **Researched Services**: I researched port 53, which runs DNS (Domain Name System), a service that translates domain names to IP addresses.  
7. **Identified Security Risks**: An open DNS port (53) might be vulnerable to attacks like DNS amplification or cache poisoning if misconfigured or unpatched.  
8. **Saved Scan Results**: The results were saved to `scan.txt` using the `-oN` flag in the Nmap command.  

#### Results  
The scan revealed the following about 192.168.83.37:  
- **IP Address**: 192.168.83.37  
- **Open Port**: Port 53 (TCP) running the "domain" service (DNS).  
- **Other Ports**: 999 TCP ports were closed (connection refused).  
The host responded with a latency of 0.0018 seconds, indicating it was active and likely on the same network.  

#### Observations and Learning Outcomes  
- Using the `-sS` flag for a TCP SYN scan made the scan stealthier, as it avoids completing the TCP connection, which I confirmed by the scan’s behavior.  
- I learned that port 53 being open indicates a DNS server, which is essential but can be a target for attacks if not secured properly.  
- This practical highlighted the importance of choosing the right scan type for the task, as SYN scans are less likely to be logged by the target.  

#### Key Concepts Applied  
- **Port Scanning**: I used Nmap to identify open ports on the target IP.  
- **TCP SYN Scan**: The `-sS` flag performed a stealth scan by sending SYN packets without completing the handshake.  
- **IP Address**: I scanned a single IP (192.168.83.37), making the process focused and quick.  
- **Network Reconnaissance**: This simulated how attackers might gather information about a device.  
- **Open Ports**: Port 53 being open shows a listening DNS service, which could be an entry point if not secured.  
- **Network Security Basics**: I understood the need to secure DNS services to prevent attacks like amplification.  

#### Challenges Faced  
- I briefly wondered if the `-sS` flag would change the results compared to a default scan, but the output matched expectations since the default scan in the previous run was also a SYN scan for TCP ports.  
- The scan ran smoothly with no technical issues, as the host was responsive.  

#### Interview Questions and Reflections  
While performing the scan, I thought about related interview questions:  
1. **What is an open port?**  
   An open port, like port 53 on 192.168.83.37, is a port listening for connections, running a service (DNS here).
   
2. **How does Nmap perform a TCP SYN scan?**  
   Nmap sends a SYN packet, gets a SYN-ACK if the port is open, and sends a RST to close the connection. I used this with the `-sS` flag.
   
3. **What risks are associated with open ports?**  
   Port 53 could be exploited for DNS attacks, like amplification, if the server isn’t configured to restrict recursive queries.
   
4. **Explain the difference between TCP and UDP scanning.**  
   TCP scanning (like my SYN scan) checks connection-oriented services, while UDP scanning checks connectionless ones. DNS on port 53 often uses both, so a UDP scan might reveal more.
   
5. **How can open ports be secured?**  
   For port 53, I could restrict DNS queries to trusted clients, keep the server patched, and use a firewall.
   
6. **What is a firewall’s role regarding ports?**  
   A firewall could limit access to port 53, allowing only specific IPs to query the DNS server.
   
7. **What is a port scan, and why do attackers perform it?**  
   A port scan identifies open ports to find vulnerabilities. My scan on 192.168.83.37 showed how attackers might find a DNS server.
   
8. **How does Wireshark complement port scanning?**  
   If used, Wireshark could capture DNS queries on port 53, helping me spot unusual activity like unauthorized requests.  

#### Conclusion  
This practical allowed me to scan IP 192.168.83.37 for open ports using Nmap with a TCP SYN scan (`-sS`). I identified port 53 (DNS) as open, which taught me the importance of securing network services to prevent potential attacks. The results were saved in `scan.txt` for reference. I plan to further explore DNS security measures and possibly use Wireshark to analyze DNS traffic in future scans. This exercise strengthened my understanding of network reconnaissance and security.  

