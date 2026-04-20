<img width="630" height="380" alt="Screenshot 2026-04-17 115932" src="https://github.com/user-attachments/assets/371b2b97-a12e-4235-8e65-1fe5499346be" />

This screenshot shows the output of ip a confirming Kali is assigned to a valid IP address within the host-only lab network

<img width="574" height="326" alt="Screenshot 2026-04-17 115954" src="https://github.com/user-attachments/assets/d8220764-6b7e-4247-bfcd-1ab514854965" />

The shows the output of ipconfig, showing the assigned IP and confirming the system is correctly configured with the host-only network

<img width="717" height="461" alt="Screenshot 2026-04-19 112624" src="https://github.com/user-attachments/assets/0a9af423-8311-4ff2-9650-500b0a4a5b71" />

This screenshot shows the output of ifconfig, confirming that Metasploitable2 has been assigned an IP address within the 192.168.56.0/24 subnet. Ensuring proper network configuration.

<img width="592" height="175" alt="Screenshot 2026-04-17 120406" src="https://github.com/user-attachments/assets/225328e4-4f1a-4560-8bd9-e3f334e15789" />

This screenshot shows Kali linux failing to ping Windows VM and showing 100% packet loss, indicating a network connectivity issue requiring further troubleshooting.

<img width="568" height="305" alt="Screenshot 2026-04-17 120446" src="https://github.com/user-attachments/assets/d54e8ba4-e10a-4dc3-9a30-d768e6856a7e" />

Here you can see a successful ICMP communication from the windows vm, confirming it is functioning correctly post troubleshooting. Indicating the network configuration and firewall issues have been resolved.

<img width="530" height="236" alt="Screenshot 2026-04-17 120623" src="https://github.com/user-attachments/assets/ab55539c-e5c0-4bd5-beb8-8ab99bb8b8a3" />

This screenshot shows a successful ping from Kali to Metasploitable2, signalling that its operating correctly and connected to the Host-Only network.

<img width="627" height="409" alt="Screenshot 2026-04-17 120650" src="https://github.com/user-attachments/assets/a87e91e0-e0d0-491c-a777-de4a04c259c8" />

This screenshot shows a host discovery scan performed using nmap by using the command nmap -sn. Identifying active devices within the 192.168.56.0/24 subnet. Results confirm multiple active hosts, including windows and metasploitable vm's.

<img width="620" height="377" alt="Screenshot 2026-04-17 120727" src="https://github.com/user-attachments/assets/166e19bf-d5d2-4965-b806-21b4cf514d36" />

This screenshot demonstrates service enumeration using Nmap, identifying open ports and running services on the Windows VM. The presence of services such as NetBIOS and Microsoft RPC highlights potential entry points for attacks.

<img width="1685" height="914" alt="Screenshot 2026-04-17 121005" src="https://github.com/user-attachments/assets/da8c3ce1-3924-4bf4-a4f3-d260f723de81" />

This creenshot captures ICMP echo requests and replies between Kali Linux and the Windows VM using Wireshark. Illustrating successful network communication and provides insight into how connectivity tests such as ping operate at the protocol level.





