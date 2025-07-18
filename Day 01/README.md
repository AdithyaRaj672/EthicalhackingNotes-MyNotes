# Header 1
## Header 2
### Header 3
```python
def hello():
    print("Hello, World!")
```

# EthicalHacking Notes - Day 01
*Date:* 15/07/2025 
*Duration:* 2 hours  
*Focus:* Introduction To Cyber Security

---
### What is Ethical Hacking?

Ethical hacking, also known as penetration testing or white-hat hacking, is the practice of intentionally probing systems, networks, and applications to find security vulnerabilities before malicious attackers do.

**Key Principles:**
- **Authorization**: Always have explicit permission before testing
- **Documentation**: Record all findings and methods used
- **Responsible disclosure**: Report vulnerabilities to appropriate parties
- **Legal compliance**: Follow all applicable laws and regulations

### Core Principles (CIA Triad):
- *Confidentiality*: Ensuring information is accessible only to authorized individuals
- *Integrity*: Maintaining accuracy and completeness of data
- *Availability*: Ensuring systems and data are accessible when needed

---

## 🛡 Three Major Divisions of Cyber Security Teams

### 1. *Red Team* 🔴
- *Role*: Offensive security (Attackers)
- *Focus*: Simulating real-world attacks to find vulnerabilities
- *Activities*: Penetration testing, social engineering, exploit development
- *Skills*: Ethical hacking, vulnerability assessment, attack simulation
- *Goal*: Think like attackers to identify weaknesses before malicious hackers do

### 2. *Blue Team* 🔵
- *Role*: Defensive security (Defenders)
- *Focus*: Protecting, monitoring, and responding to security threats
- *Activities*: Security monitoring, incident response, threat hunting, forensics
- *Skills*: SIEM management, log analysis, incident handling, network defense
- *Goal*: Detect, prevent, and respond to security incidents

### 3. *Purple Team* 🟣
- *Role*: Collaborative security (Bridge between Red and Blue)
- *Focus*: Combining offensive and defensive approaches
- *Activities*: Coordinating red/blue exercises, sharing threat intelligence, continuous improvement
- *Skills*: Both offensive and defensive techniques, communication, strategic planning
- *Goal*: Maximize security effectiveness through collaboration and knowledge sharing

---

## 👥 Types of Hackers

### White Hat Hackers (Ethical Hackers)
- Work with permission to find and fix vulnerabilities
- Follow legal and ethical guidelines
- Help organizations improve security

### Black Hat Hackers (Malicious Hackers)
- Exploit vulnerabilities for personal gain
- Operate without permission
- May cause damage or steal data

### Grey Hat Hackers
- Fall between white and black hat
- May discover vulnerabilities without permission but don't exploit maliciously
- Often notify organizations about findings

### Red Hat Hackers
- Vigilante hackers who target black hat hackers
- Use aggressive methods to stop malicious activities
- Often work to take down black hat operations

### Script Kiddies
- Use existing tools and scripts created by others
- Limited technical knowledge and skills
- Often motivated by curiosity or showing off rather than malicious intent

### Hacktivists
- Hack for political or social causes
- Target organizations they oppose ideologically
- Examples: Anonymous, WikiLeaks operations

### State-Sponsored Hackers
- Government-backed cyber operatives
- Conduct cyber espionage and warfare
- Well-funded with advanced capabilities and resources

### Cyber Terrorists
- Use cyber attacks to cause fear and disruption
- Target critical infrastructure and essential services
- Motivated by ideological or political extremism

---
## 🌐 Types of Cybersecurity Threats

- *Phishing*: Fraudulent communications designed to steal sensitive information like usernames, passwords, and credit card details

- *Ransomware*: Malicious software that encrypts victim's files and demands payment for decryption

- *Malware*: General term for malicious software including viruses, worms, trojans, and spyware

- *Social Engineering*: Psychological manipulation techniques used to trick people into divulging confidential information

- *Man-in-the-Middle (MitM)*: Intercepting and potentially altering communications between two parties

- *Zero-Day Attack*: Exploiting previously unknown vulnerabilities before patches are available

---

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
---
### Essential Tools for Ethical Hackers

#### Operating Systems
- **Kali Linux**: Penetration testing distribution
- **Virual Box**: Safe environment for testing your hacking skills and running linux
- **Windows**: For Windows-specific testing
---
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
---
### SCADA and Industrial Control Systems

#### What is SCADA?
- **SCADA**: Supervisory Control and Data Acquisition (For more info watch youtube videos)
- Used in critical infrastructure (power grids, water treatment, manufacturing)
- **SCADA Programmer**: Develops software for monitoring and controlling industrial processes
---
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
---
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
---
## Important Acronyms and Full Forms

*VAPT*: Vulnerability Assessment and Penetration Testing  
*IPS*: Intrusion Prevention System  
*IDS*: Intrusion Detection System  
*POC*: Proof of Concept  
*SOC*: Security Operations Center  
*SIEM*: Security Information and Event Management  
*SAAS*: Software as a Service  
*SSL*: Secure Sockets Layer  
*TLS*: Transport Layer Security  
