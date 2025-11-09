# Lab 1: DNS Packet Capture & Analysis (Wireshark)

## Objectives
1. Capture DNS Traffic
2. Explore DNS Query Traffic
3. Explore DNS Response Traffic

## Tools Used
- Wireshark (GUI)
- Kali Linux 
- Powershell

## Setup / Capture
1. Launch Wireshark. Select an active interface with traffic for packet capture (vmnet8).
![traffic capture](https://github.com/Psyberify/Tech-Learning-Journey/blob/186f21fab592dcf1a7a297e38053d0ca24e88956/Cybersecurity/DNS-Packet-Capture/screenshots/Exploring%20DNS%20traffic/traffic%20capture%20.pcapng?raw=true)
2. Clear DNS cache.
- In Windows, enter ipconfig /flushdns in Command Prompt.
3. At Powershell terminal, type nslookup enter the interactive mode.
4. Enter the domain name of a website. The domain name www.cisco.com is used in this example.
5. Exit and close the command prompt.
![nslookup on linux](https://github.com/Psyberify/Tech-Learning-Journey/blob/186f21fab592dcf1a7a297e38053d0ca24e88956/Cybersecurity/DNS-Packet-Capture/screenshots/Exploring%20DNS%20traffic/nslookup%20on%20linux.png?raw=true)
6. Click Stop capturing packets to stop the Wireshark capture.

## Explore DNS Query Traffic.
1. Observe the traffic captured in the Wireshark Packet List pane. Enter udp.port == 53 in the filter box and enter to display only DNS packets.
![DNS Query Traffic](https://github.com/Psyberify/Tech-Learning-Journey/blob/186f21fab592dcf1a7a297e38053d0ca24e88956/Cybersecurity/DNS-Packet-Capture/screenshots/Exploring%20DNS%20traffic/DNS%20query%20traffiic.png?raw=true)

2. Select the DNS packet contains Standard query and A www.cisco.com in the Info column.
3. In the Packet Details pane, notice this packet has Ethernet II, Internet Protocol Version 4, User Datagram Protocol and Domain Name System (query).
4.  Expand Ethernet II to view the details. Observe the source and destination fields.
5. Expand Internet Protocol Version 4. Observe the source and destination IPv4 addresses.
6. Expand the User Datagram Protocol. Observe the source and destination ports.
7. In a Powershell, enter arp –a and ipconfig /all to record the MAC and IP addresses of the PC.
![Interface IPv4 Address](https://github.com/Psyberify/Tech-Learning-Journey/blob/186f21fab592dcf1a7a297e38053d0ca24e88956/Cybersecurity/DNS-Packet-Capture/screenshots/Exploring%20DNS%20traffic/interface%20Ipv4%20address.png?raw=true)


##  Explore DNS Response Traffic
1. Select the corresponding response DNS packet has Standard query response and A www.cisco.com in the Info column.
![DNS response traffic](https://github.com/Psyberify/Tech-Learning-Journey/blob/186f21fab592dcf1a7a297e38053d0ca24e88956/Cybersecurity/DNS-Packet-Capture/screenshots/Exploring%20DNS%20traffic/DNS%20response%20traffic.png?raw=true)
2. Expand Domain Name System (response). Then expand the Flags, Queries, and Answers.
3. Observe the results.
4. Observe the CNAME and A records in the Answers details.


