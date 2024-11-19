1- **B**

2- BIOS (Basic Input/Output System): BIOS is a firmware interface found in older computers that initializes hardware components during the boot process and provides a way to load the operating system. It uses the Master Boot Record (MBR) partitioning scheme.
  while  UEFI (Unified Extensible Firmware Interface): UEFI is a more modern firmware interface designed to replace BIOS, offering faster boot times, larger storage support, and enhanced security features. It uses the GUID Partition Table (GPT)


3- The lsmod command ,
  to load a new module jammy , you will have to First, check if the module named “jammy” is available on your system ,  then use module avail jammy :This command will list any available versions of the “jammy” module. Then Load the Module "jammy". 


4- The /proc directory where kernel keeps it's setting and properties . it is created on ram.
  The /sys directory is a structured view of hardware devices and kernel configurations. it is use as a way to manage device drivers and kernel settings on a device and subsystems .
  
5- **C**

6- apt: ⁠High-level package manager , it⁠ ⁠Handles package installation, updates, and removals⁠, ⁠Resolves dependencies automatically⁠, ⁠Fetches packages from repositories and ⁠Provides a user-friendly interface.
  dpkg : it's a ⁠Low-level package manager , ⁠Installs, removes, and manages packages locally. it  ⁠Does not resolve dependencies automatically and its more ⁠Command-line interface friendly 


7- Find Orphaned Packages: sudo deborphan , Remove Orphaned Packages: sudo apt autoremove

9- **B**

10 grep -i "error" /var/log/syslog | wc -l

11-
| Hard link         |  Soft link                       |
|-------------------|--------------------------|
| hard link is a direct reference to the same inode as the original file, meaning it acts as an exact copy of the original file | A soft link is a separate file that points to the path of the original file.|
|If the original file is deleted, a hard link still points to the same data, so the content remains accessible.| It is a shortcut, and it takes up a small amount of disk space to store the path.|
|	Hard links cannot span across different filesystems, and they cannot be used for directories| Soft links can span across different filesystems and can link to directories.|
|	Hard links do not occupy additional disk space, as they point to the same data blocks on disk| If the original file is deleted, a soft link becomes broken and cannot access the data.|
| Use the ln command to create a hard link.| ln -s original_file soft_link |

12- find /etc -name "*.conf" -type f -mtime -7

13- Cron Daemon: The cron daemon is a background service in Unix like systems that schedules and automates repetitive tasks by running specified commands or scripts at set intervals. Cron jobs are defined in crontab files and can be scheduled to run at specific times or intervals, making it useful for tasks like backups, system maintenance, and periodic data processing.
	•	Example Cron Job:
	•	To run a script named backup.sh every day at midnight, add line to the crontab file :  0 0 * * * /path/to/backup.s

14- **B**

15- **blkid** command

16- Difference between ext3 and ext4 filesystems: Ext3 is an older filesystem than ext4, which offers several improvements in performance, reliability, and storage management.

  -Two features of ext4 that make it better:
   1-.	ext4 supports file sizes up to 16 TB and volumes up to 1 EB ( Extent Block) , compared to ext3’s maximum of 2 TB.

   2-.	ext4 uses extents (contiguous blocks) for large files, reducing fragmentation and improving read/write performance over ext3, which uses indirect block mapping.


 17- 


18- Purpose of the /etc/fstab file: 	The /etc/fstab file contains information about disk partitions and filesystems that should be automatically mounted when system boots. It improves the management of persistent mounts.

Example : /etc/fstab entry: UUID=abcd-1234   /data   ext4   defaults   0   2

This mounts the partition with UUID abcd-1234 to /data using the ext4 filesystem with default options.

BONUS 

The Linux boot process begins the moment you power on your machine :

BIOS or UEFI: The system’s firmware (BIOS or UEFI) , performs a Power-On Self Test (POST) to check that essential hardware is working. It then locates a hard drive and hands over control to the bootloader. GRUB (Grand Unified Bootloader ): GRUB is a bootloader that manages and loads the Linux kernel into memory. It also offers a boot menu, letting you choose between different OS versions. GRUB loads the kernel and an initial RAM disk (initramfs), which contains essential drivers for booting.	Kernel: Once the kernel is loaded, it initializes and  controls the hardware, setting up memory , detecting connected devices, and mounting the root filesystem. The kernel is essentially the core of Linux, handlings system processes and resources.init or systemd (System Initialization): The kernel starts the init process (the first process ) or, on modern systems, systemd. This is the parent of all processes and is responsible for booting userspace applications. systemd initializes the system by loading various services, mounting file systems, and starting essential daemons.User Space and Login: Finally, systemd (or init) loads the graphical interface or command-line login prompt. Once you log in, the OS is fully functional , with services, daemons, and applications running in the background, ready for use.
 










