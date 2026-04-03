# Workflow: Copy from remote

## Single file

```bash
scp <USER>@<HOST>:/var/www/app/.env ./   # <- copy down one file
```

## Whole directory

```bash
rsync -avz -e "ssh -p <PORT>" <USER>@<HOST>:/var/www/app/ ./app-remote/   # <- sync down
```
