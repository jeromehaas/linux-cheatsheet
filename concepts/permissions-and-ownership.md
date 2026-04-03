# Permissions and ownership

## Reading permission strings

```bash
ls -la                  # <- example: drwxr-x---
```

```bash
d        <- file type (directory here)
rwx      <- owner permissions
r-x      <- group permissions
---      <- others permissions
```

## File types

```text
- <- regular file
d <- directory
l <- symbolic link
c <- character device
b <- block device
p <- pipe
s <- local socket
```

## Permission bits

```text
r <- read
w <- write
x <- execute
```

## Numeric chmod

```bash
chmod 700 /data         # <- owner full access, nobody else
chmod 644 sample.txt    # <- owner rw, group r, others r
chmod 755 script.sh     # <- owner rwx, group rx, others rx
```

## Symbolic chmod

```bash
chmod a+x my-script.sh      # <- add execute for all
chmod go-rw document.pdf    # <- remove group/other read+write
chmod -R g+rwX /data        # <- recursive; X only on dirs/executables
chmod a-x /data/file        # <- remove execute for all
```

## Ownership

```bash
sudo chown devops /data             # <- change owner
sudo chown :devs /data              # <- change group
sudo chown devops:devs /data        # <- change owner and group
sudo chown -R student ~/Documents   # <- recursive ownership change
```

## Special bits

```bash
chmod 1777 /tmp         # <- sticky bit; users can only delete own files
chmod 2775 shared/      # <- setgid; new files inherit directory group
chmod 4755 program      # <- setuid; runs with file owner's privileges
```

```text
sticky bit <- good for shared writable dirs like /tmp
setgid     <- good for shared project directories
setuid     <- powerful, use carefully
```
