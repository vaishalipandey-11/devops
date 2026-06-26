# DevOps Linux Commands – Frequently Used Flags

| Command | Flag | Meaning | Example | DevOps Use Case |
|-------|------|--------|--------|----------------|
| ls | -l | Long listing format | ls -l | View file permissions and ownership |
| ls | -a | Show hidden files | ls -a | Debug hidden config files |
| ls | -lh | Human readable size | ls -lh | Check file sizes in logs/builds |
| ls | -lt | Sort by modified time | ls -lt | Identify recently changed files |
| ls | -R | Recursive listing | ls -R | Inspect directory structure |

| cp | -r | Copy directories recursively | cp -r dir backup/ | Backup configs |
| cp | -v | Verbose copy | cp -v file dest/ | Track file movement |
| cp | -u | Copy only if newer | cp -u file dest/ | Sync updated configs |

| mv | -v | Verbose move | mv -v file new/ | Deployment file movement |
| mv | -i | Confirm overwrite | mv -i file dest/ | Prevent accidental overwrite |

| rm | -r | Recursive delete | rm -r dir | Remove directories |
| rm | -f | Force delete | rm -f file | Automation scripts |
| rm | -rf | Force recursive delete | rm -rf build/ | Clean build artifacts |

| mkdir | -p | Create parent directories | mkdir -p app/logs | Setup project structure |
| mkdir | -v | Verbose | mkdir -v test | Debug scripts |

| chmod | +x | Add execute permission | chmod +x deploy.sh | Make scripts executable |
| chmod | 755 | Owner full access | chmod 755 script.sh | Secure script permissions |

| chown | -R | Recursive ownership | chown -R user:user dir | Fix ownership issues |

| tar | -c | Create archive | tar -cvf backup.tar dir | Backup configs |
| tar | -x | Extract archive | tar -xvf backup.tar | Restore files |
| tar | -z | Use gzip compression | tar -czvf backup.tar.gz dir | Compressed backups |
| tar | -v | Verbose | tar -xvf file.tar | Monitor extraction |

| grep | -i | Case insensitive search | grep -i error log.txt | Log analysis |
| grep | -r | Recursive search | grep -r "ERROR" /logs | Debug production logs |
| grep | -n | Show line numbers | grep -n fail log.txt | Find exact issue lines |
| grep | -v | Invert match | grep -v debug log.txt | Filter logs |

| find | -name | Search by filename | find / -name file.txt | Locate configs |
| find | -type f | Files only | find . -type f | Scan codebase |
| find | -type d | Directories only | find . -type d | Manage directories |
| find | -size | File size filter | find . -size +100M | Identify large logs |
| find | -exec | Execute command | find . -name "*.log" -exec rm {} \; | Cleanup logs |

| df | -h | Human readable disk usage | df -h | Check disk space |
| df | -T | Filesystem type | df -T | Debug storage issues |

| du | -h | Human readable | du -h | Check directory size |
| du | -sh | Summary | du -sh logs/ | Monitor log size |

| free | -h | Human readable memory | free -h | Memory monitoring |

| ps | aux | Show all running processes | ps aux | Process inspection |
| ps | -ef | Full process list | ps -ef | Debug system processes |

| top | -u | Monitor specific user | top -u ubuntu | User process monitoring |
| top | -p | Monitor specific PID | top -p 1234 | Track problematic process |

| kill | -9 | Force kill process | kill -9 1234 | Stop stuck services |
| kill | -15 | Graceful termination | kill -15 PID | Safe process shutdown |

| pgrep | -l | Show process name | pgrep -l nginx | Process detection |
| pgrep | -f | Match full command | pgrep -f node | Find running apps |

| systemctl | status | Show service status | systemctl status nginx | Debug services |
| systemctl | start | Start service | systemctl start docker | Start infrastructure |
| systemctl | stop | Stop service | systemctl stop nginx | Maintenance |
| systemctl | restart | Restart service | systemctl restart ssh | Apply config changes |
| systemctl | enable | Start service at boot | systemctl enable docker | Persistent services |
| systemctl | disable | Disable startup | systemctl disable apache | Service control |

| journalctl | -u | Logs for service | journalctl -u ssh | Debug service logs |
| journalctl | -f | Follow logs live | journalctl -f | Real-time monitoring |
| journalctl | -xe | Detailed errors | journalctl -xe | Troubleshoot failures |

| tail | -f | Follow logs | tail -f app.log | Live log monitoring |
| tail | -n | Last N lines | tail -n 50 log.txt | Quick log inspection |

| head | -n | First N lines | head -n 20 file | Preview logs |

| ip | a | Show IP addresses | ip a | Network debugging |
| ip | r | Show routing table | ip r | Network routing check |

| ping | -c | Number of packets | ping -c 4 google.com | Connectivity test |

| curl | -I | Fetch headers only | curl -I site.com | Check API response |
| curl | -X | HTTP method | curl -X POST api | API testing |
| curl | -H | Add header | curl -H "Auth: token" api | API authentication |

| wget | -O | Save with filename | wget -O file url | Download artifacts |
| wget | -c | Resume download | wget -c file.iso | Continue large downloads |

| ssh | -i | Identity key | ssh -i key.pem user@host | Server login |
| ssh | -p | Custom port | ssh -p 2222 host | Access custom SSH |

| scp | -r | Copy directories | scp -r dir server:/path | Deploy files |
| scp | -i | Use SSH key | scp -i key.pem file host:/ | Secure transfer |

| netstat | -tuln | Show listening ports | netstat -tuln | Service port check |

| ss | -tulnp | Show sockets and processes | ss -tulnp | Network debugging |





# DevOps Linux – Top 50 Commands Used Daily

| # | Command | Example | Purpose | DevOps Scenario |
|---|--------|--------|--------|----------------|
| 1 | ls | ls -lh | List files | Inspect project directories |
| 2 | cd | cd /var/log | Change directory | Navigate system folders |
| 3 | pwd | pwd | Show current path | Verify working directory |
| 4 | mkdir | mkdir -p app/logs | Create directories | Setup project structure |
| 5 | rm | rm -rf build/ | Delete files/dirs | Clean build artifacts |
| 6 | cp | cp config.yml backup/ | Copy files | Backup configs |
| 7 | mv | mv file new/ | Move/rename files | Deployment changes |
| 8 | chmod | chmod +x deploy.sh | Change permissions | Make scripts executable |
| 9 | chown | chown user:user file | Change ownership | Fix permission issues |
| 10 | touch | touch app.log | Create empty file | Create logs/configs |

| 11 | cat | cat config.yml | View file content | Inspect configuration |
| 12 | less | less large.log | Scroll file | Read large logs |
| 13 | head | head -n 20 file | First lines | Quick preview |
| 14 | tail | tail -f app.log | Live logs | Monitor production logs |
| 15 | grep | grep ERROR app.log | Search text | Debug errors |

| 16 | find | find / -name nginx.conf | Locate files | Find configs |
| 17 | du | du -sh logs/ | Directory size | Log storage check |
| 18 | df | df -h | Disk usage | Server storage monitoring |
| 19 | free | free -h | Memory usage | Monitor RAM |
| 20 | uptime | uptime | System uptime | Server health check |

| 21 | ps | ps aux | Running processes | Debug running apps |
| 22 | top | top | Live process monitor | CPU usage monitoring |
| 23 | htop | htop | Interactive process view | Process debugging |
| 24 | kill | kill -9 1234 | Kill process | Stop stuck services |
| 25 | pgrep | pgrep nginx | Find process ID | Check if service running |

| 26 | systemctl status | systemctl status nginx | Service status | Debug services |
| 27 | systemctl start | systemctl start docker | Start service | Start infrastructure |
| 28 | systemctl stop | systemctl stop nginx | Stop service | Maintenance |
| 29 | systemctl restart | systemctl restart ssh | Restart service | Apply config changes |
| 30 | systemctl enable | systemctl enable docker | Start at boot | Persistent services |

| 31 | journalctl | journalctl -u ssh | View service logs | Debug service issues |
| 32 | tail | tail -n 100 syslog | Recent logs | Incident analysis |
| 33 | dmesg | dmesg | Kernel logs | Hardware issues |
| 34 | watch | watch df -h | Run command repeatedly | Monitor resources |

| 35 | ip a | ip a | Show IP address | Network debugging |
| 36 | ip r | ip r | Show routes | Network troubleshooting |
| 37 | ping | ping google.com | Test connectivity | Network checks |
| 38 | curl | curl -I site.com | HTTP request | API testing |
| 39 | wget | wget file.url | Download files | Download artifacts |

| 40 | ssh | ssh user@server | Remote login | Access servers |
| 41 | scp | scp file server:/path | Secure copy | Deploy files |
| 42 | rsync | rsync -av dir server:/ | Sync files | Deployment sync |

| 43 | tar | tar -czvf backup.tar.gz dir | Create archive | Backup configs |
| 44 | unzip | unzip file.zip | Extract zip | Restore files |

| 45 | history | history | Command history | Debug past commands |
| 46 | clear | clear | Clear terminal | Clean terminal |
| 47 | alias | alias ll='ls -lh' | Shortcut command | Productivity |
| 48 | crontab | crontab -e | Schedule jobs | Automation |
| 49 | env | env | Environment variables | Debug env configs |
| 50 | export | export VAR=value | Set env variable | CI/CD configuration |
