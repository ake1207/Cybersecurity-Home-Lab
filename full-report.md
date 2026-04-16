Building, Analysing and Testing a Virtual Cyber Security Lab using Kali Linux, W10 and Metasploitable2
	This project involved designing and implementing a virtual cyber security lab environment to simulate real-world network interactions and penetration testing scenarios. The lab consisted of three virtual machines: an attacker system operating on Kali Linux, and 2 target systems running on Windows 10 and Metasploitable2. 
My Objective was to: 
•	Configure an isolated virtual network/lab environment.
•	Troubleshoot connectivity issues between the machines
•	Perform network diagnostics 
•	Conduct reconnaissance and basic port enumeration using Nmap
•	Analyse traffic using Wireshark
	The lab was built using Oracle VirtualBox, with Kali as an attacker, and Windows 10 as a regular target followed by Metasploitable2 acting as a vulnerable target. I created the virtual network environment using a Host-Only network: 192.168.56.0/24. All machines were assigned IPs within this subnet. Ensuring isolation from external networks to therefore create a safe testing environment. Here is a network diagram to better visualize this virtual network:
 

	Each virtual machine was constructed with appropriate resources: (RAM, CPU, Storage). The key configuration step was ensuring that all VMs used the same Host-Only Adapter within VirtualBox. Metasploitable2 was imported using a preconfigured virtual disk, whereas Windows10 and Kali Linux were installed via ISO images to ensure a boot medium was installed as the virtual machines wouldn’t operate otherwise.
	During the setup process, many networking issues were encountered. Windows displayed “Unidentified Network” which caused a 100% packet loss when pinging Windows from Kali Linux. Some commands used to test the lab were ipconfig in CMD on Windows, ip a on Kali Linux, ifconfig on Metasploitable2 and ping for connectivity testing. I originally thought there was a potential DHCP issue as the DHCP server address was set to 192.168.56.2 and it should’ve been at a value between 100-200, but fixing that didn’t change anything. Then I tried creating a new Host-Only Adapter and connecting them to it ensuring it was done correctly and that didn’t fix it either. I also tried releasing and renewing the windows network via the command’s ipconfig /release and /renew as well as disabling and enabling the adapter using Win + R and ncpa.cpl but both to no avail. And finally I figured out that the root issue was traced to the Windows firewall settings blocking ICMP traffic, so I temporarily disabled firewall in using the command netsh advfirewall set allprofiles state off in CMD in admin mode which fixed the issue. After resolving this, communication between all virtual systems was established.
	Connectivity between systems was verified using ICMP: in bash: ping 192.168.56.x. Successful responses on all sides confirmed proper network configuration. This step highlights the importance of: Firewall rules, Correct subnet configuration and proper virtual adapter selection.
	
	Network reconnaissance was conducted using Nmap, in bash using nmap -sn 192.168.56.0/24. Helping me identify active devices on the network without scanning ports. I also used nmap -sV 192.168.56.x for basic service enumeration, revealing: open ports, active services and software versions. This information is critical for identifying potential vulnerabilities in a system.
	Further traffic analysis was performed using Wireshark on the Kali machine. Using the command sudo wireshark in bash. Some observations from this include:
•	ICMP request/reply packets during ping tests
•	TCP SYN packets during nmap scans
•	SYN-ACK responses indicating open ports
Providing useful insight into how networks communicate as well as how scanning tools interact with targets. Understanding how routers and hosts utilise ICMP packets to diagnose connectivity issues and manage traffic. As well as how 3-way TCP handshakes work during scanning, SYN-ACK-RST.




This project providing a lot of practical understanding of things like:
•	Virtual network configurations such as NAT and Host-Only networking and firewall impacts to network communication.
•	Relationships between protocols like TCP and ICMP and security tools
•	Basic network troubleshooting techniques and the importance of visibility when diagnosing network issues.
•	How reconnaissance tools operate at protocol level
However, some improvements I could implement to the lab include:
•	Adding an Active Directory environment: Would simulate an organisation network environment, orgs use AD and would help me to learn about Domain authentication.
•	Deploying vulnerable web applications such as DVWA: Add a web-layer attack surface enabling me to understand more about SQL injections, and authentication bypassing.
•	Integrating logging and monitoring tools for further analysis: Such as Splunk, helping me expand into defensive security by learning blue team skills like: Log analysis and detection of attacks
•	Learn more advanced scripting skills to use bash/python to help automate scans and provide feedback, would help me demonstrate efficiency and prove my scripting ability.

This project demonstrated the design, implementation and analysis of a controlled virtual cyber security lab environment. By configuring three connected virtual machines, this lab simulated a semi-realistic network scenario in which an attacking system could interact and analyse multiple targets in safe and isolated conditions. One key outcome of this project was the development of practical troubleshooting skills. There were initial connectivity issues like failed ICMP communication with Windows 10, requiring diagnosis using tools like, ping, ipconfig, ip a, and netsh advfirewall set allprofiles state off to turn off firewall to fix the issue. Resolving these issues opened my eyes to the importance of understanding how virtual networking operates, specifically the role of host-only adapters, DHCP configurations and firewall behaviour. Furthermore, the use of Nmap demonstrated to me how attackers perform reconnaissance by identifying live hosts, open ports and running services. I also strengthened this by using Wireshark for packet inspection, providing visibility into how scanning and communication occur across the network. Overall, this project not only strengthened my technical skills in system setup and networking, but also in developing a deeper understanding of how offensive security tools operate. The ability to configure and troubleshoot this environment shows the foundational skill and knowledge required in cybersecurity roles.

