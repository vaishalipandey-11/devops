| Command       | Purpose                             | Common Flags                 | DevOps Use Case              |
| ------------- | ----------------------------------- | ---------------------------- | ---------------------------- |
| `ip`          | Network configuration (modern tool) | `a`, `r`, `link`, `-s`       | Check IP, routes, interfaces |
| `ifconfig`    | Show/configure interfaces (legacy)  | `-a`                         | View IP (older systems)      |
| `ping`        | Test connectivity                   | `-c`, `-i`                   | Check server reachability    |
| `traceroute`  | Show route path                     | `-n`, `-I`                   | Debug routing issues         |
| `mtr`         | Live traceroute + ping              | `-r`, `-c`                   | Advanced network debugging   |
| `netstat`     | Network statistics (legacy)         | `-tulnp`                     | Check open ports             |
| `ss`          | Modern netstat replacement          | `-tulnp`                     | Check listening services     |
| `curl`        | Test APIs / HTTP requests           | `-I`, `-X`, `-d`, `-H`, `-s` | Test backend services        |
| `wget`        | Download files                      | `-O`, `-q`, `-c`             | Download artifacts           |
| `nc` (netcat) | TCP/UDP testing                     | `-zv`, `-l`                  | Test port connectivity       |
| `telnet`      | Test TCP connection                 | (no major flags)             | Quick port test              |
| `nslookup`    | DNS lookup                          | —                            | Check DNS records            |
| `dig`         | Advanced DNS lookup                 | `+short`, `@server`          | Debug DNS                    |
| `host`        | Simple DNS lookup                   | —                            | Quick DNS test               |
| `scp`         | Secure file copy                    | `-r`, `-P`                   | Transfer files               |
| `rsync`       | Efficient file sync                 | `-avz`, `--delete`           | Deploy builds                |
| `ssh`         | Remote login                        | `-i`, `-p`, `-v`             | Connect to servers           |
| `route`       | Show routing table (old)            | `-n`                         | View routes                  |
| `arp`         | ARP table                           | `-a`                         | LAN debugging                |
| `tcpdump`     | Packet capture                      | `-i`, `-n`, `-c`             | Deep packet debugging        |
| `nmap`        | Port scanning                       | `-p`, `-sS`                  | Security scanning            |

