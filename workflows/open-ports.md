# Workflow: Open ports

## Show all listening ports

```bash
sudo ss -lntup            # <- TCP/UDP listeners with process info
sudo ss -ltnp             # <- TCP only
sudo ss -lunp             # <- UDP only
```

## Alternative with lsof

```bash
sudo lsof -i -P -n | grep LISTEN   # <- open listening ports
```
