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
	- `USER`: To enter username
	- `PASS`: To enter password
	- `RETR`: to download
	- `STOR`: to upload
	Commonly uses TCP port 21.

SMTP: Simple Mail Transfer Protocol
	Listens on port 25 by default. Some commands are:
	- `HELO` or `EHLO`: Initializes an SMTP session
	- `MAIL FROM`: Specifies senders email address
	- `RCPT TO`: Specifies the receivers email address
	- `DATA`: Indicates that the client will begin sending the content of the mail, ends with a `.`

POP3: Post Office Protocol 3; used to retrieve emails
	Listens on port 110 by default. Some common commands are:
	- `AUTH`: To begin authentication
	- `USER <username>`: To enter username
	- `PASS<password>`: To enter password
	- `STAT`: To display total number of emails and total size information
	- `LIST`: Lists the number of messages with sizes
	- `RETR <message_number>`: To retrieve a message
	- `DELE <message_number>`: To delete a message
	- `QUIT`: Ends the POP3 sessio

IMAP: Internet Message Access Protocol. 
	More functional version of SMTP and POP3. Messages are not delete from the server after being downloaded by the user. Listens on port 143 by default. Some common commands include:
	- `LOGIN <username> <password>`: authenticates the user
	- `SELECT <mailbox>`: selects the mailbox folder to work with
	- `FETCH <mail_number> <data_item_name>`: Example: `fetch 3 body[]` to fetch message number 3, header and body.
	- `MOVE <sequence_set> <mailbox>`: moves the specified messages to another mailbox
	- `COPY <sequence_set> <data_item_name>`: copies the specified messages to another mailbox
	- `LOGOUT`: logs out.  
