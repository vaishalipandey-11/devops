# Day 11 – File Ownership Challenge (chown & chgrp)

---

# Task 1 – Understanding Ownership

| Step | Command | Purpose | Example Output |
|-----|--------|--------|---------------|
| Check files in directory | `ls -l` | Shows file permissions, owner and group | `-rw-r--r-- 1 user user file.txt` |
| Identify owner | Look at column 3 | Shows who owns the file | `user` |
| Identify group | Look at column 4 | Shows group ownership | `user` |

| Concept | Meaning |
|--------|--------|
| Owner | The user who created or owns the file |
| Group | A group of users that may access the file |

---

# Task 2 – Basic chown Operations

| Step | Command | Purpose |
|-----|--------|--------|
| Create file | `touch devops-file.txt` | Creates a test file |
| Check owner | `ls -l devops-file.txt` | View current ownership |
| Change owner to tokyo | `sudo chown tokyo devops-file.txt` | Change file owner |
| Change owner to berlin | `sudo chown berlin devops-file.txt` | Update owner again |
| Verify | `ls -l devops-file.txt` | Confirm ownership change |

---

# Task 3 – Basic chgrp Operations

| Step | Command | Purpose |
|-----|--------|--------|
| Create file | `touch team-notes.txt` | Create test file |
| Check group | `ls -l team-notes.txt` | View group ownership |
| Create group | `sudo groupadd heist-team` | Create new group |
| Change group | `sudo chgrp heist-team team-notes.txt` | Change file group |
| Verify | `ls -l team-notes.txt` | Confirm group change |

---

# Task 4 – Change Owner & Group Together

| Step | Command | Purpose |
|-----|--------|--------|
| Create file | `touch project-config.yaml` | Create configuration file |
| Change owner & group | `sudo chown professor:heist-team project-config.yaml` | Change both owner and group |
| Create directory | `mkdir app-logs` | Create directory |
| Change directory ownership | `sudo chown berlin:heist-team app-logs` | Assign ownership |

---

# Task 5 – Recursive Ownership Change

| Step | Command | Purpose |
|-----|--------|--------|
| Create directories | `mkdir -p heist-project/vault` | Create directory structure |
| Create directories | `mkdir -p heist-project/plans` | Create second directory |
| Create files | `touch heist-project/vault/gold.txt` | Create file |
| Create files | `touch heist-project/plans/strategy.conf` | Create config file |
| Create group | `sudo groupadd planners` | Create planners group |
| Change ownership recursively | `sudo chown -R professor:planners heist-project/` | Apply ownership to all files |
| Verify | `ls -lR heist-project/` | Confirm ownership change |

---

# Task 6 – Practice Challenge

| Step | Command | Purpose |
|-----|--------|--------|
| Create directory | `mkdir bank-heist` | Create project directory |
| Create files | `touch bank-heist/access-codes.txt` | Create file |
| Create files | `touch bank-heist/blueprints.pdf` | Create file |
| Create files | `touch bank-heist/escape-plan.txt` | Create file |
| Change ownership | `sudo chown tokyo:vault-team bank-heist/access-codes.txt` | Assign owner and group |
| Change ownership | `sudo chown berlin:tech-team bank-heist/blueprints.pdf` | Assign owner and group |
| Change ownership | `sudo chown nairobi:vault-team bank-heist/escape-plan.txt` | Assign owner and group |
| Verify | `ls -l bank-heist/` | Confirm ownership |

---

# Commands Reference

| Command | Purpose |
|--------|--------|
| `ls -l` | View file ownership |
| `chown user file` | Change file owner |
| `chgrp group file` | Change file group |
| `chown user:group file` | Change owner and group together |
| `chown -R user:group dir` | Change ownership recursively |
| `chown :group file` | Change only group |

---

# Files & Directories Created

| Item | Type |
|-----|------|
| devops-file.txt | File |
| team-notes.txt | File |
| project-config.yaml | File |
| app-logs | Directory |
| heist-project | Directory |
| bank-heist | Directory |

---

# What I Learned

| Learning | Explanation |
|--------|-------------|
| File ownership | Every file has an owner and group |
| chown usage | Used to change file owner |
| chgrp usage | Used to change file group |
| Recursive ownership | `-R` changes ownership for directories and files inside |
| DevOps usage | Ownership helps control access to logs, configs, and deployments |
