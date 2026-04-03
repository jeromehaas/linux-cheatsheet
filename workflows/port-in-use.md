# Workflow: Port in use

## Find the process using port 3000

```bash
sudo ss -ltnp 'sport = :3000'                 # <- Linux: listener + process
sudo lsof -iTCP:3000 -sTCP:LISTEN -P -n       # <- Linux/macOS alternative
kill $(lsof -t -i:3000)                       # <- quick kill by port
```

## Stop it safely

```bash
sudo kill -TERM <PID>     # <- graceful stop
sudo kill -KILL <PID>     # <- force stop
```

## If it is a service

```bash
systemctl status <service>      # <- inspect service
sudo systemctl stop <service>   # <- stop service
```
