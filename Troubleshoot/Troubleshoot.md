# Troubleshoot

## Golden Rule

**CPU -> Memory -> Swap -> Disk I/O -> Service -> Logs -> Network -> OS**

1. Use `top` command to check the CPU and Memory usage.
2. Use `free -h` command to check the memory usage.
3. Use `iostat` command to check the swap usage.
4. Use `iotop` command to check the disk I/O usage.
5. Use `ss` or `netstat` command to check the network usage.
6. Use `journalctl` command to check the logs.
7. Use `dmesg` command to check the OS logs.