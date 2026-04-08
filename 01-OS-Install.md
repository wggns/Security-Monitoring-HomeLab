Ubuntu Server Installation (HP EliteDesk Mini PC)
1. Project Context

For this lab environment, Ubuntu Server 22.04 LTS (64-bit) and Kali Linux Desktop was installed on 2 HP EliteDesk Mini PCS. Ubuntu Server was selected instead of Ubuntu Desktop for the following reasons:
>Lightweight (no graphical user interface)
>CLI-focused environment
>Better suited for logging and security testing
>Aligns with cybersecurity and cloud lab objectives
>Reduced attack surface compared to GUI-based systems
>Ubuntu Server does not include a graphical interface by default, making it ideal for infrastructure and monitoring roles.

2. Download Ubuntu Server ISO

Download the official ISO:Ubuntu Server LTS (64-bit) https://ubuntu.com/download. Always download directly from the official Ubuntu website to ensure integrity.

3. Create a Bootable USB Drive
Requirements: USB flash drive (minimum 8GB) and I used 64GB SanDisk USB used for this installation

Rufus (Windows utility) Download Rufus: https://rufus.ie/en/
Rufus Configuration that I used
Use the following configuration:

>Device: Select USB drive
>Boot Selection: Ubuntu Server ISO
>Partition Scheme: GPT
>Target System: UEFI (non-CSM)
>File System: FAT32
>Click Start.
Now Wait until Rufus displays DONE before removing the USB drive.

4. Boot from USB (HP EliteDesk Mini PC)
>Insert USB drive into Mini PC
>power on and immediately press ESC repeatedly and When the Startup Menu appears, press F9 (Boot Device Options)
>Select the USB drive
>Press enter then system will boot into the Ubuntu Server installer.

5. Ubuntu Server Installation Configuration
>Language
English

>Keyboard
English (US)

For the network configuration
If using Ethernet then DHCP automatically detected and no manual configuration required. If you are using WiFi then select SSID then enter WiFi password.
Storage Configuration
Then Select Use entire disk, Automatic partitioning
This will erase the previous operating system (Windows) and install Ubuntu Server as the primary OS. Then install OpenSSH Server (Critical Step)

During installation, select:
Install OpenSSH Server

This enables:
>Remote administration
>SSH access from Kali Linux
>Secure management from the monitoring laptop
>Brute-force simulation testing
>Log-based intrusion detection validation

This step is essential for a cybersecurity lab environment.

8. Final Installation Steps
After installation completes:
>Remove USB flash drive
>Press Enter to reboot
>The system will now boot from the internal SSD.
>You should see:

Ubuntu 22.04 LTS login:

At this stage, Ubuntu Server is successfully installed and ready for:

Docker installation

Monitoring stack deployment

Fail2ban configuration

SSH-based attack simulation

To install Kali Linux I watched this exact video step by step. https://www.youtube.com/watch?v=56VTPxJ0QEc. But typically you will be doing the same exact steps! just the installation setup is a bit different.
