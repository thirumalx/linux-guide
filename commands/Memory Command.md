# Cheat sheet for linux memory commands

* To Check memory summary
  
```bash
free -h
```

* To Check live memory usage

```bash
top
```

Interactive view

```bash
htop
```

* Top memory consuming process

```bash
ps aux --sort=%mem | head
```

* Check swap usage

```bash
swapon --show
```

* Complete memory usage

```bash
cat /proc/meminfo | head -5
```

* Memory & swap details

```bash
vmstat 1
```