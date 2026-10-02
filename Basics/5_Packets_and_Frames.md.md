**Packets** are small chunks of a big piece of data.

**Frames** are the layer 2 encapsulation of data.

-        When packets are sent over the internet using IP, the following headers are included:

o   TTL

o   Checksum

o   Source address

o   Destination address

**TCP** is a slow but reliable method for transferring data. It encapsulates data with important headers like port numbers, IP addresses, sequence number, acknowledgement number, checksum, the actual data itself, and flag etc.

TCP does this thing called a **Three-way** handshake to ensure the connection is stable.

-        SYN – requesting a connection

-        SYN/ACK – acknowledging the request

-        ACK – acknowledging the acknowledgement

-        DATA – time to send the data

-        FIN – closing the connection

-        RST – this is a special packet sent only in case of failures

**UDP** is another way to send data. It’s much faster and more unsafe than TCP because there is no “three-way handshake” or any checksums. It also has fewer headers than TCP, although they still have some in common like the TTL, port numbers, IP addresses, and the actual data.

**Ports** are aptly named interfaces for devices to connect to a server. Ports 0-1024 are called common ports. Some important port numbers worth memorizing are:

* **21**: File Transfer Protocol (FTP)
* **22**: Secure Shell (SSH)`
-  **80**: Hyper Text Transfer Protocol (HTTP)
-  **443**: HTTPS
-  **445**: Server Message Block (SMB). Similar to FTP, but allows connecting to **printers.**
-  **3389**: Remote Desktop Protocol (RDP). Allows logging into a system with a visual desktop interface.