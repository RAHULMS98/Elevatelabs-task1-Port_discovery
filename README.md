# 🕵️‍♂️ Task 1: Scan Your Local Network for Open Ports

## 🎯 Objective
To perform basic network reconnaissance on a local network and identify open ports on connected devices.  
This task helps understand network service exposure and potential security risks.

---

## 🧰 Tools Used
- **Nmap** – Primary tool for port scanning and OS detection.  
- **arp-scan** – Used for host discovery to find live devices in the subnet.  
- **ping** – Command-line tool to test basic connectivity.  
- **Wireshark** – Optional packet analyzer used to observe network traffic during the scan.

---

## 💻 Task Steps & Process

1. **Identify Local IP and Subnet**  
   Used the `ifconfig` command to find the local IP (`192.168.196.128`) and subnet (`192.168.196.131`).

2. **Discover Active Hosts**  
   Ran `arp-scan` to identify live hosts on the network, including multiple VMware virtual machines.

3. **Perform Nmap Scans**  
   Executed TCP SYN scans to detect open ports and running services:  
   ```bash
   sudo nmap -sS 192.168.196.131
