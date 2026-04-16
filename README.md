# Cybersecurity-Home-Lab
This project documents the creation, analysis and testing of a virtual cybersecurity lab environment designed to simulate real-world interactions and penetration testing procedures.

# Lab was built using:

•Oracle VirtualBox

•Kali Linux (Attacker)

•Windows 10 (Target)

•Metasploitable2 (Vulnerable Target)

# Lab Architecture

•Isolated Host-Only Network: 192.168.56.0/24

•All systems configured within same subnet
•No external network exposure

Here is a network diagram to better visualise the Lab Architecure:

<img width="3124" height="3444" alt="image" src="https://github.com/user-attachments/assets/6bc30149-9d26-4192-a1ed-8df1788eba20" />


# Skills Demonstrated

•Virtual machine deployment and configuration

•Network troubleshooting and diagnostics

•Firewall analysis and resolution

•Host discovery and service enumeration using Nmap

•Packet-level traffic analysis using Wireshark

# Networking Challenges & Solutions

During setup, several issues were encountered:

•“Unidentified Network” on Windows

•Failed ICMP communication

•DHCP inconsistencies

These were resolved by:

•Reconfiguring VirtualBox Host-Only adapters

•Adjusting firewall rules to allow ICMP

•Verifying subnet consistency across all VMs

# Reconnaissance Techniques

•nmap -sn 192.168.56.0/24 #Host Discovery

•nmap -sV 192.168.56.x #Service Enumeration

# Packet Analysis

Wireshark was used to analyse:

•ICMP request/reply traffic

•TCP SYN scanning behaviour

•Service detection probes

This provided insight into how network scanning tools operate at the protocol level

# Full Report

A detailed full technical report is available in the /fullreport directory













