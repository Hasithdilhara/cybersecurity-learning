# Firewalls

## What is a Firewall?

A firewall is a security system that monitors and controls network traffic based on predefined security rules.

A firewall can allow or block network traffic depending on factors such as:

- Source IP address
- Destination IP address
- Port number
- Protocol
- Network interface
- Connection state

Firewalls are commonly used to protect networks, servers, and individual devices.

---

## Why are Firewalls Used?

Firewalls are used to:

- Control network traffic
- Prevent unauthorized access
- Protect internal networks
- Restrict unnecessary services
- Control inbound and outbound connections
- Reduce the attack surface
- Monitor network communication

---

## How Does a Firewall Work?

A firewall examines network traffic and compares it with configured rules.

Basic example:

```text
Internet
    |
    v
+-----------+
| Firewall  |
+-----------+
    |
    v
Internal Network
```

If traffic matches an allowed rule, the firewall permits it.

If traffic matches a blocking rule, the firewall denies it.

---

## Firewall Rules

Firewall rules define what network traffic should be allowed or blocked.

A rule may contain:

- Source IP
- Destination IP
- Source port
- Destination port
- Protocol
- Action

Example:

```text
Source: Any
Destination: Web Server
Port: 443
Protocol: TCP
Action: Allow
```

This rule allows HTTPS traffic to the web server.

Another example:

```text
Source: Any
Destination: Server
Port: 23
Protocol: TCP
Action: Deny
```

This rule blocks Telnet traffic.

---

## Allow and Deny

Firewalls commonly use actions such as:

### Allow

Allows matching network traffic to pass.

### Deny

Blocks matching network traffic.

Example:

```text
TCP Port 443 → Allow
TCP Port 23  → Deny
```

The exact behaviour of denied traffic can depend on the firewall configuration and platform.

---

# Inbound Traffic

Inbound traffic is traffic coming into a network or device.

Example:

```text
Internet
   |
   v
Firewall
   |
   v
Server
```

The firewall can control which external connections are allowed to reach internal systems.

---

# Outbound Traffic

Outbound traffic is traffic leaving a network or device.

Example:

```text
Internal Device
      |
      v
   Firewall
      |
      v
   Internet
```

A firewall can control which internal devices or applications are allowed to communicate with external networks.

---

# Inbound vs Outbound

| Traffic | Direction | Example |
|---|---|---|
| Inbound | Outside → Inside | Internet to Web Server |
| Outbound | Inside → Outside | Laptop to Internet |

Both inbound and outbound traffic can be controlled using firewall rules.

---

# Stateful Firewall

A stateful firewall keeps track of active network connections.

For example:

```text
Client
   |
   | Request
   v
Server
   |
   | Response
   v
Client
```

The firewall can understand that the response belongs to an existing connection.

Stateful firewalls can make decisions based on the state of network connections.

---

# Stateless Firewall

A stateless firewall evaluates packets individually based on configured rules.

It does not maintain the same level of connection state information as a stateful firewall.

Example factors can include:

- Source IP
- Destination IP
- Port
- Protocol

---

# Stateful vs Stateless

| Feature | Stateful | Stateless |
|---|---|---|
| Tracks connections | Yes | No |
| Evaluates traffic | Based on rules and connection state | Mainly packet-by-packet |
| Context awareness | Higher | Lower |
| Configuration | Can be more complex | Generally simpler |

---

# Network Firewall

A network firewall protects traffic passing between networks.

Example:

```text
Internet
    |
    v
Network Firewall
    |
    v
Internal Network
```

Network firewalls are commonly used in:

- Organizations
- Data centers
- Enterprise networks
- Cloud environments

---

# Host-Based Firewall

A host-based firewall runs directly on an individual device.

Examples include firewalls on:

- Windows
- Linux
- Servers
- Workstations

Example:

```text
Internet
   |
   v
Router / Network
   |
   v
Host Firewall
   |
   v
Computer
```

Host-based firewalls provide an additional layer of protection for individual systems.

---

# Firewall and NAT

Firewalls and NAT can work together, but they have different purposes.

### NAT

NAT translates IP addresses between networks.

### Firewall

A firewall controls network traffic based on security rules.

Example:

```text
Internet
   |
   v
Firewall
   |
   v
NAT / Router
   |
   v
Private Network
```

NAT should not be considered a replacement for a firewall.

---

# Firewall and Network Security

Firewalls are an important part of network security.

They can help with:

- Access control
- Network segmentation
- Traffic filtering
- Attack surface reduction
- Unauthorized access prevention
- Security monitoring

However, a firewall alone cannot protect an entire environment.

Other security controls are also important, such as:

- Strong authentication
- Endpoint security
- Security monitoring
- Regular updates
- Access control
- Network segmentation
- Incident response

---

# Example Firewall Scenario

Consider a company web server.

The company wants users on the Internet to access the website using HTTPS.

A firewall rule may be:

```text
Source: Any
Destination: Web Server
Protocol: TCP
Port: 443
Action: Allow
```

Other unnecessary services can be restricted.

For example:

```text
Port 23 (Telnet)
Action: Deny
```

This reduces unnecessary exposure.

---

# Default Allow vs Default Deny

Firewall policies can be designed using different approaches.

## Default Allow

Traffic is generally allowed unless a specific rule blocks it.

## Default Deny

Traffic is generally blocked unless a specific rule allows it.

A carefully designed default-deny approach can reduce unnecessary network exposure.

---

# Firewall Logging

Many firewalls can generate logs about network traffic and security events.

Firewall logs may contain information such as:

- Source IP
- Destination IP
- Port
- Protocol
- Timestamp
- Action
- Connection information

Example:

```text
Source: 192.168.1.20
Destination: 10.0.0.10
Port: 443
Protocol: TCP
Action: Allow
```

Security teams can use firewall logs for:

- Monitoring
- Troubleshooting
- Incident investigation
- Detecting suspicious activity
- Security analysis

---

# Firewall in Cyber Security

Understanding firewalls is important for cybersecurity professionals because firewalls are commonly used as a network security control.

Security professionals may need to:

- Review firewall rules
- Monitor firewall alerts
- Analyse firewall logs
- Identify unusual traffic
- Check exposed services
- Verify access controls
- Investigate blocked connections

---

# Firewall in Cloud Environments

Cloud platforms also provide network security controls that perform firewall-like functions.

For example, cloud environments can use rules to control traffic between:

- Internet
- Virtual networks
- Servers
- Applications
- Private resources

Understanding traditional firewall concepts makes it easier to understand cloud network security.

---

# Firewall Best Practices

Some general firewall security practices include:

- Allow only necessary traffic
- Block unnecessary services
- Review firewall rules regularly
- Remove unused rules
- Monitor firewall logs
- Restrict administrative access
- Use network segmentation
- Document important rules
- Follow the principle of least privilege

---

# Common Firewall Terms

### Rule

A condition that determines whether traffic should be allowed or blocked.

### Inbound

Traffic entering a network or device.

### Outbound

Traffic leaving a network or device.

### Stateful

A firewall that tracks active connections.

### Stateless

A firewall that evaluates traffic mainly packet-by-packet without maintaining connection state.

### ACL

Access Control List. A set of rules used to control access to network resources or traffic.

### Logging

Recording network events and firewall actions for monitoring and investigation.

---

# What I Learned

- A firewall monitors and controls network traffic.
- Firewall rules determine which traffic is allowed or blocked.
- Inbound traffic enters a network or device.
- Outbound traffic leaves a network or device.
- Stateful firewalls track connection state.
- Stateless firewalls evaluate traffic mainly packet-by-packet.
- Network and host-based firewalls provide different layers of protection.
- NAT and firewalls have different purposes.
- Firewall logs are useful for monitoring and incident investigation.
- Firewalls are an important part of network security.
