# Workflow: Copy to remote

## Single file

```bash
scp ./dist/app.tar.gz <USER>@<HOST>:/tmp/   # <- quick secure copy
```

## Project or folder

```bash
rsync -avzn --delete -e "ssh -p <PORT>" ./ <USER>@<HOST>:/var/www/app/   # <- dry run first
rsync -avz --delete -e "ssh -p <PORT>" ./ <USER>@<HOST>:/var/www/app/    # <- apply
```

## Config folder only

```bash
rsync -avz -e ssh ./config/ <USER>@<HOST>:/etc/myapp/   # <- sync config directory
```
