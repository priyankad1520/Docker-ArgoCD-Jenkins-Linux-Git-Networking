# Operating System (OS)
An **Operating System (OS)** is system software that acts as a bridge between: User, Applications and Hardware. It manages all computer resources and allows applications to run.
```text id="os1"
OS = Software that manages hardware and software resources
OS helps applications communicate with hardware.
```
**Real Architecture:**
```text id="os2"
User --> Applications --> Operating System --> Hardware
```
### Main Components of OS

```
1. Kernel: Core of OS      
2. File System: Manages files/folders  
3. Process Manager: Runs applications/processes   / Manages running programs
4. Memory Manager: Allocates RAM / Handles RAM               
5. Device Drivers:  Controls keyboard, disk, printer / Controls hardware         
6. Network Manager: Internet communication / Handles networking       
7. Security Manager: Authentication and permissions / User permissions/security
8. File Management: Stores/retrieves files
9. Resource Scheduling:CPU scheduling 

#  Example
When opening Chrome browser:
Chrome Request --> Operating System --> CPU + RAM + Disk + Network
OS allocates resources to Chrome.
```
## Kernel 
Kernel is the core part of an Operating System, it acts as a bridge between hardware and software. It allows applications to communicate with hardware, without directly accessing the hardware components.

Kernel **manages system resources:** such as CPU, memory, storage. **file systems:** it helps in reading, writing, and storing files on storage devices. **memory allocation:** it decides how much memory each program can use. **CPU scheduling:** it decides which process should use the CPU first.

Kernel **controls process management:** such as creating, scheduling, and terminating processes. **multitasking:** it allows multiple applications to run at the same time.

Kernel **handles device management:** such as keyboard, mouse, printer, disk, and network devices and **system calls:** applications use system calls to request services from the operating system. **interrupt management:** it responds when hardware devices send signals to the system.

Kernel **provides security and access control**, it prevents unauthorized access to system resources. It improves system stability, it prevents applications from directly damaging hardware or memory.

- There are different types of kernels, such as Monolithic Kernel, Microkernel, Hybrid Kernel, and Exokernel.

Monolithic Kernel contains all services inside the kernel space, it provides high performance. Microkernel contains only essential services in kernel space, other services run in user space. Hybrid Kernel combines features of Monolithic and Microkernel, it balances performance and flexibility.

## Linux File System
Linux File System is the method used by Linux Operating System to organize, store, and manage files and directories. In Linux, everything is treated as a file, such as documents, devices, processes, and directories.

Linux File System follows a hierarchical structure, everything starts from the root directory called `/`. The root directory `/` is the top-level directory, all other directories exist under it.

- `/bin`:  contains essential user commands, such as ls, cp, mv, and cat.

- `/sbin`:  contains system administration commands, such as fdisk, reboot, and iptables.

- `/etc`:  stores system configuration files, such as network configuration and user settings.

- `/home`: contains personal directories of users, each user gets a separate folder inside `/home`.

- `/root`:  is the home directory of the root user, it is different from `/home`.

- `/dev`:  contains device files, such as hard disks, USB devices, and terminals.

- `/proc`:  contains process and kernel information, it provides real-time system details.

- `/var`:  stores variable data, such as logs, cache files, and mail files.

- `/tmp`:  stores temporary files, files in this directory may be deleted after reboot.

- `/usr`:  contains user applications and software packages, such as programs and libraries.

- `/lib`:  contains shared libraries required by system programs and commands.

- `/boot`:  contains boot loader files and Linux kernel files required during system startup.

- `/mnt`:  is used to temporarily mount storage devices, such as USB drives and external disks.

- `/media`:  is used for automatic mounting of removable devices, such as CDs and USB drives.

- `/opt`:  contains optional third-party software packages and applications.

- `/srv`:  stores data related to services provided by the system, such as web server files.

- `/run`:  stores runtime process information, it exists only while the system is running.

A file system manages file permissions, it controls who can read, write, or execute files. Linux file permissions are divided into User, Group, and Others, each having read, write, and execute permissions.

Linux uses inode structure to store file metadata, such as file size, permissions, and ownership. Mounting is the process of attaching a file system to a directory structure, so users can access the storage device. Unmounting removes the attached file system safely from the directory structure.

- The `df` command shows disk space usage, the `du` command shows directory file size usage.

- The `ls` command lists files and directories, the `pwd` command shows the current directory path.

- The `cd` command changes the current directory, the `mkdir` command creates a new directory.

- The `rm` command removes files or directories, the `cp` command copies files and directories.

- The `mv` command moves or renames files and directories.

Linux File System is important because it helps organize data efficiently, securely, and systematically in the operating system.

## Linux Users & Permissions
Linux Users are accounts created in the Linux Operating System, they allow people or services to access the system securely. it controls who can access files and system resources. Each user in Linux has a unique username and User ID called UID.

There are mainly three types of users in Linux, Root User, Regular User, and Service/System User. Root User is the administrator account, it has full control over the entire system. Regular User is a normal user account, it has limited permissions for security purposes. System Users are used by applications and services, they usually do not log in manually.

Linux stores user information in the `/etc/passwd` file, it contains usernames and user details. Encrypted user passwords are stored in the `/etc/shadow` file, only privileged users can access it.

Groups in Linux are used to manage permissions for multiple users together. Each group has a unique Group ID called GID. Linux stores group information in the `/etc/group` file. A user can belong to one primary group and multiple secondary groups.

- The `whoami` command shows the currently logged-in user.

- The `id` command displays user ID, group ID, and group information.

- The `adduser` or `useradd` command is used to create a new user.

- The `passwd` command is used to set or change a user password.

- The `usermod` command is used to modify user account details.

- The `userdel` command is used to delete a user account.

- The `groupadd` command is used to create a new group.

- The `groupdel` command is used to delete a group.

- The `su` command switches from one user to another user.

- The `sudo` command allows a regular user to execute administrative commands temporarily.

#### There are three permission types in Linux, Read, Write, and Execute.
Linux permissions control access to files and directories, they improve security and prevent unauthorized access.

- Read permission allows viewing file contents or listing directory contents.

- Write permission allows modifying files or creating and deleting files inside directories.

- Execute permission allows running a file as a program or entering a directory.

- Numeric permission values are Read = 4, Write = 2, Execute = 1.

- Permission `7` means read, write, and execute together because `4+2+1=7`. Permission `6` means read and write because `4+2=6`. Permission `5` means read and execute because `4+1=5`. Permission `4` means only read permission.
- The `ls -l` command displays file permissions in long format.
- Example permission format is `-rwxr-xr--`, it represents permissions for user, group, and others. `r` means read permission, `w` means write permission, `x` means execute permission. A dash `-` means that permission is not granted.

#### Permissions are assigned to three categories, User, Group, and Others.
- The `chmod` command changes file permissions. Example `chmod 765 file.sh` gives full permissions to 7 to owner and read-write permissions to 6 to Group and read-execute permissions to 5 to others.

- User permissions apply to the file owner, group permissions apply to users in the same group, others permissions apply to all remaining users.

- The `chown` command changes file ownership. Example `chown user1 file.txt` changes the owner of the file.

- The `chgrp` command changes group ownership of a file or directory.

File ownership and permissions are important in Linux, they protect system files and user data from unauthorized access.

## Q1: What is OS?

👉 Software that manages hardware and software resources.

---

## Q2: What are main functions of OS?

👉 Process, memory, file, device, networking, security management.

---

## Q3: Why Linux OS is preferred in DevOps?

👉 Stable, lightweight, automation-friendly, and container support.

---

# 🧠 Easy Way to Remember

```text id="os15"
User → Application → OS → Hardware
```

👉 OS acts as manager/controller of the entire system.
