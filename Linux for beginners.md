# Linux File System

The Linux file system is a hierarchical structure used to organize and manage files on a Linux operating system. Here's a concise explanation of its key components and structure:

### Key Concepts

1. **Hierarchy and Root Directory**:
   - The Linux file system is structured as a tree, with the root directory (`/`) at the top.
   - All other directories and files are branches and leaves descending from the root.

2. **File Types**:
   - **Regular files**: Contain data, text, or executable code.
   - **Directories**: Containers that hold files and other directories.
   - **Symbolic links**: Pointers or shortcuts to other files or directories.
   - **Device files**: Represent hardware devices (e.g., `/dev/sda` for a disk).
   - **Sockets** and **Pipes**: Used for inter-process communication.

### Common Directories

1. **`/` (Root)**:
   - The top-level directory of the file system.

2. **`/bin`**:
   - Essential command binaries for all users (e.g., `ls`, `cp`).

3. **`/sbin`**:
   - System binaries, typically for administrative tasks (e.g., `ifconfig`, `reboot`).

4. **`/etc`**:
   - Configuration files for the system and applications (e.g., `/etc/passwd` for user account information).

5. **`/home`**:
   - User home directories. Each user has a personal directory under this (e.g., `/home/username`).

6. **`/root`**:
   - The home directory for the root (administrative) user.

7. **`/var`**:
   - Variable data files such as logs (`/var/log`), databases, email, and web servers.

8. **`/tmp`**:
   - Temporary files, often cleared on reboot.

9. **`/usr`**:
   - User-related programs and data. Includes subdirectories like:
     - **`/usr/bin`**: Non-essential command binaries.
     - **`/usr/sbin`**: Non-essential system binaries.
     - **`/usr/local`**: Locally installed software.

10. **`/opt`**:
    - Optional or third-party software packages.

11. **`/lib`** and **`/lib64`**:
    - Essential shared libraries and kernel modules.

12. **`/dev`**:
    - Device files representing hardware (e.g., `/dev/sda` for a disk drive).

13. **`/proc`**:
    - Virtual file system providing information about running processes and the kernel (e.g., `/proc/cpuinfo`).

14. **`/sys`**:
    - Virtual file system providing information and control interfaces for devices and other kernel attributes.

### File Permissions and Ownership

- **Permissions**:
  - Each file and directory has permissions for the owner, group, and others (e.g., `rwxr-xr-x`).
  - **r**: Read, **w**: Write, **x**: Execute.

- **Ownership**:
  - Each file has an owner and a group.
  - Commands like `chown` (change owner) and `chmod` (change mode) manage these attributes.

### Mounting and File System Types

- **Mounting**:
  - Attaching a storage device or partition to a directory so its contents are accessible.
  - Example: `mount /dev/sda1 /mnt`

- **File System Types**:
  - **ext4**: Common default file system for Linux.
  - **xfs**, **btrfs**, **zfs**: Other file systems offering different features and performance characteristics.

Understanding this structure is fundamental to effectively navigating and managing a Linux system.


# Basic Commands

Certainly! Here's a list of essential Linux commands along with explanations that can be very useful for beginners:

### Basic Navigation and File Management

1. **`pwd` (Print Working Directory)**:
   - Displays the full path of the current directory.
   - Example: `pwd`

2. **`ls` (List)**:
   - Lists files and directories in the current directory.
   - Common options:
     - `ls -l` (detailed list)
     - `ls -a` (show all files, including hidden files)
   - Example: `ls -la`

3. **`cd` (Change Directory)**:
   - Changes the current directory.
   - Example: `cd /path/to/directory`
   - Use `cd ..` to move up one directory.

4. **`mkdir` (Make Directory)**:
   - Creates a new directory.
   - Example: `mkdir new_directory`

5. **`rmdir` (Remove Directory)**:
   - Removes an empty directory.
   - Example: `rmdir old_directory`

6. **`rm` (Remove)**:
   - Removes files or directories.
   - Example: `rm file_name`
   - Use `rm -r directory_name` to remove a directory and its contents.

7. **`cp` (Copy)**:
   - Copies files or directories.
   - Example: `cp source_file destination_file`
   - Use `cp -r source_directory destination_directory` to copy directories.

8. **`mv` (Move)**:
   - Moves or renames files or directories.
   - Example: `mv old_name new_name` or `mv file_name /new/directory`

### Viewing and Editing Files

9. **`cat` (Concatenate)**:
   - Displays the content of a file.
   - Example: `cat file_name`

10. **`less`**:
    - Views file content page by page.
    - Example: `less file_name`
    - Use `q` to quit.

11. **`head`**:
    - Displays the first 10 lines of a file.
    - Example: `head file_name`
    - Use `head -n 20 file_name` to display the first 20 lines.

12. **`tail`**:
    - Displays the last 10 lines of a file.
    - Example: `tail file_name`
    - Use `tail -n 20 file_name` to display the last 20 lines.
    - Use `tail -f file_name` to follow the file (useful for logs).

13. **`nano`**:
    - Simple text editor.
    - Example: `nano file_name`
    - Use `Ctrl + X` to exit, `Y` to save changes.

14. **`vim`**:
    - Advanced text editor.
    - Example: `vim file_name`
    - Use `:w` to save, `:q` to quit.

### System Information and Management

15. **`top`**:
    - Displays real-time system processes and resource usage.
    - Example: `top`
    - Use `q` to quit.

16. **`htop`**:
    - Enhanced version of `top`.
    - Example: `htop` (needs to be installed separately on some systems)
    - Use `F10` to quit.

17. **`df` (Disk Free)**:
    - Shows disk space usage.
    - Example: `df -h` (human-readable format)

18. **`du` (Disk Usage)**:
    - Shows disk usage of files and directories.
    - Example: `du -sh directory_name` (summary, human-readable)

19. **`free`**:
    - Displays memory usage.
    - Example: `free -h` (human-readable format)

### Network Commands

20. **`ping`**:
    - Tests connectivity to another host.
    - Example: `ping example.com`

21. **`ifconfig`** (or `ip addr` on newer systems):
    - Displays or configures network interfaces.
    - Example: `ifconfig` or `ip addr`

22. **`wget`**:
    - Downloads files from the internet.
    - Example: `wget http://example.com/file`

23. **`curl`**:
    - Transfers data from or to a server.
    - Example: `curl http://example.com`

### Package Management

24. **`apt-get` (Debian/Ubuntu)**:
    - Manages packages (install, update, remove).
    - Example: `sudo apt-get update` (updates package list)
    - Example: `sudo apt-get install package_name` (installs a package)

25. **`yum` (Red Hat/CentOS)**:
    - Manages packages.
    - Example: `sudo yum install package_name`

### File Permissions and Ownership

26. **`chmod` (Change Mode)**:
    - Changes file permissions.
    - Example: `chmod 755 file_name` (sets permissions to rwxr-xr-x)

27. **`chown` (Change Owner)**:
    - Changes file owner and group.
    - Example: `chown user:group file_name`

### Searching and Finding

28. **`find`**:
    - Searches for files and directories.
    - Example: `find /path -name "file_name"`

29. **`grep`**:
    - Searches for patterns within files.
    - Example: `grep "pattern" file_name`
    - Use `grep -r "pattern" /path` to search recursively.

### Miscellaneous

30. **`history`**:
    - Shows the command history.
    - Example: `history`

31. **`alias`**:
    - Creates shortcuts for commands.
    - Example: `alias ll='ls -la'`

32. **`echo`**:
    - Displays a line of text.
    - Example: `echo "Hello, World!"`

33. **`date`**:
    - Displays or sets the system date and time.
    - Example: `date`

These commands cover a wide range of basic tasks in Linux and are essential for anyone starting out with the operating system.


# Linux Server Commands

When managing a Linux server, there are additional commands that are particularly useful for system administration tasks such as monitoring, user management, and service control. Here's a comprehensive list of commands that are essential for managing a Linux server:

### System Monitoring and Performance

1. **`top`**:
   - Displays real-time system processes and resource usage.
   - Example: `top`

2. **`htop`**:
   - Enhanced version of `top` with a more user-friendly interface.
   - Example: `htop`

3. **`vmstat`**:
   - Reports virtual memory statistics.
   - Example: `vmstat 5` (updates every 5 seconds)

4. **`iostat`**:
   - Reports CPU and I/O statistics.
   - Example: `iostat`

5. **`dstat`**:
   - Combines vmstat, iostat, netstat, and ifstat in one.
   - Example: `dstat`

6. **`netstat`**:
   - Displays network connections, routing tables, interface statistics, masquerade connections, and multicast memberships.
   - Example: `netstat -tuln`

7. **`ss`**:
   - More modern replacement for `netstat`.
   - Example: `ss -tuln`

8. **`uptime`**:
   - Shows how long the system has been running, the number of users, and system load averages.
   - Example: `uptime`

9. **`sar`**:
   - Collects, reports, or saves system activity information.
   - Example: `sar -u 1 3` (CPU usage every second for 3 seconds)

### Disk Management

10. **`df`**:
    - Shows disk space usage.
    - Example: `df -h`

11. **`du`**:
    - Displays disk usage of files and directories.
    - Example: `du -sh /var/log`

12. **`fdisk`**:
    - Manipulates disk partition table.
    - Example: `fdisk /dev/sda`

13. **`parted`**:
    - A more advanced partitioning tool.
    - Example: `parted /dev/sda`

14. **`lsblk`**:
    - Lists information about all available or the specified block devices.
    - Example: `lsblk`

15. **`mount`**:
    - Mounts a filesystem.
    - Example: `mount /dev/sda1 /mnt`

16. **`umount`**:
    - Unmounts a filesystem.
    - Example: `umount /mnt`

### User and Permission Management

17. **`adduser`**:
    - Adds a new user.
    - Example: `adduser username`

18. **`deluser`**:
    - Deletes a user.
    - Example: `deluser username`

19. **`usermod`**:
    - Modifies a user account.
    - Example: `usermod -aG groupname username` (adds user to a group)

20. **`passwd`**:
    - Changes a user's password.
    - Example: `passwd username`

21. **`chown`**:
    - Changes file owner and group.
    - Example: `chown user:group file_name`

22. **`chmod`**:
    - Changes file permissions.
    - Example: `chmod 755 file_name`

23. **`groups`**:
    - Shows the groups a user is a member of.
    - Example: `groups username`

### Network Management

24. **`ping`**:
    - Tests connectivity to another host.
    - Example: `ping example.com`

25. **`traceroute`**:
    - Tracks the route packets take to a network host.
    - Example: `traceroute example.com`

26. **`ifconfig`**:
    - Configures network interfaces.
    - Example: `ifconfig`

27. **`ip`**:
    - More modern command for network configuration.
    - Example: `ip addr show`

28. **`iptables`**:
    - Configures the packet filtering rules of the Linux kernel firewall.
    - Example: `iptables -L`

29. **`systemctl`**:
    - Controls the systemd system and service manager.
    - Example: `systemctl status` (shows system status)
    - Example: `systemctl restart nginx` (restarts nginx service)

30. **`service`**:
    - Controls services on System V init systems.
    - Example: `service nginx restart`

### Package Management

31. **`apt-get` (Debian/Ubuntu)**:
    - Manages packages.
    - Example: `sudo apt-get update` (updates package list)
    - Example: `sudo apt-get upgrade` (upgrades all packages)
    - Example: `sudo apt-get install package_name` (installs a package)

32. **`yum` (Red Hat/CentOS)**:
    - Manages packages.
    - Example: `sudo yum update` (updates all packages)
    - Example: `sudo yum install package_name` (installs a package)

33. **`dnf` (Fedora)**:
    - Next-generation version of `yum`.
    - Example: `sudo dnf update`
    - Example: `sudo dnf install package_name`

### Logs and Troubleshooting

34. **`tail -f`**:
    - Follows log file output.
    - Example: `tail -f /var/log/syslog`

35. **`journalctl`**:
    - Views logs collected by `systemd`.
    - Example: `journalctl -xe` (shows recent log entries with extra details)

36. **`dmesg`**:
    - Prints kernel ring buffer messages.
    - Example: `dmesg`

37. **`strace`**:
    - Traces system calls and signals.
    - Example: `strace -p process_id`

38. **`lsof`**:
    - Lists open files.
    - Example: `lsof`

### System Management

39. **`reboot`**:
    - Reboots the system.
    - Example: `reboot`

40. **`shutdown`**:
    - Shuts down the system.
    - Example: `shutdown -h now`

41. **`cron`**:
    - Schedules periodic tasks.
    - Example: `crontab -e` (edits the current user's cron jobs)

42. **`at`**:
    - Schedules commands to run at a specific time.
    - Example: `at 10:00`

### Miscellaneous

43. **`scp`**:
    - Securely copies files between hosts.
    - Example: `scp file_name user@remote_host:/path/to/destination`

44. **`rsync`**:
    - Synchronizes files and directories between locations.
    - Example: `rsync -avz /local/path/ user@remote_host:/remote/path/`

45. **`tar`**:
    - Archives files.
    - Example: `tar -czvf archive_name.tar.gz /path/to/directory`

46. **`gzip`/`gunzip`**:
    - Compresses and decompresses files.
    - Example: `gzip file_name`
    - Example: `gunzip file_name.gz`

47. **`systemctl`**:
    - Controls the systemd system and service manager.
    - Example: `systemctl status` (shows system status)
    - Example: `systemctl restart nginx` (restarts nginx service)

48. **`service`**:
    - Controls services on System V init systems.
    - Example: `service nginx restart`

### Automation and Scripting

49. **`crontab`**:
    - Schedules regular jobs.
    - Example: `crontab -e` (edit cron jobs)

50. **`screen`**:
    - Manages multiple shell sessions from a single SSH session.
    - Example: `screen -S session_name`

51. **`tmux`**:
    - Terminal multiplexer that allows multiple terminal sessions to be accessed in a single window.
    - Example: `tmux new -s session_name`

By mastering these commands, you'll be well-equipped to handle various administrative tasks on a Linux server, ensuring efficient and effective system management.
