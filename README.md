# Bobcat 300 Custom Debian Distribution
A custom Debian 11 Bullseye distribution specifically built for Bobcat 300 miners with optimized kernel and configuration. 

## 📋 Overview
This distribution provides a stable, lightweight Debian environment for Bobcat 300 miners with pre-configured settings and optimizations for mining operations. 

### System Specifications
- **Base OS**: Debian 11 Bullseye
- **Kernel**: Linux 4.19.232
- **Architecture**: Compatible with ARM-based Bobcat 300 hardware

### Supported Models and Download Links
- [Bobcat 300 G280](https://github.com/sicXnull/Bobcat300-Debian/releases/download/1.0/BobcatDebian280.img.xz) 
- [Bobcat 300 G285](https://github.com/sicXnull/Bobcat300-Debian/releases/download/1.0/BobcatDebian285.img.xz) 
- [Bobcat 300 G290](https://github.com/sicXnull/Bobcat300-Debian/releases/download/1.0/BobcatDebian29X.img.xz)
- [Bobcat 300 G295](https://github.com/sicXnull/Bobcat300-Debian/releases/download/1.0/BobcatDebian29X.img.xz)

### Feature Compatibility

#### ✅ Preinstalled
- ✅ Docker
- ✅ Helium Miner Container
- ✅ Packet Forwarder

#### ✅ What Works
- ✅ WiFi

#### ⚠️ Partially Working
- ⚠️ Bluetooth (limited functionality)

#### ❌ What Doesn't Work
- ❌ Onboarding

## 🔐 Default Credentials

### System Access
- **Username**: `root`
- **Password**: `bobcat`

### Web Dashboard ([Source Code](https://github.com/sicXnull/BobcatDashboard))
- **URL**: `https://[device-ip]`
- **Username**: `admin`
- **Password**: `admin`

> ⚠️ **Security Notice**: Change default passwords immediately after installation for production use.

## 📦 Installation Instructions

### Prerequisites
- Bobcat 300 miner (G280, G285, G290, or G295)
- MicroSD card (16GB or larger recommended)
- SD card reader
- Computer with Etcher or DD utility

### Installation Steps

1. **Download the Image**
   - Download the `.xz` compressed image file
   - Verify the download integrity if checksums are provided

2. **Prepare the SD Card**
   ```bash
   # Using Etcher (Recommended - GUI method)
   # 1. Open Etcher
   # 2. Select the downloaded .xz file
   # 3. Select your SD card
   # 4. Click "Flash"
   
   # Using DD (Command line method)
   # First, extract the image
   xz -d bobcat-debian-image.xz
   
   # Then write to SD card (replace /dev/sdX with your SD card device)
   sudo dd if=bobcat-debian-image.img of=/dev/sdX bs=4M status=progress
   sudo sync
   ```

3. **Install on Bobcat Miner**
   - Power off your Bobcat 300 miner
   - Insert the prepared SD card into the miner
   - Power on the device
   - Wait for the system to boot (first boot may take longer)

## 🌐 Network Configuration

### Finding Your Device IP
The device will obtain an IP address via DHCP. Check your router's admin panel or use network scanning tools:

### Accessing the Web Dashboard
1. Open a web browser
2. Navigate to `https://[your-device-ip]`
3. Accept the self-signed certificate warning
4. Login with credentials: `admin` / `admin`
5. Navigate to Tools -> Set Region to set your Region (US915,etc)

## 🛠️ Troubleshooting

### Common Issues

**Device won't boot:**
- Verify SD card is properly inserted
- Check if image was written correctly
- Try re-flashing the SD card

**Can't access web dashboard:**
- Verify device IP address
- Check if device is connected to network
- Ensure firewall isn't blocking HTTPS traffic

## ⚡ Performance Optimization

### Recommended Settings
- Use Class 10 or better SD card for optimal performance
- Ensure adequate cooling for continuous operation
- Regular system updates and maintenance

### System Monitoring
```bash
# Monitor system temperature
sensors

# Check memory usage
free -h

# Monitor disk I/O
iotop
```

## 🔒 Security Recommendations

1. **Change Default Passwords**
   ```bash
   # Change root password
   passwd root
   
   # Change web admin password via dashboard settings
   ```

2. **Regular Updates**
   ```bash
   apt update && apt upgrade
   ```

## 📄 License and Disclaimer

This custom Debian distribution is provided as-is. Users are responsible for:
- Backing up important data before installation
- Ensuring compatibility with their specific hardware
- Following proper security practices
- Compliance with local regulations regarding mining operations
