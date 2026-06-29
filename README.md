# elevate_lab_task1
# Task 1: Local Network Reconnaissance & Traffic Analysis

## Objective
To discover active devices and open ports on a local network and analyze the resulting network traffic to understand service exposure and communication patterns.

## Tools Used
- **Nmap:** Used for network scanning and service/OS detection.
- **Wireshark:** Used for packet analysis and observing network traffic.

## Methodology
1. **Network Discovery:** Performed a TCP SYN scan using `nmap -sS 10.91.167.0/24` to identify active hosts.
2. **Detailed Reconnaissance:** Performed version detection and OS fingerprinting using `nmap -sV -O 10.91.167.0/24` on the identified target.
3. **Traffic Analysis:** Captured network traffic using Wireshark, filtering by the target IP range to observe communication protocols (DNS/DHCP).

## Key Findings
### Nmap Scan Results
- **Target Host:** `10.91.167.194`
- **Open Port:** 80/tcp (Service: `http`, Apache httpd 2.4.65 on Debian).
- **OS Fingerprint:** Linux (Kernel 2.6.32, 5.0 - 6.2).
- **Network Status:** Confirmed as a general-purpose Linux device.

### Wireshark Traffic Analysis
- Observed standard DNS queries (`push.services.mozilla.com`) and DHCP requests originating from the target host (`10.91.167.194`).
- Confirmed the use of UDP protocol for DNS traffic (Port 53).

## Evidence
- **Scan Results:** See `network_report.txt` for full command output.
- **Screenshots:**
  - `screenshot.png`: Nmap discovery and fingerprinting results.
  - `screenshot.png`: Packet capture showing DNS and DHCP traffic.

## Conclusion
This task demonstrated how network reconnaissance (Nmap) identifies active services, while packet analysis (Wireshark) provides visibility into the actual data exchange between devices. Understanding these patterns is essential for identifying potential security vulnerabilities and unauthorized network activity.
