# humbleOS

![Arch Linux](https://img.shields.io/badge/Arch_Linux-1793D1?style=for-the-badge&logo=arch-linux&logoColor=white)
![KDE Plasma](https://img.shields.io/badge/KDE_Plasma-1D99F3?style=for-the-badge&logo=kde&logoColor=white)

## Overview

humbleOS is an automated Arch Linux installation configuration featuring KDE Plasma desktop environment, essential utilities, and development tools. This repository provides a complete archinstall JSON configuration for quick and consistent Arch Linux deployments.

## Features

### System Configuration
- **Hostname**: humbleOS
- **Disk**: Full `/dev/sda` installation with Btrfs filesystem
- **Bootloader**: GRUB with os-prober support
- **Locale**: en_US.UTF-8
- **Keyboard**: US layout

### Desktop Environment
- **KDE Plasma** with X11
- **SDDM** display manager
- Plasma Network Manager (plasma-nm)
- Plasma Add-ons

### Kernels
- Linux (mainline)
- Linux LTS (Long Term Support)
- Linux Hardened

### User Accounts
- **Root user**: Password set to `humbleOS`
- **Primary user**: `humble` with sudo privileges, password: `humble`

⚠️ **Security Notice**: Change these default passwords immediately after installation!

### Included Software

#### Development Tools
- base-devel
- git
- yay (AUR helper)

#### Productivity
- LibreOffice Still
- Firefox
- VLC Media Player

#### Utilities
- htop, neofetch, nmap
- vim, nano
- unzip, zip
- flameshot (screenshots)
- timeshift (Btrfs snapshots)
- GIMP (image editing)
- Kdenlive (video editing)
- qBittorrent
- filezilla
- gnome-disk-utility
- partitionmanager
- discover (KDE package manager)

#### System & Network
- NetworkManager
- ufw (firewall)
- firewalld

#### Fonts
- ttf-dejavu
- ttf-liberation
- noto-fonts
- noto-fonts-emoji

#### Shell Options
- fish
- zsh

## Installation Instructions

### Prerequisites
1. Boot into Arch Linux installation media
2. Ensure you have internet connectivity
3. **Backup any important data** - this will erase `/dev/sda`!

### Using the Configuration

1. Download the configuration file:
```bash
curl -O https://raw.githubusercontent.com/Steve56UX/humbleOS/main/archinstall_autoinstall.json
```

2. Run archinstall with the configuration:
```bash
archinstall --config archinstall_autoinstall.json
```

3. Follow any prompts and wait for installation to complete

4. Reboot into your new humbleOS system:
```bash
reboot
```

### Post-Installation

1. **Change default passwords**:
```bash
passwd root
passwd humble
```

2. **Update system**:
```bash
sudo pacman -Syu
```

3. **Enable firewall**:
```bash
sudo ufw enable
```

4. **Configure Timeshift** for system snapshots

## Manual Configuration Generation

You can also generate a configuration interactively:

```bash
archinstall
```

After completing the interactive setup, archinstall will offer to save your configuration for future use.

## Customization

To customize this configuration:

1. Clone this repository
2. Edit `archinstall_autoinstall.json`
3. Modify packages, users, or system settings as needed
4. Use your modified configuration for installation

## Repository Contents

- `README.md` - This file
- `archinstall_autoinstall.json` - Complete archinstall configuration

## Important Notes

- ⚠️ This configuration will **erase all data** on `/dev/sda`
- Default passwords are intentionally simple - **change them immediately**
- The configuration uses Btrfs for easy snapshot management
- Multiple kernels are installed for flexibility and fallback options
- NetworkManager is configured for DHCP by default

## Troubleshooting

### Installation Issues
- Ensure your system supports UEFI if using GPT partitioning
- Verify internet connectivity before starting
- Check that `/dev/sda` is the correct target disk

### Post-Installation
- If display manager doesn't start, try: `sudo systemctl enable sddm`
- For network issues: `sudo systemctl enable NetworkManager`
- Check logs: `journalctl -xe`

## Contributing

Feel free to submit issues or pull requests to improve this configuration!

## License

This project is provided as-is for educational and personal use.

## Acknowledgments

- Arch Linux community
- archinstall developers
- KDE Plasma team

---

**Built with ❤️ for the Arch Linux community**
