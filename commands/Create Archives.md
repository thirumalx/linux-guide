# Create Archives

# Create a `.tar.gz` Archive

```bash
tar -zcvf log.tar.gz logs/
```

Excluding folders

```bash
tar -cvf folder.tar --exclude='folder/log/*' --exclude='folder/tmp/*' --exclude='folder/data/*' folder
```

# Create a ZIP Archive

```bash
zip -r folder.zip folder/
```

Zip file by exluding folders

```bash
zip -r myproject.zip myproject \
  -x "myproject/logs/*" \
  -x "myproject/tmp/*" \
  -x "myproject/standalone/tmp/*"
```

# ZIP a Single File

```bash
zip file.zip filename
```

---

