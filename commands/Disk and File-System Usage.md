# Disk and File-System Usage

### Display Directory Usage

```bash
du
```

### Human-Readable Disk Usage

```bash
du -h
```

### Current Directory Usage

```bash
du -sh .
```

### Size of Each Directory

```bash
du -sh ./*/
```

### Display Immediate Subdirectory Usage

```bash
du -h --max-depth=1
```

Example:

```bash
du -h --max-depth=1 /opt/alfresco
```

### Display File-System Usage

```bash
df
```

### Human-Readable File-System Usage

```bash
df -h
```

### Display All File Systems

```bash
df -a -h
```

### Display Total Disk Usage

```bash
df -h --total
```

---

