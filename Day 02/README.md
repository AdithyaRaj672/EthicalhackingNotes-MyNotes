# EthicalHacking Notes - Day 02
**Date:** 18/07/2025

**Duration:** 2 hours  

**Focus:** Installing Kali Linux & Virtualbox

---

# Kali Linux Pre-built VM Installation Guide for Windows

## Prerequisites

### System Requirements
- Windows 10/11 (64-bit recommended)
- Minimum 8GB RAM (16GB+ recommended)
- At least 25GB free disk space
- Virtualization enabled in BIOS/UEFI
- Stable internet connection
---
### Required Downloads
1. **VirtualBox** - Latest version from Oracle VirtualBox website `https://www.virtualbox.org/wiki/Downloads`
2. **7-Zip** - Download from the the official website for unpacking the Kali file `https://www.7-zip.org/`
3. **Kali Linux Pre-built VM** - From official Kali Linux downloads page `https://www.kali.org/get-kali/#kali-virtual-machines`
---
## Step 1: Installing VirtualBox on Windows

### Installation Process
1. Download VirtualBox installer (.exe) from official Oracle website
2. Run installer as Administrator
3. Accept default installation settings
4. Open windows after installation type **add features**
5. Turn on the features **Virtual Machine Platform** and **Windows Hypervision Platform**
6. Restart Windows after installation and adding the features completes
---
## Step 2: Downloading Kali Linux Pre-built VM

### Download Options
1. Visit official Kali Linux downloads page
2. Navigate to **Virtual Machines** section
3. Download VirtualBox version
4. File size typically 3.3GB compressed
---
## Step 3: Setting Up Kali VM in VirtualBox
1. Unzip the Kali file using 7 Zip 
2. Open the Kali file
3. Double click or open the **Virtual Box Machine File**
4. You will be redirected to Virtual Box Application with Kali imported in it
---
## Step 4: First Boot and Initial Setup

### Starting the VM
1. Select Kali VM in VirtualBox Manager
2. Click "Start" button
3. Wait for boot process to complete
---
### Default Credentials
- **Username**: `kali`
- **Password**: `kali`

### Initial Configuration Steps
1. Update system: `sudo apt update && sudo apt upgrade -y`
2. Change default password: `passwd` (Optional)
3. Configure keyboard layout if needed
4. Install VirtualBox Guest Additions (see troubleshooting section)
---
## Common Problems and Solutions

### Problem 1: Virtualization Not Enabled
**Symptoms**: VM fails to start, error about VT-x/AMD-V
**Solution**:
1. Restart computer and enter BIOS/UEFI
2. Navigate to CPU/Advanced settings
3. Enable Intel VT-x or AMD-V
4. Enable Intel VT-d or AMD IOMMU if available
5. Save and exit BIOS
---
### Problem 2: VM Running Slowly
**Symptoms**: Sluggish performance, high CPU usage
**Solutions**:
1. Increase RAM allocation (minimum 2GB)
2. Assign more CPU cores
3. Enable hardware acceleration in VM settings
4. Close unnecessary Windows applications
5. Disable Windows real-time antivirus scanning for VM folder
---
### Problem 3: Screen Resolution Issues
**Symptoms**: Low resolution, unable to resize display
**Solution - Install Guest Additions**:
1. Start Kali VM
2. Insert Guest Additions CD: `Devices → Insert Guest Additions CD Image`
3. Open terminal in Kali
4. Run: `sudo apt update && sudo apt install -y dkms build-essential linux-headers-generic`
5. Mount and install: `sudo sh /media/cdrom/VBoxLinuxAdditions.run`
6. Reboot VM
7. Enable auto-resize: `View → Auto-resize Guest Display`
---
### Problem 4: Network Connectivity Issues
**Symptoms**: No internet access in VM
**Solutions**:
1. Check VM network settings (NAT should work for most cases)
2. In Kali terminal: `sudo dhclient eth0`
3. Reset network: `sudo systemctl restart networking`
4. Windows firewall: Add VirtualBox to exceptions
5. Try different network adapter types (Intel PRO/1000, PCnet-PCI II)
---
### Problem 5: USB Devices Not Recognized
**Symptoms**: USB devices don't appear in VM
**Solution**:
1. Ensure VirtualBox Extension Pack is installed
2. Add user to vboxusers group in Windows
3. Enable USB in VM settings
4. Select USB 2.0 or 3.0 Controller
5. Add USB filters for specific devices
---
### Problem 6: Audio Not Working
**Symptoms**: No sound in Kali VM
**Solution**:
1. VM Settings → Audio
2. Enable Audio
3. Host Audio Driver: Windows DirectSound
4. Audio Controller: Intel HD Audio
5. In Kali: `sudo apt install pulseaudio pavucontrol`
---
### Problem 7: Shared Folders Not Working
**Symptoms**: Cannot access Windows folders from Kali
**Solution**:
1. Install Guest Additions first
2. VM Settings → Shared Folders → Add folder
3. Choose Windows folder and mount point
4. Enable "Auto-mount" and "Make Permanent"
5. In Kali: `sudo adduser kali vboxsf`
6. Reboot VM
7. Access via `/media/sf_foldername`
---
### Problem 8: VM Won't Start After Windows Update
**Symptoms**: VirtualBox fails to start VMs after Windows update
**Solution**:
1. Disable Hyper-V: `bcdedit /set hypervisorlaunchtype off`
2. Restart Windows
3. Alternatively, use Windows Hypervisor Platform compatibility
4. VirtualBox Settings → Enable Hyper-V support
---
## Performance Optimization Tips

### Host System Optimization
1. Close unnecessary Windows applications
2. Disable Windows visual effects
3. Add VM folder to antivirus exclusions
4. Use SSD storage if available
5. Ensure adequate free disk space (20%+)

### VM Optimization
1. Allocate optimal RAM (50-75% of available)
2. Enable hardware acceleration
3. Adjust video memory based on usage
4. Use fixed-size disk instead of dynamic
5. Disable unnecessary startup services in Kali
---
## Security Considerations

### Isolation Best Practices
1. Use snapshots before major changes
2. Keep VM and host systems updated
3. Use Host-only networking for isolation
4. Regular backups of VM files
5. Consider using separate user account for VMs

### Kali-Specific Security
1. Change default passwords immediately
2. Keep Kali tools updated: `sudo apt update && sudo apt full-upgrade`
3. Use non-root user for daily operations
4. Enable firewall if needed: `sudo ufw enable`
---
## Maintenance and Updates

### Regular Maintenance
1. **Weekly**: Update Kali packages
2. **Monthly**: Clean package cache: `sudo apt autoremove && sudo apt autoclean`
3. **As needed**: Create VM snapshots before major changes
4. **Quarterly**: Check for VirtualBox updates

### Backup Strategy
1. Export VM regularly: `File → Export Appliance`
2. Backup important files to host system
3. Keep multiple snapshots for rollback capability
4. Document custom configurations
