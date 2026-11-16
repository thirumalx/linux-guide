# Allow `other` users to execute the files

Suppose you want to give permission to `TamilVendhan` to run the file that is in your home directory `/home/Thirumal/scripts/print_hello_world.sh`, then  give permission 

```bash
sudo chmod 755 /home/Thirumal/scripts/print_hello_world.sh
```

* If `/home/Thirumal` or another `parent directory `does not allow `TamilVendhan` to traverse it, you can grant access using `ACLs`:

```bash
sudo setfacl -m u:jboss:--x /home/Thirumal
sudo setfacl -m u:jboss:--x /home/Thirumal/scripts
```

* Check the owner of all level

```bash
namei -l /home/Thirumal/scripts/clear_merged_stamped_pdf.sh
```

