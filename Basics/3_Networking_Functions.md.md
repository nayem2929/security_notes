For a network as big as the internet to work, there’s a lot that goes on behind the scenes. Ensuring secure remote access from anywhere in the world, managing traffic, and supporting protocols are some of the most important ones.

·        One way to ensure fast access to media is using **CDN** (Content Delivery Network). These are **geographically distributed** **caching servers** that duplicate the data and send it to the local users.

·        **VPN** (Virtual Private Network) is used to secure private data traversing public network. It uses a concentrator/head-end, which is an encryption/decryption access device that is often integrated into a firewall. It can be deployed using either specialized cryptographic hardware for enterprise application, or a software-based option. Sometimes, it’s built into the OS.

·        **QoS** (Quality of Service) shapes traffic/packet and controls applications by bandwidth usage, or data rates. It can be used to **set priorities** for important apps. Can be managed by routers, switches, firewalls, and QoS devices.

·        **TTL** (Time to live) is a tool used to tell a system to stop a process after it has lived long enough. It creates a **timer** that might count number of hops for a packet, or wait until a certain amount of time has passed before stopping it. Sometimes, it is done to drop a packet caught in a **routing loop**, sometimes it’s done to clear a cache that’s not been used for a while. Default TTL for windows is 128, for macOS/Linux, it’s 64 (An average . Each time a packet passes through a router TTL is decreased by 1, and a TTL of zero gets dropped by the router. Below is a **protocol decode** of an **IP header** where it shows the TTL:
![[Screenshot 2026-05-19 174540.png]]


·        **DNS** (Domain Name System) is used to resolve an IP address from a fully-qualified domain name. Then a device caches the lookup for exactly **TTL** seconds long. Below is a typical DNS lookup report using dig.

![[Screenshot 2026-05-19 180124.png]]

- **IP Address**:
IP addresses can be two types: i) Public and ii) Private.
RFC 1918 defines the following three ranges of private IP addresses:
- `10.0.0.0` - `10.255.255.255` (`10/8`)
- `172.16.0.0` - `172.31.255.255` (`172.16/12`)
- `192.168.0.0` - `192.168.255.255` (`192.168/16`)
### The Life of a Packet

Let’s consider the scenario where you search for a room on TryHackMe.

1. On the TryHackMe search page, you enter your search query and hit enter.
2. Your web browser, using HTTPS, prepares an HTTP request and pushes it to the layer below it, the transport layer.
3. The TCP layer needs to establish a connection via a three-way handshake between your browser and the TryHackMe web server. After establishing the TCP connection, it can send the HTTP request containing the search query. Each TCP segment created is sent to the layer below it, the Internet layer.
4. The IP layer adds the source IP address, i.e., your computer, and the destination IP address, i.e., the IP address of the TryHackMe web server. For this packet to reach the router, your laptop delivers it to the layer below it, the link layer.
5. Depending on the protocol, The link layer adds the proper link layer header and trailer, and the packet is sent to the router.
6. The router removes the link layer header and trailer, inspects the IP destination, among other fields, and routes the packet to the proper link. Each router repeats this process until it reaches the router of the target server.

The steps will then be reversed as the packet reaches the router of the destination network. As we cover additional protocols, we will revisit this exercise and create a more in-depth version.