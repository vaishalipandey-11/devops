
```bash
pwd
```

List files in the directory:

```bash
ls
```

---

# 2. Create a File

Create a new file called `notes.txt`.

```bash
touch notes.txt
```

Verify it exists:

```bash
ls
```

---

# 3. Write Text to File

Write a line into the file using output redirection.

```bash
echo "This is my Linux practice file." > notes.txt
```

### Important
`>` means **overwrite file contents**.

Check file contents:

```bash
cat notes.txt
```

Expected output:

```
This is my Linux practice file.
```

---

# 4. Append Text to File

Add more lines without deleting the existing content.

```bash
echo "I am learning file operations." >> notes.txt
```

```bash
echo "Linux is powerful." >> notes.txt
```

### Important
`>>` means **append to file**.

Check the file again:

```bash
cat notes.txt
```

Expected output:

```
This is my Linux practice file.
I am learning file operations.
Linux is powerful.
```

---

# 5. Read File Content

## Method 1 – Using `cat`

```bash
cat notes.txt
```

Shows entire file.

---

## Method 2 – Using `less`

```bash
less notes.txt
```

Useful for **large files** because it allows scrolling.

Controls:

| Key | Action |
|----|----|
| `Space` | Scroll down |
| `b` | Scroll up |
| `q` | Quit |

---

## Method 3 – Using `head`

Shows first lines of a file.

```bash
head notes.txt
```

Default: first **10 lines**

Example:

```bash
head -n 2 notes.txt
```

---

## Method 4 – Using `tail`

Shows last lines of a file.

```bash
tail notes.txt
```

Example:

```bash
tail -n 1 notes.txt
```

---

# 6. Verify File Details

Check file metadata:

```bash
ls -l notes.txt
```

Example output:

```
-rw-r--r-- 1 user user 85 Mar 6 10:22 notes.txt
```

Meaning:

| Field | Description |
|------|-------------|
| `-rw-r--r--` | File permissions |
| `1` | Link count |
| `user` | Owner |
| `user` | Group |
| `85` | File size |
| `Mar 6` | Last modified |
| `notes.txt` | File name |

---

# 7. Practice Drill (Repeat 3 Times)

1. Create a file

```bash
touch practice.txt
```

2. Write a line

```bash
echo "Linux file practice" > practice.txt
```

3. Append two lines

```bash
echo "Appending line 1" >> practice.txt
echo "Appending line 2" >> practice.txt
```

4. Read file

```bash
cat practice.txt
```

---

# Expected Final Output

```
Linux file practice
Appending line 1
Appending line 2
```

---

# DevOps Tip

Basic file operations are used everywhere in DevOps:

| Task | Example |
|-----|------|
| Write logs | `echo "deploy started" >> deploy.log` |
| Store script output | `command > output.txt` |
| Append monitoring results | `>> system.log` |
| Read configuration | `cat config.yaml` |

---


