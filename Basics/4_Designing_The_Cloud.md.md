·        The goal of the cloud is to provide **on-demand computing power** that’s **elastic**, with **scalability for large implementations** that is **accessible** from anywhere. It also implements multitenancy (multiple clients use the same cloud infrastructure).

·        Imagine there is a server farm with 100 computers that connected to each other via routers and switches. This introduces redundancy and can be energy-inefficient. We can open up 100 virtual servers instead inside of each of those physical servers and virtualize the network. This is called **Network Function Virtualization (NFV)**. This has many benefits including quick and easy deployment, having many options while retaining the same functionalities as a physical network.

·        **Virtual Private Cloud (VPC)** is a pool of resources inside a public cloud. VPCs communicate with each other using an internal transit gateway and users connect to it through a public virtual router. They can be securely connected to through a [[6_Port_Forwarding_Firewalls_and_VPNs.md|VPN]] and typically exist in different IP subnets.

·        **VPC NAT gateway**: Stands for **Network Address Translation**. It allows private cloud subnets to connect to external resources, but external resources cannot access the private cloud.

·        Sometimes, a company might use different cloud providers for their services. In that case, a **VPC Endpoint** is used to provide connection between those different providers.

![](file:///C:/Users/LENOVO/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

Figure 1: Example of a VPC endpoint

·        **Security groups and lists**: This is essentially the firewall for the cloud.

-        controls inbound and outbound traffic

-        Layer 4 port number (TCP or UDP port)

-        Layer 3 addresses can also be added as either individual addresses, CIDR block notation, or IPv4 or IPv6 addresses.