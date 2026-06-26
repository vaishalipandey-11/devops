| Flag        | Long Form          | Meaning                     | Common Commands                      | DevOps Use Case                             |
| ----------- | ------------------ | --------------------------- | ------------------------------------ | ------------------------------------------- |
| `-a`        | `--all`            | Show all (including hidden) | `ls`, `docker ps`                    | Debug hidden files, list stopped containers |
| `-l`        | —                  | Long format                 | `ls`                                 | Check permissions, ownership                |
| `-h`        | `--human-readable` | Human readable sizes        | `ls`, `du`, `df`                     | Disk monitoring                             |
| `-r`        | `--recursive`      | Recursive operation         | `cp`, `rm`, `chmod`, `chown`, `grep` | Manage directories                          |
| `-R`        | —                  | Recursive (capital)         | `chmod`, `chown`                     | Apply permissions recursively               |
| `-f`        | `--force`          | Force without prompt        | `rm`, `cp`, `docker rm`              | Automation scripts                          |
| `-i`        | `--interactive`    | Ask before action           | `rm`, `cp`                           | Safety while deleting                       |
| `-v`        | `--verbose`        | Show detailed output        | `cp`, `mv`, `rm`, `tar`              | Debug scripts                               |
| `-q`        | `--quiet`          | Suppress output             | `grep`, `wget`                       | Clean CI logs                               |
| `-n`        | —                  | Number of lines/items       | `head`, `tail`                       | Log monitoring                              |
| `-t`        | —                  | Sort by time                | `ls`                                 | Find recent logs                            |
| `-S`        | —                  | Sort by size                | `ls`                                 | Debug disk usage                            |
| `-u`        | —                  | User / user ID              | `useradd`, `ps`                      | User management                             |
| `-p`        | —                  | Port / preserve             | `ssh`, `cp`, `docker run`            | Networking / permissions                    |
| `-d`        | —                  | Run in background           | `docker run`, `systemctl`            | Run services                                |
| `-e`        | —                  | Execute / environment       | `docker run`, `grep`                 | Pass env variables                          |
| `-c`        | —                  | Create / count              | `tar`, `wc`                          | Archive creation                            |
| `-x`        | —                  | Extract                     | `tar`                                | Deploy builds                               |
| `-z`        | —                  | Use gzip                    | `tar`                                | Compressed backups                          |
| `-j`        | —                  | Use bzip2                   | `tar`                                | Compressed backups                          |
| `-k`        | —                  | Insecure SSL                | `curl`                               | Testing APIs                                |
| `-L`        | `--location`       | Follow redirects            | `curl`                               | API debugging                               |
| `-o`        | `--output`         | Output file                 | `curl`, `gcc`                        | Save artifacts                              |
| `-P`        | —                  | Port (capital P)            | `ssh`, `scp`                         | Remote server access                        |
| `-A`        | —                  | All processes               | `ps`                                 | Process debugging                           |
| `-u`        | —                  | User processes              | `ps`                                 | Monitor specific user                       |
| `-m`        | —                  | Memory sort                 | `ps`                                 | Debug memory usage                          |
| `-s`        | `--silent`         | Silent mode                 | `curl`                               | CI/CD clean logs                            |
| `-I`        | —                  | Head request                | `curl`                               | Check API headers                           |
| `--name`    | —                  | Container name              | `docker run`                         | Identify containers                         |
| `--rm`      | —                  | Auto remove container       | `docker run`                         | Temp containers                             |
| `--build`   | —                  | Build image                 | `docker-compose`                     | Deploy apps                                 |
| `--restart` | —                  | Restart policy              | `docker run`                         | Production resilience                       |
| `--help`    | —                  | Show help                   | Almost all                           | Quick reference                             |
| `--version` | —                  | Show version                | Almost all                           | Debug environment                           |

