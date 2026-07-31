# Process Management

### Check Process Elapsed Time

```bash
ps -p <process_id> -o etime
```

Example:

```bash
ps -p 12345 -o etime
```

### Run a Process in the Background

```bash
setsid skype
```

`setsid` starts the program in a new session, allowing it to continue independently of the current terminal.

---

