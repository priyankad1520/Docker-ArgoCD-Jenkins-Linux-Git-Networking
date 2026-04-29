# Linux 

## What is Linux?
Linux is an **open-source operating system** 

used in:

* Servers
* Cloud computing
* DevOps
* Networking
* Cybersecurity
* Embedded systems
* Android phones

Most companies use Linux servers because it is: Fast, Secure, Stable, Free, Highly customizable

---

# Linux Architecture
![Image](https://images.openai.com/static-rsc-4/EiL1vXNJH3cD7rOCTPQTKC-6sbXAQEdMRQpuppUTEr_6SoSRgLONKbEQMuxy-li6BmMW1j_oDbowSNHo1jcgDDEKGQdouh2ioEV5ogyAoVadJ9JTPi-aWisprUyv8PAhuI4Uykek6bxK_-E5rsdZjQQryrdPm62gcWSaEOwevHBVSfTKg679qMqT9diXByLt?purpose=fullsize)


### Components

| Component        | Purpose                     |
| ---------------- | --------------------------- |
| Kernel           | Core of Linux OS            |
| Shell            | Command interpreter         |
| File System      | Organizes files/directories |
| Terminal         | Interface to run commands   |
| Services/Daemons | Background processes        |

---

# Important Linux Directories

```text
/        → Root directory
/home    → User files
/etc     → Configuration files
/var     → Logs and variable data
/tmp     → Temporary files
/bin     → Basic commands
/sbin    → System commands
/usr     → User applications
/opt     → Optional software
/dev     → Device files
/proc    → Process information
```

---

### Basic Linux Commands

## File & Directory Commands

| Command          | Purpose                |
| ---------------- | ---------------------- |
| `pwd`            | Show current directory |
| `ls`             | List files             |
| `ls -l`          | Long listing           |
| `ls -a`          | Hidden files           |
| `cd dir`         | Change directory       |
| `mkdir test`     | Create folder          |
| `touch file.txt` | Create file            |
| `cp a b`         | Copy file              |
| `mv a b`         | Move/Rename            |
| `rm file`        | Delete file            |
| `rm -rf dir`     | Delete directory       |
| `cat file`       | View file              |
| `nano file`      | Edit file              |
| `vim file`       | Advanced editor        |

---

# User Management Commands

| Command        | Purpose      |
| -------------- | ------------ |
| `whoami`       | Current user |
| `id`           | User ID      |
| `useradd`      | Add user     |
| `passwd`       | Set password |
| `su user`      | Switch user  |
| `sudo command` | Run as admin |
| `groups`       | Show groups  |

---

# File Permissions

```text
r = read
w = write
x = execute
```

Example:

```bash
chmod 755 file.sh
```

Meaning:

```text
7 = rwx
5 = r-x
5 = r-x
```

---

# Process Management

| Command      | Purpose              |
| ------------ | -------------------- |
| `ps -ef`     | List processes       |
| `top`        | Live process monitor |
| `htop`       | Better top           |
| `kill PID`   | Stop process         |
| `pkill name` | Kill by name         |
| `jobs`       | Background jobs      |

---

# Networking Commands

| Command          | Purpose           |
| ---------------- | ----------------- |
| `ping`           | Test connectivity |
| `ifconfig`       | Network info      |
| `ip a`           | IP address        |
| `netstat -tulnp` | Open ports        |
| `ss -tulnp`      | Socket stats      |
| `curl URL`       | API/web request   |
| `wget URL`       | Download file     |
| `traceroute`     | Route tracing     |
| `nslookup`       | DNS lookup        |

---

# Disk & Memory Commands

| Command    | Purpose       |
| ---------- | ------------- |
| `df -h`    | Disk usage    |
| `du -sh *` | Folder size   |
| `free -m`  | Memory usage  |
| `uptime`   | System uptime |

---

# Service Management

Linux uses `systemd`.

| Command                   | Purpose        |
| ------------------------- | -------------- |
| `systemctl start nginx`   | Start service  |
| `systemctl stop nginx`    | Stop service   |
| `systemctl restart nginx` | Restart        |
| `systemctl status nginx`  | Service status |
| `systemctl enable nginx`  | Auto-start     |

---

# Package Management

## Ubuntu/Debian

```bash
apt update
apt install nginx
apt remove nginx
```

## RHEL/CentOS

```bash
yum install nginx
dnf install nginx
```

---

# Log Monitoring

| Command                   | Purpose      |
| ------------------------- | ------------ |
| `tail -f /var/log/syslog` | Live logs    |
| `journalctl -u nginx`     | Service logs |
| `dmesg`                   | Kernel logs  |

---

# Important Linux Concepts for DevOps

## SSH

Secure remote login.

```bash
ssh user@server-ip
```

---

## Cron Jobs

Schedule tasks.

```bash
crontab -e
```

Example:

```text
0 2 * * * backup.sh
```

Runs at 2 AM daily.

---

## Environment Variables

```bash
echo $PATH
export JAVA_HOME=/opt/java
```

---

# Linux Boot Process

```text
BIOS/UEFI
   ↓
GRUB Bootloader
   ↓
Kernel
   ↓
systemd/init
   ↓
Services
   ↓
Login
```

---

# Linux for DevOps Engineers

Common tools used on Linux:

* Docker
* Kubernetes
* Jenkins
* Ansible
* Terraform
* Git
* Prometheus
* Grafana

---

# Most Important Daily Linux Commands for DevOps

```bash
ls
cd
pwd
grep
find
cat
tail -f
top
ps -ef
systemctl
journalctl
curl
wget
ssh
scp
chmod
chown
df -h
free -m
netstat
ss
docker ps
kubectl get pods
```

---

# Simple Example Workflow

## Check server issue

```bash
top
df -h
free -m
systemctl status nginx
tail -f /var/log/nginx/error.log
```

Purpose:

* Check CPU
* Check disk
* Check memory
* Check service
* Check logs

---
