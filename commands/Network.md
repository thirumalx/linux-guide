# Network commands

## Netstat
```bash
# Display all active TCP connections
sudo ss -tuln

# Display all active UDP connections
sudo ss -uln

# Display all active TCP connections in listening state
sudo ss -lntu

# Display all active UDP connections in listening state
sudo ss -lun

# Display all active TCP connections in non-listening state
sudo ss -ntu

# Display all active UDP connections in non-listening state
sudo ss -un

# Display all active TCP connections in non-listening state and without numerical addresses
sudo ss -ntu -no-numeric

# Display all active UDP connections in non-listening state and without numerical addresses
sudo ss -un -no-numeric

# Display all active TCP connections in non-listening state and without numerical addresses and without port names
sudo ss -ntu -no-numeric -no-ports

# Display all active UDP connections in non-listening state and without numerical addresses and without port names
sudo ss -un -no-numeric -no-ports

# Display all active TCP connections in non-listening state and without numerical addresses and without port names and without service names
sudo ss -ntu -no-numeric -no-ports -no-service

# Display all active UDP connections in non-listening state and without numerical addresses and without port names and without service names
sudo ss -un -no-numeric -no-ports -no-service

# Count connections by state for a specific port
netstat -an | grep ':3306' | awk '{print $6}' | sort | uniq -c | sort -nr

```
