# Linux Command Reference

## 1. File and Directory Listing

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

## 2. Change Directory

### Change to a Directory

```bash
cd /tmp
```

Changes to `/tmp`.

### Go to Parent Directory

```bash
cd ..
```

Moves to the parent directory.

### Change to Root Directory

```bash
cd /
```

---

## 3. Print Current Working Directory

```bash
pwd
```

Displays the current working directory.

---

## 4. Create and Remove Directories

### Create a Directory

```bash
mkdir newFolderName
```

Creates a new directory.

### Remove an Empty Directory

```bash
rmdir directoryName
```

> `rmdir` works only when the directory is empty.

For a directory containing files:

```bash
rm -r directoryName
```

Use `rm -rf` carefully because it can permanently delete files without confirmation.

---

## 5. Change Shell

### Check Available / Current Shell

```bash
echo $SHELL
```

Displays the user's default shell.

To see the shell currently running:

```bash
echo $0
```

### Change to C Shell

```bash
csh
```

Common shells include:

* `bash` — Bourne Again Shell
* `sh` — Bourne Shell
* `csh` — C Shell
* `tcsh` — TENEX C Shell
* `zsh` — Z Shell

---

## 6. File Information

### Find Which Package Installed a File

For Debian/Ubuntu packages:

```bash
dpkg -L neo4j
```

Lists all files installed by the `neo4j` package.

### Find Command Location

```bash
which java
```

or:

```bash
which mvn
```

Displays the location of the executable.

### Display Environment PATH

```bash
echo $PATH
```

Displays directories searched when executing commands.

---

## 7. Archive and Compression

### Extract `.tar.gz`

```bash
tar -xvzf filename.tar.gz
```

Options:

* `x` — Extract
* `v` — Verbose
* `z` — gzip
* `f` — File

### Extract `.tar.bz2`

```bash
tar -xvjf filename.tar.bz2
```

### Extract Using `dtrx`

```bash
dtrx file.tar.gz
```

```bash
dtrx file.tar.bz2
```

### Extract `.7z`

```bash
7z x file.7z
```

---

## 8. Create Archives

### Create a `.tar.gz` Archive

```bash
tar -zcvf log.tar.gz logs/
```

### Create a ZIP Archive

```bash
zip -r folder.zip folder/
```

### ZIP a Single File

```bash
zip file.zip filename
```

---

## 9. Disk and File-System Usage

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

## 10. Memory Usage

### Check RAM

```bash
free
```

### Human-Readable Memory Information

```bash
free -h
```

### Memory in MB

```bash
free -m
```

### Continuously Monitor Memory

```bash
watch -n 5 free -m
```

Refreshes memory information every 5 seconds.

---

## 11. File Permissions

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

## 12. Common Permission Values

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

## 13. Copy Files

### Copy a File

```bash
cp filename.ext /home/user/
```

### Copy a Directory

```bash
cp -r sourceDirectory /home/user/
```

---

## 14. USB Drive / Disk Mounting

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

## 15. File Search and Line Counting

### Search Text in a File

```bash
grep "search content" filename
```

Example:

```bash
grep "192.168.0.24" /config/ip.config
```

### Count Lines in Java Files

```bash
find . -name "*.java" | xargs cat | wc -l
```

A safer version for filenames containing spaces is:

```bash
find . -name "*.java" -print0 | xargs -0 cat | wc -l
```

---



## 17. Increase Open File Limit

### Check Current Limit

```bash
ulimit -n
```

### Temporarily Increase Limit

```bash
ulimit -n 4096
```

This changes the limit for the current shell/session.

---

## 18. Change Password

```bash
passwd
```

Changes the password of the current user.

### Switch to Root

```bash
sudo su
```

Then:

```bash
passwd
```

> Prefer `sudo -i` or `sudo <command>` where possible instead of routinely working as root.

---

## 19. Copy Files Between Systems

### Using SCP

```bash
scp orbeon-2016.1.201604200638-PE.zip enkindle@192.168.0.16:/home/enkindle
```

### Copy a Directory

```bash
scp -r myfolder user@192.168.0.16:/home/user/
```

---

## 20. Connect to a Remote System

### SSH

```bash
ssh username@ipaddress
```

Example:

```bash
ssh enkindle@192.168.0.16
```

---

## 21. Remove SSH Host Identification

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

## 22. Create Symbolic Links

### Create a Symbolic Link

```bash
sudo ln -s /usr/local/apache-maven-3.3.3/bin/mvn /usr/bin/mvn
```

Example:

```text
/usr/bin/mvn -> /usr/local/apache-maven-3.3.3/bin/mvn
```

Check the link:

```bash
ls -l /usr/bin/mvn
```

---

## 23. VI / VIM Editor

### Open a File

```bash
vi filename
```

### Go to the Last Line

Press:

```text
Esc
G
```

### Common VI Commands

| Command | Function            |
| ------- | ------------------- |
| `i`     | Insert mode         |
| `Esc`   | Exit insert mode    |
| `G`     | Go to last line     |
| `gg`    | Go to first line    |
| `:w`    | Save                |
| `:q`    | Quit                |
| `:wq`   | Save and quit       |
| `:q!`   | Quit without saving |
| `/text` | Search for text     |

---

## 24. VPN — OpenConnect

### Install OpenConnect

```bash
sudo apt-get install openconnect
```

### Connect to a VPN Server

```bash
sudo openconnect <vpn-server>
```

Example:

```bash
sudo openconnect 173.231.120.210
```

### Install NetworkManager OpenConnect GUI

```bash
sudo apt-get install network-manager-openconnect-gnome
```

This provides OpenConnect integration with the GNOME NetworkManager interface.

---

## 25. VirtualBox

### Switch from Scale Mode

In VirtualBox, press:

```text
Host Key + C
```

The default Host Key is usually:

```text
Right Ctrl
```

Therefore:

```text
Right Ctrl + C
```

> The exact shortcut depends on the VirtualBox Host Key configuration.

### Resize a VirtualBox VDI Disk

Navigate to the directory containing the `.vdi` file and run:

```bash
VBoxManage modifymedium disk YOUR_HARD_DISK.vdi --resize SIZE_IN_MB
```

Example:

```bash
VBoxManage modifymedium disk "Windows 10.vdi" --resize 35840
```

Older VirtualBox versions may use:

```bash
VBoxManage modifyhd "Windows 10.vdi" --resize 35840
```

Example output:

```text
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
```

> Increasing the virtual disk size does not automatically increase the partition or filesystem inside the guest OS. Those must be expanded separately.

---

## 26. Calendar

Display the current month's calendar:

```bash
cal
```

Display a specific year:

```bash
cal 2026
```

---

## 27. Special Directory Symbols

| Symbol | Meaning                              |
| ------ | ------------------------------------ |
| `.`    | Current directory                    |
| `..`   | Parent directory                     |
| `/`    | Root directory / directory separator |
| `~`    | User's home directory                |

Examples:

```bash
cd .
```

Stay in the current directory.

```bash
cd ..
```

Go to the parent directory.

```bash
cd ~
```

Go to the user's home directory.

---

# Quick Reference

| Command  | Function                   | Example                    |
| -------- | -------------------------- | -------------------------- |
| `ls`     | List files                 | `ls`                       |
| `ls -l`  | Long listing               | `ls -l`                    |
| `ls -a`  | Show hidden files          | `ls -a`                    |
| `pwd`    | Current directory          | `pwd`                      |
| `cd`     | Change directory           | `cd /tmp`                  |
| `mkdir`  | Create directory           | `mkdir test`               |
| `rmdir`  | Remove empty directory     | `rmdir test`               |
| `cp`     | Copy files                 | `cp a.txt /tmp/`           |
| `mv`     | Move/rename                | `mv a.txt b.txt`           |
| `rm`     | Remove files               | `rm a.txt`                 |
| `grep`   | Search text                | `grep "error" app.log`     |
| `find`   | Find files                 | `find . -name "*.log"`     |
| `du`     | Directory usage            | `du -sh .`                 |
| `df`     | File-system usage          | `df -h`                    |
| `free`   | Memory usage               | `free -h`                  |
| `ps`     | Process information        | `ps aux`                   |
| `kill`   | Terminate process          | `kill 1234`                |
| `chmod`  | Change permissions         | `chmod 644 file`           |
| `chown`  | Change ownership           | `chown user:group file`    |
| `tar`    | Archive/extract            | `tar -xvzf file.tar.gz`    |
| `zip`    | Create ZIP                 | `zip -r file.zip folder/`  |
| `unzip`  | Extract ZIP                | `unzip file.zip`           |
| `ssh`    | Remote login               | `ssh user@host`            |
| `scp`    | Remote file copy           | `scp file user@host:/tmp/` |
| `ln -s`  | Create symbolic link       | `ln -s source target`      |
| `which`  | Locate executable          | `which java`               |
| `passwd` | Change password            | `passwd`                   |
| `ulimit` | Shell resource limits      | `ulimit -n`                |
| `watch`  | Repeatedly run command     | `watch -n 5 free -m`       |
| `vi`     | Text editor                | `vi file.txt`              |
| `sudo`   | Execute as privileged user | `sudo command`             |
| `mount`  | Mount filesystem           | `mount /dev/sdb1 /media`   |
| `fdisk`  | Disk/partition information | `sudo fdisk -l`            |

---

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
