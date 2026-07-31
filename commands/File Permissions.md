# File Permissions

### Change File or Directory Permissions

```bash
chmod 777 filename
```

### Recursively Change Permissions

```bash
chmod -R 777 directoryName
```

> **Warning:** Avoid `777` unless it is genuinely required. Prefer the minimum permissions needed.

### Symbolic Permission Examples

```bash
chmod g-w sales.data
```

Remove write permission from the group.

```bash
chmod g+wx sales.data
```

Add write and execute permissions for the group.

```bash
chmod ug+wx sales.data
```

Add write and execute permissions for both user and group.

---

