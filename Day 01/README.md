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

# Zero Day Attack

## Definition
A zero day attack is a cyber attack that exploits a previously unknown vulnerability in software or hardware before developers have had time to create and distribute a security patch.

## Key Characteristics
- **Unknown vulnerability**: The security flaw is not publicly known or documented
- **No available patch**: Developers haven't released a fix for the vulnerability
- **Zero days to respond**: Organizations have "zero days" to defend against the attack once it's discovered
- **High success rate**: Attacks often succeed because there are no existing defenses

## Attack Process
1. **Discovery**: Attacker finds an unknown vulnerability
2. **Exploitation**: Develops code to exploit the vulnerability
3. **Deployment**: Launches the attack against target systems
4. **Detection**: Security researchers or vendors eventually discover the attack
5. **Patching**: Developers create and release a security update

## Why They're Dangerous
- Difficult to detect with traditional security measures
- Can cause significant damage before being discovered
- Often used in advanced persistent threats (APTs)
- High value on black markets due to their effectiveness

## Defense Strategies
- **Behavioral analysis**: Monitor for unusual system behavior
- **Sandboxing**: Isolate suspicious files and processes
- **Regular updates**: Keep all software current with latest patches
- **Network segmentation**: Limit potential damage scope
- **Threat intelligence**: Stay informed about emerging threats

## Notable Examples
- Stuxnet (2010): Targeted industrial control systems
- WannaCry (2017): Used Windows SMB vulnerability
- Various browser and operating system exploits
- For more info watch the netflix movie on Zero day

# WhatsApp Encryption

## Primary Encryption Protocol
WhatsApp uses the **Signal Protocol** (formerly TextSecure Protocol) for end-to-end encryption, developed by Open Whisper Systems.

## Key Features

### End-to-End Encryption (E2EE)
- Messages are encrypted on sender's device and only decrypted on recipient's device
- WhatsApp servers cannot read message content
- Applies to text messages, voice calls, video calls, photos, videos, and documents

### Cryptographic Components
- **AES-256**: Symmetric encryption for message content
- **Curve25519**: Elliptic curve cryptography for key exchange
- **HMAC-SHA256**: Message authentication
- **Double Ratchet Algorithm**: Provides forward secrecy and future secrecy

## Security Mechanisms

### Key Exchange
- **X3DH (Extended Triple Diffie-Hellman)**: Initial key agreement protocol
- **Prekey bundles**: Allow secure communication even when recipient is offline
- **Identity keys**: Long-term cryptographic identity for each user

### Forward Secrecy
- New encryption keys generated for each message
- Compromising one key doesn't affect other messages
- Old keys are automatically deleted

### Authentication
- Safety numbers (QR codes/60-digit codes) verify encryption keys
- Prevents man-in-the-middle attacks
- Users can verify each other's identity

## What's Protected
- Message content
- Voice and video calls
- Media files (photos, videos, documents)
- Status updates
- Group messages

## What's Not Encrypted
- Metadata (who, when, frequency of communication)
- Profile information
- Contact lists
- Backup files (unless backup encryption is enabled)

## Limitations
- Metadata collection by WhatsApp/Meta
- Potential vulnerabilities in implementation
- No protection against endpoint compromise
- Backup encryption is optional and not default
