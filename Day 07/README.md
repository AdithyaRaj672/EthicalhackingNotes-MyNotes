Day 07

Ethical Hacking

# Day 7: Ethical Hacking - Scanning & Network Reconnaissance

## Overview
This lesson covers network scanning fundamentals, IP address types, and practical use of Nmap for ethical hacking reconnaissance.

---

## 1. Introduction to Scanning

### What is Scanning?
Scanning is the process of identifying active hosts, open ports, and services running on a network. It's a crucial phase in the ethical hacking methodology that comes after footprinting and before enumeration.

### Purpose of Scanning
- Discover live systems on a network
- Identify open ports and services
- Determine operating systems and versions
- Map network topology
- Gather information for vulnerability assessment

---

## 2. Types of Scanning

### 2.1 Network Scanning
- **Purpose**: Identify live hosts on a network
- **Methods**: Ping sweeps, ARP scans, ICMP scans
- **Output**: List of active IP addresses

### 2.2 Port Scanning
- **Purpose**: Identify open ports on target systems
- **Common ports**: 
  - 21 (FTP)
  - 22 (SSH)
  - 23 (Telnet)
  - 25 (SMTP)
  - 53 (DNS)
  - 80 (HTTP)
  - 443 (HTTPS)
  - 3389 (RDP)

### 2.3 Service Scanning
- **Purpose**: Identify services and their versions running on open ports
- **Techniques**: Banner grabbing, service fingerprinting
- **Information gathered**: Service names, versions, configurations

### 2.4 Vulnerability Scanning
- **Purpose**: Identify known security vulnerabilities
- **Tools**: Nessus, OpenVAS, Nikto
- **Output**: Vulnerability reports with severity ratings

---

## 3. IP Addresses: Public vs Private

### 3.1 Public IP Addresses
- **Definition**: Globally unique addresses routable on the internet
- **Assignment**: Managed by Internet Service Providers (ISPs)
- **Characteristics**:
  - Directly accessible from the internet
  - Required for hosting public services
  - Limited in number (IPv4 exhaustion)

### 3.2 Private IP Addresses
- **Definition**: Addresses used within private networks, not routable on the internet
- **RFC 1918 Private IP Ranges**:
  - Class A: `10.0.0.0/8` (10.0.0.0 to 10.255.255.255)
  - Class B: `172.16.0.0/12` (172.16.0.0 to 172.31.255.255)
  - Class C: `192.168.0.0/16` (192.168.0.0 to 192.168.255.255)

### 3.3 Key Differences
| Aspect | Public IP | Private IP |
|--------|-----------|------------|
| Internet Access | Direct | Through NAT/Router |
| Uniqueness | Globally unique | Unique within local network |
| Cost | Usually costs money | Free to use |
| Security | More exposed | Protected by NAT |

---

## 4. IP Scanning Techniques

### 4.1 Ping Sweep
- **Method**: Send ICMP Echo Request packets to range of IPs
- **Command**: `ping 192.168.1.1`
- **Limitations**: Many systems block ICMP

### 4.2 TCP Connect Scan
- **Method**: Attempt full TCP connection to each port
- **Characteristics**: Reliable but slow and easily detected
- **States**: Open, Closed, Filtered

### 4.3 SYN Scan (Stealth Scan)
- **Method**: Send SYN packet, analyze response
- **Advantages**: Faster, less detectable
- **Responses**:
  - SYN/ACK = Open port
  - RST = Closed port
  - No response = Filtered

### 4.4 UDP Scan
- **Method**: Send UDP packets to ports
- **Challenges**: UDP is connectionless, harder to determine state
- **Common UDP ports**: 53 (DNS), 69 (TFTP), 161 (SNMP)

---

## 5. Nmap (Network Mapper)

### 5.1 What is Nmap?
Nmap is a powerful, open-source network scanning tool used for network discovery and security auditing. It's considered the gold standard for port scanning.

### 5.2 Basic Nmap Syntax
```bash
nmap [Scan Type] [Options] [Target Specification]
```

### 5.3 Common Nmap Scan Types

#### Host Discovery
```bash
# Ping sweep
nmap -sn 192.168.1.0/24

# ARP scan (local network)
nmap -PR 192.168.1.0/24
```

#### Port Scanning
```bash
# TCP SYN scan (default)
nmap -sS 192.168.1.100

# TCP Connect scan
nmap -sT 192.168.1.100

# UDP scan
nmap -sU 192.168.1.100

# Comprehensive scan
nmap -sS -sU 192.168.1.100
```

#### Service Detection
```bash
# Service version detection
nmap -sV 192.168.1.100

# OS detection
nmap -O 192.168.1.100

# Aggressive scan (OS, version, script, traceroute)
nmap -A 192.168.1.100
```

### 5.4 Nmap Port Specifications
```bash
# Specific ports
nmap -p 80,443 192.168.1.100

# Port range
nmap -p 1-1000 192.168.1.100

# All ports
nmap -p- 192.168.1.100

# Common ports
nmap --top-ports 100 192.168.1.100
```

### 5.5 Nmap Timing Options
```bash
# Timing templates (0-5)
nmap -T0 192.168.1.100  # Paranoid (slowest)
nmap -T1 192.168.1.100  # Sneaky
nmap -T2 192.168.1.100  # Polite
nmap -T3 192.168.1.100  # Normal (default)
nmap -T4 192.168.1.100  # Aggressive
nmap -T5 192.168.1.100  # Insane (fastest)
```

### 5.6 Nmap Output Options
```bash
# Normal output
nmap 192.168.1.100

# Verbose output
nmap -v 192.168.1.100

# Save to file
nmap -oN scan_results.txt 192.168.1.100
nmap -oX scan_results.xml 192.168.1.100
nmap -oG scan_results.gnmap 192.168.1.100
```

### 5.7 Nmap Scripts (NSE)
```bash
# Default scripts
nmap -sC 192.168.1.100

# Specific script category
nmap --script vuln 192.168.1.100

# Specific script
nmap --script http-title 192.168.1.100
```

---

## 6. Practical Examples

### 6.1 Basic Network Discovery
```bash
# Discover live hosts on local network
nmap -sn 192.168.1.0/24
```

### 6.2 Port Scan a Single Host
```bash
# Quick port scan
nmap -F 192.168.1.100

# Detailed service scan
nmap -sV -O 192.168.1.100
```

### 6.3 Scan Multiple Targets
```bash
# Multiple IPs
nmap 192.168.1.1 192.168.1.5 192.168.1.10

# IP range
nmap 192.168.1.1-50

# From file
nmap -iL targets.txt
```

---

## 7. Ethical Considerations & Best Practices

### 7.1 Legal Guidelines
- Only scan systems you own or have explicit permission to test
- Follow responsible disclosure practices
- Document all scanning activities
- Respect rate limits and avoid disrupting services

### 7.2 Defensive Considerations
- **Firewalls**: Can block or filter scan attempts
- **IDS/IPS**: May detect and alert on scanning activities
- **Rate limiting**: Slow scans to avoid detection
- **Decoy scans**: Use decoy IPs to mask source

### 7.3 Best Practices
- Start with less intrusive scans
- Document findings thoroughly
- Use appropriate timing options
- Combine multiple scanning techniques
- Verify results with different tools

---

## 8. Key Takeaways

1. **Scanning is essential** for network reconnaissance and vulnerability assessment
2. **Different scan types** serve different purposes (host discovery, port scanning, service detection)
3. **Public vs Private IPs** have different security implications and use cases
4. **Nmap is versatile** and offers numerous options for different scanning scenarios
5. **Ethical considerations** are paramount in any scanning activity
6. **Combining techniques** provides more comprehensive results than single approaches

---

## 9. Next Steps & Further Learning

- Practice Nmap commands in a lab environment
- Learn about firewall evasion techniques
- Study network protocols in depth
- Explore advanced Nmap scripts (NSE)
- Understand how to interpret and analyze scan results
- Learn about network segmentation and defense strategies

---

## Resources for Further Study
- Nmap official documentation: https://nmap.org/docs.html
- RFC 1918 (Private Internet Address Allocation)
- OWASP Testing Guide
- "Nmap Network Scanning" by Gordon Lyon
