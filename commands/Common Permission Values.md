# Common Permission Values

| Symbolic     | Octal | Meaning                                                   |
| ------------ | ----: | --------------------------------------------------------- |
| `-rwx------` | `700` | Owner can read, write and execute; nobody else has access |
| `-rwxr-xr-x` | `755` | Owner can modify; everyone can read and execute           |
| `-rw-rw-r--` | `664` | Owner and group can modify; others can read               |
| `-rw-rw----` | `660` | Owner and group can read/write                            |
| `-rw-r--r--` | `644` | Owner can modify; everyone can read                       |

### Permission Reference

| Permission    | Value |
| ------------- | ----: |
| Read (`r`)    |     4 |
| Write (`w`)   |     2 |
| Execute (`x`) |     1 |

For example:

```text
755 = 7 5 5
     = rwx r-x r-x
```

---

