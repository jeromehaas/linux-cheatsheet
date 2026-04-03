# Remote access

## SSH login

```bash
ssh student@server             # <- connect to remote server
ssh -p 2222 student@server     # <- connect on custom port
```

## SSH keys

```bash
ssh-keygen -t ed25519 -C "you@example.com"            # <- create key pair
ls -lah ~/.ssh                                        # <- inspect keys
ssh-copy-id -i ~/.ssh/id_ed25519.pub student@server   # <- install key
```

## Copy files

```bash
scp file.txt student@server:/tmp/                                 # <- copy to remote
scp student@server:/etc/nginx/nginx.conf ./                       # <- copy from remote
rsync -avz --progress ./ student@server:/var/www/app/             # <- sync up
rsync -avz --progress student@server:/var/www/app/ ./app-remote/  # <- sync down
```

## SSH tunnels

```bash
ssh -L 5432:localhost:5432 student@server   # <- local forward
ssh -R 8080:localhost:3000 student@server   # <- remote forward
ssh -D 1080 student@server                  # <- SOCKS proxy
```

## Persistent remote work

```bash
tmux new -s work            # <- new tmux session
tmux attach -t work         # <- reconnect to session
```
