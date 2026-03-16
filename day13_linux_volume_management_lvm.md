# Day 13 – Linux Volume Management (LVM)

## Goal
Learn how to create and manage storage using **LVM (Logical Volume Manager)**.

---

# 1️⃣ LVM Basic Architecture

| Layer | Short Form | Meaning | Example |
|------|------|------|------|
| Physical Disk | Disk | Actual storage device | `/dev/sdb` |
| Physical Volume | PV | Disk prepared for LVM | `/dev/sdb` |
| Volume Group | VG | Storage pool made from PV | `devops-vg` |
| Logical Volume | LV | Virtual partition | `app-data` |
| Mount Point | FS | Directory where storage is used | `/mnt/app-data` |

---

# 2️⃣ Important LVM Commands

| Command | Full Form | Purpose |
|------|------|------|
| `pvs` | Physical Volume Scan | Shows PV information |
| `vgs` | Volume Group Scan | Shows VG information |
| `lvs` | Logical Volume Scan | Shows LV information |
| `pvcreate` | Create Physical Volume | Initializes disk for LVM |
| `vgcreate` | Create Volume Group | Creates storage pool |
| `lvcreate` | Create Logical Volume | Creates virtual partition |
| `lvextend` | Extend Logical Volume | Increases LV size |
| `resize2fs` | Resize Filesystem | Expands filesystem |

---

# 3️⃣ Step-by-Step LVM Process

| Step | Command | Purpose |
|------|------|------|
| 1 | `lsblk` | Check available disks |
| 2 | `pvcreate /dev/sdb` | Create physical volume |
| 3 | `vgcreate devops-vg /dev/sdb` | Create volume group |
| 4 | `lvcreate -L 500M -n app-data devops-vg` | Create logical volume |
| 5 | `mkfs.ext4 /dev/devops-vg/app-data` | Format volume |
| 6 | `mkdir /mnt/app-data` | Create mount folder |
| 7 | `mount /dev/devops-vg/app-data /mnt/app-data` | Mount volume |
| 8 | `df -h` | Check mounted storage |

---

# 4️⃣ Create Virtual Disk (If No Extra Disk)

| Command | Purpose |
|------|------|
| `dd if=/dev/zero of=/tmp/disk1.img bs=1M count=1024` | Create 1GB disk file |
| `losetup -fP /tmp/disk1.img` | Attach file as disk |
| `losetup -a` | Check loop devices |

Example device:

| Device | File |
|------|------|
| `/dev/loop0` | `/tmp/disk1.img` |

---

# 5️⃣ Extend Logical Volume

| Step | Command | Purpose |
|------|------|------|
| 1 | `lvextend -L +200M /dev/devops-vg/app-data` | Increase LV size |
| 2 | `resize2fs /dev/devops-vg/app-data` | Resize filesystem |
| 3 | `df -h` | Verify new storage |

---

# 6️⃣ Useful Verification Commands

| Command | What It Shows |
|------|------|
| `lsblk` | All disks |
| `pvs` | Physical volumes |
| `vgs` | Volume groups |
| `lvs` | Logical volumes |
| `df -h` | Mounted storage usage |

---

# 7️⃣ LVM Flow (Memory Trick)

| Step | Flow |
|------|------|
| 1 | Disk |
| 2 | PV |
| 3 | VG |
| 4 | LV |
| 5 | Filesystem |
| 6 | Mount |

Memory Trick:

```
Disk → PV → VG → LV → Mount
```

-# 8️⃣ What I Learned

| No | Learning |
|---|---|
| 1 | LVM allows flexible disk management |
| 2 | Storage can be extended without deleting data |
| 3 | Multiple disks can be combined into one storage pool |

----
