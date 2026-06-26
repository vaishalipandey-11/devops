# Day 10 – File Permissions & File Operations Challenge

---

# Task 1 – Create Files

| Step | Command | Purpose | Verify |
|-----|--------|--------|--------|
| Create empty file | `touch devops.txt` | Creates a blank file | `ls -l` |
| Create file with content | `echo "DevOps Notes" > notes.txt` | Writes content to file | `cat notes.txt` |
| Create script file | `vim script.sh` | Create and edit script | `ls -l` |
| Script content | `echo "Hello DevOps"` | Simple bash script | `cat script.sh` |

---

# Task 2 – Read Files

| Task | Command | Purpose |
|-----|--------|--------|
| Read notes.txt | `cat notes.txt` | Display file content |
| View script read-only | `vim -R script.sh` | Open file in read-only mode |
| First 5 lines | `head -n 5 /etc/passwd` | Show first lines of file |
| Last 5 lines | `tail -n 5 /etc/passwd` | Show last lines of file |

---

# Task 3 – Understand Permissions

| Command | Example Output | Meaning |
|-------|---------------|--------|
| `ls -l devops.txt` | `-rw-r--r--` | Owner read/write |
| `ls -l notes.txt` | `-rw-r--r--` | Group & others read |
| `ls -l script.sh` | `-rw-r--r--` | Not executable yet |

---

# Permission Code Understanding

| Symbol | Value | Meaning |
|------|------|--------|
| r | 4 | Read |
| w | 2 | Write |
| x | 1 | Execute |

| Code | Owner | Group | Others | Symbol |
|-----|------|------|------|------|
| 7 | rwx | | | Full |
| 6 | rw- | | | Read + Write |
| 5 | r-x | | | Read + Execute |
| 4 | r-- | | | Read only |

---

# Task 4 – Modify Permissions

| Task | Command | Result |
|-----|--------|--------|
| Make script executable | `chmod +x script.sh` | Script can run |
| Run script | `./script.sh` | Prints Hello DevOps |
| Make file read-only | `chmod 444 devops.txt` | No write allowed |
| Set permission 640 | `chmod 640 notes.txt` | Owner rw, group r |
| Create directory | `mkdir project` | New directory |
| Set directory permission | `chmod 755 project` | Owner full access |

---

# Task 5 – Test Permissions

| Test | Command | Expected Result |
|-----|--------|---------------|
| Write to read-only file | `echo "test" >> devops.txt` | Permission denied |
| Execute without permission | `./notes.txt` | Execution denied |
| Check permissions | `ls -l` | Shows updated permissions |

---

# Files Created

| File | Purpose |
|-----|--------|
| devops.txt | Empty file for permission testing |
| notes.txt | File containing notes |
| script.sh | Simple bash script |
| project/ | Directory for permission practice |

---

# Commands Used

| Command | Purpose |
|-------|--------|
| touch | Create empty file |
| echo | Write text to file |
| vim | Edit files |
| cat | Display file content |
| head | View first lines |
| tail | View last lines |
| chmod | Change permissions |
| ls -l | View file permissions |

---

# What I Learned

| Learning | Explanation |
|--------|-------------|
| File creation | Creating files using touch, echo, vim |
| File reading | Viewing files using cat, head, tail |
| Permission system | Understanding rwx permissions |
| chmod usage | Changing file permissions |
| Execution control | Scripts require execute permission |


