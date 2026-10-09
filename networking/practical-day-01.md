# Networking Practical — Day 01

## Objective

The objective of this practical session was to understand basic network configuration, test network connectivity, perform DNS lookups, and trace the network path to a destination using Windows Command Prompt.

## Environment

- Operating System: Windows
- Tool: Command Prompt (CMD)
- Practical Area: Networking Fundamentals

---

## 1. IP Configuration — `ipconfig`

### Command

```cmd
ipconfig
```

### Purpose

Displays the basic IP configuration of network adapters on the computer.

### What I Learned

- **IPv4 Address:** Identifies the computer on an IPv4 network.
- **Subnet Mask:** Helps determine the network and host portions of an IPv4 address.
- **Default Gateway:** The router or network device used to reach other networks.
- **Network Adapter:** An interface used to connect to a network.

### Extended Command

```cmd
ipconfig /all
```

This displays additional details, including the MAC address, DHCP configuration, DNS servers, and IP address lease information.

### Important Concepts

- **DHCP:** Automatically assigns network configuration to a device.
- **DNS Server:** Resolves domain names into IP addresses.
- **MAC Address:** Identifies a network interface at the data-link layer.

### Key Learning

I learned how to identify the active network adapter and understand the basic network configuration of a Windows computer.

---

## 2. Testing Connectivity — `ping`

### Commands

```cmd
ping 127.0.0.1
ping <default-gateway>
ping google.com
```

Replace `<default-gateway>` with the gateway address shown by `ipconfig`.

### Purpose

The `ping` command tests connectivity by sending ICMP Echo Requests and waiting for Echo Replies.

### What I Learned

- `127.0.0.1` is the IPv4 loopback address used to test the local TCP/IP stack.
- The default gateway can be tested to check whether it responds to ping.
- A domain name such as `google.com` can be used to test DNS resolution and network reachability.
- **Time:** Shows the approximate round-trip time in milliseconds.
- **TTL (Time To Live):** Limits how long an IP packet can circulate through a network.
- **Request timed out:** Means no expected reply arrived within the timeout period.

### Important Note

A ping timeout does not always mean a destination is offline. ICMP traffic may be filtered, or a device may not respond to ping.

### Key Learning

I learned how to perform basic connectivity tests and interpret ping responses, latency, and timeouts.

---

## 3. DNS Lookup — `nslookup`

### Commands

```cmd
nslookup google.com
nslookup facebook.com
nslookup -type=A facebook.com
nslookup -type=AAAA facebook.com
```

### Purpose

The `nslookup` command queries DNS to retrieve records associated with a domain name.

### What I Learned

- **A record:** Maps a domain name to an IPv4 address.
- **AAAA record:** Maps a domain name to an IPv6 address.
- **DNS Server:** The server that processes the DNS query.
- **Non-authoritative answer:** A response provided by a resolver rather than directly by the domain's authoritative DNS server.

### Key Learning

I learned how to look up domain-related IP addresses and distinguish between IPv4 and IPv6 DNS records.

---

## 4. Tracing the Network Path — `tracert`

### Command

```cmd
tracert google.com
```

### Purpose

The `tracert` command traces the network path toward a destination and attempts to identify intermediate hops.

### What I Learned

- **Hop:** An intermediate router or Layer 3 network device along the path.
- **Round-Trip Time:** The time taken for a probe and its response, measured in milliseconds.
- **Destination IP:** The IP address resolved for the target domain.
- **Trace complete:** Indicates that the trace reached its destination.

### Practical Observation

The trace to Google completed successfully and displayed six hops in my observed output.

### Key Learning

I learned how to examine the route toward a destination and interpret hop numbers, IP addresses, and response times.

---

## 5. Summary of Commands

| Command | Purpose |
|---|---|
| `ipconfig` | View basic IP configuration |
| `ipconfig /all` | View detailed network configuration |
| `ping 127.0.0.1` | Test the local TCP/IP stack |
| `ping <default-gateway>` | Test gateway reachability |
| `ping google.com` | Test domain resolution and ping reachability |
| `nslookup google.com` | Query DNS records |
| `nslookup -type=A facebook.com` | Query IPv4 records |
| `nslookup -type=AAAA facebook.com` | Query IPv6 records |
| `tracert google.com` | Trace the network path |

---

## 6. Key Takeaways

Through this practical session, I gained hands-on experience with basic Windows networking commands. I learned how to inspect IP configuration, test connectivity, query DNS records, and trace network routes.

These fundamentals will support my next learning steps in network security, Linux networking, security tools, and cloud networking.


# Networking Practical — Network Connections

## Objective

To learn how to inspect network connections, identify listening ports, understand TCP connection states, and identify processes using their Process IDs (PIDs) in Windows.

## Environment

- Operating System: Windows
- Tool: Command Prompt (CMD)

---

## 1. Netstat

### Command

```cmd
netstat
```

### Purpose

Displays active TCP connections and their states.

### Important Columns

- **Proto:** Network protocol, such as TCP.
- **Local Address:** Local IP address and port.
- **Foreign Address:** Remote IP address and port.
- **State:** Current TCP connection state.

### Key Learning

I learned how to inspect active network connections and understand their local and remote endpoints.

---

## 2. Netstat with Additional Information

### Command

```cmd
netstat -ano
```

### Purpose

Displays active connections, listening ports, numerical addresses, and associated process IDs.

- `-a`: Displays active connections and listening ports.
- `-n`: Displays addresses and port numbers numerically.
- `-o`: Displays the Process ID (PID) associated with each connection.

### Important TCP States

- **LISTENING:** A service is waiting for incoming TCP connections.
- **ESTABLISHED:** A TCP connection has been established.
- **CLOSE_WAIT:** The remote side has initiated closure, and the local application has not yet fully closed the connection.
- **TIME_WAIT:** A connection remains in a waiting state briefly after closure.

### Key Learning

I learned how to identify listening ports, examine active connections, and find PIDs for further investigation.

---

## 3. Identify a Process Using Its PID

### Command

```cmd
tasklist /FI "PID eq 10840"
```

### Purpose

Filters the running process list to show the process with PID `10840`.

- `tasklist`: Displays running processes.
- `/FI`: Applies a filter.
- `PID eq 10840`: Selects the specified Process ID.

### Key Learning

A PID can help identify which running process is associated with a network connection. The process name should be investigated further when necessary.

*Note: This command identifies a process by PID. It does not, by itself, prove that a connection or process is safe or malicious.*


## 4. Cybersecurity Relevance

These commands are useful for:

- Reviewing active network connections.
- Identifying services listening on ports.
- Associating connections with running processes.
- Supporting initial network troubleshooting and security investigations.

A connection should not be considered suspicious solely because it is established or uses a particular port. Additional context and evidence are needed.



