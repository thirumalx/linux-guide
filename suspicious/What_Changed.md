# What changed

After anything suspicious, the first question is simple, what changed?

`mtime` list all file that are modified in last `1` day

```bash
find /etc /usr/bin -mtime -1 -type f 2>/dev/null
```

Files modified between two specific dates/times → use `-newermt`:

```bash
find /etc /usr/bin -type f -newermt "2026-09-29 00:00" ! -newermt "2026-09-30 00:00" 2>/dev/null
```

Check on specfic file

```bash
stat /home/ubuntu/thirumal.txt
```