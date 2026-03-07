7. Linux File System Hierarchy & Scenario-Based Practice

## Goal
Understand where things live in Linux and practice troubleshooting like a DevOps engineer.

---

# Part 1 – Linux File System Hierarchy

| Directory | Purpose | Example Command | Example Files/Folders | When I Would Use This |
|-----------|--------|----------------|----------------------|----------------------|
| `/` | Root directory. Starting point of the entire Linux filesystem. | `ls -l /` | bin, etc, home, var | When exploring the overall system structure or navigating to core directories. |
| `/home` | Stores home directories for normal users. | `ls -l /home` | vaishali, user1 | When accessing personal files, downloads, scripts, and projects. |
| `/root` | Home directory of the root (administrator) user. | `ls -l /root` | .bashrc, .ssh | When performing administrative tasks as the root user. |
| `/etc` | Stores system-wide configuration files used by services and the OS. | `ls -l /etc` | hostname, passwd, ssh/ | When modifying service configuration or troubleshooting system settings. |
| `/var/log` | Contains system logs and application logs used for debugging. | `ls -l /var/log` | syslog, auth.log, kern.log | When investigating errors, service failures, or authentication issues. |
| `/tmp` | Stores temporary files created by applications. | `ls -l /tmp` | temporary files, cache files | When debugging temporary data or runtime files created by applications. |

---

# Additional Directories

| Directory | Purpose | Example Command | Example Files | When I Would Use This |
|-----------|--------|----------------|---------------|----------------------|
| `/bin` | Contains essential command binaries needed for basic system operation. | `ls -l /bin` | ls, cp, mv, cat | When learning where core system commands are stored. |
| `/usr/bin` | Contains most user-level command binaries and installed programs. | `ls -l /usr/bin` | python, git, vim | When checking installed command-line programs. |
| `/opt` | Used for optional or third-party software installations. | `ls -l /opt` | google, custom-app | When managing manually installed or enterprise applications. |

---

# Hands-On Commands

| Task | Command | Purpose |
|-----|--------|--------|
| Find largest log files | `du -sh /var/log/* 2>/dev/null \| sort -h \| tail -5` | Identify log files consuming the most disk space |
| Check system hostname | `cat /etc/hostname` | Display the hostname of the machine |
| Check home directory contents | `ls -la ~` | View hidden and visible files in the home directory |

---

# Part 2 – Scenario-Based Practice

---

# Scenario 1 – Service Not Starting

| Step | Command | Why |
|-----|--------|-----|
| 1 | `systemctl status myapp` | Check whether the service is running, stopped, or failed. |
| 2 | `journalctl -u myapp -n 50` | View the last 50 log entries to identify errors. |
| 3 | `systemctl is-enabled myapp` | Check if the service is configured to start automatically at boot. |
| 4 | `systemctl restart myapp` | Attempt to restart the service after diagnosing the issue. |

---

# Scenario 2 – High CPU Usage

| Step | Command | Why |
|-----|--------|-----|
| 1 | `top` | Shows real-time CPU and process usage. |
| 2 | `ps aux --sort=-%cpu \| head -10` | Lists processes sorted by highest CPU usage. |
| 3 | `htop` | Provides an interactive process viewer (if installed). |
| 4 | `kill <PID>` | Terminates a process consuming excessive CPU resources. |

---

# Scenario 3 – Finding Service Logs

| Step | Command | Why |
|-----|--------|-----|
| 1 | `systemctl status docker` | Confirm the service status and see recent logs. |
| 2 | `journalctl -u docker -n 50` | View the last 50 log entries of the docker service. |
| 3 | `journalctl -u docker -f` | Follow logs in real time for debugging. |

---

# Scenario 4 – File Permission Issue

| Step | Command | Purpose |
|-----|--------|--------|
| 1 | `ls -l /home/user/backup.sh` | Check current file permissions. |
| 2 | `chmod +x /home/user/backup.sh` | Add execute permission to the script. |
| 3 | `ls -l /home/user/backup.sh` | Verify the execute permission was added. |
| 4 | `./backup.sh` | Run the script. |

---

# What I Learned Today

| Concept | Explanation |
|--------|-------------|
| Linux filesystem structure | Linux organizes files into logical directories for easier management. |
| Configuration files | Located mainly inside `/etc`. |
| Logs | Stored in `/var/log` and essential for debugging. |
| Service troubleshooting | Done using `systemctl` and `journalctl`. |
| Process monitoring | Tools like `top`, `htop`, and `ps` help identify CPU usage. |
| File permissions | Files must have execute (`x`) permission to run as scripts.
