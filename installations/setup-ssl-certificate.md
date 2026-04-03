# Setup SSL certificate

## Preconditions

```text
- DNS record for <DOMAIN> points to this server
- port 80 is reachable from the internet
- nginx is already installed and serving the site
```

## Install certbot

```bash
sudo apt update                                     # <- update apt package manager
sudo apt install -y certbot python3-certbot-nginx   # <- Debian/Ubuntu
sudo dnf install -y certbot python3-certbot-nginx   # <- Fedora-like
```

## Obtain certificate

```bash
sudo certbot --nginx -d <DOMAIN>    # <- request cert and update nginx
```

## Test renewal

```bash
sudo certbot renew --dry-run  # renew certificate
curl -I https://<DOMAIN>      # fetch domain
sudo nginx -t                 # test nginx config
```
