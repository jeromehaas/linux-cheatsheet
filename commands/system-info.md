# System info

## Identity and sessions

```bash
whoami                  # <- current user
id                      # <- uid, gid, groups
groups                  # <- group names
uptime                  # <- uptime and load
history                 # <- command history
```

## OS and kernel

```bash
uname -a                # <- kernel + machine info
cat /etc/os-release     # <- distro info
hostnamectl             # <- hostname and OS details (if available)
```

## CPU / memory / disk

```bash
top                     # <- interactive process list
free -h                 # <- memory usage
lscpu                   # <- CPU details
df -h                   # <- filesystem usage
lsblk                   # <- block devices
```

## Networking

```bash
ip addr                 # <- interfaces and IPs
ip route                # <- routes
ss -lntup               # <- listening TCP/UDP sockets
```

## Logs and services

```bash
journalctl -xe                  # <- recent logs with context
journalctl -u nginx -f          # <- follow one service
systemctl status nginx          # <- service status
sudo systemctl restart nginx    # <- restart service
```
