# VirtualBox

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

