# 📁 Linux Directory Structure (FHS)

A reference guide to the standard Linux Filesystem Hierarchy Structure. Understanding these directories is critical for finding configuration files, managing logs, and deploying applications safely.

## 1. `/home`
* **Purpose:** The user home directory space.
* **DevOps Context:** Contains user-specific settings, custom shell profiles (like `.bashrc` or `.zshrc`), and default secure shell keys (`~/.ssh/`).
* **Example Path:** `/home/ubuntu/` or `/home/jenkins/`

## 2. `/etc`
* **Purpose:** Host-specific system-wide configuration files and scripts.
* **DevOps Context:** This is the most edited directory. It holds configurations for system services like Nginx, Docker, SSH daemons, and system users.
* **Example Files:** 
  * `/etc/nginx/nginx.conf` (Web server configuration)
  * `/etc/ssh/sshd_config` (SSH server security settings)

## 3. `/var`
* **Purpose:** Variable data files that change constantly while the system runs.
* **DevOps Context:** Crucial for monitoring system health. It stores dynamic application logs, system error queues, process locks, and temporary container data.
* **Example Paths:**
  * `/var/log/nginx/` (Web traffic and error logs)
  * `/var/lib/docker/` (Default storage space for Docker containers and images)

## 4. `/bin`
* **Purpose:** Essential user command binaries required for system booting and repair.
* **DevOps Context:** Contains basic executable utilities used every single day in shell automation scripts.
* **Example Commands Located Here:** `/bin/cp`, `/bin/mv`, `/bin/rm`, and `/bin/cat`.

## 5. `/dev`
* **Purpose:** Device files that represent physical or virtual hardware components.
* **DevOps Context:** Used when mounting persistent volume disks to cloud instances (like AWS EBS volumes) or discarding automated script output.
* **Example Paths:**
  * `/dev/sda1` (The primary hard drive partition)
  * `/dev/null` (The system "black hole" used to discard unwanted command outputs, e.g., `command > /dev/null 2>&1`)
