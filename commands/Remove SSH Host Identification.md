# Remove SSH Host Identification

If the SSH host key has changed:

```bash
ssh-keygen -R <host>
```

Example:

```bash
ssh-keygen -R 192.168.0.14
```

This removes the saved host key for that host from `known_hosts`.

---

