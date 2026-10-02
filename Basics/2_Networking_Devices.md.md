There are many ways forward data traffic. In a data center, different equipment is installed, each with a specific purpose, but with the overall goal of moving data from point A to B. In this lesson, we learn about some of these devices.

**Router**:
·        This is a device that routes traffic between **IP subnets**.
·        It’s an OSI Layer 3 device
·        Often connects diverse types of networks, e.g.: LAN, WAN, copper, fiber

**Switch**:
·        Bridging hardware using ASIC (Application-Specific Integrated Circuit)
·        OSI layer 2 device that forwards traffic based on data link address

**Firewalls**:
·        Filter traffic by port number (old) or application (new)
·        It often sits on the ingress/egress of the network
·        Performs Network Address Translation (NAT)


**IDS and IPS**:
Abbr.: Intrusion Detection System. Intrusion Prevention System.
·        Intrusion - Watches network traffic to detect intrusion
·        Prevention – Stop it before it gets into the network.

**Load Balancer**:
·        Distributes the load to multiple servers
·        Used in web-server farms, database farms
·        Provides a server with fault tolerance
When accessing a webpage from the internet, the user’s request might interact with the load balancer first which can perform the some operations like TCP offload, caching etc. and route the traffic.

**Proxies**:
·        Sits between users and the external network
·        Receives user request and sends the request on their behalf
·        Useful for caching information, access control, URL filtering, content scanning
·        Applications might need to know how to use the proxy (**explicit**)
·        Some proxies are invisible (**Implicit**)

**NAS vs. SAN**:
·        Network Attached Storage allows users to connect to a shared storage device across the network with File-level access.
·        Storage Area Network looks and feels like a local storage device with the main difference being it provides users with Block-level access. This makes it very efficient in reading and writing
·        Both require a lot of bandwidth

 **Access point (AP)**
·        Not a wireless router
·        It extends the wired network onto the wireless network
·        OSI layer 2 device

**Wireless LAN Controllers**:
Controllers for access points (AP). These allow us to:
·        Centralize management of access points
·        Performance and security monitoring
·        Usually, a proprietary system