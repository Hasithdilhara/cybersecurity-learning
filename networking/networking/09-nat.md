## What I Learned
- NAT translates IP addresses between networks.
- Private IP addresses are commonly used inside local networks.
- Public IP addresses are used for Internet communication.
- Static NAT provides a fixed mapping.
- Dynamic NAT uses a pool of public addresses.
- PAT allows multiple devices to share one public IP address.
- NAT can work together with firewalls.
- NAT is useful for understanding enterprise and cloud networking.
- NAT is not a replacement for a firewall.


# Network Address Translation (NAT)

## What is NAT?

NAT stands for Network Address Translation.

NAT is a networking technique used to translate IP addresses between different networks, commonly between a private internal network and the public Internet.

A router commonly performs NAT at the boundary between a private network and an external network.

---

## Why is NAT Used?

NAT is mainly used to:

- Allow private devices to access the Internet
- Reduce the need for public IPv4 addresses
- Translate private IP addresses to public IP addresses
- Manage network addressing
- Separate internal and external networks
- Support communication between private networks and external networks

---

## Private IP Addresses

Private IP addresses are used inside local networks.

The main private IPv4 ranges are:

### 10.0.0.0/8

Range:

```text
10.0.0.0 – 10.255.255.255



## Types of NAT

There are several common ways NAT can be implemented.

1. Static NAT
Static NAT creates a fixed one-to-one mapping between a private IP address and a public IP address.

2. Dynamic NAT
Dynamic NAT maps private IP addresses to public IP addresses from a pool of available public addresses.

3. PAT
PAT stands for Port Address Translation.
PAT allows multiple private devices to share a single public IP address by using different port numbers.
This is very common in home and office networks.

Inside and Outside Networks

NAT commonly separates network traffic into:
Inside Network

The internal/private network containing devices such as:
- Laptops
- Desktop computers
- Servers
- Mobile devices
- IoT devices
Outside Network
The external network, commonly the Internet.

NAT and Security

NAT can provide some separation between internal and external addressing.
For example, internal devices may use private IP addresses that are not directly routable on the public Internet.
However:
NAT is not a replacement for a firewall.

A secure network should use appropriate security controls such as:
- Firewalls
- Access control
- Network segmentation
- Authentication
- Monitoring
- Secure configurations

NAT and Cyber Security

Understanding NAT is important for:
- Network security
- Firewall configuration
- Network troubleshooting
- Traffic analysis
- Incident investigation
- Network architecture
- Understanding internal and external traffic
- Cloud networking
When analysing network traffic, security professionals need to understand that the source or destination address may have been translated by a NAT device.
