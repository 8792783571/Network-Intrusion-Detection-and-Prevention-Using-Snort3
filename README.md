# Network Intrusion Detection and Prevention System (NIDPS) Using Snort 3

## Overview

This project demonstrates the implementation of a **Network Intrusion Detection and Prevention System (NIDPS)** using **Snort 3** on Ubuntu Linux. The primary objective is to monitor network traffic, detect suspicious activities, and prevent malicious packets using custom Snort rules. The implementation showcases both **Intrusion Detection System (IDS)** and **Intrusion Prevention System (IPS)** modes.

The project includes the installation and configuration of Snort 3, creation of custom detection and prevention rules, testing with simulated attacks, and analysis of generated alerts. The system was validated using tools such as **Kali Linux**, **Nmap**, and **ICMP ping traffic**.

---

## Objectives

- Install and configure Snort 3 on Ubuntu.
- Monitor live network traffic.
- Detect network attacks using custom Snort rules.
- Prevent malicious ICMP traffic in inline IPS mode.
- Generate real-time alerts for suspicious activities.
- Understand the working of IDS and IPS technologies.

---

## Features

- Real-time packet inspection
- Signature-based intrusion detection
- Intrusion prevention using inline mode
- Custom Snort rule creation
- ICMP attack detection
- TCP SYN scan detection
- Fast alert logging
- Passive IDS mode
- Inline IPS mode using AFPacket
- Live traffic monitoring

---

## Technologies Used

- Ubuntu Linux
- Snort 3.12.2.0
- DAQ Library
- AFPacket
- libpcap
- Lua
- Kali Linux
- Nmap
- VMware Workstation
- Wireshark (Optional)

---

## Project Workflow

1. Install all required dependencies.
2. Install and configure Snort 3.
3. Create custom Snort rules.
4. Configure Snort for IDS mode.
5. Detect network attacks and generate alerts.
6. Configure Snort for IPS mode.
7. Block malicious ICMP traffic.
8. Verify prevention by monitoring dropped packets.
9. Analyze logs and packet statistics.

---

## IDS Implementation

The **Intrusion Detection System (IDS)** monitors incoming and outgoing network traffic without modifying or blocking packets. During testing, Snort successfully detected ICMP packets and TCP SYN scan attempts and generated alert messages in real time.

### Detection Mode Command

```bash
sudo /usr/local/snort/bin/snort --daq pcap -i ens33 -c /usr/local/snort/etc/snort/snort.lua -R /usr/local/snort/etc/rules/local.rules -A alert_fast
```

---

## IPS Implementation

The **Intrusion Prevention System (IPS)** was configured using **AFPacket** inline mode. When packets matched the custom **drop** rule, Snort prevented them from reaching the destination. Packet statistics confirmed that malicious ICMP packets were successfully blocked.

### IPS Mode Command

```bash
sudo /usr/local/snort/bin/snort --daq afpacket -Q -i ens33 -c /usr/local/snort/etc/snort/snort.lua -R /usr/local/snort/etc/rules/local.rules -A alert_fast
```

---

## Custom Rules Used

- ICMP Ping Detection
- TCP SYN Scan Detection
- ICMP Packet Blocking

These rules were stored in the **local.rules** file and loaded during Snort execution.

---

## Testing Performed

The implementation was tested using:

- ICMP Ping
- TCP SYN Scan using Nmap
- Normal network traffic
- Inline packet blocking

---

## Results

- Successfully installed and configured Snort 3.
- Successfully detected ICMP traffic.
- Successfully detected TCP SYN scan attacks.
- Successfully generated real-time alerts.
- Successfully blocked ICMP packets in IPS mode.
- Verified packet blocking through Snort statistics.
- Demonstrated both IDS and IPS functionality.

---

## Learning Outcomes

Through this project, I gained practical experience in:

- Network Intrusion Detection Systems (NIDS)
- Network Intrusion Prevention Systems (NIPS)
- Snort 3 configuration
- Writing custom Snort rules
- Linux system administration
- Packet analysis
- Network traffic monitoring
- Signature-based attack detection
- Inline packet filtering
- Cybersecurity monitoring techniques

---

## Applications

- Enterprise network security
- Educational laboratories
- Security Operations Centers (SOC)
- Data center monitoring
- Small and medium business network protection
- Cybersecurity research and training

---

## Future Enhancements

- Integrate with the ELK Stack for centralized logging.
- Forward alerts to a SIEM platform such as Splunk.
- Develop advanced custom rules for detecting additional attack types.
- Add automated email notifications for critical security alerts.
- Extend detection capabilities to web application attacks and malware traffic.

---

## Author

**Prajwal K.S.**

**M.E**  
**Cybersecurity Enthusiast | Network Security | Ethical Hacking | Linux | Snort 3**
