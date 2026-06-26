Linux Service Inspection Commands
| Category | Command                | Example                               | Purpose                                            |
| -------- | ---------------------- | ------------------------------------- | -------------------------------------------------- |
| Process  | `ps`                   | `ps aux \| grep ssh`                  | Show running processes related to SSH              |
| Process  | `pgrep`                | `pgrep sshd`                          | Find process ID of SSH daemon                      |
| Service  | `systemctl status`     | `systemctl status ssh`                | Check if SSH service is active, failed, or stopped |
| Service  | `systemctl list-units` | `systemctl list-units --type=service` | List all running services                          |
| Logs     | `journalctl -u`        | `journalctl -u ssh`                   | Show logs of SSH service                           |
| Logs     | `tail`                 | `tail -n 50 /var/log/auth.log`        | Show last 50 authentication log entries            |

🚀 Quick DevOps Workflow
| Step | Command                               | What It Checks        |
| ---- | ------------------------------------- | --------------------- |
| 1    | `pgrep sshd`                          | Is process running?   |
| 2    | `ps aux \| grep ssh`                  | Detailed process info |
| 3    | `systemctl status ssh`                | Service state         |
| 4    | `systemctl list-units --type=service` | Running services      |
| 5    | `journalctl -u ssh`                   | Service logs          |
| 6    | `tail -n 50 /var/log/auth.log`        | Recent login errors   |

