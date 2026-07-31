# Service Management

## To check service health

```bash
systemctl status <service>
```

## To start service

```bash
sudo systemctl start <service>
```

## To stop service

```bash
sudo systemctl stop <service>
```

## To restart service

```bash
sudo systemctl restart <service>
```

## To enable service

```bash
sudo systemctl enable <service>
```

## To disable service

```bash
sudo systemctl disable <service>
```

## To check service status

```bash
sudo systemctl status <service>
```

## To view service logs

```bash
sudo journalctl -u <service>
```

## To view service logs in real time

```bash
sudo journalctl -u <service> -f
```

## To view service logs in real time with tailing

```bash
sudo journalctl -u <service> -f -n 50
```

## To view service logs in real time with tailing and without paging

```bash
sudo journalctl -u <service> -f -n 50 | cat
```

## To view service logs in real time with tailing and without paging and without color

```bash
sudo journalctl -u <service> -f -n 50 | cat | sed 's/\x1B\[[0-9;]*m//g'
```