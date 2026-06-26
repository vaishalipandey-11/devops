# Day 09 – Linux User & Group Management Challenge

## Goal
Practice Linux **user management, group management, and permission control** by completing hands-on administrative tasks similar to what a DevOps or system administrator would do.

---

# Task 1 – Create Users

| Step | Command | Purpose | Verification |
|-----|--------|--------|-------------|
| Create user `tokyo` | `sudo useradd -m tokyo` | Creates user with a home directory | `ls /home` |
| Set password | `sudo passwd tokyo` | Assign login password | Login test |
| Create user `berlin` | `sudo useradd -m berlin` | Creates another user with home directory | `ls /home` |
| Set password | `sudo passwd berlin` | Assign login password | Login test |
| Create user `professor` | `sudo useradd -m professor` | Creates third user | `ls /home` |
| Set password | `sudo passwd professor` | Assign password | Login test |

### Verification Commands

| Command | Purpose |
|--------|--------|
| `cat /etc/passwd | grep tokyo` | Verify user entry exists |
| `cat /etc/passwd | grep berlin` | Verify user entry |
| `cat /etc/passwd | grep professor` | Verify user entry |
| `ls /home` | Confirm home directories were created |

---

# Task 2 – Create Groups

| Step | Command | Purpose | Verification |
|-----|--------|--------|-------------|
| Create developers group | `sudo groupadd developers` | Creates group for developers | `cat /etc/group` |
| Create admins group | `sudo groupadd admins` | Creates admin group | `cat /etc/group` |

### Verification

| Command | Purpose |
|--------|--------|
| `cat /etc/group | grep developers` | Confirm developers group exists |
| `cat /etc/group | grep admins` | Confirm admins group exists |

---

# Task 3 – Assign Users to Groups

| User | Command | Purpose |
|-----|--------|--------|
| tokyo → developers | `sudo usermod -aG developers tokyo` | Adds tokyo to developers group |
| berlin → developers | `sudo usermod -aG developers berlin` | Adds berlin to developers |
| berlin → admins | `sudo usermod -aG admins berlin` | Adds berlin to admins |
| professor → admins | `sudo usermod -aG admins professor` | Adds professor to admins |

### Verification

| Command | Purpose |
|--------|--------|
| `groups tokyo` | Shows group membership |
| `groups berlin` | Verify multiple group membership |
| `groups professor` | Verify admin group membership |

---

# Task 4 – Shared Directory Setup

## Step-by-step Configuration

| Step | Command | Purpose |
|-----|--------|--------|
| Create directory | `sudo mkdir /opt/dev-project` | Creates shared project directory |
| Change group owner | `sudo chgrp developers /opt/dev-project` | Assigns developers group |
| Set permissions | `sudo chmod 775 /opt/dev-project` | Allows group read/write/execute |
| Check permissions | `ls -ld /opt/dev-project` | Verify permissions and group |

### Test File Creation

| Test | Command | Purpose |
|-----|--------|--------|
| Create file as tokyo | `sudo -u tokyo touch /opt/dev-project/tokyo-file.txt` | Test developer access |
| Create file as berlin | `sudo -u berlin touch /opt/dev-project/berlin-file.txt` | Test shared access |
| Verify files | `ls -l /opt/dev-project` | Confirm files created successfully |

---

# Task 5 – Team Workspace Setup

## Step-by-step Configuration

| Step | Command | Purpose |
|-----|--------|--------|
| Create user | `sudo useradd -m nairobi` | Adds new team member |
| Set password | `sudo passwd nairobi` | Assign login password |
| Create group | `sudo groupadd project-team` | Creates team group |
| Add nairobi to group | `sudo usermod -aG project-team nairobi` | Adds nairobi to team |
| Add tokyo to group | `sudo usermod -aG project-team tokyo` | Adds tokyo to team |
| Create workspace directory | `sudo mkdir /opt/team-workspace` | Shared team workspace |
| Change group ownership | `sudo chgrp project-team /opt/team-workspace` | Assign group access |
| Set permissions | `sudo chmod 775 /opt/team-workspace` | Enable group collaboration |

---

## Test Workspace Access

| Test | Command | Purpose |
|-----|--------|--------|
| Create file as nairobi | `sudo -u nairobi touch /opt/team-workspace/test.txt` | Verify access |
| Check files | `ls -l /opt/team-workspace` | Confirm file creation |

---

# Commands Used

| Command | Description |
|-------|-------------|
| `useradd -m` | Creates a new user with home directory |
| `passwd` | Sets user password |
| `groupadd` | Creates a new group |
| `usermod -aG` | Adds user to a group |
| `groups` | Displays user group membership |
| `mkdir` | Creates directory |
| `chgrp` | Changes group ownership |
| `chmod` | Changes file permissions |
| `sudo -u` | Run command as another user |

---

# Verification Files

| File | Purpose |
|----|---------|
| `/etc/passwd` | Stores user account information |
| `/etc/group` | Stores group information |
| `/home/` | Contains user home directories |
| `/opt/dev-project` | Developer shared workspace |
| `/opt/team-workspace` | Project team workspace |

---

# Linux File Permission Learning

| Permission | Symbol | Value |
|-------------|--------|-------|
| Read | r | 4 |
| Write | w | 2 |
| Execute | x | 1 |

| Symbol | Calculation | Code |
|--------|-------------|------|
| rwx | 4+2+1 | 7 |
| rw- | 4+2 | 6 |
| r-x | 4+1 | 5 |
| r-- | 4 | 4 |
| --- | 0 | 0 |

| Code | Owner | Group | Others | Symbol |
|------|------|------|------|--------|
| 755 | rwx | r-x | r-x | rwxr-xr-x |
| 644 | rw- | r-- | r-- | rw-r--r-- |
| 700 | rwx | --- | --- | rwx------ |
| 775 | rwx | rwx | r-x | rwxrwxr-x |

# What I Learned

| Concept | Explanation |
|-------|-------------|
| User management | Creating and managing Linux users |
| Group management | Organizing users into groups |
| Permission control | Managing access using `chmod` and `chgrp` |
| Shared directories | Allowing team collaboration through group permissions |
| Verification methods | Checking `/etc/passwd`, `/etc/group`, and using `groups` |

---

# DevOps Takeaway

| DevOps Skill | Why It Matters |
|--------------|---------------|
| User management | Controls access to servers |
| Group permissions | Enables secure team collaboration |
| Directory permissions | Prevents unauthorized access |
| Multi-user systems | Essential for production infrastructure |
| Access verification | Helps troubleshoot permission issues |


