# Useful Permission Cheat Sheet

```text
       User   Group  Other
        ↓      ↓      ↓
      ┌───┐  ┌───┐  ┌───┐
      rwx    rwx    rwx

r = 4
w = 2
x = 1
```

Common combinations:

```text
700 = rwx------
755 = rwxr-xr-x
664 = rw-rw-r--
660 = rw-rw----
644 = rw-r--r--
```

For example:

```bash
chmod 755 script.sh
```

means:

```text
Owner  → read + write + execute
Group  → read + execute
Others → read + execute
```
