# Workflow: SSH key share

## Create a key

```bash
ssh-keygen -t ed25519 -C "you@example.com"   # <- generate ~/.ssh/id_ed25519
```

## Copy public key to clipboard

```bash
cat ~/.ssh/id_ed25519.pub                 # <- fallback: print in terminal
xclip -sel clip < ~/.ssh/id_ed25519.pub   # <- X11 clipboard
wl-copy < ~/.ssh/id_ed25519.pub           # <- Wayland clipboard
pbcopy < ~/.ssh/id_ed25519.pub            # <- macOS clipboard
```

## Install key on remote server

```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub <USER>@<HOST>   # <- recommended
```

## Manual install if ssh-copy-id is missing

```bash
cat ~/.ssh/id_ed25519.pub | ssh <USER>@<HOST> \                                                              # <- send your local public SSH key to the remote server over SSH
'mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys'   # <- create ~/.ssh if needed, secure it, append the key, and secure authorized_keys
```

## Rare case: copy public key file with rsync

```bash
rsync -avz -e ssh ~/.ssh/id_ed25519.pub <USER>@<HOST>:/tmp/   # <- copies .pub file
```
