# Manage permissions

## Inspect

```bash
ls -l                    # <- show owner, group, permissions
ls -ld /data             # <- show directory permissions only
```

## Change ownership

```bash
sudo chown devops /data            # <- owner only
sudo chown :devs /data             # <- group only
sudo chown devops:devs /data       # <- owner and group
sudo chown -R student ~/Documents  # <- recursive
```

## Change permissions

```bash
chmod 700 /data            # <- owner only
chmod 755 script.sh        # <- executable by all, writable by owner
chmod 644 file.txt         # <- common file mode
chmod +x script.sh         # <- make executable
chmod a-x /data/file       # <- remove execute for all
chmod go-rw /data/doc.pdf  # <- remove read/write for group and others
sudo chmod -R 700 /data    # <- recursive strict mode
```

## Special bits

```bash
chmod 1777 /tmp            # <- sticky bit
chmod 2775 shared/         # <- setgid on directory
chmod 4755 binary          # <- setuid on file
```

## When to use what

```bash
chmod +x      <- scripts you want to run directly
chmod 644     <- normal text/config files
chmod 755     <- directories and executable scripts
chmod 1777    <- shared temp dirs
chmod 2775    <- shared team dirs with fixed group inheritance
```
