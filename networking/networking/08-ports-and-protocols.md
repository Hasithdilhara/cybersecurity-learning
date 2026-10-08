# Ports and Protocols

## What is a Port?

A port is a logical endpoint used by network services to communicate with applications on a device.

Port numbers range from:

0 – 65535

Example:

192.168.1.10:443

Here:
- 192.168.1.10 = IP address
- 443 = Port number

## Port Number Ranges

### Well-Known Ports
Range:
0 – 1023

These ports are commonly used by standard network services.

### Registered Ports
Range:
1024 – 49151

These ports are commonly used by applications and services.

### Dynamic / Private Ports
Range:
49152 – 65535

These ports are commonly used temporarily by client applications.

## Common Ports and Protocols

| Port | Protocol / Service | Transport |
|---|---|---|
| 20/21 | FTP | TCP |
| 22 | SSH | TCP |
| 25 | SMTP | TCP |
| 53 | DNS | TCP/UDP |
| 67/68 | DHCP | UDP |
| 80 | HTTP | TCP |
| 443 | HTTPS | TCP |
| 3389 | RDP | TCP/UDP |

## Common Services

### Port 22 – SSH
SSH is used for secure remote access to systems.

### Port 53 – DNS
DNS uses port 53 for domain name resolution.

### Port 80 – HTTP
HTTP is commonly used for web communication without encryption.

### Port 443 – HTTPS
HTTPS provides encrypted communication between a client and a web server.

### Port 3389 – RDP
RDP is used for remote desktop access to Windows systems.

## Why Ports Matter in Cyber Security

Understanding ports is important for:

- Firewall configuration
- Network monitoring
- Network scanning
- Service identification
- Incident investigation
- Detecting exposed services
- Traffic analysis

For example, if an unnecessary service is listening on a port, it may increase the attack surface of a system.

## Example

A web server may listen on:

```text
192.168.1.10:443
