# USB Drive / Disk Mounting

### Identify Disks

```bash
sudo fdisk -l
```

This displays available disks and partitions.

Example:

```text
/dev/sda
/dev/sdb
/dev/sdb1
```

### Mount a Partition

```bash
sudo mount /dev/sdb1 /media
```

### Access the Mounted Directory

```bash
cd /media
```

### Copy a File

```bash
cp filename.ext /home/user/
```

---

