# VM-Manually (Windows & MacOS Intel chip)

## Manual Virtual Machine Setup for Windows & MacOS (Intel Chip)
This lecture covers the step-by-step process to manually set up virtual machines on Windows and MacOS (Intel chip), focusing on the necessary prerequisites, configuration, and installation of CentOS and Ubuntu virtual machines using Oracle VirtualBox.

## Prerequisites for Windows Users
- Enable virtualization in the BIOS. This is not an operating system setting; you must access the BIOS during boot (e.g., by pressing F2, F12, Delete, or Escape, depending on your computer model).
- Look for settings named VTx, secure virtual machine, or virtualization, and enable the relevant option.
- Save and exit the BIOS after enabling virtualization.
- Disable certain Windows features: Microsoft Hyper-V, Windows Hypervisor Platform, Windows Subsystem for Linux, Docker Desktop, and Virtual Machine Platform. Search for 'Windows features' in the Start menu, open 'Turn Windows features on or off,' and uncheck these options. Reboot your computer after making these changes.

## Precautionary Steps for Network Issues
If your VM does not receive an IP address, reboot your router and then power on your computer. This is a precautionary measure to avoid network-related issues during VM setup.

## Creating a New Virtual Machine in VirtualBox
1. Open Oracle VirtualBox (installed in the prerequisite lecture).
2. Check the VirtualBox version via Help > About VirtualBox.
3. Click the gear symbol (New) to create a new VM.

## CentOS VM Configuration
- Name: centosvm (or any name you prefer)
- Type: Linux
- Subtype: Red Hat
- Version: Red Hat 64 bit
    - If only 32 bit is available, virtualization is not enabled in BIOS.
- Hardware:
    - Base memory: 2048 MB (2 GB) recommended; 1024 MB (1 GB) if resources are limited.
    - CPU: 2 CPUs recommended.
- Hard Disk:
    - Size: 20 GB (dynamically allocated unless 'pre-allocate full size' is checked).
- Click Finish to create the VM.

## Ubuntu VM Configuration
Name: ubuntuvm
Type: Linux
Subtype: Ubuntu
Version: Ubuntu 64 bit
Hardware: 2 CPUs, 2 GB RAM (or 1 GB if needed)
Hard Disk: Defaults to 25 GB for Ubuntu
Click Finish to create the VM.

## Attaching ISO Files and Starting Installation
- Download CentOS Stream 9 ISO (boot.iso, around 1 GB) from the official site.
- In VirtualBox, select the VM, go to Settings > Storage, click the empty disk, and choose the downloaded ISO file. Check 'Live CD/DVD.'
- Repeat the process for Ubuntu VM with Ubuntu 22 Server ISO.

## Networking Concepts and Bridged Adapter Setup
- Every computer needs a network adapter to connect to a network. Laptops may have wireless and/or ethernet adapters.
- Routers assign IP addresses to network adapters using DHCP.
- Virtual machines also have virtual network adapters. To connect the VM to the physical network, use a bridged adapter.
- In VirtualBox, go to VM Settings > Network. Adapter 1 is NAT by default. Enable Adapter 2, set it to 'Bridged Adapter,' and select your computer's network adapter (WiFi or Ethernet). Ensure 'Cable Connected' is checked.

## Checking Network Adapter and IP Address
- On Windows, open Command Prompt and run:

```
ipconfig
```

- On MacOS, open Terminal and run:

```
ifconfig
```

Note the IP address of your computer's network adapter. When the VM is set up, it should receive an IP address in the same range.

## Additional VM Settings
- In VM Settings > System > Motherboard, set the Pointing Device to 'USB Tablet' for better mouse integration.

## Installing CentOS Stream 9
1. Start the VM and select 'Install CentOS Stream 9.'
2. Choose English as the language and continue.
3. Select the virtual hard disk (20 GB) as the installation destination and use automatic partitioning.
4. In 'Network & Hostname,' ensure both adapters are visible. The bridged adapter should have an IP in your local range (e.g., 192.168.1.x).
5. Set the hostname (e.g., centosvm).
6. Set the root password (admin user in Linux). If the password is weak, confirm by clicking 'Done' twice.
7. Begin installation and wait for completion.

## Post-Installation Steps for CentOS
- After installation, power off the VM.
- Go to VM Settings > Storage and remove the ISO from the virtual drive to avoid booting from it again.
- Start the VM, complete the initial setup (user creation, password), and open the Terminal inside CentOS.

## Checking IP Address in CentOS
- In the CentOS terminal, run:

```
ip addr show
```

Note the IP address assigned to the bridged adapter.

## SSH into CentOS VM
Open Git Bash and connect using SSH:

```
ssh centosuser@192.168.1.10
```

Enter the password when prompted. You can verify the connection by running:

```
ip addr show
hostname
```

Exit the SSH session and shut down the VM when finished.

## Installing Ubuntu Server 22
- Download Ubuntu 22 Server ISO.
- Attach the ISO to the Ubuntu VM in VirtualBox (Settings > Storage).
- Set up the bridged adapter as before.
- Start the VM and proceed through the installation screens, accepting defaults.
- When prompted, select 'Install OpenSSH Server' (use space bar to check).
- Complete the installation, power off the VM, and remove the ISO from the virtual drive.

## Post-Installation Steps for Ubuntu
- Start the VM, log in with the username and password set during installation.
- In the Ubuntu terminal, run:

```
ip addr show
```
Note the IP address (e.g., 192.168.1.11). Open Git Bash and SSH into the VM:

```
ssh devops@192.168.1.11
```

After logging in, verify with:

```
ip addr show
hostname
```

Exit the SSH session and power off the VM.

## Summary
In this lecture, we set up two virtual machines, one with CentOS and the other with Ubuntu, on VirtualBox. We configured hardware, attached ISO images, set up bridged networking, installed the operating systems, and verified connectivity via SSH. The next lectures will cover automating this process.

## Key Takeaways
- Enabled virtualization in BIOS and disabled conflicting Windows features before VM setup.
- Created and configured CentOS and Ubuntu virtual machines in VirtualBox, including hardware and network settings.
- Attached ISO images and installed operating systems, ensuring correct network adapter configuration for bridged networking.
- Verified VM connectivity and accessed VMs via SSH using assigned IP addresses.