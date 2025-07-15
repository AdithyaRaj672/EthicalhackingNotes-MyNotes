# Header 1
## Header 2
### Header 3
```python
def hello():
    print("Hello, World!")
```

# Ethical Hacking Course Notes

## Class 1 - Introduction to Ethical Hacking (2 Hours)

### What is Ethical Hacking?

Ethical hacking, also known as penetration testing or white-hat hacking, is the practice of intentionally probing systems, networks, and applications to find security vulnerabilities before malicious attackers do.

**Key Principles:**
- **Authorization**: Always have explicit permission before testing
- **Documentation**: Record all findings and methods used
- **Responsible disclosure**: Report vulnerabilities to appropriate parties
- **Legal compliance**: Follow all applicable laws and regulations

### Types of Hackers

1. **White Hat Hackers (Ethical Hackers)**
   - Work to improve security
   - Have proper authorization
   - Follow responsible disclosure

2. **Black Hat Hackers (Malicious Hackers)**
   - Exploit systems for personal gain
   - Cause damage or steal data
   - Act without permission

3. **Grey Hat Hackers**
   - Fall between white and black hat
   - May find vulnerabilities without permission but don't cause harm
   - Often notify organizations of findings

### Phases of Ethical Hacking

#### 1. Reconnaissance (Information Gathering)
- **Passive Reconnaissance**: Gathering information without directly interacting with target
- **Active Reconnaissance**: Direct interaction with target systems
- Tools: Google dorking, social media analysis, DNS lookups

#### 2. Scanning and Enumeration
- Port scanning to identify open services
- Service enumeration to determine versions and configurations
- Vulnerability scanning
- Tools: Nmap, Nessus, OpenVAS

#### 3. Gaining Access
- Exploiting identified vulnerabilities
- Password attacks
- Social engineering
- Physical access attempts

#### 4. Maintaining Access
- Installing backdoors
- Privilege escalation
- Covering tracks
- Establishing persistence

#### 5. Analysis and Reporting
- Documenting all findings
- Risk assessment
- Recommendations for remediation
- Executive summary for management

### Legal and Ethical Considerations

#### Legal Framework
- **Computer Fraud and Abuse Act (CFAA)** - US federal law
- **Data Protection regulations** (GDPR, CCPA)
- **Industry-specific regulations** (HIPAA, PCI-DSS)

#### Ethical Guidelines
- Only test systems you own or have explicit permission to test
- Do not cause damage or disruption
- Respect privacy and confidentiality
- Report vulnerabilities responsibly

#### Network Security Issues
- Unencrypted communications
- Weak authentication mechanisms
- Unnecessary open ports
- Outdated software and systems

### Essential Tools for Ethical Hackers

#### Operating Systems
- **Kali Linux**: Penetration testing distribution
- **Virual Box**: Safe environment for testing your hacking skills and running linux
- **Windows**: For Windows-specific testing

### Cryptography Basics

#### Key Concepts
- **Encryption**: Converting plaintext to ciphertext
- **Decryption**: Converting ciphertext back to plaintext
- **Hashing**: One-way function for data integrity
- **Digital signatures**: Authentication and non-repudiation

#### Common Protocols
- **SSL/TLS**: Secure communication over networks
  - SSL: Secure Sockets Layer (deprecated)
  - TLS: Transport Layer Security (current standard)
- **HTTPS**: HTTP over TLS/SSL
- **SSH**: Secure Shell for remote access

### SCADA and Industrial Control Systems

#### What is SCADA?
- **SCADA**: Supervisory Control and Data Acquisition (For more info watch youtube videos)
- Used in critical infrastructure (power grids, water treatment, manufacturing)
- **SCADA Programmer**: Develops software for monitoring and controlling industrial processes
