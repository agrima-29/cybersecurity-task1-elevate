# cybersecurity-task1-elevate
Nmap TCP SYN scan and intense scan on local network
# Task 1:

## Objective
The objective of this task was to perform basic network reconnaissance by identifying open ports on local network devices using Nmap, and to validate the scanning process using Wireshark for packet-level analysis.

## Tools Used
- Nmap (for SYN scan)
- Wireshark (for network packet capture and analysis)

## Steps Performed

1. Installed Nmap from the official [Nmap website](https://nmap.org/).
2. Identified the local IP range: '192.168.1.0/24'
3. Performed a TCP SYN scan using the command:
   '''bash
   nmap -sS -oN syn_scan.txt 192.168.1.0/24
''''

4. Simultaneously captured packets using Wireshark during the scan.
5. Saved outputs:

   * 'syn_scan.txt' – Nmap scan result
   * 'wireshark_capture.pcapng' – Wireshark capture file (not uploaded due to size/privacy)

## Files Included

* 'syn_scan.txt': Nmap scan result with identified live hosts and open ports.
* 'task 1.pdf': Task brief for reference.

## Key Findings from Nmap

Hosts Detected as Up:

* '192.168.1.1' (Router)
* '192.168.1.4' (Local Windows system)
* '192.168.1.5' (Smart/IoT device)

Open Ports Detected:

192.168.1.1 (Router):

* 53/tcp (DNS)
* 80/tcp (HTTP)
* 443/tcp (HTTPS)
* 5555/tcp (likely UPnP)

192.168.1.4 (Windows System):

* 135/tcp (Microsoft RPC)
* 139/tcp (NetBIOS Session Service)
* 445/tcp (SMB)
* 902, 912 (VMware-related)
* 3306/tcp (MySQL)
* 4443–4446/tcp (Misc. services)
* 5357/tcp (WSD)
* 5432/tcp (PostgreSQL)

192.168.1.5 (IoT/TV device):

* 8008, 8009, 8443, 9000/tcp (Chromecast/Smart device services)

## Wireshark Analysis

* While the Nmap scan was running, Wireshark successfully captured SYN packets being sent to different hosts.
* Verified:

  * SYN packets were sent to multiple ports
  * For open ports: SYN-ACK responses were received
  * For closed/filtered ports: RST or no response
  * This validated the SYN scan behavior and showed real-time traffic patterns.

## Security Insight

* Multiple ports are open on network devices, some exposing critical services (databases, SMB, etc.).
* Router and smart devices expose web-based interfaces and UPnP.
* Recommendation:

  * Disable unnecessary services
  * Regularly audit open ports
  * Use firewall rules to restrict external access

## Concepts Learned

* How to perform and interpret TCP SYN scans with Nmap.
* Understanding network traffic using Wireshark.
* Basics of port states (open, closed, filtered) and service exposure risks.

## Conclusion

This task helped develop a strong understanding of how port scanning works and how attackers might enumerate open services. It also demonstrated the usefulness of Wireshark in confirming scan behavior at the packet level.

## Submission

Repository link has been submitted as per the internship guidelines.
