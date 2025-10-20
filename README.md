# rtinst (Modernized)

This project is a modernized and enhanced version of the original rtinst seedbox installation script by arakasi72. It has been updated for better performance, security, and compatibility with modern operating systems, including Ubuntu 24.04.

**Original Repository:** https://github.com/arakasi72/rtinst

## Key Features and Improvements

This version includes several significant improvements over the original script:

- **Modern OS Support:** Full compatibility with Ubuntu 24.04, 22.04, 20.04 and Debian 12, 11.
- **Let's Encrypt SSL:** The script now automatically installs Let's Encrypt SSL certificates, providing a secure HTTPS connection out of the box.
- **Optional Tracker Favicon Fetcher:** Automatically downloads and updates tracker icons for the ruTorrent tracklabels plugin, making it easier to identify torrents at a glance.
- **System Optimizations:** Includes automated optimizations for VPS stability, including filesystem checks, memory and disk cache tuning, and I/O scheduler configuration for virtual disks.
- **Enhanced Monitoring and Logging:**
  - `view-all-logs.sh`: A comprehensive, color-coded log viewer for real-time monitoring of all critical services.
  - `disk-maintenance.sh`: A daily cron job to monitor disk health, inode usage, and system memory.
  - `rtorrent-maintenance.sh`: A cron job that runs every 10 minutes to ensure rTorrent and related processes are running correctly.
- **Modern Software Stack:** Utilizes up-to-date packages, including PHP 8.3, and includes modern configurations for Nginx and rTorrent.
- **Improved Security:**
  - Enhanced SSH security settings.
  - Modern SSL/TLS settings and security headers for Nginx.
- **Bug Fixes and Performance Tweaks:**
  - The ratio plugin is now disabled by default to prevent a common 488 KiB/s throttle bug.
  - The dumptorrent utility is built from source to fix issues with the dump plugin.
  - The rTorrent configuration file (rtorrent.rc) has been completely overhauled with modern syntax and optimizations for performance and stability.

## Quick Installation Guide

This guide will get you set up in minutes. For a more detailed walkthrough, see the links in the resources section.

### 1. Download and Run the Setup Script

Log into your server and run the following command. If you are logged in as the root user, you can omit `sudo`.
```bash
sudo bash -c "$(wget --no-check-certificate -qO - https://raw.githubusercontent.com/meisnick/rtinst/master/rtsetup)"
```

### 2. Run the Main Installation

After the setup is complete, run the main script. You can find a full list of available options in the main script options guide.
```bash
# Standard installation
sudo rtinst

# To include the optional tracker favicon fetcher
sudo rtinst --favicons
```

The installation typically takes about 10 minutes. After the script finishes, a reboot is recommended to apply all system optimizations.

**IMPORTANT:** The script will change your SSH port. Note the new port during the installation so you don't lock yourself out of your server!

## Included Services

The following services will be automatically installed and configured:

- **vsftpd** - A secure and stable FTP server.
- **libtorrent/rtorrent** - The command-line torrent client.
- **rutorrent** - A popular web-based front-end for rtorrent.
- **Nginx** - High-performance web server.
- **autodl-irssi** - A plugin for rutorrent that automates downloads from IRC announce channels.
- **Webmin** - A web-based server administration panel (optional).

## System Requirements

The current release has been tested on clean installs of the following operating systems:

- Ubuntu 24.04, 22.04, 20.04
- Debian 12 "Bookworm", 11 "Bullseye"

## Additional Resources

- [Detailed Installation Guide](#)
- [Detailed User Guide](#)
- [Project Change Log](#)

## License

Copyright (c) 2015 arakasi72 (https://github.com/arakasi72)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

--> Licensed under the MIT license: http://www.opensource.org/licenses/mit-license.php
