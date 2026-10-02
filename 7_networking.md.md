- **DHCP**: Dynamic Host Configuration Protocol
This was made to facilitate network switching on mobile devices. Basically, every time a device wants to connect to the internet using a network, the host device (routers and such) can use this protocol to dynamically allocate an available IP within the subnet to the device requesting the connection, and also configure the rest of the network settings for it.
**Steps**:
	- Server is always listening on UDP port 67
	- Client sends out a **DHCPDISCOVER** request to broadcast address 255.255.255.255 from 0.0.0.0 (since no IP address has been configured yet)
	- Server responds with a **DHCPOFFER** message with an available IP address.
	- Client responds with a **DHCPREQUEST** message to indicate that it has accepted the offered IP.
	- Server finally responds with a **DHCPACK** message to confirm the assignment.
The DHCP server usually provides the following in the configuration file:
	- IP Address along with a subnet mask
	- Router (or Gateway)
	- DNS Server

ARP: Address Resolution Protocol is used to look up and connect to a local device on the internet using MAC Addresses (Layer 2). 
- ICMP: Used for diagnosis and error reporting. Two common commands: ping, traceroute
- Routing algorithms: Popular ones include:
	- OSPF: Open Shortest Path First. This algorithm allows router to share their network topology and calculate the best route.
	- EIGRP: Enhanced Interior Gateway Routing Protocol is a Cisco proprietary protocol that considers the cost/bandwidth of different paths along with their network so routers can choose the most efficient route.
	- BGP: Border Gateway Protocol is how most of the information travels the internet. It allows Internet Service Providers to share routing information that allows them to calculate the most efficient path across different networks. 
	- RIP: Routing Information Protocol is used by routers in small networks. It works by obtaining network information and the required number of hops to reach there, then it uses this information to build a routing table. Finally the path with the least hops is chosen.

- NAT: Network Address Translation is used by routers to distinguish between private and public addresses and allow network traffic to go through seamlessly.  
![[Pasted image 20260930191647.png|625]]

WHOIS: A WHOIS record provides information about the entity that registered a domain name, including name, phone number, email, and address. Syntax: `whois example.com`

FTP: File transfer protocol
	Used to exchange files. Common requests include:
	- USER: To enter username
	- PASS: To enter password
	- RETR: to download
	- STOR: to upload
	Commonly uses TCP port 21.

SMTP: Protocol used for sending mail
	Listens on port 25 by default. Some commands are:
	- HELO or EHLO: Initializes an SMTP session
	- MAIL FROM: Specifies senders email address
	- RCPT TO: Specifies the receivers email address
	- DATA: Indicates that the client will begin sending the content of the mail, ends with a `.`

