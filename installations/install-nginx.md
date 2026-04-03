# Install nginx

## Install

```bash
sudo apt update && sudo apt install -y nginx       # <- Debian/Ubuntu
sudo dnf install -y nginx                          # <- Fedora/RHEL
sudo pacman -S --needed nginx                      # <- Arch
```

## Start and enable

```bash
sudo systemctl enable --now nginx   # <- enable nginx at boot and start it immediately
systemctl status nginx              # <- show whether nginx is running and its current service status
```

## Verify

```bash
curl -I http://localhost            # <- request only the response headers from the local nginx server
sudo ss -ltnp 'sport = :80'         # <- show which process is listening on TCP port 80
sudo nginx -t                       # <- test the nginx configuration for syntax errors
sudo systemctl reload nginx         # <- reload nginx after config changes without fully restarting it
```
