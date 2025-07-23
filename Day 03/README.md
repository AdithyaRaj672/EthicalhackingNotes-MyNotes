# EthicalHacking Notes - Day 03
**Date:** 21/07/2025

**Duration:** 2 hours  

**Focus:**  Kali Linux & Villain
---
### What is Kali Linux?
- Debian-based Linux distribution designed for digital forensics and penetration testing
- Pre-installed with numerous security tools and utilities
- Maintained by Offensive Security

### Essential Kali Linux Commands

#### System Information
```bash
# Check system information
uname -a
lsb_release -a

# Check network interfaces
ifconfig
ip addr show

# Check running processes
ps aux
top
htop
```

#### File System Navigation
```bash
# Basic navigation
ls -la          # List files with details
cd /path/       # Change directory
pwd             # Print working directory
find / -name "filename"  # Find files
```

#### Network Commands
```bash
# Network scanning
nmap -sn 192.168.1.0/24    # Ping scan
nmap -sV target_ip         # Service version detection
netstat -tulpn             # Show listening ports
```

#### Package Management
```bash
# Update system
sudo apt update && sudo apt upgrade

# Search for tools
apt search [tool_name]

# Install packages
sudo apt install [package_name]
```

### Key Directories in Kali
- `/usr/share/` - Contains most security tools
- `/opt/` - Optional software packages
- `/home/kali/` - User home directory
- `/etc/` - Configuration files

---

## Villain Framework

### What is Villain?
- Post-exploitation framework designed for Windows environments
- Provides Command & Control (C2) capabilities
- Useful for penetration testing and red team operations
- **Note: Use only in authorized testing environments**

### Villain Installation on Kali Linux

#### Prerequisites
```bash
# Update system first
sudo apt update && sudo apt upgrade

# Install Python3 and pip if not already installed
sudo apt install python3 python3-pip git
```

#### Installation Steps

1. **Clone the Repository**
```bash
git clone https://github.com/t3l3machus/Villain.git
cd Villain
```

2. **Install Dependencies**
```bash
pip3 install -r requirements.txt
```

3. **Make Executable**
```bash
chmod +x Villain.py
```

4. **Run Villain**
```bash
python3 Villain.py
```

### Villain Basic Usage

#### Starting the Framework
```bash
# Basic startup
python3 Villain.py

# Start with specific interface
python3 Villain.py -i eth0

# Start with custom port
python3 Villain.py -p 8080
```

#### Key Villain Commands
```bash
# Generate payload
generate           # Create Windows executable payload

# Start listener
listen             # Start listening for connections

# List sessions
sessions           # Show active sessions

# Interact with session
use session_id     # Switch to specific session
```

### Payload Generation
- Generates Windows executables (.exe files)
- Can create PowerShell scripts
- Supports various encoding methods
- Always test in isolated environments

---

## Important Security Considerations

### Legal and Ethical Guidelines
- **Only use on systems you own or have explicit permission to test**
- Always obtain written authorization before testing
- Follow responsible disclosure practices
- Respect privacy and data protection laws

### Lab Environment Setup
- Use isolated virtual machines
- Never test on production systems
- Document all testing activities
- Have proper backups before testing

### Best Practices
- Keep Kali Linux updated regularly
- Use strong passwords for all accounts
- Enable firewall when not actively testing
- Store sensitive data securely

---

## Common Troubleshooting

### Villain Installation Issues
```bash
# If pip packages fail to install
sudo apt install python3-dev build-essential

# If git clone fails
sudo apt install git

# Permission errors
sudo chmod +x Villain.py
```

### Network Issues
```bash
# Check network connectivity
ping google.com

# Verify interface configuration
ifconfig
```

---

## Additional Resources

### Useful Kali Tools to Explore
- **Nmap** - Network discovery and security auditing
- **Metasploit** - Penetration testing framework
- **Burp Suite** - Web application security testing
- **Wireshark** - Network protocol analyzer
- **John the Ripper** - Password cracking tool

### Learning Resources
- Kali Linux official documentation
- Offensive Security training materials
- Ethical hacking certification courses
- Penetration testing methodologies (OWASP, NIST)

---

## Class Notes Section

### Key Points from Today's Lesson
- [ ] Kali Linux file system structure
- [ ] Basic command line navigation
- [ ] Network reconnaissance basics
- [ ] Villain framework overview
- [ ] Legal considerations in ethical hacking
