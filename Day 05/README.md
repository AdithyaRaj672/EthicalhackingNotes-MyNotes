# EthicalHacking Notes - Day 04
**Date:** 21/07/2025

**Duration:** 2 hours  

**Focus:** Networking Fundamentals & Nmap Commands

---
## 📡 What is a Network?

A **network** is a collection of interconnected devices (computers, servers, routers, switches, etc.) that can communicate and share resources with each other. Networks enable data transmission, resource sharing, and communication between different systems.

### Types of Networks:
- **LAN (Local Area Network)**: Small geographic area (home, office)
- **WAN (Wide Area Network)**: Large geographic area (cities, countries)
- **MAN (Metropolitan Area Network)**: City-wide network
- **PAN (Personal Area Network)**: Very small area (Bluetooth devices)

---

## 🔗 What is a Subnet?

A **subnet** (subnetwork) is a logical subdivision of an IP network. It allows a single network to be divided into multiple smaller networks, improving security, performance, and organization.

### Key Concepts:
- **Subnet Mask**: Defines which portion of an IP address represents the network and which represents the host
- **CIDR Notation**: Example: `192.168.1.0/24` (where /24 means first 24 bits are network portion)
- **Benefits**: 
  - Reduces network congestion
  - Improves security through segmentation
  - Better network management
  - Efficient IP address utilization

### Example:
```
Network: 192.168.1.0/24
Subnet Mask: 255.255.255.0
Available IPs: 192.168.1.1 to 192.168.1.254
```

---

## 🏷️ What is a MAC Address?

**MAC (Media Access Control) Address** is a unique identifier assigned to network interface controllers (NICs) for communications at the data link layer.

### Characteristics:
- **Length**: 48 bits (6 bytes)
- **Format**: 12 hexadecimal digits (e.g., `00:1B:44:11:3A:B7`)
- **Uniqueness**: Globally unique identifier
- **Scope**: Only relevant within the same network segment
- **Burned-in**: Typically hardcoded into network hardware

### MAC Address Structure:
- **First 3 bytes**: Organizationally Unique Identifier (OUI) - identifies manufacturer
- **Last 3 bytes**: Device-specific identifier

---

## 🌐 IPv4 vs IPv6 Differences

| Aspect | IPv4 | IPv6 |
|--------|------|------|
| **Address Length** | 32 bits | 128 bits |
| **Format** | Dotted decimal (192.168.1.1) | Hexadecimal with colons (2001:0db8::1) |
| **Address Space** | ~4.3 billion addresses | ~340 undecillion addresses |
| **Header Size** | 20-60 bytes (variable) | 40 bytes (fixed) |
| **Fragmentation** | Routers and hosts | Only hosts |
| **Security** | Optional (IPSec) | Built-in (IPSec mandatory) |
| **Auto-configuration** | DHCP required | SLAAC (Stateless Address Auto-config) |
| **Checksum** | Present in header | No checksum in header |
| **Broadcasting** | Supported | Not supported (uses multicast) |

### IPv4 Example: `192.168.1.100`
### IPv6 Example: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

---

## 🚛 TCP vs UDP

| Feature | TCP (Transmission Control Protocol) | UDP (User Datagram Protocol) |
|---------|-------------------------------------|------------------------------|
| **Connection Type** | Connection-oriented | Connectionless |
| **Reliability** | Reliable (guaranteed delivery) | Unreliable (best effort) |
| **Speed** | Slower (due to overhead) | Faster (minimal overhead) |
| **Data Ordering** | Maintains order | No ordering guarantee |
| **Error Checking** | Extensive error checking | Basic error checking |
| **Flow Control** | Yes | No |
| **Header Size** | 20-24 bytes | 8 bytes |
| **Use Cases** | Web browsing, email, file transfer | Video streaming, gaming, DNS |

### TCP Three-Way Handshake:
1. **SYN**: Client initiates connection
2. **SYN-ACK**: Server acknowledges and responds
3. **ACK**: Client acknowledges, connection established

---

## 🔍 Nmap Commands Reference

### Basic Syntax:
```bash
nmap [options] [target(s)]
```

### Command Options Explained:

#### `-Pn` (Skip Host Discovery)
```bash
nmap -Pn 192.168.1.1
```
- Treats all hosts as online
- Skips ping sweep
- Useful when ICMP is blocked

#### `-A` (Aggressive Scan)
```bash
nmap -A 192.168.1.1
```
- Enables OS detection, version detection, script scanning, and traceroute
- Equivalent to `-O -sV -sC --traceroute`

#### `-sV` (Version Detection)
```bash
nmap -sV 192.168.1.1
```
- Probes open ports to determine service/version info
- Identifies what services are running and their versions

#### `-O` (OS Detection)
```bash
nmap -O 192.168.1.1
```
- Attempts to identify the target's operating system
- Uses TCP/IP stack fingerprinting

#### `-oN` (Normal Output)
```bash
nmap -oN scan_results.txt 192.168.1.1
```
- Saves scan results to a file in normal format
- Human-readable output

#### `--script` (NSE Scripts)
```bash
nmap --script vuln 192.168.1.1
nmap --script=http-title 192.168.1.1
nmap --script "not intrusive" 192.168.1.1
```
- Runs Nmap Scripting Engine (NSE) scripts
- Categories: auth, broadcast, brute, default, discovery, dos, exploit, external, fuzzer, intrusive, malware, safe, version, vuln

#### `-vv` (Very Verbose)
```bash
nmap -vv 192.168.1.1
```
- Provides detailed output during scanning
- Shows real-time progress and additional information

#### `-p-` (Scan All Ports)
```bash
nmap -p- 192.168.1.1
```
- Scans all 65,535 TCP ports
- Much slower than default scan (top 1,000 ports)

#### `-sS` (SYN Stealth Scan)
```bash
nmap -sS 192.168.1.1
```
- Half-open scan (doesn't complete TCP handshake)
- Stealthier than full connect scan
- Requires root privileges

#### `-sT` (TCP Connect Scan)
```bash
nmap -sT 192.168.1.1
```
- Full TCP connection scan
- More detectable but doesn't require root privileges
- Uses system's connect() call

### Practical Examples:

#### Comprehensive Network Scan:
```bash
nmap -A -T4 -oN comprehensive_scan.txt 192.168.1.0/24
```

#### Stealth Service Detection:
```bash
nmap -sS -sV -O -Pn --script=safe -vv 192.168.1.100
```

#### Vulnerability Assessment:
```bash
nmap --script vuln -sV -oN vuln_scan.txt target.com
```

#### Fast Port Scan:
```bash
nmap -F -sS -T5 192.168.1.1-254
```

---

## 🛡️ Ethical Considerations

### Always Remember:
- **Authorization**: Only scan networks you own or have explicit permission to test
- **Legal Compliance**: Follow local laws and regulations
- **Responsible Disclosure**: Report vulnerabilities through proper channels
- **Documentation**: Keep detailed logs of your testing activities
- **Scope Limitation**: Stay within the defined scope of your engagement

---

## 📚 Additional Resources

- **Nmap Official Documentation**: https://nmap.org/book/
- **NSE Script Database**: https://nmap.org/nsedoc/
- **RFC 791 (IPv4)**: Internet Protocol specification
- **RFC 8200 (IPv6)**: Internet Protocol Version 6 specification
- **TCP/IP Illustrated Series**: Comprehensive networking reference

---

*Remember: Knowledge is power, but with power comes responsibility. Use these skills ethically and legally.*
