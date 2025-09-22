
                                                 Task 1: Scan Your Local Network for Open Ports
The objective was to perform basic network reconnaissance on a local network to identify open ports on devices. This task helped in understanding network service exposure and associated security risks.

🛠️ Tools Used
Nmap: The primary tool used for port scanning and OS detection.

arp-scan: Used for initial host discovery to find live devices on the local network.

ping: A basic command-line utility used to test network connectivity.

Wireshark: An optional packet analyzer used to observe network traffic during the scan.

💻 Task Steps & Process
The following steps were performed to complete the task:

Identified Local IP and Subnet: I first used the ifconfig command to determine my local IP address (192.168.196.128) and network subnet (192.168.196.131).

Discovered Active Hosts: Using arp-scan, I identified active hosts on the network, which included several VMware virtual machines.

Performed Nmap Scans: I ran Nmap scans targeting the identified hosts (192.168.196.1, 192.168.196.2, etc.) to perform a TCP SYN scan and detect open ports. The commands used were similar to:

Bash

sudo nmap -sS 192.168.196.131
Documented Findings: I noted down the open ports found on each host and saved the scan results to text files (os_report.txt, os_report2.txt).

Analyzed Packet Capture: I used Wireshark to observe the packets being sent during the scans, which helped visualize how Nmap interacts with the network.

📝 Key Findings & Analysis
The Nmap scans revealed the following open ports on different hosts within the network:

Host 192.168.196.2: Found open port 53/tcp. This port is used by the Domain Name System (DNS).

Host 192.168.196.1: Found open ports 135/tcp and 445/tcp. These are associated with Microsoft Remote Procedure Call (MSRPC) and the Server Message Block (SMB) protocol, respectively.

🛡️ Security Risks Identified
The presence of these open ports poses several potential security risks:

Open Port 53 (DNS): This port can be exploited for DNS tunneling, where attackers hide malicious data inside DNS traffic to bypass security controls. It can also be abused in DDoS amplification attacks.

Open Ports 135 (MSRPC) & 445 (SMB): These ports are known for being exploited by malware and ransomware, such as WannaCry, to spread across a network. They can be used for lateral movement and remote code execution by attackers.

This task provided hands-on experience with fundamental network reconnaissance tools and highlighted the importance of securing open ports to protect against common cyber threats.
