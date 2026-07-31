# File Search and Line Counting

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

