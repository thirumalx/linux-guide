# File and Directory Listing

### List Files and Directories

```bash
ls
```

List files and directories in the current directory.

```bash
ls -l
```

Long format — displays permissions, ownership, size, modification time, etc.

```bash
ls -a
```

Displays all files, including hidden files.

```bash
ls -lF
```

Long format with file-type indicators.

* `/` — Directory
* `@` — Symbolic link
* `*` — Executable file
* `->` — Shows the target of a symbolic link

### Common `ls` Options

| Option    | Description                                    |
| --------- | ---------------------------------------------- |
| `-a`      | Show all files, including hidden files         |
| `--color` | Display files with colors                      |
| `-d`      | List directory names instead of their contents |
| `-l`      | Long format                                    |
| `-r`      | Reverse sort order                             |
| `-R`      | List recursively                               |
| `-t`      | Sort by modification time, newest first        |

---

